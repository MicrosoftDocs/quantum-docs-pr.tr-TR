---
title: Temel işlem sayacı-hisse geliştirme seti
description: 'Bir Q # programında işlemler tarafından kullanılan temel yürütmeleri izlemek için hisse izi simülatörü kullanan Microsoft QDK temel işlem sayacı hakkında bilgi edinin.'
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.primitive-counter
ms.openlocfilehash: ea022d499354f7cefd60da690466496e0ce7c336
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2020
ms.locfileid: "86871034"
---
# <a name="quantum-trace-simulator-primitive-operations-counter"></a><span data-ttu-id="e5d86-103">Hisse izleme simülatörü: temel işlemler sayacı</span><span class="sxs-lookup"><span data-stu-id="e5d86-103">Quantum trace simulator: primitive operations counter</span></span>

<span data-ttu-id="e5d86-104">Temel işlem sayacı, hisse Geliştirme Seti [hisse izleme benzeticisinin](xref:microsoft.quantum.machines.qc-trace-simulator.intro)bir parçasıdır.</span><span class="sxs-lookup"><span data-stu-id="e5d86-104">The primitive operation counter is a part of the Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="e5d86-105">Bir hisse bir programda çağrılan her işlem tarafından kullanılan temel yürütme sayısını sayar.</span><span class="sxs-lookup"><span data-stu-id="e5d86-105">It counts the number of primitive executions used by every operation invoked in a quantum program.</span></span> 

<span data-ttu-id="e5d86-106">Tüm <xref:microsoft.quantum.intrinsic> işlemler tek qubit döndürmeler, T işlemleri, tek qubit Clienfford işlemleri, CNOT işlemleri ve Multi-Qubitpauli gözlemlenenler ölçümleri bakımından ifade edilir.</span><span class="sxs-lookup"><span data-stu-id="e5d86-106">All <xref:microsoft.quantum.intrinsic> operations are expressed in terms of single-qubit rotations, T operations, single-qubit Clifford operations, CNOT operations, and measurements of multi-qubit Pauli observables.</span></span> <span data-ttu-id="e5d86-107">Temel Işlem sayacı, işlemin [çağrı grafiğinin](https://en.wikipedia.org/wiki/Call_graph)tüm kenarlarına ilişkin istatistikleri toplar ve toplar.</span><span class="sxs-lookup"><span data-stu-id="e5d86-107">The Primitive Operations Counter aggregates and collects statistics over all the edges of the operation's [call graph](https://en.wikipedia.org/wiki/Call_graph).</span></span>

## <a name="invoking-the-primitive-operation-counter"></a><span data-ttu-id="e5d86-108">Temel işlem sayacını çağırma</span><span class="sxs-lookup"><span data-stu-id="e5d86-108">Invoking the primitive operation counter</span></span>

<span data-ttu-id="e5d86-109">Temel işlem sayacı ile hisse izi simülatörü çalıştırmak için bir <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> örnek oluşturmanız, `UsePrimitiveOperationsCounter` özelliği **true**olarak ayarlamanız ve sonra <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> parametresi olarak ile yeni bir örnek oluşturmanız gerekir `QCTraceSimulatorConfiguration` .</span><span class="sxs-lookup"><span data-stu-id="e5d86-109">To run the quantum trace simulator with the primitive operation counter, you must create a <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instance, set the `UsePrimitiveOperationsCounter` property to **true**, and then create a new <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instance with the `QCTraceSimulatorConfiguration` as the parameter.</span></span>

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UsePrimitiveOperationsCounter = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-primitive-operation-counter-in-a-c-host-program"></a><span data-ttu-id="e5d86-110">C# ana programında temel işlem sayacını kullanma</span><span class="sxs-lookup"><span data-stu-id="e5d86-110">Using the primitive operation counter in a C# host program</span></span>

<span data-ttu-id="e5d86-111">Bu bölümde aşağıdaki C# örneği, <xref:microsoft.quantum.intrinsic.t> <xref:microsoft.quantum.intrinsic.ccnot> aşağıdaki Q # örnek koduna bağlı olarak, işlemi uygulamak için kaç işlemin gerekli olduğunu sayar:</span><span class="sxs-lookup"><span data-stu-id="e5d86-111">The C# example that follows in this section counts how many <xref:microsoft.quantum.intrinsic.t> operations are needed to implement the <xref:microsoft.quantum.intrinsic.ccnot> operation, based on the following Q# sample code:</span></span>

```qsharp
open Microsoft.Quantum.Intrinsic;
operation ApplySampleWithCCNOT() : Unit {

    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

<span data-ttu-id="e5d86-112">Bunun `CCNOT` yedi `T` işlem gerektirdiğini ve `ApplySampleWithCCNOT` sekiz işlem çalıştırmasını denetlemek Için `T` Aşağıdaki C# kodunu kullanın:</span><span class="sxs-lookup"><span data-stu-id="e5d86-112">To check that `CCNOT` requires seven `T` operations and that `ApplySampleWithCCNOT` runs eight `T` operations, use the following C# code:</span></span>

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

<span data-ttu-id="e5d86-113">Programın ilk kısmı çalışır `ApplySampleWithCCNOT` .</span><span class="sxs-lookup"><span data-stu-id="e5d86-113">The first part of the program runs `ApplySampleWithCCNOT`.</span></span> <span data-ttu-id="e5d86-114">İkinci bölüm, [`QCTraceSimulator.GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) tarafından çalıştırılan işlem sayısını almak için yöntemini kullanır `T` `ApplySampleWithCCNOT` :</span><span class="sxs-lookup"><span data-stu-id="e5d86-114">The second part uses the [`QCTraceSimulator.GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) method to retrieve the number of `T` operations run by `ApplySampleWithCCNOT`:</span></span> 

<span data-ttu-id="e5d86-115">`GetMetric`İki tür parametresiyle çağırdığınızda, belirli bir çağrı grafiği kenarıyla ilişkili ölçüm değerini döndürür.</span><span class="sxs-lookup"><span data-stu-id="e5d86-115">When you call `GetMetric` with two type parameters, it returns the value of the metric associated with a given call graph edge.</span></span> <span data-ttu-id="e5d86-116">Önceki örnekte program `Primitive.CCNOT` içindeki işlemi çağırır `ApplySampleWithCCNOT` ve bu nedenle çağrı grafı kenarı içerir `<Primitive.CCNOT, ApplySampleWithCCNOT>` .</span><span class="sxs-lookup"><span data-stu-id="e5d86-116">In the preceding example, the program calls the `Primitive.CCNOT` operation  within `ApplySampleWithCCNOT` and therefore the call graph contains the edge `<Primitive.CCNOT, ApplySampleWithCCNOT>`.</span></span> 

<span data-ttu-id="e5d86-117">Kullanılan işlem sayısını almak için `CNOT` aşağıdaki satırı ekleyin:</span><span class="sxs-lookup"><span data-stu-id="e5d86-117">To retrieve the number of `CNOT` operations used, add the following line:</span></span>
```csharp
double cxCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.CX);
```

<span data-ttu-id="e5d86-118">Son olarak, aşağıdakiler kullanılarak CSV biçiminde Temel Işlemler sayacı tarafından toplanan tüm istatistiklerin çıktısını alabilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="e5d86-118">Finally, you can output all the statistics collected by the Primitive Operations Counter in CSV format using the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.primitiveOperationsCounter];
```

## <a name="see-also"></a><span data-ttu-id="e5d86-119">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="e5d86-119">See also</span></span>

- <span data-ttu-id="e5d86-120">Hisse Geliştirme Seti [hisse izi simülatörü](xref:microsoft.quantum.machines.qc-trace-simulator.intro) genel bakış.</span><span class="sxs-lookup"><span data-stu-id="e5d86-120">The Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
- <span data-ttu-id="e5d86-121"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator>API başvurusu.</span><span class="sxs-lookup"><span data-stu-id="e5d86-121">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API reference.</span></span>
- <span data-ttu-id="e5d86-122"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>API başvurusu.</span><span class="sxs-lookup"><span data-stu-id="e5d86-122">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API reference.</span></span>
- <span data-ttu-id="e5d86-123"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.PrimitiveOperationsGroupsNames>API başvurusu.</span><span class="sxs-lookup"><span data-stu-id="e5d86-123">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.PrimitiveOperationsGroupsNames> API reference.</span></span>