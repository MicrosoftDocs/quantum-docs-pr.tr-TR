---
title: Enerji düzeyi tahminleri edinme
description: Q#Molesel Hydrogen 'ın enerji düzeyi değerlerini tahmin eden örnek bir program aracılığıyla ilerleyin.
author: guanghaolow
ms.author: gulow
ms.date: 07/02/2020
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.examples.energyestimate
no-loc:
- Q#
- $$v
ms.openlocfilehash: 05506f4099de754cd02d81fbd9200f2de091e37e
ms.sourcegitcommit: 8256ff463eb9319f1933820a36c0838cf1e024e8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2020
ms.locfileid: "90759741"
---
# <a name="obtaining-energy-level-estimates"></a><span data-ttu-id="e017e-103">Enerji düzeyi tahminleri edinme</span><span class="sxs-lookup"><span data-stu-id="e017e-103">Obtaining energy level estimates</span></span>
<span data-ttu-id="e017e-104">Enerji seviyelerinin değerlerini tahmin etmek, hisse Chemistry 'ın asıl uygulamalarından biridir.</span><span class="sxs-lookup"><span data-stu-id="e017e-104">Estimating the values of energy levels is one of the principal applications of quantum chemistry.</span></span> <span data-ttu-id="e017e-105">Bu makalede, bu işlemi, molesel Hydrogen 'nin kurallı örneği için nasıl gerçekleştirebileceğiniz özetlenmektedir.</span><span class="sxs-lookup"><span data-stu-id="e017e-105">This article outlines how you can perform this for the canonical example of molecular hydrogen.</span></span> <span data-ttu-id="e017e-106">Bu bölümde başvurulan örnek, [`MolecularHydrogen`](https://github.com/microsoft/Quantum/tree/main/samples/chemistry/MolecularHydrogen) Kimya örnekleri deposunda bulunur.</span><span class="sxs-lookup"><span data-stu-id="e017e-106">The sample referenced in this section is [`MolecularHydrogen`](https://github.com/microsoft/Quantum/tree/main/samples/chemistry/MolecularHydrogen) in the chemistry samples repository.</span></span> <span data-ttu-id="e017e-107">Çıktıyı gösteren daha fazla görsel örnek [`MolecularHydrogenGUI`](https://github.com/microsoft/Quantum/tree/main/samples/chemistry/MolecularHydrogenGUI) tanıtım olur.</span><span class="sxs-lookup"><span data-stu-id="e017e-107">A more visual example that plots the output is the [`MolecularHydrogenGUI`](https://github.com/microsoft/Quantum/tree/main/samples/chemistry/MolecularHydrogenGUI) demo.</span></span>

## <a name="estimating-the-energy-values-of-molecular-hydrogen"></a><span data-ttu-id="e017e-108">Molesel Hydrogen 'ın enerji değerlerini tahmin etme</span><span class="sxs-lookup"><span data-stu-id="e017e-108">Estimating the energy values of molecular hydrogen</span></span>

<span data-ttu-id="e017e-109">İlk adım, molesel Hydrogen 'i temsil eden Hamiltonian 'yi oluşturmak için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="e017e-109">The first step is to construct the Hamiltonian representing molecular hydrogen.</span></span> <span data-ttu-id="e017e-110">Bu işlemi NWChem aracını kullanarak oluşturabilseniz de, kısaltma için bu örnek Hamiltonian koşullarını el ile ekler.</span><span class="sxs-lookup"><span data-stu-id="e017e-110">Although you can construct this using the NWChem tool, for brevity, this sample adds the Hamiltonian terms manually.</span></span>

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

<span data-ttu-id="e017e-111">Hamiltonian benzetimi yapmak, fermıon işleçlerini qubit işleçlerine dönüştürmeyi gerektirir.</span><span class="sxs-lookup"><span data-stu-id="e017e-111">Simulating the Hamiltonian requires converting the fermion operators to qubit operators.</span></span> <span data-ttu-id="e017e-112">Bu dönüştürme, şu şekilde Ürdün-Wigner kodlaması aracılığıyla gerçekleştirilir:</span><span class="sxs-lookup"><span data-stu-id="e017e-112">This conversion is performed through the Jordan-Wigner encoding as follows:</span></span>

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

<span data-ttu-id="e017e-113">Daha sonra, `qSharpData` Hamiltonian 'yi temsil eden, `TrotterStepOracle` işlevine.</span><span class="sxs-lookup"><span data-stu-id="e017e-113">Next, pass `qSharpData`, which represents the Hamiltonian, to the `TrotterStepOracle` function.</span></span> <span data-ttu-id="e017e-114">`TrotterStepOracle` Hamiltonian 'ın gerçek zamanlı evrimini yaklaştırın bir hisse işlemi döndürür.</span><span class="sxs-lookup"><span data-stu-id="e017e-114">`TrotterStepOracle` returns a quantum operation that approximates the real-time evolution of the Hamiltonian.</span></span> <span data-ttu-id="e017e-115">Daha fazla bilgi için bkz. [Hamiltonian Dynamics benzetimi](xref:microsoft.quantum.chemistry.concepts.simulationalgorithms).</span><span class="sxs-lookup"><span data-stu-id="e017e-115">For more information, see [Simulating Hamiltonian dynamics](xref:microsoft.quantum.chemistry.concepts.simulationalgorithms).</span></span>

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

<span data-ttu-id="e017e-116">Bu noktada, önceki simülasyonu kullanarak kara eyalet enerji hakkında bilgi edinmek için standart kitaplığın [aşama tahmini algoritmalarını](xref:microsoft.quantum.libraries.characterization) kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e017e-116">At this point, you can use the standard library's [phase estimation algorithms](xref:microsoft.quantum.libraries.characterization) to learn the ground state energy using the previous simulation.</span></span> <span data-ttu-id="e017e-117">Bu, hisse zemin durumu için iyi bir yaklaşık hazırlama gerektirir.</span><span class="sxs-lookup"><span data-stu-id="e017e-117">This requires preparing a good approximation to the quantum ground state.</span></span> <span data-ttu-id="e017e-118">Bu tür bir ilgili önermeler [`Broombridge`](xref:microsoft.quantum.libraries.chemistry.schema.broombridge) şemada verilmiştir.</span><span class="sxs-lookup"><span data-stu-id="e017e-118">Suggestions for such approximations are provided in the [`Broombridge`](xref:microsoft.quantum.libraries.chemistry.schema.broombridge) schema.</span></span> <span data-ttu-id="e017e-119">Ancak, Bu önerilerin karşılanmasına `hamiltonian.NElectrons` izin vermek için varsayılan yaklaşım, diyagonal tek bir elektron terim enerji düzeyini en aza indirmek için bir dizi elektricü ekler.</span><span class="sxs-lookup"><span data-stu-id="e017e-119">However, absent these suggestions, the default approach adds a number of `hamiltonian.NElectrons` electrons to greedily minimize the diagonal one-electron term energies.</span></span> <span data-ttu-id="e017e-120">Aşama tahmini işlevleri ve işlemleri, [Microsoft. hisse. karakterleştirme](xref:microsoft.quantum.characterization) ad alanındaki docfx gösteriminde verilmiştir.</span><span class="sxs-lookup"><span data-stu-id="e017e-120">The phase estimation functions and operations are provided in DocFX notation in the [Microsoft.Quantum.Characterization](xref:microsoft.quantum.characterization) namespace.</span></span>

<span data-ttu-id="e017e-121">Aşağıdaki kod parçacığında, kimya simülasyonu kitaplığı tarafından gerçek zamanlı evmin çıktısının hisse alma tahminiyle nasıl tümleştirildiğini gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="e017e-121">The following snippet shows how the real-time evolution output by the chemistry simulation library integrates with quantum phase estimation.</span></span>

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

<span data-ttu-id="e017e-122">Artık Q# kodu konak programından çağırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e017e-122">You can now invoke the Q# code from the host program.</span></span> <span data-ttu-id="e017e-123">Aşağıdaki C# kodu bir tam durumlu simülatör oluşturur ve `GetEnergyByTrotterization` zemin durumu enerji elde etmek için çalışır.</span><span class="sxs-lookup"><span data-stu-id="e017e-123">The following C# code creates a full-state simulator and runs `GetEnergyByTrotterization` to obtain the ground state energy.</span></span>

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

<span data-ttu-id="e017e-124">İşlem iki parametre döndürür:</span><span class="sxs-lookup"><span data-stu-id="e017e-124">The operation returns two parameters:</span></span> 

- <span data-ttu-id="e017e-125">`energyEst` , orta eyalet enerji tahminidir ve `-1.137` Ortalama üzerinde yakın olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="e017e-125">`energyEst` is the estimate of the ground state energy and should be close to `-1.137` on average.</span></span> 
- <span data-ttu-id="e017e-126">`phaseEst` , aşama tahmini algoritması tarafından döndürülen ham aşamadır.</span><span class="sxs-lookup"><span data-stu-id="e017e-126">`phaseEst` is the raw phase returned by the phase estimation algorithm.</span></span> <span data-ttu-id="e017e-127">Bu, çok büyük bir değer nedeniyle ortaya çıktığında diğer ad tanılarken yararlı olur `trotterStep` .</span><span class="sxs-lookup"><span data-stu-id="e017e-127">This useful for diagnosing aliasing when it occurs due to a `trotterStep` value that is too large.</span></span>
