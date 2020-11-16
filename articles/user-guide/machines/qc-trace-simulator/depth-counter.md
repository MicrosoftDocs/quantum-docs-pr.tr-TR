---
title: Derinlik sayacı-hisse geliştirme seti
description: 'Bir programda çağrılan her işlemin derinlik sayısını toplamak için hisse izi simülatörü kullanan Microsoft QDK derinlik sayacı hakkında bilgi edinin Q# .'
author: vadym-kl
ms.author: vadym
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.depth-counter
no-loc:
- 'Q#'
- '$$v'
ms.openlocfilehash: 89d8a2c9f2ecd5c5332215cd4307bcf4a6422036
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92692102"
---
# <a name="quantum-trace-simulator-depth-counter"></a><span data-ttu-id="901d2-103">Hisse izleme simülatörü: derinlik sayacı</span><span class="sxs-lookup"><span data-stu-id="901d2-103">Quantum trace simulator: depth counter</span></span>

<span data-ttu-id="901d2-104">Derinlik sayacı, hisse Geliştirme Seti [hisse izleyici benzeticisinin](xref:microsoft.quantum.machines.qc-trace-simulator.intro)bir parçasıdır.</span><span class="sxs-lookup"><span data-stu-id="901d2-104">The depth counter is a part of the Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span>
<span data-ttu-id="901d2-105">Bu işlemi, bir hisse dosyasında çağrılan her işlemin derinliğine ait derinlik alt sınırını temsil eden sayıları toplamak için kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="901d2-105">You can use it to gather counts that represent the lower bound of the depth of every operation invoked in a quantum program.</span></span> 

## <a name="depth-values"></a><span data-ttu-id="901d2-106">Derinlik değerleri</span><span class="sxs-lookup"><span data-stu-id="901d2-106">Depth values</span></span>

<span data-ttu-id="901d2-107">Varsayılan olarak, tüm işlemler, **0** `T` **1** derinliğine sahip olan işlem haricinde 0 derinliğine sahiptir.</span><span class="sxs-lookup"><span data-stu-id="901d2-107">By default, all operations have a depth of **0** except the `T` operation, which has a depth of **1** .</span></span> <span data-ttu-id="901d2-108">Bu, varsayılan olarak yalnızca `T` işlemlerin derinliğini (çoğunlukla tercih edilir) hesaplandığı anlamına gelir.</span><span class="sxs-lookup"><span data-stu-id="901d2-108">This means that by default, only the `T` depth of operations is computed (which is often desirable).</span></span> <span data-ttu-id="901d2-109">Derinlik sayacı, işlemin [çağrı grafiğinin](https://en.wikipedia.org/wiki/Call_graph)tüm kenarlarındaki istatistikleri toplar ve toplar.</span><span class="sxs-lookup"><span data-stu-id="901d2-109">The depth counter aggregates and collects statistics over all the edges of the operation's [call graph](https://en.wikipedia.org/wiki/Call_graph).</span></span>

<span data-ttu-id="901d2-110">Tüm <xref:Microsoft.Quantum.Intrinsic> işlemler tek qubit döndürmeler, <xref:Microsoft.Quantum.Intrinsic.T> işlemler, tek qubit Clienfford işlemleri, <xref:Microsoft.Quantum.Intrinsic.CNOT> işlemler ve Multi-Qubitpauli gözlemlenenler ölçümleri bakımından ifade edilir.</span><span class="sxs-lookup"><span data-stu-id="901d2-110">All <xref:Microsoft.Quantum.Intrinsic> operations are expressed in terms of single-qubit rotations, <xref:Microsoft.Quantum.Intrinsic.T> operations, single-qubit Clifford operations, <xref:Microsoft.Quantum.Intrinsic.CNOT> operations, and measurements of multi-qubit Pauli observables.</span></span> <span data-ttu-id="901d2-111">Kullanıcılar, alanı aracılığıyla temel işlemlerin her biri için derinlik ayarlayabilir `gateTimes` <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> .</span><span class="sxs-lookup"><span data-stu-id="901d2-111">Users can set the depth for each of the primitive operations via the `gateTimes` field of <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>.</span></span>

## <a name="invoking-the-depth-counter"></a><span data-ttu-id="901d2-112">Derinlik sayacını çağırma</span><span class="sxs-lookup"><span data-stu-id="901d2-112">Invoking the depth counter</span></span>

<span data-ttu-id="901d2-113">Hisse izi izleme simülatörünü derinlik sayacından çalıştırmak için bir <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> örnek oluşturmanız, özelliğini true olarak ayarlamanız `UseDepthCounter` ve sonra **true** <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> parametresi olarak yeni bir örnek oluşturmanız gerekir `QCTraceSimulatorConfiguration` .</span><span class="sxs-lookup"><span data-stu-id="901d2-113">To run the quantum trace simulator with the depth counter, you must create a <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instance, set its `UseDepthCounter` property to **true** , and then create a new <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instance with `QCTraceSimulatorConfiguration` as the parameter.</span></span> 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseDepthCounter = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-depth-counter-in-a-c-host-program"></a><span data-ttu-id="901d2-114">C# ana programında derinlik sayacını kullanma</span><span class="sxs-lookup"><span data-stu-id="901d2-114">Using the depth counter in a C# host program</span></span>

<span data-ttu-id="901d2-115">Bu bölümde takip edilen C# örneği `T` `CCNOT` , aşağıdaki örnek koda göre işlemin derinliğini hesaplar Q# :</span><span class="sxs-lookup"><span data-stu-id="901d2-115">The C# example that follows in this section computes the `T` depth of the `CCNOT` operation, based on the following Q# sample code:</span></span>

```qsharp
open Microsoft.Quantum.Intrinsic;

operation ApplySampleWithCCNOT() : Unit {
    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

<span data-ttu-id="901d2-116">Bunun derinliğine sahip olup olmadığını denetlemek için `CCNOT` `T` **5** `ApplySampleWithCCNOT` `T` aşağıdaki **6** C# kodunu kullanın:</span><span class="sxs-lookup"><span data-stu-id="901d2-116">To check that `CCNOT` has `T` depth **5** and `ApplySampleWithCCNOT` has `T` depth **6** , use the following C# code:</span></span>

```csharp
using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.UseDepthCounter = true;
var sim = new QCTraceSimulator(config);
var res = ApplySampleWithCCNOT.Run(sim).Result;

double tDepth = sim.GetMetric<Intrinsic.CCNOT, ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
double tDepthAll = sim.GetMetric<ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
```

<span data-ttu-id="901d2-117">Programın ilk kısmı çalışır `ApplySampleWithCCNOT` .</span><span class="sxs-lookup"><span data-stu-id="901d2-117">The first part of the program runs `ApplySampleWithCCNOT`.</span></span> <span data-ttu-id="901d2-118">İkinci bölüm, [`GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) ve derinliğini almak için yöntemini kullanır `T` `CCNOT` `ApplySampleWithCCNOT` .</span><span class="sxs-lookup"><span data-stu-id="901d2-118">The second part uses the [`GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) method to retrieve the `T` depth of `CCNOT` and `ApplySampleWithCCNOT`.</span></span> 

<span data-ttu-id="901d2-119">Son olarak, aşağıdaki kullanarak, derinlik sayacı tarafından toplanan tüm istatistiklerin CSV biçiminde çıktısını alabilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="901d2-119">Finally, you can output all the statistics collected by the depth counter in CSV format using the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.depthCounter];
```

## <a name="see-also"></a><span data-ttu-id="901d2-120">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="901d2-120">See also</span></span>

- <span data-ttu-id="901d2-121">Hisse Geliştirme Seti [hisse izi simülatörü](xref:microsoft.quantum.machines.qc-trace-simulator.intro) genel bakış.</span><span class="sxs-lookup"><span data-stu-id="901d2-121">The Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
- <span data-ttu-id="901d2-122"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator>API başvurusu.</span><span class="sxs-lookup"><span data-stu-id="901d2-122">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API reference.</span></span>
- <span data-ttu-id="901d2-123"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>API başvurusu.</span><span class="sxs-lookup"><span data-stu-id="901d2-123">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API reference.</span></span>
- <span data-ttu-id="901d2-124"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.MetricsNames.DepthCounter>API başvurusu.</span><span class="sxs-lookup"><span data-stu-id="901d2-124">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.MetricsNames.DepthCounter> API reference.</span></span>
