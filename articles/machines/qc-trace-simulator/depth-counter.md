---
title: Derinlik sayacı
description: Hisse bir programda çağrılan her işlemin derinlik sayısını toplayan Microsoft QDK derinlik sayacı hakkında bilgi edinin.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.depth-counter
ms.openlocfilehash: d532a9f512b8c87d83d62ed26e3bb67e1b6f668b
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/28/2020
ms.locfileid: "77906109"
---
# <a name="depth-counter"></a><span data-ttu-id="6e200-103">Derinlik sayacı</span><span class="sxs-lookup"><span data-stu-id="6e200-103">Depth Counter</span></span>

<span data-ttu-id="6e200-104">`Depth Counter`, hisse bilgisayar [Izleme Benzeticisinin](xref:microsoft.quantum.machines.qc-trace-simulator.intro)bir parçasıdır.</span><span class="sxs-lookup"><span data-stu-id="6e200-104">The `Depth Counter` is a part of the quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span>
<span data-ttu-id="6e200-105">Hisse bir programda çağrılan her işlemin derinlik sayısını toplamak için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="6e200-105">It is used to gather counts of the depth of every operation invoked in a quantum program.</span></span> <span data-ttu-id="6e200-106"><xref:microsoft.quantum.intrinsic> tüm işlemler tek qubit döndürmeler, T kapıları, tek qubit Clienfford kapıları, CNOT kapıları ve Multi-qubitpauli gözlemlenenler ölçümleri bakımından ifade edilir.</span><span class="sxs-lookup"><span data-stu-id="6e200-106">All operations from <xref:microsoft.quantum.intrinsic> are expressed in terms of single qubit rotations, T gates, single qubit Clifford gates, CNOT gates and measurements of multi-qubit Pauli observables.</span></span> <span data-ttu-id="6e200-107">Kullanıcılar, <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>`gateTimes` alanı aracılığıyla temel işlemlerin her biri için derinlik belirleyebilir.</span><span class="sxs-lookup"><span data-stu-id="6e200-107">Users can set the depth for each of the primitive operations via the `gateTimes` field of <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>.</span></span>

<span data-ttu-id="6e200-108">Varsayılan olarak, tüm işlemler, 1 derinliğine sahip T kapısı dışında derinlik 0 ' dır.</span><span class="sxs-lookup"><span data-stu-id="6e200-108">By default, all operations have depth 0 except the T gate which has depth 1.</span></span> <span data-ttu-id="6e200-109">Bu, varsayılan olarak yalnızca T ve Operations 'in yalnızca T derinliğini hesaplandığı anlamına gelir (Bu genellikle tercih edilir).</span><span class="sxs-lookup"><span data-stu-id="6e200-109">This means that by default, only the T depth of operations is computed (which is often desirable).</span></span> <span data-ttu-id="6e200-110">Toplanan istatistikler, işlemler çağrı grafiğinin tüm kenarlarına toplanır.</span><span class="sxs-lookup"><span data-stu-id="6e200-110">Collected statistics are aggregated over all the edges of the operations call graph.</span></span> 

<span data-ttu-id="6e200-111">Şimdi <xref:microsoft.quantum.intrinsic.ccnot> işleminin <xref:microsoft.quantum.intrinsic.t> derinliğini hesaplamıza izin verin.</span><span class="sxs-lookup"><span data-stu-id="6e200-111">Let us now compute the <xref:microsoft.quantum.intrinsic.t> depth of the <xref:microsoft.quantum.intrinsic.ccnot> operation.</span></span> <span data-ttu-id="6e200-112">Aşağıdaki Q # örnek kodunu kullanacağız:</span><span class="sxs-lookup"><span data-stu-id="6e200-112">We will use the following Q# sample code:</span></span>

```qsharp
open Microsoft.Quantum.Intrinsic;

operation ApplySampleWithCCNOT() : Unit {
    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

## <a name="using-depth-counter-within-a-c-program"></a><span data-ttu-id="6e200-113">Bir C# program Içinde derinlik sayacı kullanma</span><span class="sxs-lookup"><span data-stu-id="6e200-113">Using Depth Counter within a C# Program</span></span>

<span data-ttu-id="6e200-114">`CCNOT` `T` Derinlik 5 ' i ve `ApplySampleWithCCNOT` `T` derinliğine sahip olduğunu denetlemek için aşağıdaki C# kodu kullanabilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="6e200-114">To check that `CCNOT` has `T` depth 5 and `ApplySampleWithCCNOT` has `T` depth 6 we can use the following C# code:</span></span>

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

<span data-ttu-id="6e200-115">Programın ilk kısmı `ApplySampleWithCCNOT`yürütür.</span><span class="sxs-lookup"><span data-stu-id="6e200-115">The first part of the program executes `ApplySampleWithCCNOT`.</span></span> <span data-ttu-id="6e200-116">İkinci bölümde, `CCNOT` ve `ApplySampleWithCCNOT``T` derinliğini almak için yöntemi `QCTraceSimulator.GetMetric` kullanırız:</span><span class="sxs-lookup"><span data-stu-id="6e200-116">In the second part, we use the method `QCTraceSimulator.GetMetric` to get the `T` depth of `CCNOT` and `ApplySampleWithCCNOT`:</span></span> 

```csharp
double tDepth = sim.GetMetric<Intrinsic.CCNOT, ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
double tDepthAll = sim.GetMetric<ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
```

<span data-ttu-id="6e200-117">Son olarak, `Depth Counter` tarafından toplanan tüm istatistikleri CSV biçiminde çıkarmak için aşağıdakileri kullanabiliriz:</span><span class="sxs-lookup"><span data-stu-id="6e200-117">Finally, to output all the statistics collected by `Depth Counter` in CSV format we can use the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.depthCounter];
```

## <a name="see-also"></a><span data-ttu-id="6e200-118">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="6e200-118">See also</span></span> ##

- <span data-ttu-id="6e200-119">Hisse bilgisayar [Izleme simülatörü](xref:microsoft.quantum.machines.qc-trace-simulator.intro) genel bakış.</span><span class="sxs-lookup"><span data-stu-id="6e200-119">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
