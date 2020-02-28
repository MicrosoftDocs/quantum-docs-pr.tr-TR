---
title: Kaynak sayılarını alma
description: Bir hisse izi izleme simülatörü kullanarak kaynak tahminleri elde etme hakkında bilgi edinin.
author: guanghaolow
ms.author: gulow
ms.date: 10/23/2018
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.examples.resourcecounts
ms.openlocfilehash: 14d0a703a20a801dcee9678a113a33404859a1a9
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907843"
---
# <a name="obtaining-resource-counts"></a>Kaynak sayılarını alma

Klasik bilgisayarlarda $n $ qubits benzetimi yapma maliyeti $n $ ile katlanarak ölçeklendirin. Bu, tam durum simülatörü ile gerçekleştiriyoruz bir hisse ımız simülasyonu boyutunu büyük ölçüde sınırlar. Büyük Chemistry örnekleri için, yine de yararlı bilgiler elde edebilirsiniz. Burada, bir T-kapısı veya CNOT kapısı sayısı gibi kaynak maliyetlerinin, [izleme simülatörü](xref:microsoft.quantum.machines.qc-trace-simulator.intro)kullanılarak otomatik bir şekilde elde edilmesi için de Bu tür bilgiler, bu hisse maçör. Başvuru için bkz. sunulan `GetGateCount` örneği.

[Dosya yükleme](xref:microsoft.quantum.chemistry.examples.loadhamiltonian) örneğinde anlatıldığı gibi Broombridge şemasından yüklenmiş bir `FermionHamiltonian` örneğine zaten sahip olduğumuz olduğunu varsayalım. 

```csharp
    // Filename of Hamiltonian to be loaded.
    var filename = "...";

    // This deserializes Broombridge.
    var problem = Broombridge.Deserializers.DeserializeBroombridge(filename).ProblemDescriptions.First();

    // This is a data structure representing the Jordan-Wigner encoding 
    // of the Hamiltonian that we may pass to a Q# algorithm.
    var qSharpData = problem.ToQSharpFormat();
```

Kaynak tahminleri elde etmek için sözdizimi, algoritmayı tam durum benzeticisinde çalıştırmaya neredeyse aynıdır. Yalnızca farklı bir hedef makine seçtik. Kaynak tahminlerinin amaçları doğrultusunda, tek bir rahatlık adımının maliyetini veya Qubitişleştirme tekniği tarafından oluşturulan bir hisse diyi değerlendirmek için yeterli olacaktır. Bu algoritmaları çağırmaya yönelik demirbaş aşağıdaki gibidir.

```qsharp
//////////////////////////////////////////////////////////////////////////
// Using Trotterization //////////////////////////////////////////////////
//////////////////////////////////////////////////////////////////////////

/// # Summary
/// This allocates qubits and applies a single Trotter step.
operation RunTrotterStep (qSharpData: JordanWignerEncodingData) : Unit {
    
    // The data describing the Hamiltonian for all these steps is contained in
    // `qSharpData`
    // We use a Product formula, also known as `Trotterization` to
    // simulate the Hamiltonian.
    // The integrator step size does not affect the gate cost of a single step.
    let trotterStepSize = 1.0;
    
    // Order of integrator
    let trotterOrder = 1;
    let (nQubits, (rescaleFactor, oracle)) = TrotterStepOracle(qSharpData, trotterStepSize, trotterOrder);
    
    // We not allocate qubits an run a single step.
    using (qubits = Qubit[nQubits]) {
        oracle(qubits);
        ResetAll(qubits);
    }
}


//////////////////////////////////////////////////////////////////////////
// Using Qubitization ////////////////////////////////////////////////////
//////////////////////////////////////////////////////////////////////////

/// # Summary
/// This allocates qubits and applies a single qubitization step.
operation RunQubitizationStep (qSharpData: JordanWignerEncodingData) : Double {
    
    // The data describing the Hamiltonian for all these steps is contained in
    // `qSharpData`
    let (nQubits, (l1Norm, oracle)) = QubitizationOracle(qSharpData);
    
    // We now allocate qubits and run a single step.
    using (qubits = Qubit[nQubits]) {
        oracle(qubits);
        ResetAll(qubits);
    }
    
    return l1Norm;
}
```

Artık ilgilendiğiniz kaynakları izlemek için izleme simülatörünü yapılandıracağız. Bu durumda, `usePrimitiveOperationsCounter` bayrağını `true`ayarlayarak temel hisse işlemleri sayıyoruz. Bir teknik ayrıntı `throwOnUnconstraintMeasurement`, Q # kodunun, varsa ölçüm sonuçları olasılığını doğru bir şekilde olmadığı durumlarda özel durumları önlemek için `false` olarak ayarlanır.

```csharp
private static QCTraceSimulator CreateAndConfigureTraceSim()
{
    // Create and configure Trace Simulator
    var config = new QCTraceSimulatorConfiguration()
    {
        usePrimitiveOperationsCounter = true,
        throwOnUnconstraintMeasurement = false
    };

    return new QCTraceSimulator(config);
}
```

Şimdi sürücü programından hisse algoritması 'nı aşağıda gösterildiği gibi çalıştırdık.

```csharp
// Instantiate a trace simulator instance
QCTraceSimulator sim = CreateAndConfigureTraceSim();

// Run the quantum algorithm on the trace simulator.
RunQubitizationStep.Run(sim, qSharpData);

// Print all resource counts to file.
var gateStats = sim.ToCSV();
foreach (var x in gateStats)
{
    System.IO.File.WriteAllLines($"QubitizationGateCountEstimates.{x.Key}.csv", new string[] { x.Value });
}
```