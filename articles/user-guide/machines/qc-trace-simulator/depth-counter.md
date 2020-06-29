---
title: Derinlik sayacı
description: Hisse bir programda çağrılan her işlemin derinlik sayısını toplayan Microsoft QDK derinlik sayacı hakkında bilgi edinin.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.depth-counter
ms.openlocfilehash: 0029a00e6a3563dc542daeda2afa7cabf42441fb
ms.sourcegitcommit: af10179284967bd7a72a52ae7e1c4da65c7d128d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/26/2020
ms.locfileid: "85415288"
---
# <a name="depth-counter"></a><span data-ttu-id="ff2ad-103">Derinlik sayacı</span><span class="sxs-lookup"><span data-stu-id="ff2ad-103">Depth Counter</span></span>

<span data-ttu-id="ff2ad-104">, `Depth Counter` Hisse bilgisayar [Izleme simülatörü](xref:microsoft.quantum.machines.qc-trace-simulator.intro)'nin bir parçasıdır.</span><span class="sxs-lookup"><span data-stu-id="ff2ad-104">The `Depth Counter` is a part of the quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span>
<span data-ttu-id="ff2ad-105">Bir hisse bir programda çağrılan her işlemin derinliğine yönelik alt sınırı temsil eden sayıları toplamak için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="ff2ad-105">It is used to gather counts that represent the lower bound of the depth of every operation invoked in a quantum program.</span></span> <span data-ttu-id="ff2ad-106">' Den tüm işlemler <xref:microsoft.quantum.intrinsic> tek qubit ifade, T kapıları, tek qubit Clienfford kapıları, CNOT kapıları ve Multi-Qubitpauli gözlemlenenler ölçümleri bakımından ifade edilir.</span><span class="sxs-lookup"><span data-stu-id="ff2ad-106">All operations from <xref:microsoft.quantum.intrinsic> are expressed in terms of single qubit rotations, T gates, single qubit Clifford gates, CNOT gates and measurements of multi-qubit Pauli observables.</span></span> <span data-ttu-id="ff2ad-107">Kullanıcılar, alanı aracılığıyla temel işlemlerin her biri için derinlik ayarlayabilir `gateTimes` <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> .</span><span class="sxs-lookup"><span data-stu-id="ff2ad-107">Users can set the depth for each of the primitive operations via the `gateTimes` field of <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>.</span></span>

<span data-ttu-id="ff2ad-108">Varsayılan olarak, tüm işlemler, 1 derinliğine sahip T kapısı dışında derinlik 0 ' dır.</span><span class="sxs-lookup"><span data-stu-id="ff2ad-108">By default, all operations have depth 0 except the T gate which has depth 1.</span></span> <span data-ttu-id="ff2ad-109">Bu, varsayılan olarak yalnızca T ve Operations 'in yalnızca T derinliğini hesaplandığı anlamına gelir (Bu genellikle tercih edilir).</span><span class="sxs-lookup"><span data-stu-id="ff2ad-109">This means that by default, only the T depth of operations is computed (which is often desirable).</span></span> <span data-ttu-id="ff2ad-110">Toplanan istatistikler, işlemler çağrı grafiğinin tüm kenarlarına toplanır.</span><span class="sxs-lookup"><span data-stu-id="ff2ad-110">Collected statistics are aggregated over all the edges of the operations call graph.</span></span> 

<span data-ttu-id="ff2ad-111">Şimdi işlemin derinliğini hesaplamıza izin verin <xref:microsoft.quantum.intrinsic.t> <xref:microsoft.quantum.intrinsic.ccnot> .</span><span class="sxs-lookup"><span data-stu-id="ff2ad-111">Let us now compute the <xref:microsoft.quantum.intrinsic.t> depth of the <xref:microsoft.quantum.intrinsic.ccnot> operation.</span></span> <span data-ttu-id="ff2ad-112">Aşağıdaki Q # örnek kodunu kullanacağız:</span><span class="sxs-lookup"><span data-stu-id="ff2ad-112">We will use the following Q# sample code:</span></span>

```qsharp
open Microsoft.Quantum.Intrinsic;

operation ApplySampleWithCCNOT() : Unit {
    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

## <a name="using-depth-counter-within-a-c-program"></a><span data-ttu-id="ff2ad-113">C# programı içinde derinlik sayacı kullanma</span><span class="sxs-lookup"><span data-stu-id="ff2ad-113">Using Depth Counter within a C# Program</span></span>

<span data-ttu-id="ff2ad-114">Bunun derinliğine sahip olup olmadığını denetlemek için `CCNOT` `T` `ApplySampleWithCCNOT` `T` Aşağıdaki C# kodunu kullanabiliriz:</span><span class="sxs-lookup"><span data-stu-id="ff2ad-114">To check that `CCNOT` has `T` depth 5 and `ApplySampleWithCCNOT` has `T` depth 6 we can use the following C# code:</span></span>

```csharp
using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.useDepthCounter = true;
var sim = new QCTraceSimulator(config);
var res = ApplySampleWithCCNOT.Run(sim).Result;

double tDepth = sim.GetMetric<Intrinsic.CCNOT, ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
double tDepthAll = sim.GetMetric<ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
```

<span data-ttu-id="ff2ad-115">Programın ilk kısmı yürütülür `ApplySampleWithCCNOT` .</span><span class="sxs-lookup"><span data-stu-id="ff2ad-115">The first part of the program executes `ApplySampleWithCCNOT`.</span></span> <span data-ttu-id="ff2ad-116">İkinci bölümde, `QCTraceSimulator.GetMetric` ve derinliğini almak için yöntemini kullanıyoruz `T` `CCNOT` `ApplySampleWithCCNOT` :</span><span class="sxs-lookup"><span data-stu-id="ff2ad-116">In the second part, we use the method `QCTraceSimulator.GetMetric` to get the `T` depth of `CCNOT` and `ApplySampleWithCCNOT`:</span></span> 

```csharp
double tDepth = sim.GetMetric<Intrinsic.CCNOT, ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
double tDepthAll = sim.GetMetric<ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
```

<span data-ttu-id="ff2ad-117">Son olarak, CSV biçiminde toplanan tüm istatistiklerin çıktısını almak için `Depth Counter` aşağıdakileri kullanabilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="ff2ad-117">Finally, to output all the statistics collected by `Depth Counter` in CSV format we can use the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.depthCounter];
```

## <a name="see-also"></a><span data-ttu-id="ff2ad-118">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="ff2ad-118">See also</span></span> ##

- <span data-ttu-id="ff2ad-119">Hisse bilgisayar [Izleme simülatörü](xref:microsoft.quantum.machines.qc-trace-simulator.intro) genel bakış.</span><span class="sxs-lookup"><span data-stu-id="ff2ad-119">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
