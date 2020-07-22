---
title: Derinlik sayacı-hisse geliştirme seti
description: 'Bir Q # programında çağrılan her işlemin derinlik sayısını toplamak için hisse izi simülatörü kullanan Microsoft QDK derinlik sayacı hakkında bilgi edinin.'
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.depth-counter
ms.openlocfilehash: 811e387fedf547d2681518ae0bb525c13dc84ff4
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2020
ms.locfileid: "86871136"
---
# <a name="quantum-trace-simulator-depth-counter"></a><span data-ttu-id="77d54-103">Hisse izleme simülatörü: derinlik sayacı</span><span class="sxs-lookup"><span data-stu-id="77d54-103">Quantum trace simulator: depth counter</span></span>

<span data-ttu-id="77d54-104">Derinlik sayacı, hisse Geliştirme Seti [hisse izleyici benzeticisinin](xref:microsoft.quantum.machines.qc-trace-simulator.intro)bir parçasıdır.</span><span class="sxs-lookup"><span data-stu-id="77d54-104">The depth counter is a part of the Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span>
<span data-ttu-id="77d54-105">Bu işlemi, bir hisse dosyasında çağrılan her işlemin derinliğine ait derinlik alt sınırını temsil eden sayıları toplamak için kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="77d54-105">You can use it to gather counts that represent the lower bound of the depth of every operation invoked in a quantum program.</span></span> 

## <a name="depth-values"></a><span data-ttu-id="77d54-106">Derinlik değerleri</span><span class="sxs-lookup"><span data-stu-id="77d54-106">Depth values</span></span>

<span data-ttu-id="77d54-107">Varsayılan olarak, tüm işlemler, **0** `T` **1**derinliğine sahip olan işlem haricinde 0 derinliğine sahiptir.</span><span class="sxs-lookup"><span data-stu-id="77d54-107">By default, all operations have a depth of **0** except the `T` operation, which has a depth of **1**.</span></span> <span data-ttu-id="77d54-108">Bu, varsayılan olarak yalnızca `T` işlemlerin derinliğini (çoğunlukla tercih edilir) hesaplandığı anlamına gelir.</span><span class="sxs-lookup"><span data-stu-id="77d54-108">This means that by default, only the `T` depth of operations is computed (which is often desirable).</span></span> <span data-ttu-id="77d54-109">Derinlik sayacı, işlemin [çağrı grafiğinin](https://en.wikipedia.org/wiki/Call_graph)tüm kenarlarındaki istatistikleri toplar ve toplar.</span><span class="sxs-lookup"><span data-stu-id="77d54-109">The depth counter aggregates and collects statistics over all the edges of the operation's [call graph](https://en.wikipedia.org/wiki/Call_graph).</span></span>

<span data-ttu-id="77d54-110">Tüm <xref:microsoft.quantum.intrinsic> işlemler tek qubit döndürmeler, <xref:microsoft.quantum.intrinsic.t> işlemler, tek qubit Clienfford işlemleri, <xref:microsoft.quantum.intrinsic.cnot> işlemler ve Multi-Qubitpauli gözlemlenenler ölçümleri bakımından ifade edilir.</span><span class="sxs-lookup"><span data-stu-id="77d54-110">All <xref:microsoft.quantum.intrinsic> operations are expressed in terms of single-qubit rotations, <xref:microsoft.quantum.intrinsic.t> operations, single-qubit Clifford operations, <xref:microsoft.quantum.intrinsic.cnot> operations, and measurements of multi-qubit Pauli observables.</span></span> <span data-ttu-id="77d54-111">Kullanıcılar, alanı aracılığıyla temel işlemlerin her biri için derinlik ayarlayabilir `gateTimes` <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> .</span><span class="sxs-lookup"><span data-stu-id="77d54-111">Users can set the depth for each of the primitive operations via the `gateTimes` field of <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>.</span></span>

## <a name="invoking-the-depth-counter"></a><span data-ttu-id="77d54-112">Derinlik sayacını çağırma</span><span class="sxs-lookup"><span data-stu-id="77d54-112">Invoking the depth counter</span></span>

<span data-ttu-id="77d54-113">Hisse izi izleme simülatörünü derinlik sayacından çalıştırmak için bir <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> örnek oluşturmanız, özelliğini true olarak ayarlamanız `UseDepthCounter` ve sonra **true** <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> parametresi olarak yeni bir örnek oluşturmanız gerekir `QCTraceSimulatorConfiguration` .</span><span class="sxs-lookup"><span data-stu-id="77d54-113">To run the quantum trace simulator with the depth counter, you must create a <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instance, set its `UseDepthCounter` property to **true**, and then create a new <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instance with `QCTraceSimulatorConfiguration` as the parameter.</span></span> 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseDepthCounter = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-depth-counter-in-a-c-host-program"></a><span data-ttu-id="77d54-114">C# ana programında derinlik sayacını kullanma</span><span class="sxs-lookup"><span data-stu-id="77d54-114">Using the depth counter in a C# host program</span></span>

<span data-ttu-id="77d54-115">Bu bölümde aşağıdaki C# örneği `T` `CCNOT` , aşağıdaki Q # örnek koduna bağlı olarak işlemin derinliğini hesaplar:</span><span class="sxs-lookup"><span data-stu-id="77d54-115">The C# example that follows in this section computes the `T` depth of the `CCNOT` operation, based on the following Q# sample code:</span></span>

```qsharp
open Microsoft.Quantum.Intrinsic;

operation ApplySampleWithCCNOT() : Unit {
    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

<span data-ttu-id="77d54-116">Bunun derinliğine sahip olup olmadığını denetlemek için `CCNOT` `T` **5** `ApplySampleWithCCNOT` `T` aşağıdaki **6**C# kodunu kullanın:</span><span class="sxs-lookup"><span data-stu-id="77d54-116">To check that `CCNOT` has `T` depth **5** and `ApplySampleWithCCNOT` has `T` depth **6**, use the following C# code:</span></span>

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

<span data-ttu-id="77d54-117">Programın ilk kısmı çalışır `ApplySampleWithCCNOT` .</span><span class="sxs-lookup"><span data-stu-id="77d54-117">The first part of the program runs `ApplySampleWithCCNOT`.</span></span> <span data-ttu-id="77d54-118">İkinci bölüm, [`GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) ve derinliğini almak için yöntemini kullanır `T` `CCNOT` `ApplySampleWithCCNOT` .</span><span class="sxs-lookup"><span data-stu-id="77d54-118">The second part uses the [`GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) method to retrieve the `T` depth of `CCNOT` and `ApplySampleWithCCNOT`.</span></span> 

<span data-ttu-id="77d54-119">Son olarak, aşağıdaki kullanarak, derinlik sayacı tarafından toplanan tüm istatistiklerin CSV biçiminde çıktısını alabilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="77d54-119">Finally, you can output all the statistics collected by the depth counter in CSV format using the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.depthCounter];
```

## <a name="see-also"></a><span data-ttu-id="77d54-120">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="77d54-120">See also</span></span>

- <span data-ttu-id="77d54-121">Hisse Geliştirme Seti [hisse izi simülatörü](xref:microsoft.quantum.machines.qc-trace-simulator.intro) genel bakış.</span><span class="sxs-lookup"><span data-stu-id="77d54-121">The Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
- <span data-ttu-id="77d54-122"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator>API başvurusu.</span><span class="sxs-lookup"><span data-stu-id="77d54-122">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API reference.</span></span>
- <span data-ttu-id="77d54-123"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>API başvurusu.</span><span class="sxs-lookup"><span data-stu-id="77d54-123">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API reference.</span></span>
- <span data-ttu-id="77d54-124"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.MetricsNames.DepthCounter>API başvurusu.</span><span class="sxs-lookup"><span data-stu-id="77d54-124">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.MetricsNames.DepthCounter> API reference.</span></span>
