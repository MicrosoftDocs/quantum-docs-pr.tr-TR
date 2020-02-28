---
title: Temel Işlem sayacı
description: Bir hisse bir programdaki işlemler tarafından kullanılan temel yürütmelerin sayısını izleyen Microsoft QDK temel Işlem sayacı hakkında bilgi edinin.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.primitive-counter
ms.openlocfilehash: 8bdb0aed370e72b58b23025f1685ad7ce1a77a43
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/28/2020
ms.locfileid: "77905956"
---
# <a name="primitive-operations-counter"></a><span data-ttu-id="7f76a-103">Temel Işlem sayacı</span><span class="sxs-lookup"><span data-stu-id="7f76a-103">Primitive Operations Counter</span></span>  

<span data-ttu-id="7f76a-104">`Primitive Operations Counter`, hisse bilgisayar [Izleme Benzeticisinin](xref:microsoft.quantum.machines.qc-trace-simulator.intro)bir parçasıdır.</span><span class="sxs-lookup"><span data-stu-id="7f76a-104">The `Primitive Operations Counter` is a part of the quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="7f76a-105">Bir hisse bir programda çağrılan her işlem tarafından kullanılan temel yürütme sayısını sayar.</span><span class="sxs-lookup"><span data-stu-id="7f76a-105">It counts the number of primitive executions used by every operation invoked in a quantum program.</span></span> <span data-ttu-id="7f76a-106">`Microsoft.Quantum.Intrinsic` tüm işlemler tek qubit döndürmeler, T kapıları, tek qubit Clienfford kapıları, CNOT kapıları ve Multi-qubitpauli gözlemlenenler ölçümleri bakımından ifade edilir.</span><span class="sxs-lookup"><span data-stu-id="7f76a-106">All operations from `Microsoft.Quantum.Intrinsic` are expressed in terms of single qubit rotations, T gates, single qubit Clifford gates, CNOT gates and measurements of multi-qubit Pauli observables.</span></span> <span data-ttu-id="7f76a-107">Toplanan istatistikler, işlemler çağrı grafiğinin kenarları üzerinden toplanır.</span><span class="sxs-lookup"><span data-stu-id="7f76a-107">Collected statistics are aggregated over the edges of the operations call graph.</span></span> <span data-ttu-id="7f76a-108">Şimdi `CCNOT` işleminin uygulanması için kaç `T` kapısı gerektiğini sayalım.</span><span class="sxs-lookup"><span data-stu-id="7f76a-108">Let us now count how many `T` gates are needed to implement the `CCNOT` operation.</span></span> 

```qsharp
open Microsoft.Quantum.Intrinsic;
operation ApplySampleWithCCNOT() : Unit {

    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    } 
}
```

## <a name="using-the-primitive-operations-counter-within-a-c-program"></a><span data-ttu-id="7f76a-109">Bir C# program Içinde temel işlem sayacını kullanma</span><span class="sxs-lookup"><span data-stu-id="7f76a-109">Using the Primitive Operations Counter within a C# Program</span></span>

<span data-ttu-id="7f76a-110">`CCNOT`, gerçekten 7 `T` kapısı gerektirdiğini ve `ApplySampleWithCCNOT` 8 `T` kapıları yürüttüğünü denetlemek için aşağıdaki C# kodu kullanabiliriz:</span><span class="sxs-lookup"><span data-stu-id="7f76a-110">To check that `CCNOT` indeed requires 7 `T` gates and that `ApplySampleWithCCNOT` executes 8 `T` gates we can use the following C# code:</span></span>

```csharp 
// using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
// using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.usePrimitiveOperationsCounter = true;
var sim = new QCTraceSimulator(config);
var res = ApplySampleWithCCNOT.Run(sim).Result;

double tCountAll = sim.GetMetric<ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
double tCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
```

<span data-ttu-id="7f76a-111">Programın ilk kısmı `ApplySampleWithCCNOT`yürütür.</span><span class="sxs-lookup"><span data-stu-id="7f76a-111">The first part of the program executes `ApplySampleWithCCNOT`.</span></span> <span data-ttu-id="7f76a-112">İkinci bölümde, `ApplySampleWithCCNOT`tarafından yürütülen T kapıları sayısını almak için yöntemi `QCTraceSimulator.GetMetric` kullanırız:</span><span class="sxs-lookup"><span data-stu-id="7f76a-112">In the second part, we use the method `QCTraceSimulator.GetMetric` to get the number of T gates executed by `ApplySampleWithCCNOT`:</span></span> 

```csharp
double tCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
double tCountAll = sim.GetMetric<ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
```

<span data-ttu-id="7f76a-113">`GetMetric` iki tür parametresiyle çağrıldığında, belirli bir çağrı grafiği kenarıyla ilişkili ölçüm değerini döndürür.</span><span class="sxs-lookup"><span data-stu-id="7f76a-113">When `GetMetric` is called with two type parameters it returns the value of the metric associated with a given call graph edge.</span></span> <span data-ttu-id="7f76a-114">Örnek işlem `Primitive.CCNOT` `ApplySampleWithCCNOT` içinde çağrılır ve bu nedenle çağrı grafı Edge `<Primitive.CCNOT, ApplySampleWithCCNOT>`içerir.</span><span class="sxs-lookup"><span data-stu-id="7f76a-114">In our example operation `Primitive.CCNOT` is called within `ApplySampleWithCCNOT` and therefore the call graph contains the edge `<Primitive.CCNOT, ApplySampleWithCCNOT>`.</span></span> 

<span data-ttu-id="7f76a-115">Kullanılan `CNOT` kapıları sayısını almak için aşağıdaki satırı ekleyebiliriz:</span><span class="sxs-lookup"><span data-stu-id="7f76a-115">To get the number of `CNOT` gates used, we can add the following line:</span></span>
```csharp
double cxCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.CX);
```

<span data-ttu-id="7f76a-116">Son olarak, ağ geçidi sayacı tarafından toplanan tüm istatistikleri CSV biçiminde çıkarmak için şunları kullanabilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="7f76a-116">Finally, to output all the statistics collected by the gate counter in CSV format we can use the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.primitiveOperationsCounter];
```

## <a name="see-also"></a><span data-ttu-id="7f76a-117">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="7f76a-117">See also</span></span> ##

- <span data-ttu-id="7f76a-118">Hisse bilgisayar [Izleme simülatörü](xref:microsoft.quantum.machines.qc-trace-simulator.intro) genel bakış.</span><span class="sxs-lookup"><span data-stu-id="7f76a-118">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
