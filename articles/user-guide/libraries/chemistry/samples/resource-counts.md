---
title: Kaynak sayılarını alma
description: Bir hisse izi izleme simülatörü kullanarak kaynak tahminleri elde etme hakkında bilgi edinin.
author: guanghaolow
ms.author: gulow
ms.date: 10/23/2018
ms.topic: sample
uid: microsoft.quantum.chemistry.examples.resourcecounts
no-loc:
- Q#
- $$v
ms.openlocfilehash: b8974114a5629fa1928b5774e79aba93fa3d1f7d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856236"
---
# <a name="obtaining-resource-counts"></a><span data-ttu-id="39a3b-103">Kaynak sayılarını alma</span><span class="sxs-lookup"><span data-stu-id="39a3b-103">Obtaining resource counts</span></span>

<span data-ttu-id="39a3b-104">Klasik bilgisayarlarda $n $ qubits benzetimi yapma maliyeti $n $ ile katlanarak ölçeklendirin.</span><span class="sxs-lookup"><span data-stu-id="39a3b-104">The cost of simulating $n$ qubits on classical computers scales exponentially with $n$.</span></span> <span data-ttu-id="39a3b-105">Bu, tam durum simülatörü ile gerçekleştiriyoruz bir hisse ımız simülasyonu boyutunu büyük ölçüde sınırlar.</span><span class="sxs-lookup"><span data-stu-id="39a3b-105">This greatly limits the size of a quantum chemistry simulation we may perform with the full-state simulator.</span></span> <span data-ttu-id="39a3b-106">Büyük Chemistry örnekleri için, yine de yararlı bilgiler elde edebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="39a3b-106">For large instances of chemistry, we may nevertheless obtain useful information.</span></span> <span data-ttu-id="39a3b-107">Burada, bir T-kapısı veya CNOT kapısı sayısı gibi kaynak maliyetlerinin, [izleme simülatörü](xref:microsoft.quantum.machines.qc-trace-simulator.intro)kullanılarak otomatik bir şekilde elde edilmesi için de</span><span class="sxs-lookup"><span data-stu-id="39a3b-107">Here, we examine how resource costs, such as the number of T-gates or CNOT gates, for simulating chemistry may be obtained in an automated fashion using the [trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="39a3b-108">Bu tür bilgiler, bu hisse maçör.</span><span class="sxs-lookup"><span data-stu-id="39a3b-108">Such information informs us of when quantum computers might be large enough to run these quantum chemistry algorithms.</span></span> <span data-ttu-id="39a3b-109">Başvuru için bkz `GetGateCount` . belirtilen örnek.</span><span class="sxs-lookup"><span data-stu-id="39a3b-109">For reference, see the provided `GetGateCount` sample.</span></span>

<span data-ttu-id="39a3b-110">`FermionHamiltonian` [Dosya yükleme](xref:microsoft.quantum.chemistry.examples.loadhamiltonian) örneğinde anlatıldığı gibi Broombridge şemasından yüklenmiş bir örneğimiz olduğunu varsayalım.</span><span class="sxs-lookup"><span data-stu-id="39a3b-110">Let us assume that we already have a `FermionHamiltonian` instance, say, loaded from the Broombridge schema as discussed in the [loading-from-file](xref:microsoft.quantum.chemistry.examples.loadhamiltonian) example.</span></span> 

```csharp
    // Filename of Hamiltonian to be loaded.
    var filename = "...";

    // This deserializes Broombridge.
    var problem = Broombridge.Deserializers.DeserializeBroombridge(filename).ProblemDescriptions.First();

    // This is a data structure representing the Jordan-Wigner encoding 
    // of the Hamiltonian that we may pass to a Q# algorithm.
    var qSharpData = problem.ToQSharpFormat();
```

<span data-ttu-id="39a3b-111">Kaynak tahminleri elde etmek için sözdizimi, algoritmayı tam durum benzeticisinde çalıştırmaya neredeyse aynıdır.</span><span class="sxs-lookup"><span data-stu-id="39a3b-111">The syntax for obtaining resource estimates is almost identical to running the algorithm on the full-state simulator.</span></span> <span data-ttu-id="39a3b-112">Yalnızca farklı bir hedef makine seçtik.</span><span class="sxs-lookup"><span data-stu-id="39a3b-112">We simply choose a different target machine.</span></span> <span data-ttu-id="39a3b-113">Kaynak tahminlerinin amaçları doğrultusunda, tek bir rahatlık adımının maliyetini veya Qubitişleştirme tekniği tarafından oluşturulan bir hisse diyi değerlendirmek için yeterli olacaktır.</span><span class="sxs-lookup"><span data-stu-id="39a3b-113">For the purposes of resource estimates, it suffices to evaluate the cost of a single Trotter step, or a quantum walk created by the Qubitization technique.</span></span> <span data-ttu-id="39a3b-114">Bu algoritmaları çağırmaya yönelik demirbaş aşağıdaki gibidir.</span><span class="sxs-lookup"><span data-stu-id="39a3b-114">The boilerplate for invoking these algorithms is as follows.</span></span>

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

<span data-ttu-id="39a3b-115">Artık ilgilendiğiniz kaynakları izlemek için izleme simülatörünü yapılandıracağız.</span><span class="sxs-lookup"><span data-stu-id="39a3b-115">We now configure the trace simulator to track the resources we are interested in.</span></span> <span data-ttu-id="39a3b-116">Bu durumda, bayrağını olarak ayarlayarak temel hisse işlemleri sayılır `usePrimitiveOperationsCounter` `true` .</span><span class="sxs-lookup"><span data-stu-id="39a3b-116">In this case, we count primitive quantum operations by setting the `usePrimitiveOperationsCounter` flag to `true`.</span></span> <span data-ttu-id="39a3b-117">Bir teknik ayrıntı, kodun, varsa `throwOnUnconstraintMeasurement` `false` Q# , ölçüm sonuçları olasılığa doğru bir şekilde olmadığı durumlarda özel durumların önüne geçmek için olarak ayarlanmıştır.</span><span class="sxs-lookup"><span data-stu-id="39a3b-117">A technical detail `throwOnUnconstraintMeasurement` is set to `false` to avoid exceptions in cases where the Q# code does not correctly assert of probability of measurement outcomes, if any are performed.</span></span>

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

<span data-ttu-id="39a3b-118">Şimdi sürücü programından hisse algoritması 'nı aşağıda gösterildiği gibi çalıştırdık.</span><span class="sxs-lookup"><span data-stu-id="39a3b-118">We now run the quantum algorithm from the driver program as follows.</span></span>

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