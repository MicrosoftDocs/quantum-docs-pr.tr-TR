---
title: Temel işlem sayacı-hisse geliştirme seti
description: 'Bir programdaki işlemler tarafından kullanılan temel işlemleri izlemek için hisse izi simülatörü kullanan Microsoft QDK temel işlem sayacı hakkında bilgi edinin Q# .'
author: vadym-kl
ms.author: vadym
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.primitive-counter
no-loc:
- 'Q#'
- '$$v'
ms.openlocfilehash: bf75eb94696a489a587316928bc3f33baa4a1785
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92690946"
---
# <a name="quantum-trace-simulator-primitive-operations-counter"></a><span data-ttu-id="cff5f-103">Hisse izleme simülatörü: temel işlemler sayacı</span><span class="sxs-lookup"><span data-stu-id="cff5f-103">Quantum trace simulator: primitive operations counter</span></span>

<span data-ttu-id="cff5f-104">Temel işlem sayacı, hisse Geliştirme Seti [hisse izleme benzeticisinin](xref:microsoft.quantum.machines.qc-trace-simulator.intro)bir parçasıdır.</span><span class="sxs-lookup"><span data-stu-id="cff5f-104">The primitive operation counter is a part of the Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="cff5f-105">Bir hisse bir programda çağrılan her işlem tarafından kullanılan temel işlem sayısını sayar.</span><span class="sxs-lookup"><span data-stu-id="cff5f-105">It counts the number of primitive processes used by every operation invoked in a quantum program.</span></span> 

<span data-ttu-id="cff5f-106">Tüm <xref:Microsoft.Quantum.Intrinsic> işlemler tek qubit döndürmeler, T işlemleri, tek qubit Clienfford işlemleri, CNOT işlemleri ve Multi-Qubitpauli gözlemlenenler ölçümleri bakımından ifade edilir.</span><span class="sxs-lookup"><span data-stu-id="cff5f-106">All <xref:Microsoft.Quantum.Intrinsic> operations are expressed in terms of single-qubit rotations, T operations, single-qubit Clifford operations, CNOT operations, and measurements of multi-qubit Pauli observables.</span></span> <span data-ttu-id="cff5f-107">Temel Işlem sayacı, işlemin [çağrı grafiğinin](https://en.wikipedia.org/wiki/Call_graph)tüm kenarlarına ilişkin istatistikleri toplar ve toplar.</span><span class="sxs-lookup"><span data-stu-id="cff5f-107">The Primitive Operations Counter aggregates and collects statistics over all the edges of the operation's [call graph](https://en.wikipedia.org/wiki/Call_graph).</span></span>

## <a name="invoking-the-primitive-operation-counter"></a><span data-ttu-id="cff5f-108">Temel işlem sayacını çağırma</span><span class="sxs-lookup"><span data-stu-id="cff5f-108">Invoking the primitive operation counter</span></span>

<span data-ttu-id="cff5f-109">Temel işlem sayacı ile hisse izi simülatörü çalıştırmak için bir <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> örnek oluşturmanız, `UsePrimitiveOperationsCounter` özelliği **true** olarak ayarlamanız ve sonra <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> parametresi olarak ile yeni bir örnek oluşturmanız gerekir `QCTraceSimulatorConfiguration` .</span><span class="sxs-lookup"><span data-stu-id="cff5f-109">To run the quantum trace simulator with the primitive operation counter, you must create a <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instance, set the `UsePrimitiveOperationsCounter` property to **true** , and then create a new <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instance with the `QCTraceSimulatorConfiguration` as the parameter.</span></span>

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UsePrimitiveOperationsCounter = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-primitive-operation-counter-in-a-c-host-program"></a><span data-ttu-id="cff5f-110">C# ana programında temel işlem sayacını kullanma</span><span class="sxs-lookup"><span data-stu-id="cff5f-110">Using the primitive operation counter in a C# host program</span></span>

<span data-ttu-id="cff5f-111"><xref:Microsoft.Quantum.Intrinsic.T> <xref:Microsoft.Quantum.Intrinsic.ccnot> Aşağıdaki örnek koda bağlı olarak, bu bölümde aşağıdaki C# örneği, işlemi uygulamak için kaç işlem gerektiğini sayar Q# :</span><span class="sxs-lookup"><span data-stu-id="cff5f-111">The C# example that follows in this section counts how many <xref:Microsoft.Quantum.Intrinsic.T> operations are needed to implement the <xref:Microsoft.Quantum.Intrinsic.ccnot> operation, based on the following Q# sample code:</span></span>

```qsharp
open Microsoft.Quantum.Intrinsic;
operation ApplySampleWithCCNOT() : Unit {

    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

<span data-ttu-id="cff5f-112">Bunun `CCNOT` yedi `T` işlem gerektirdiğini ve `ApplySampleWithCCNOT` sekiz işlem çalıştırmasını denetlemek Için `T` Aşağıdaki C# kodunu kullanın:</span><span class="sxs-lookup"><span data-stu-id="cff5f-112">To check that `CCNOT` requires seven `T` operations and that `ApplySampleWithCCNOT` runs eight `T` operations, use the following C# code:</span></span>

```csharp 
// using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
// using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.UsePrimitiveOperationsCounter = true;
var sim = new QCTraceSimulator(config);
var res = ApplySampleWithCCNOT.Run(sim).Result;

double tCountAll = sim.GetMetric<ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
double tCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
```

<span data-ttu-id="cff5f-113">Programın ilk kısmı çalışır `ApplySampleWithCCNOT` .</span><span class="sxs-lookup"><span data-stu-id="cff5f-113">The first part of the program runs `ApplySampleWithCCNOT`.</span></span> <span data-ttu-id="cff5f-114">İkinci bölüm, [`QCTraceSimulator.GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) tarafından çalıştırılan işlem sayısını almak için yöntemini kullanır `T` `ApplySampleWithCCNOT` :</span><span class="sxs-lookup"><span data-stu-id="cff5f-114">The second part uses the [`QCTraceSimulator.GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) method to retrieve the number of `T` operations run by `ApplySampleWithCCNOT`:</span></span> 

<span data-ttu-id="cff5f-115">`GetMetric`İki tür parametresiyle çağırdığınızda, belirli bir çağrı grafiği kenarıyla ilişkili ölçüm değerini döndürür.</span><span class="sxs-lookup"><span data-stu-id="cff5f-115">When you call `GetMetric` with two type parameters, it returns the value of the metric associated with a given call graph edge.</span></span> <span data-ttu-id="cff5f-116">Önceki örnekte program `Primitive.CCNOT` içindeki işlemi çağırır `ApplySampleWithCCNOT` ve bu nedenle çağrı grafı kenarı içerir `<Primitive.CCNOT, ApplySampleWithCCNOT>` .</span><span class="sxs-lookup"><span data-stu-id="cff5f-116">In the preceding example, the program calls the `Primitive.CCNOT` operation  within `ApplySampleWithCCNOT` and therefore the call graph contains the edge `<Primitive.CCNOT, ApplySampleWithCCNOT>`.</span></span> 

<span data-ttu-id="cff5f-117">Kullanılan işlem sayısını almak için `CNOT` aşağıdaki satırı ekleyin:</span><span class="sxs-lookup"><span data-stu-id="cff5f-117">To retrieve the number of `CNOT` operations used, add the following line:</span></span>
```csharp
double cxCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.CX);
```

<span data-ttu-id="cff5f-118">Son olarak, aşağıdakiler kullanılarak CSV biçiminde Temel Işlemler sayacı tarafından toplanan tüm istatistiklerin çıktısını alabilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="cff5f-118">Finally, you can output all the statistics collected by the Primitive Operations Counter in CSV format using the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.primitiveOperationsCounter];
```

## <a name="see-also"></a><span data-ttu-id="cff5f-119">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="cff5f-119">See also</span></span>

- <span data-ttu-id="cff5f-120">Hisse Geliştirme Seti [hisse izi simülatörü](xref:microsoft.quantum.machines.qc-trace-simulator.intro) genel bakış.</span><span class="sxs-lookup"><span data-stu-id="cff5f-120">The Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
- <span data-ttu-id="cff5f-121"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator>API başvurusu.</span><span class="sxs-lookup"><span data-stu-id="cff5f-121">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API reference.</span></span>
- <span data-ttu-id="cff5f-122"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>API başvurusu.</span><span class="sxs-lookup"><span data-stu-id="cff5f-122">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API reference.</span></span>
- <span data-ttu-id="cff5f-123"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.PrimitiveOperationsGroupsNames>API başvurusu.</span><span class="sxs-lookup"><span data-stu-id="cff5f-123">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.PrimitiveOperationsGroupsNames> API reference.</span></span>