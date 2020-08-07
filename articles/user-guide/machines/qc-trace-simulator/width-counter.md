---
title: Genişlik sayacı-hisse geliştirme seti
description: Bir programdaki işlemler tarafından ayrılan ve ödünç alınan qubits sayısını saymak için hisse izi simülatörü kullanan Microsoft QDK genişlik sayacı hakkında bilgi edinin Q# .
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.width-counter
no-loc:
- Q#
- $$v
ms.openlocfilehash: 02f4937aaccf7bf49d6450355c6b42b273071b2e
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868211"
---
# <a name="quantum-trace-simulator-width-counter"></a><span data-ttu-id="1613a-103">Hisse izleme simülatörü: Genişlik sayacı</span><span class="sxs-lookup"><span data-stu-id="1613a-103">Quantum trace simulator: width counter</span></span>

<span data-ttu-id="1613a-104">Genişlik sayacı, hisse Geliştirme Seti [hisse izleyici benzeticisinin](xref:microsoft.quantum.machines.qc-trace-simulator.intro)bir parçasıdır.</span><span class="sxs-lookup"><span data-stu-id="1613a-104">The width counter is a part of the Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="1613a-105">Bu işlemi, bir programdaki her bir işlem tarafından ayrılan ve ödünç alınan qubits sayısını saymak için kullanabilirsiniz Q# .</span><span class="sxs-lookup"><span data-stu-id="1613a-105">You can use it to count the number of qubits allocated and borrowed by each operation in a Q# program.</span></span> <span data-ttu-id="1613a-106">Bazı temel işlemler ek qubit ayırabilir, örneğin, denetlenen `X` işlemleri veya denetlenen işlemleri de çarpır `T` .</span><span class="sxs-lookup"><span data-stu-id="1613a-106">Some primitive operations can allocate extra qubits, for example, multiply controlled `X` operations or controlled `T` operations.</span></span>

## <a name="invoking-the-width-counter"></a><span data-ttu-id="1613a-107">Genişlik sayacını çağırma</span><span class="sxs-lookup"><span data-stu-id="1613a-107">Invoking the width counter</span></span>

<span data-ttu-id="1613a-108">Hisse izi izleme simülatörünü Width sayacından çalıştırmak için bir <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> örnek oluşturmanız, özelliği true olarak ayarlamanız `UseWidthCounter` ve sonra **true** <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> parametresi olarak ile yeni bir örnek oluşturmanız gerekir `QCTraceSimulatorConfiguration` .</span><span class="sxs-lookup"><span data-stu-id="1613a-108">To run the quantum trace simulator with the width counter, you must create a <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instance, set the `UseWidthCounter` property to **true**, and then create a new <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instance with the `QCTraceSimulatorConfiguration` as the parameter.</span></span> 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseWidthCounter = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-width-counter-in-a-c-host-program"></a><span data-ttu-id="1613a-109">C# ana programında Width sayacını kullanma</span><span class="sxs-lookup"><span data-stu-id="1613a-109">Using the width counter in a C# host program</span></span>

<span data-ttu-id="1613a-110">Bu bölümde aşağıdaki C# örneği, <xref:microsoft.quantum.intrinsic.x> Aşağıdaki örnek koda bağlı olarak, çarpma denetimli bir işlemin uygulanmasıyla ayrılan ek qubits sayısını hesaplar Q# :</span><span class="sxs-lookup"><span data-stu-id="1613a-110">The C# example that follows in this section computes the number of extra qubits allocated by the implementation of a multiply controlled <xref:microsoft.quantum.intrinsic.x> operation, based on the following Q# sample code:</span></span>

```qsharp
open Microsoft.Quantum.Intrinsic;
open Microsoft.Quantum.Arrays;
operation ApplyMultiControlledX( numberOfQubits : Int ) : Unit {
    using(qubits = Qubit[numberOfQubits]) {
        Controlled X (Rest(qubits), Head(qubits));
    } 
}
```

<span data-ttu-id="1613a-111">Çarpma kontrollü <xref:microsoft.quantum.intrinsic.x> işlemi, toplam beş qubit üzerinde çalışır, iki [anyaya bitleri](xref:microsoft.quantum.glossary#ancilla)ayırır ve bir giriş genişliğine **5**sahiptir.</span><span class="sxs-lookup"><span data-stu-id="1613a-111">The multiply controlled <xref:microsoft.quantum.intrinsic.x> operation acts on a total of five qubits, allocates two [ancillary qubits](xref:microsoft.quantum.glossary#ancilla), and has an input width of **5**.</span></span> <span data-ttu-id="1613a-112">Sayıları doğrulamak için aşağıdaki C# programını kullanın:</span><span class="sxs-lookup"><span data-stu-id="1613a-112">Use the following C# program to verify the counts:</span></span>

```csharp 
var config = new QCTraceSimulatorConfiguration();
config.UseWidthCounter = true;
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

<span data-ttu-id="1613a-113">Programın ilk kısmı `ApplyMultiControlledX` işlemi çalıştırır.</span><span class="sxs-lookup"><span data-stu-id="1613a-113">The first part of the program runs the `ApplyMultiControlledX` operation.</span></span> <span data-ttu-id="1613a-114">İkinci bölüm, [`QCTraceSimulator.GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) ayrılan qubits sayısını ve `Controlled X` işlemin girdi olarak aldığı qubit sayısını almak için yöntemini kullanır.</span><span class="sxs-lookup"><span data-stu-id="1613a-114">The second part uses the [`QCTraceSimulator.GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) method to retrieve the number of allocated qubits as well as the number of qubits that the `Controlled X` operation received as input.</span></span> 

<span data-ttu-id="1613a-115">Son olarak, aşağıdaki şekilde, Genişlik sayacı tarafından toplanan tüm istatistiklerin CSV biçiminde çıktısını alabilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="1613a-115">Finally, you can output all the statistics collected by the width counter in CSV format using the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.widthCounter];
```

## <a name="see-also"></a><span data-ttu-id="1613a-116">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="1613a-116">See also</span></span>

- <span data-ttu-id="1613a-117">Hisse Geliştirme Seti [hisse izi simülatörü](xref:microsoft.quantum.machines.qc-trace-simulator.intro) genel bakış.</span><span class="sxs-lookup"><span data-stu-id="1613a-117">The Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
- <span data-ttu-id="1613a-118"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator>API başvurusu.</span><span class="sxs-lookup"><span data-stu-id="1613a-118">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API reference.</span></span>
- <span data-ttu-id="1613a-119"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>API başvurusu.</span><span class="sxs-lookup"><span data-stu-id="1613a-119">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API reference.</span></span>
- <span data-ttu-id="1613a-120"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.MetricsNames.WidthCounter>API başvurusu.</span><span class="sxs-lookup"><span data-stu-id="1613a-120">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.MetricsNames.WidthCounter> API reference.</span></span>
