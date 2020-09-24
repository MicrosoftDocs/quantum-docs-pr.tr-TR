---
title: Kuantum izleme simülatörü - Quantum geliştirme seti
description: Klasik kodda hata ayıklamak ve bir Q# programının kaynak gereksinimlerini tahmin etmek için Microsoft kuantum bilgisayarı izleme simülatörünü nasıl kullanacağınızı öğrenin.
author: vadym-kl
ms.author: vadym
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.intro
no-loc:
- Q#
- $$v
ms.openlocfilehash: 54a1f63461cfcc8146f7dc4d18d321238d77454d
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/21/2020
ms.locfileid: "90833363"
---
# <a name="microsoft-quantum-development-kit-qdk-quantum-trace-simulator"></a><span data-ttu-id="e8809-103">Microsoft Quantum geliştirme seti (QDK) kuantum izleme simülatörü</span><span class="sxs-lookup"><span data-stu-id="e8809-103">Microsoft Quantum Development Kit (QDK) quantum trace simulator</span></span>

<span data-ttu-id="e8809-104">QDK <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> sınıfı, bir kuantum bilgisayarı durumunun gerçekten simülasyonunu yapmadan kuantum programı çalıştırır.</span><span class="sxs-lookup"><span data-stu-id="e8809-104">The QDK <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> class runs a quantum program without actually simulating the state of a quantum computer.</span></span> <span data-ttu-id="e8809-105">Bu nedenle, kuantum izleme simülatörü binlerce kubit kullanan kuantum programlarını çalıştırabilir.</span><span class="sxs-lookup"><span data-stu-id="e8809-105">For this reason, the quantum trace simulator is able to run quantum programs that use thousands of qubits.</span></span>  <span data-ttu-id="e8809-106">İki ana amaç için yararlıdır:</span><span class="sxs-lookup"><span data-stu-id="e8809-106">It is useful for two main purposes:</span></span> 

* <span data-ttu-id="e8809-107">Kuantum programının parçası olan klasik kodun hatalarını ayıklamak.</span><span class="sxs-lookup"><span data-stu-id="e8809-107">Debugging classical code that is part of a quantum program.</span></span> 
* <span data-ttu-id="e8809-108">Kuantum programının belirli bir örneğini bir kuantum bilgisayarında çalıştırmak için gereken kaynakları tahmin etmek.</span><span class="sxs-lookup"><span data-stu-id="e8809-108">Estimating the resources required to run a given instance of a quantum program on a quantum computer.</span></span> <span data-ttu-id="e8809-109">Dahası, çok daha sınırlı bir ölçüm kümesi sağlayan [Kaynak tahmin aracı](xref:microsoft.quantum.machines.resources-estimator), izleme simülatörünü temel almıştır.</span><span class="sxs-lookup"><span data-stu-id="e8809-109">In fact, the [Resources estimator](xref:microsoft.quantum.machines.resources-estimator), which provides a more limited set of metrics, is built upon the trace simulator.</span></span>

## <a name="invoking-the-quantum-trace-simulator"></a><span data-ttu-id="e8809-110">Kuantum izleme simülatörünü çağırma</span><span class="sxs-lookup"><span data-stu-id="e8809-110">Invoking the quantum trace simulator</span></span>

<span data-ttu-id="e8809-111">Tüm Q# işlemlerini çalıştırmak için kuantum izleme simülatörünü kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e8809-111">You can use the quantum trace simulator to run any Q# operation.</span></span>

<span data-ttu-id="e8809-112">Diğer hedef makinelerde olduğu gibi, önce `QCTraceSimulator` sınıfının bir örneğini oluşturup ardından bunu bir işlemin `Run` metodunun ilk parametresi olarak geçirirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e8809-112">As with other target machines, you first create an instance of the `QCTraceSimulator` class and then pass it as the first parameter of an operation's `Run` method.</span></span>

<span data-ttu-id="e8809-113">`QuantumSimulator` sınıfının aksine, `QCTraceSimulator` sınıfının <xref:System.IDisposable> arabirimini uygulamadığını ve bu nedenle bunu bir `using` deyimi içine almanız gerekmediğini unutmayın.</span><span class="sxs-lookup"><span data-stu-id="e8809-113">Note that, unlike the `QuantumSimulator` class, the `QCTraceSimulator` class does not implement the <xref:System.IDisposable> interface, and thus you do not need to enclose it within a `using` statement.</span></span>

```csharp
using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;
using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;

namespace Quantum.MyProgram
{
    class Driver
    {
        static void Main(string[] args)
        {
            QCTraceSimulator sim = new QCTraceSimulator();
            var res = MyQuantumProgram.Run(sim).Result;
            System.Console.WriteLine("Press any key to continue...");
            System.Console.ReadKey();
        }
    }
}
```

## <a name="providing-the-probability-of-measurement-outcomes"></a><span data-ttu-id="e8809-114">Ölçüm sonuçlarının olasılığını sağlama</span><span class="sxs-lookup"><span data-stu-id="e8809-114">Providing the probability of measurement outcomes</span></span>

<span data-ttu-id="e8809-115">Kuantum izleme simülatörü gerçek kuantum durumunun simülasyonunu yapmadığından, işlem içindeki ölçüm sonuçlarının olasılığını hesaplayamaz.</span><span class="sxs-lookup"><span data-stu-id="e8809-115">Because the quantum trace simulator does not simulate the actual quantum state, it cannot calculate the probability of measurement outcomes within an operation.</span></span> 

<span data-ttu-id="e8809-116">Bu nedenle, bir işlem ölçüm içeriyorsa, <xref:microsoft.quantum.diagnostics> ad alanındaki <xref:microsoft.quantum.diagnostics.assertmeasurementprobability> işlemini kullanarak bu olasılıkları açıkça sağlamanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="e8809-116">Therefore, if an operation includes measurements, you must explicitly provide these probabilities using the <xref:microsoft.quantum.diagnostics.assertmeasurementprobability> operation from the <xref:microsoft.quantum.diagnostics> namespace.</span></span> <span data-ttu-id="e8809-117">Aşağıdaki örnekte bu gösterilmektedir:</span><span class="sxs-lookup"><span data-stu-id="e8809-117">The following example illustrates this:</span></span>

```qsharp
operation TeleportQubit(source : Qubit, target : Qubit) : Unit {
    using (qubit = Qubit()) {
        H(qubit);
        CNOT(qubit, target);
        CNOT(source, qubit);
        H(source);

        AssertMeasurementProbability([PauliZ], [source], Zero, 0.5, "Outcomes must be equally likely", 1e-5);
        AssertMeasurementProbability([PauliZ], [q], Zero, 0.5, "Outcomes must be equally likely", 1e-5);

        if (M(source) == One)  { Z(target); X(source); }
        if (M(q) == One) { X(target); X(q); }
    }
}
```

<span data-ttu-id="e8809-118">Kuantum izleme simülatörü `AssertMeasurementProbability` ile karşılaştığında, bu `PauliZ` ölçümünü `source` üzerine kaydeder ve `q`, **0,5** olasılıkla `Zero` sonucunu vermelidir.</span><span class="sxs-lookup"><span data-stu-id="e8809-118">When the quantum trace simulator encounters `AssertMeasurementProbability` it records that measuring `PauliZ` on `source` and `q` should give an outcome of `Zero`, with probability **0.5**.</span></span> <span data-ttu-id="e8809-119">Daha sonra `M` işlemini çalıştırdığında, sonuç olasılıklarının kayıtlı değerlerini bulur ve `M`, **0,5** olasılıkla `Zero` veya `One` döndürür.</span><span class="sxs-lookup"><span data-stu-id="e8809-119">When it runs the `M` operation later, it finds the recorded values of the outcome probabilities, and `M` returns `Zero` or `One`, with probability **0.5**.</span></span> <span data-ttu-id="e8809-120">Aynı kod, kuantum durumunu takip eden bir simülatör üzerinde çalıştırıldığında, bu simülatör `AssertMeasurementProbability` içinde belirtilen olasılıkların doğru olup olmadığını kontrol eder.</span><span class="sxs-lookup"><span data-stu-id="e8809-120">When the same code runs on a simulator that keeps track of the quantum state, that simulator checks that the provided probabilities in `AssertMeasurementProbability` are correct.</span></span>

<span data-ttu-id="e8809-121">`AssertMeasurementProbability` kullanılarak not eklenmemiş en az bir ölçüm işlemi varsa, simülatörün [`UnconstrainedMeasurementException`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.unconstrainedmeasurementexception) sonucunu verdiğini unutmayın.</span><span class="sxs-lookup"><span data-stu-id="e8809-121">Note that if there is at least one measurement operation that is not annotated using `AssertMeasurementProbability`, the simulator throws an [`UnconstrainedMeasurementException`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.unconstrainedmeasurementexception).</span></span>

## <a name="quantum-trace-simulator-tools"></a><span data-ttu-id="e8809-122">Kuantum izleme simülatörü araçları</span><span class="sxs-lookup"><span data-stu-id="e8809-122">Quantum trace simulator tools</span></span>

<span data-ttu-id="e8809-123">QDK, programlarınızda hata algılamak ve kuantum programı kaynak tahminleri gerçekleştirmek için kuantum izleme simülatörü ile kullanabileceğiniz beş araç içerir:</span><span class="sxs-lookup"><span data-stu-id="e8809-123">The QDK includes five tools that you can use with the quantum trace simulator to detect bugs in your programs and perform quantum program resource estimates:</span></span> 

|<span data-ttu-id="e8809-124">Araç</span><span class="sxs-lookup"><span data-stu-id="e8809-124">Tool</span></span> | <span data-ttu-id="e8809-125">Açıklama</span><span class="sxs-lookup"><span data-stu-id="e8809-125">Description</span></span> |
|-----| -----|
|[<span data-ttu-id="e8809-126">Ayrı giriş denetleyicisi</span><span class="sxs-lookup"><span data-stu-id="e8809-126">Distinct inputs checker</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs) |<span data-ttu-id="e8809-127">Paylaşılan kubitlerle olası çakışmaları denetler</span><span class="sxs-lookup"><span data-stu-id="e8809-127">Checks for potential conflicts with shared qubits</span></span> |
|[<span data-ttu-id="e8809-128">Geçersiz kılınan kubit kullanımı denetleyicisi</span><span class="sxs-lookup"><span data-stu-id="e8809-128">Invalidated qubits use checker</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits)  |<span data-ttu-id="e8809-129">Programın zaten yayınlanmış olan bir kubite işlem uygulayıp uygulamadığını denetler</span><span class="sxs-lookup"><span data-stu-id="e8809-129">Checks if the program applies an operation to a qubit that is already released</span></span> |
|[<span data-ttu-id="e8809-130">Temel işlem sayacı</span><span class="sxs-lookup"><span data-stu-id="e8809-130">Primitive operations counter</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.primitive-counter)  | <span data-ttu-id="e8809-131">Kuantum programında çağrılan her işlem tarafından kullanılan temel işleme sayısını verir</span><span class="sxs-lookup"><span data-stu-id="e8809-131">Counts the number of primitive processes used by every operation invoked in a quantum program</span></span>  |
|[<span data-ttu-id="e8809-132">Derinlik sayacı</span><span class="sxs-lookup"><span data-stu-id="e8809-132">Depth counter</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter)  |<span data-ttu-id="e8809-133">Kuantum programında çağrılan her işlemin derinlik alt sınırını temsil eden sayıları toplar</span><span class="sxs-lookup"><span data-stu-id="e8809-133">Gathers counts that represent the lower bound of the depth of every operation invoked in a quantum program</span></span>   |
|[<span data-ttu-id="e8809-134">Genişlik sayacı</span><span class="sxs-lookup"><span data-stu-id="e8809-134">Width counter</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter)  |<span data-ttu-id="e8809-135">Kuantum programında her işlem tarafından ayrılan ve ödünç alınan kubit sayısını verir</span><span class="sxs-lookup"><span data-stu-id="e8809-135">Counts the number of qubits allocated and borrowed by each operation in a quantum program</span></span> |

<span data-ttu-id="e8809-136">Bu araçların her biri, `QCTraceSimulatorConfiguration` içinde uygun bayrakların ayarlanması ve sonra yapılandırmanın `QCTraceSimulator` bildirimine geçirilmesiyle etkinleştirilir.</span><span class="sxs-lookup"><span data-stu-id="e8809-136">Each of these tools is enabled by setting appropriate flags in `QCTraceSimulatorConfiguration` and then passing the configuration to the `QCTraceSimulator` declaration.</span></span> <span data-ttu-id="e8809-137">Bu araçların her birini kullanmayla ilgili daha fazla bilgi için önceki listede yer alan bağlantılara bakın.</span><span class="sxs-lookup"><span data-stu-id="e8809-137">For information on using each of these tools, see the links in the preceding list.</span></span> <span data-ttu-id="e8809-138">`QCTraceSimulator` yapılandırması hakkında daha fazla bilgi için bkz. [QCTraceSimulatorConfiguration](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration).</span><span class="sxs-lookup"><span data-stu-id="e8809-138">For more information about configuring `QCTraceSimulator`, see [QCTraceSimulatorConfiguration](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration).</span></span>

## <a name="qctracesimulator-methods"></a><span data-ttu-id="e8809-139">QCTraceSimulator metotları</span><span class="sxs-lookup"><span data-stu-id="e8809-139">QCTraceSimulator methods</span></span>

<span data-ttu-id="e8809-140">`QCTraceSimulator`, bir kuantum işlemi sırasında izlenen ölçümlerin değerlerini almak için birkaç yerleşik metot içerir.</span><span class="sxs-lookup"><span data-stu-id="e8809-140">`QCTraceSimulator` has several built-in methods to retrieve the values of the metrics tracked during a quantum operation.</span></span> <span data-ttu-id="e8809-141">[QCTraceSimulator.GetMetric](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) ve [QCTraceSimulator.ToCSV](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.tocsv) metodu örnekleri, [Temel işlem sayacı](xref:microsoft.quantum.machines.qc-trace-simulator.primitive-counter), [Derinlik sayacı](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter) ve [Genişlik sayacı](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter) makalelerinde bulunabilir.</span><span class="sxs-lookup"><span data-stu-id="e8809-141">Examples of the [QCTraceSimulator.GetMetric](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) and the [QCTraceSimulator.ToCSV](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.tocsv) methods can be found in the [Primitive operations counter](xref:microsoft.quantum.machines.qc-trace-simulator.primitive-counter), [Depth counter](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter), and [Width counter](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter) articles.</span></span> <span data-ttu-id="e8809-142">Kullanılabilir tüm metotlar hakkında daha fazla bilgi için Q# API başvurusundaki [QCTraceSimulator](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) konusuna bakın.</span><span class="sxs-lookup"><span data-stu-id="e8809-142">For more information on all available methods, see [QCTraceSimulator](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) in the Q# API reference.</span></span>  

## <a name="see-also"></a><span data-ttu-id="e8809-143">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="e8809-143">See also</span></span>

- [<span data-ttu-id="e8809-144">Kuantum kaynak tahmin aracı</span><span class="sxs-lookup"><span data-stu-id="e8809-144">Quantum resources estimator</span></span>](xref:microsoft.quantum.machines.resources-estimator)
- [<span data-ttu-id="e8809-145">Kuantum Toffoli simülatörü</span><span class="sxs-lookup"><span data-stu-id="e8809-145">Quantum Toffoli simulator</span></span>](xref:microsoft.quantum.machines.toffoli-simulator)
- [<span data-ttu-id="e8809-146">Kuantum tam durum simülatörü</span><span class="sxs-lookup"><span data-stu-id="e8809-146">Quantum full state simulator</span></span>](xref:microsoft.quantum.machines.full-state-simulator) 