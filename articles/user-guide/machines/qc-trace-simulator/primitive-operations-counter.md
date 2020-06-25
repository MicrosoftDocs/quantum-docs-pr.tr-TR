---
title: Temel Işlem sayacı
description: Bir hisse bir programdaki işlemler tarafından kullanılan temel yürütmelerin sayısını izleyen Microsoft QDK temel Işlem sayacı hakkında bilgi edinin.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.primitive-counter
ms.openlocfilehash: 8bdb0aed370e72b58b23025f1685ad7ce1a77a43
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275552"
---
# <a name="primitive-operations-counter"></a><span data-ttu-id="d207e-103">Temel Işlem sayacı</span><span class="sxs-lookup"><span data-stu-id="d207e-103">Primitive Operations Counter</span></span>  

<span data-ttu-id="d207e-104">, `Primitive Operations Counter` Hisse bilgisayar [Izleme simülatörü](xref:microsoft.quantum.machines.qc-trace-simulator.intro)'nin bir parçasıdır.</span><span class="sxs-lookup"><span data-stu-id="d207e-104">The `Primitive Operations Counter` is a part of the quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="d207e-105">Bir hisse bir programda çağrılan her işlem tarafından kullanılan temel yürütme sayısını sayar.</span><span class="sxs-lookup"><span data-stu-id="d207e-105">It counts the number of primitive executions used by every operation invoked in a quantum program.</span></span> <span data-ttu-id="d207e-106">' Den tüm işlemler `Microsoft.Quantum.Intrinsic` tek qubit ifade, T kapıları, tek qubit Clienfford kapıları, CNOT kapıları ve Multi-Qubitpauli gözlemlenenler ölçümleri bakımından ifade edilir.</span><span class="sxs-lookup"><span data-stu-id="d207e-106">All operations from `Microsoft.Quantum.Intrinsic` are expressed in terms of single qubit rotations, T gates, single qubit Clifford gates, CNOT gates and measurements of multi-qubit Pauli observables.</span></span> <span data-ttu-id="d207e-107">Toplanan istatistikler, işlemler çağrı grafiğinin kenarları üzerinden toplanır.</span><span class="sxs-lookup"><span data-stu-id="d207e-107">Collected statistics are aggregated over the edges of the operations call graph.</span></span> <span data-ttu-id="d207e-108">Şimdi `T` , işlemi uygulamak için kaç kapı olduğunu saymamıza izin verin `CCNOT` .</span><span class="sxs-lookup"><span data-stu-id="d207e-108">Let us now count how many `T` gates are needed to implement the `CCNOT` operation.</span></span> 

```qsharp
open Microsoft.Quantum.Intrinsic;
operation ApplySampleWithCCNOT() : Unit {

    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    } 
}
```

## <a name="using-the-primitive-operations-counter-within-a-c-program"></a><span data-ttu-id="d207e-109">C# programı içinde temel Işlem sayacını kullanma</span><span class="sxs-lookup"><span data-stu-id="d207e-109">Using the Primitive Operations Counter within a C# Program</span></span>

<span data-ttu-id="d207e-110">`CCNOT`Gerçekten 7 kapı gerektirip gerektirmediğini ve 8 kapıları çalıştıran bir denetim için `T` `ApplySampleWithCCNOT` `T` Aşağıdaki C# kodunu kullanabiliriz:</span><span class="sxs-lookup"><span data-stu-id="d207e-110">To check that `CCNOT` indeed requires 7 `T` gates and that `ApplySampleWithCCNOT` executes 8 `T` gates we can use the following C# code:</span></span>

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

<span data-ttu-id="d207e-111">Programın ilk kısmı yürütülür `ApplySampleWithCCNOT` .</span><span class="sxs-lookup"><span data-stu-id="d207e-111">The first part of the program executes `ApplySampleWithCCNOT`.</span></span> <span data-ttu-id="d207e-112">İkinci bölümde, `QCTraceSimulator.GetMetric` tarafından yürütülen T kapıları sayısını almak için yöntemini kullanıyoruz `ApplySampleWithCCNOT` :</span><span class="sxs-lookup"><span data-stu-id="d207e-112">In the second part, we use the method `QCTraceSimulator.GetMetric` to get the number of T gates executed by `ApplySampleWithCCNOT`:</span></span> 

```csharp
double tCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
double tCountAll = sim.GetMetric<ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
```

<span data-ttu-id="d207e-113">`GetMetric`İki tür parametresiyle çağrıldığında, belirli bir çağrı grafiği kenarıyla ilişkili ölçüm değerini döndürür.</span><span class="sxs-lookup"><span data-stu-id="d207e-113">When `GetMetric` is called with two type parameters it returns the value of the metric associated with a given call graph edge.</span></span> <span data-ttu-id="d207e-114">Örnek işlem `Primitive.CCNOT` içinde çağrılır `ApplySampleWithCCNOT` ve bu nedenle çağrı grafı kenarı içerir `<Primitive.CCNOT, ApplySampleWithCCNOT>` .</span><span class="sxs-lookup"><span data-stu-id="d207e-114">In our example operation `Primitive.CCNOT` is called within `ApplySampleWithCCNOT` and therefore the call graph contains the edge `<Primitive.CCNOT, ApplySampleWithCCNOT>`.</span></span> 

<span data-ttu-id="d207e-115">Kullanılan kapı sayısını almak için `CNOT` aşağıdaki satırı ekleyebiliriz:</span><span class="sxs-lookup"><span data-stu-id="d207e-115">To get the number of `CNOT` gates used, we can add the following line:</span></span>
```csharp
double cxCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.CX);
```

<span data-ttu-id="d207e-116">Son olarak, ağ geçidi sayacı tarafından toplanan tüm istatistikleri CSV biçiminde çıkarmak için şunları kullanabilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="d207e-116">Finally, to output all the statistics collected by the gate counter in CSV format we can use the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.primitiveOperationsCounter];
```

## <a name="see-also"></a><span data-ttu-id="d207e-117">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="d207e-117">See also</span></span> ##

- <span data-ttu-id="d207e-118">Hisse bilgisayar [Izleme simülatörü](xref:microsoft.quantum.machines.qc-trace-simulator.intro) genel bakış.</span><span class="sxs-lookup"><span data-stu-id="d207e-118">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
