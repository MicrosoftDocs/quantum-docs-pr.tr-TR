---
title: Genişlik sayacı
description: Bir hisse içindeki her işlem tarafından ayrılan ve ödünç alınan qubits sayısını sayan Microsoft QDK genişlik sayacı hakkında bilgi edinin.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.width-counter
ms.openlocfilehash: a76292222950310acc90dded02980e4a5b792e76
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907095"
---
# <a name="width-counter"></a><span data-ttu-id="29dba-103">Genişlik sayacı</span><span class="sxs-lookup"><span data-stu-id="29dba-103">Width Counter</span></span>

<span data-ttu-id="29dba-104">`Width Counter`, her bir işlem tarafından ayrılan ve ödünç alınan qubits sayısını sayar.</span><span class="sxs-lookup"><span data-stu-id="29dba-104">The `Width Counter` counts the number of qubits allocated and borrowed by each operation.</span></span>
<span data-ttu-id="29dba-105">`Microsoft.Quantum.Intrinsic` ad alanındaki tüm işlemler, tek qubit ifade, T kapıları, tek qubit Clienfford kapıları, CNOT kapıları ve Multi-qubitpauli gözlemlenenler ölçümleri bakımından ifade edilir.</span><span class="sxs-lookup"><span data-stu-id="29dba-105">All operations from the `Microsoft.Quantum.Intrinsic` namespace are expressed in terms of single qubit rotations, T gates, single qubit Clifford gates, CNOT gates and measurements of multi-qubit Pauli observables.</span></span> <span data-ttu-id="29dba-106">Temel işlemlerden bazıları ek qubit ayırabilirler.</span><span class="sxs-lookup"><span data-stu-id="29dba-106">Some of the primitive operations can allocate extra qubits.</span></span> <span data-ttu-id="29dba-107">Örneğin, denetlenen `X` kapıları veya denetimli `T` kapıları çarpın.</span><span class="sxs-lookup"><span data-stu-id="29dba-107">For example, multiply controlled `X` gates or controlled `T` gates.</span></span> <span data-ttu-id="29dba-108">Çarpma denetimli bir `X` kapısı uygulamasına göre ayrılan ekstra qubits sayısını hesaplamıza izin verin:</span><span class="sxs-lookup"><span data-stu-id="29dba-108">Let us compute the number of extra qubits allocated by the implementation of a multiply controlled `X` gate:</span></span>

```qsharp
open Microsoft.Quantum.Intrinsic;
open Microsoft.Quantum.Arrays;
operation ApplyMultiControlledX( numberOfQubits : Int ) : Unit {
    using(qubits = Qubit[numberOfQubits]) {
        Controlled X (Rest(qubits), Head(qubits));
    } 
}
```

## <a name="using-width-counter-within-a-c-program"></a><span data-ttu-id="29dba-109">Bir C# program Içinde Width sayacını kullanma</span><span class="sxs-lookup"><span data-stu-id="29dba-109">Using Width Counter within a C# Program</span></span>

<span data-ttu-id="29dba-110">Toplam 5 qubit üzerinde çalışan denetlenen `X` çarpıp 2 anyacal ve giriş genişliği 5 olur.</span><span class="sxs-lookup"><span data-stu-id="29dba-110">Multiply controlled `X` acting on a total of 5 qubits will allocate 2 ancillary qubits and its input width will be 5.</span></span> <span data-ttu-id="29dba-111">Bu durumun bu olduğunu denetlemek için aşağıdaki C# programı kullanabiliriz:</span><span class="sxs-lookup"><span data-stu-id="29dba-111">To check that this is the case, we can use the following C# program:</span></span>

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

<span data-ttu-id="29dba-112">Programın ilk kısmı `ApplyMultiControlledX`yürütür.</span><span class="sxs-lookup"><span data-stu-id="29dba-112">The first part of the program executes `ApplyMultiControlledX`.</span></span> <span data-ttu-id="29dba-113">İkinci bölümde, ayrılan qubits sayısını ve denetlenen `X` girdi olarak aldığı qubits sayısını almak için yöntemini `QCTraceSimulator.GetMetric` kullanırız.</span><span class="sxs-lookup"><span data-stu-id="29dba-113">In the second part we use the method `QCTraceSimulator.GetMetric` to get the number of allocated qubits as well as the number of qubits that Controlled `X` received as input.</span></span> 

<span data-ttu-id="29dba-114">Son olarak, Width sayacı tarafından toplanan tüm istatistikleri CSV biçiminde çıkarmak için aşağıdakileri kullanabilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="29dba-114">Finally, to output all the statistics collected by width counter in CSV format we can use the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.widthCounter];
```

## <a name="see-also"></a><span data-ttu-id="29dba-115">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="29dba-115">See also</span></span> ##

- <span data-ttu-id="29dba-116">Hisse bilgisayar [Izleme simülatörü](xref:microsoft.quantum.machines.qc-trace-simulator.intro) genel bakış.</span><span class="sxs-lookup"><span data-stu-id="29dba-116">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
