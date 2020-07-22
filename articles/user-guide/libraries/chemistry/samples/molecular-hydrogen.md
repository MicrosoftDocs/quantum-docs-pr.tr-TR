---
title: Enerji düzeyi tahminleri edinme
description: "Molesel Hydrogen 'ın enerji düzeyi değerlerini tahmin eden örnek bir Q # programını gözden geçir."
author: guanghaolow
ms.author: gulow
ms.date: 07/02/2020
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.examples.energyestimate
ms.openlocfilehash: b26538980366cf4cbe01fc2ef59580ae182f1e8a
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2020
ms.locfileid: "86871578"
---
# <a name="obtaining-energy-level-estimates"></a>Enerji düzeyi tahminleri edinme
Enerji seviyelerinin değerlerini tahmin etmek, hisse Chemistry 'ın asıl uygulamalarından biridir. Bu makalede, bu işlemi, molesel Hydrogen 'nin kurallı örneği için nasıl gerçekleştirebileceğiniz özetlenmektedir. Bu bölümde başvurulan örnek, [`MolecularHydrogen`](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/MolecularHydrogen) Kimya örnekleri deposunda bulunur. Çıktıyı gösteren daha fazla görsel örnek [`MolecularHydrogenGUI`](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/MolecularHydrogenGUI) tanıtım olur.

## <a name="estimating-the-energy-values-of-molecular-hydrogen"></a>Molesel Hydrogen 'ın enerji değerlerini tahmin etme

İlk adım, molesel Hydrogen 'i temsil eden Hamiltonian 'yi oluşturmak için kullanılır. Bu işlemi NWChem aracını kullanarak oluşturabilseniz de, kısaltma için bu örnek Hamiltonian koşullarını el ile ekler.

```csharp
    // These orbital integrals are represented using the OrbitalIntegral
    // data structure.
    var energyOffset = 0.713776188; // This is the coulomb repulsion
    var nElectrons = 2; // Molecular hydrogen has two electrons
    var orbitalIntegrals = new OrbitalIntegral[]
    {
        new OrbitalIntegral(new[] { 0,0 }, -1.252477495),
        new OrbitalIntegral(new[] { 1,1 }, -0.475934275),
        new OrbitalIntegral(new[] { 0,0,0,0 }, 0.674493166),
        new OrbitalIntegral(new[] { 0,1,0,1 }, 0.181287518),
        new OrbitalIntegral(new[] { 0,1,1,0 }, 0.663472101),
        new OrbitalIntegral(new[] { 1,1,1,1 }, 0.697398010),
        // This line adds the identity term.
        new OrbitalIntegral(new int[] { }, energyOffset)
    };

    // Initialize a fermion Hamiltonian data structure and add terms to it.
    var fermionHamiltonian = new OrbitalIntegralHamiltonian(orbitalIntegrals).ToFermionHamiltonian();
```

Hamiltonian benzetimi yapmak, fermıon işleçlerini qubit işleçlerine dönüştürmeyi gerektirir. Bu dönüştürme, şu şekilde Ürdün-Wigner kodlaması aracılığıyla gerçekleştirilir:

```csharp
    // The Jordan-Wigner encoding converts the fermion Hamiltonian, 
    // expressed in terms of fermionic operators, to a qubit Hamiltonian,
    // expressed in terms of Pauli matrices. This is an essential step
    // for simulating our constructed Hamiltonians on a qubit quantum
    // computer.
    var jordanWignerEncoding = fermionHamiltonian.ToPauliHamiltonian(Pauli.QubitEncoding.JordanWigner);

    // You also need to create an input quantum state to this Hamiltonian.
    // Use the Hartree-Fock state.
    var fermionWavefunction = fermionHamiltonian.CreateHartreeFockState(nElectrons);

    // This Jordan-Wigner data structure also contains a representation 
    // of the Hamiltonian and wavefunction made for consumption by the Q# operations.
    var qSharpHamiltonianData = jordanWignerEncoding.ToQSharpFormat();
    var qSharpWavefunctionData = fermionWavefunction.ToQSharpFormat();
    var qSharpData = QSharpFormat.Convert.ToQSharpFormat(qSharpHamiltonianData, qSharpWavefunctionData);
```

Daha sonra, `qSharpData` Hamiltonian 'yi temsil eden, `TrotterStepOracle` işlevine. `TrotterStepOracle`Hamiltonian 'ın gerçek zamanlı evrimini yaklaştırın bir hisse işlemi döndürür. Daha fazla bilgi için bkz. [Hamiltonian Dynamics benzetimi](xref:microsoft.quantum.chemistry.concepts.simulationalgorithms).

```qsharp
// qSharpData passed from driver
let qSharpData = ... 

// Choose the integrator step size
let stepSize = 1.0;

// Choose the order of the Trotter—Suzuki integrator.
let integratorOrder = 4;

// `oracle` is an operation that applies a single time-step of evolution for duration `stepSize`.
// `rescale` is just `1.0/stepSize` -- the number of steps required to simulate unit-time evolution.
// `nQubits` is the number of qubits that must be allocated to run the `oracle` operation.
let (nQubits, (rescale, oracle)) =  TrotterStepOracle (qSharpData, stepSize, integratorOrder);
```

Bu noktada, önceki simülasyonu kullanarak kara eyalet enerji hakkında bilgi edinmek için standart kitaplığın [aşama tahmini algoritmalarını](xref:microsoft.quantum.libraries.characterization) kullanabilirsiniz. Bu, hisse zemin durumu için iyi bir yaklaşık hazırlama gerektirir. Bu tür bir ilgili önermeler [`Broombridge`](xref:microsoft.quantum.libraries.chemistry.schema.broombridge) şemada verilmiştir. Ancak, Bu önerilerin karşılanmasına `hamiltonian.NElectrons` izin vermek için varsayılan yaklaşım, diyagonal tek bir elektron terim enerji düzeyini en aza indirmek için bir dizi elektricü ekler. Aşama tahmini işlevleri ve işlemleri, [Microsoft. hisse. karakterleştirme](xref:microsoft.quantum.characterization) ad alanındaki docfx gösteriminde verilmiştir.

Aşağıdaki kod parçacığında, kimya simülasyonu kitaplığı tarafından gerçek zamanlı evmin çıktısının hisse alma tahminiyle nasıl tümleştirildiğini gösterilmektedir.

```qsharp
operation GetEnergyByTrotterization (
    qSharpData : JordanWignerEncodingData, 
    nBitsPrecision : Int, 
    trotterStepSize : Double, 
    trotterOrder : Int) : (Double, Double) {
    
    // The data describing the Hamiltonian for all these steps is contained in
    // `qSharpData`
    let (nSpinOrbitals, fermionTermData, statePrepData, energyOffset) = qSharpData!;
    
    // Using a Product formula, also known as `Trotterization`, to
    // simulate the Hamiltonian.
    let (nQubits, (rescaleFactor, oracle)) = 
        TrotterStepOracle(qSharpData, trotterStepSize, trotterOrder);
    
    // The operation that creates the trial state is defined here.
    // By default, greedy filling of spin-orbitals is used.
    let statePrep = PrepareTrialState(statePrepData, _);
    
    // Using the Robust Phase Estimation algorithm
    // of Kimmel, Low and Yoder.
    let phaseEstAlgorithm = RobustPhaseEstimation(nBitsPrecision, _, _);
    
    // This runs the quantum algorithm and returns a phase estimate.
    let estPhase = EstimateEnergy(nQubits, statePrep, oracle, phaseEstAlgorithm);
    
    // Now, obtain the energy estimate by rescaling the phase estimate
    // with the trotterStepSize. We also add the constant energy offset
    // to the estimated energy.
    let estEnergy = estPhase * rescaleFactor + energyOffset;
    
    // Return both the estimated phase and the estimated energy.
    return (estPhase, estEnergy);
}
```

Artık ana bilgisayar programından Q # kodunu çağırabilirsiniz. Aşağıdaki C# kodu bir tam durumlu simülatör oluşturur ve `GetEnergyByTrotterization` zemin durumu enerji elde etmek için çalışır.

```csharp
using (var qsim = new QuantumSimulator())
{
    // Specify the bits of precision desired in the phase estimation 
    // algorithm
    var bits = 7;

    // Specify the step size of the simulated time evolution. The step size needs to
    // be small enough to avoid aliasing of phases, and also to control the
    // error of simulation.
    var trotterStep = 0.4;

    // Choose the Trotter integrator order
    Int64 trotterOrder = 1;

    // As the quantum algorithm is probabilistic, run a few trials.

    // This may be compared to true value of
    Console.WriteLine("Exact molecular hydrogen ground state energy: -1.137260278.\n");
    Console.WriteLine("----- Performing quantum energy estimation by Trotter simulation algorithm");
    for (int i = 0; i < 5; i++)
    {
        // EstimateEnergyByTrotterization
        var (phaseEst, energyEst) = GetEnergyByTrotterization.Run(qsim, qSharpData, bits, trotterStep, trotterOrder).Result;
    }
}
```

İşlem iki parametre döndürür: 

- `energyEst`, orta eyalet enerji tahminidir ve `-1.137` Ortalama üzerinde yakın olmalıdır. 
- `phaseEst`, aşama tahmini algoritması tarafından döndürülen ham aşamadır. Bu, çok büyük bir değer nedeniyle ortaya çıktığında diğer ad tanılarken yararlı olur `trotterStep` .
