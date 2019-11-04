---
title: Temel Işlem sayacı | Hisse bilgisayar izleme simülatörü | Microsoft Docs
description: Hisse bilgisayar izleme simülatörünü genel bakış
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.primitive-counter
ms.openlocfilehash: b7ec8b0d7a713051e36cb778c087050f0257710f
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2019
ms.locfileid: "73184891"
---
# <a name="primitive-operations-counter"></a><span data-ttu-id="0af52-103">Temel Işlem sayacı</span><span class="sxs-lookup"><span data-stu-id="0af52-103">Primitive Operations Counter</span></span>  

<span data-ttu-id="0af52-104">`Primitive Operations Counter`, hisse bilgisayar [Izleme Benzeticisinin](xref:microsoft.quantum.machines.qc-trace-simulator.intro)bir parçasıdır.</span><span class="sxs-lookup"><span data-stu-id="0af52-104">The `Primitive Operations Counter` is a part of the quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="0af52-105">Bir hisse bir programda çağrılan her işlem tarafından kullanılan temel yürütme sayısını sayar.</span><span class="sxs-lookup"><span data-stu-id="0af52-105">It counts the number of primitive executions used by every operation invoked in a quantum program.</span></span> <span data-ttu-id="0af52-106">`Microsoft.Quantum.Primitive` tüm işlemler tek qubit döndürmeler, T kapıları, tek qubit Clienfford kapıları, CNOT kapıları ve Multi-qubitpauli gözlemlenenler ölçümleri bakımından ifade edilir.</span><span class="sxs-lookup"><span data-stu-id="0af52-106">All operations from `Microsoft.Quantum.Primitive` are expressed in terms of single qubit rotations, T gates, single qubit Clifford gates, CNOT gates and measurements of multi-qubit Pauli observables.</span></span> <span data-ttu-id="0af52-107">Toplanan istatistikler, işlemler çağrı grafiğinin kenarları üzerinden toplanır.</span><span class="sxs-lookup"><span data-stu-id="0af52-107">Collected statistics are aggregated over the edges of the operations call graph.</span></span> <span data-ttu-id="0af52-108">Şimdi `CCNOT` işleminin uygulanması için kaç `T` kapısı gerektiğini sayalım.</span><span class="sxs-lookup"><span data-stu-id="0af52-108">Let us now count how many `T` gates are needed to implement the `CCNOT` operation.</span></span> 

```qsharp
open Microsoft.Quantum.Primitive;
operation CCNOTDriver() : Unit {

    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    } 
}
```

## <a name="using-the-primitive-operations-counter-within-a-c-program"></a><span data-ttu-id="0af52-109">Bir C# program Içinde temel işlem sayacını kullanma</span><span class="sxs-lookup"><span data-stu-id="0af52-109">Using the Primitive Operations Counter within a C# Program</span></span>

<span data-ttu-id="0af52-110">`CCNOT`, gerçekten 7 `T` kapısı gerektirdiğini ve `CCNOTDriver` 8 `T` kapıları yürüttüğünü denetlemek için aşağıdaki C# kodu kullanabiliriz:</span><span class="sxs-lookup"><span data-stu-id="0af52-110">To check that `CCNOT` indeed requires 7 `T` gates and that `CCNOTDriver` executes 8 `T` gates we can use the following C# code:</span></span>

```csharp 
// using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
// using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.usePrimitiveOperationsCounter = true;
var sim = new QCTraceSimulator(config);
var res = CCNOTDriver.Run(sim).Result;

double tCountAll = sim.GetMetric<CCNOTDriver>(PrimitiveOperationsGroupsNames.T);
double tCount = sim.GetMetric<Primitive.CCNOT, CCNOTDriver>(PrimitiveOperationsGroupsNames.T);
```

<span data-ttu-id="0af52-111">Programın ilk kısmı `CCNOTDriver`yürütür.</span><span class="sxs-lookup"><span data-stu-id="0af52-111">The first part of the program executes `CCNOTDriver`.</span></span> <span data-ttu-id="0af52-112">İkinci bölümde, `CCNOTDriver`tarafından yürütülen T kapıları sayısını almak için yöntemi `QCTraceSimulator.GetMetric` kullanırız:</span><span class="sxs-lookup"><span data-stu-id="0af52-112">In the second part, we use the method `QCTraceSimulator.GetMetric` to get the number of T gates executed by `CCNOTDriver`:</span></span> 

```csharp
double tCount = sim.GetMetric<Primitive.CCNOT, CCNOTDriver>(PrimitiveOperationsGroupsNames.T);
double tCountAll = sim.GetMetric<CCNOTDriver>(PrimitiveOperationsGroupsNames.T);
```

<span data-ttu-id="0af52-113">`GetMetric` iki tür parametresiyle çağrıldığında, belirli bir çağrı grafiği kenarıyla ilişkili ölçüm değerini döndürür.</span><span class="sxs-lookup"><span data-stu-id="0af52-113">When `GetMetric` is called with two type parameters it returns the value of the metric associated with a given call graph edge.</span></span> <span data-ttu-id="0af52-114">Örnek işlem `Primitive.CCNOT` `CCNOTDriver` içinde çağrılır ve bu nedenle çağrı grafı Edge `<Primitive.CCNOT,CCNOTDriver>`içerir.</span><span class="sxs-lookup"><span data-stu-id="0af52-114">In our example operation `Primitive.CCNOT` is called within `CCNOTDriver` and therefore the call graph contains the edge `<Primitive.CCNOT,CCNOTDriver>`.</span></span> 

<span data-ttu-id="0af52-115">Kullanılan `CNOT` kapıları sayısını almak için aşağıdaki satırı ekleyebiliriz:</span><span class="sxs-lookup"><span data-stu-id="0af52-115">To get the number of `CNOT` gates used, we can add the following line:</span></span>
```csharp
double cxCount = sim.GetMetric<Primitive.CCNOT, CCNOTDriver>(PrimitiveOperationsGroupsNames.CX);
```

<span data-ttu-id="0af52-116">Son olarak, ağ geçidi sayacı tarafından toplanan tüm istatistikleri CSV biçiminde çıkarmak için şunları kullanabilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="0af52-116">Finally, to output all the statistics collected by the gate counter in CSV format we can use the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.primitiveOperationsCounter];
```

## <a name="see-also"></a><span data-ttu-id="0af52-117">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="0af52-117">See also</span></span> ##

- <span data-ttu-id="0af52-118">Hisse bilgisayar [Izleme simülatörü](xref:microsoft.quantum.machines.qc-trace-simulator.intro) genel bakış.</span><span class="sxs-lookup"><span data-stu-id="0af52-118">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
