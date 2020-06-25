---
title: Genişlik sayacı
description: Bir hisse içindeki her işlem tarafından ayrılan ve ödünç alınan qubits sayısını sayan Microsoft QDK genişlik sayacı hakkında bilgi edinin.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.width-counter
ms.openlocfilehash: a76292222950310acc90dded02980e4a5b792e76
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275567"
---
# <a name="width-counter"></a><span data-ttu-id="d4f33-103">Genişlik sayacı</span><span class="sxs-lookup"><span data-stu-id="d4f33-103">Width Counter</span></span>

<span data-ttu-id="d4f33-104">`Width Counter`Her bir işlem tarafından ayrılan ve ödünç alınan qubits sayısını sayar.</span><span class="sxs-lookup"><span data-stu-id="d4f33-104">The `Width Counter` counts the number of qubits allocated and borrowed by each operation.</span></span>
<span data-ttu-id="d4f33-105">Ad alanındaki tüm işlemler `Microsoft.Quantum.Intrinsic` tek qubit ifade, T kapıları, tek qubit Clienfford kapıları, CNOT kapıları ve Multi-Qubitpauli gözlemlenenler ölçümleri bakımından ifade edilir.</span><span class="sxs-lookup"><span data-stu-id="d4f33-105">All operations from the `Microsoft.Quantum.Intrinsic` namespace are expressed in terms of single qubit rotations, T gates, single qubit Clifford gates, CNOT gates and measurements of multi-qubit Pauli observables.</span></span> <span data-ttu-id="d4f33-106">Temel işlemlerden bazıları ek qubit ayırabilirler.</span><span class="sxs-lookup"><span data-stu-id="d4f33-106">Some of the primitive operations can allocate extra qubits.</span></span> <span data-ttu-id="d4f33-107">Örneğin, denetlenen `X` kapıları veya denetimli kapıları çarpın `T` .</span><span class="sxs-lookup"><span data-stu-id="d4f33-107">For example, multiply controlled `X` gates or controlled `T` gates.</span></span> <span data-ttu-id="d4f33-108">Çarpma kontrollü kapıların uygulanması tarafından ayrılan ekstra qubits sayısını hesaplamıza izin verin `X` :</span><span class="sxs-lookup"><span data-stu-id="d4f33-108">Let us compute the number of extra qubits allocated by the implementation of a multiply controlled `X` gate:</span></span>

```qsharp
open Microsoft.Quantum.Intrinsic;
open Microsoft.Quantum.Arrays;
operation ApplyMultiControlledX( numberOfQubits : Int ) : Unit {
    using(qubits = Qubit[numberOfQubits]) {
        Controlled X (Rest(qubits), Head(qubits));
    } 
}
```

## <a name="using-width-counter-within-a-c-program"></a><span data-ttu-id="d4f33-109">Bir C# programı içinde Width sayacını kullanma</span><span class="sxs-lookup"><span data-stu-id="d4f33-109">Using Width Counter within a C# Program</span></span>

<span data-ttu-id="d4f33-110">`X`Toplam 5 qubit üzerinde işlem denetimli olan çarpmaya 2 anyacal ve giriş genişliği 5 olur.</span><span class="sxs-lookup"><span data-stu-id="d4f33-110">Multiply controlled `X` acting on a total of 5 qubits will allocate 2 ancillary qubits and its input width will be 5.</span></span> <span data-ttu-id="d4f33-111">Bu durumun bu olduğunu denetlemek için aşağıdaki C# programını kullanabiliriz:</span><span class="sxs-lookup"><span data-stu-id="d4f33-111">To check that this is the case, we can use the following C# program:</span></span>

```csharp 
var config = new QCTraceSimulatorConfiguration();
config.useWidthCounter = true;
var sim = new QCTraceSimulator(config);
int totalNumberOfQubits = 5;
var res = ApplyMultiControlledX.Run(sim, totalNumberOfQubits).Result;

double allocatedQubits = 
    sim.GetMetric<Primitive.X, ApplyMultiControlledX>(
        WidthCounter.Metrics.ExtraWidth,
        functor: OperationFunctor.Controlled); 

double inputWidth =
    sim.GetMetric<Primitive.X, ApplyMultiControlledX>(
        WidthCounter.Metrics.InputWidth,
        functor: OperationFunctor.Controlled);
```

<span data-ttu-id="d4f33-112">Programın ilk kısmı yürütülür `ApplyMultiControlledX` .</span><span class="sxs-lookup"><span data-stu-id="d4f33-112">The first part of the program executes `ApplyMultiControlledX`.</span></span> <span data-ttu-id="d4f33-113">İkinci bölümde, `QCTraceSimulator.GetMetric` ayrılan qubits sayısını ve denetlenen qubits sayısını ve denetim girişi olarak almak için yöntemini kullanırız `X` .</span><span class="sxs-lookup"><span data-stu-id="d4f33-113">In the second part we use the method `QCTraceSimulator.GetMetric` to get the number of allocated qubits as well as the number of qubits that Controlled `X` received as input.</span></span> 

<span data-ttu-id="d4f33-114">Son olarak, Width sayacı tarafından toplanan tüm istatistikleri CSV biçiminde çıkarmak için aşağıdakileri kullanabilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="d4f33-114">Finally, to output all the statistics collected by width counter in CSV format we can use the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.widthCounter];
```

## <a name="see-also"></a><span data-ttu-id="d4f33-115">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="d4f33-115">See also</span></span> ##

- <span data-ttu-id="d4f33-116">Hisse bilgisayar [Izleme simülatörü](xref:microsoft.quantum.machines.qc-trace-simulator.intro) genel bakış.</span><span class="sxs-lookup"><span data-stu-id="d4f33-116">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
