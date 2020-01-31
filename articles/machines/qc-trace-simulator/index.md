---
title: Kuantum bilgisayar izleme simülatörü | Microsoft Docs
description: Kuantum bilgisayar izleme simülatörüne genel bakış
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.intro
ms.openlocfilehash: 929745a6da6034599e97d2f573190308fde6eb75
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820445"
---
# <a name="quantum-trace-simulator"></a><span data-ttu-id="d6414-103">Kuantum İzleme Simülatörü</span><span class="sxs-lookup"><span data-stu-id="d6414-103">Quantum Trace Simulator</span></span>

<span data-ttu-id="d6414-104">Microsoft kuantum bilgisayarı izleme simülatörü, kuantum bilgisayarın durumunu gerçekten taklit etmeden bir kuantum programı yürütür.</span><span class="sxs-lookup"><span data-stu-id="d6414-104">The Microsoft quantum computer trace simulator executes a quantum program without actually simulating the state of a quantum computer.</span></span>  <span data-ttu-id="d6414-105">Bu nedenle, izleme simülatörü binlerce kuantum bit kullanan kuantum programlarını çalıştırabilir.</span><span class="sxs-lookup"><span data-stu-id="d6414-105">For this reason, the trace simulator can execute quantum programs that use thousands of qubits.</span></span>  <span data-ttu-id="d6414-106">İki ana amaç için yararlıdır:</span><span class="sxs-lookup"><span data-stu-id="d6414-106">It is useful for two main purposes:</span></span> 

* <span data-ttu-id="d6414-107">Kuantum programının parçası olan klasik kodun hatalarını ayıklamak.</span><span class="sxs-lookup"><span data-stu-id="d6414-107">Debugging classical code that is part of a quantum program.</span></span> 
* <span data-ttu-id="d6414-108">Kuantum programının belirli bir örneğini bir kuantum bilgisayarında çalıştırmak için gereken kaynakları tahmin etmek.</span><span class="sxs-lookup"><span data-stu-id="d6414-108">Estimating the resources required to run a given instance of a quantum program on a quantum computer.</span></span>

<span data-ttu-id="d6414-109">İzleme simülatörü, ölçümlerin gerçekleştirilmesi gerektiğinde kullanıcı tarafından sağlanan ek bilgileri kullanır.</span><span class="sxs-lookup"><span data-stu-id="d6414-109">The trace simulator relies on additional information provided by the user when measurements must be performed.</span></span> <span data-ttu-id="d6414-110">Bu konu hakkında daha fazla bilgi için [Ölçüm sonuçlarının olasılığını sağlama](#providing-the-probability-of-measurement-outcomes) bölümüne bakın.</span><span class="sxs-lookup"><span data-stu-id="d6414-110">See Section [Providing the probability of measurement outcomes](#providing-the-probability-of-measurement-outcomes) for more details on this.</span></span> 

## <a name="providing-the-probability-of-measurement-outcomes"></a><span data-ttu-id="d6414-111">Ölçüm Sonuçlarının Olasılığını Sağlama</span><span class="sxs-lookup"><span data-stu-id="d6414-111">Providing the Probability of Measurement Outcomes</span></span>

<span data-ttu-id="d6414-112">Kuantum algoritmalarda görünen iki tür ölçüm vardır.</span><span class="sxs-lookup"><span data-stu-id="d6414-112">There are two kinds of measurements that appear in quantum algorithms.</span></span> <span data-ttu-id="d6414-113">İlk tür, kullanıcının genellikle sonuçların olasılığını bildiği bir yardımcı rol oynar.</span><span class="sxs-lookup"><span data-stu-id="d6414-113">The first kind plays an auxiliary role where the user usually knows the probability of the outcomes.</span></span> <span data-ttu-id="d6414-114">Bu durumda kullanıcı, bu bilgileri ifade etmek için <xref:microsoft.quantum.intrinsic> ad alanından <xref:microsoft.quantum.intrinsic.assertprob> yazabilir.</span><span class="sxs-lookup"><span data-stu-id="d6414-114">In this case the user can write <xref:microsoft.quantum.intrinsic.assertprob> from the <xref:microsoft.quantum.intrinsic> namespace to express this knowledge.</span></span> <span data-ttu-id="d6414-115">Aşağıdaki örnekte bu gösterilmektedir:</span><span class="sxs-lookup"><span data-stu-id="d6414-115">The following example illustrates this:</span></span>

```qsharp
operation TeleportQubit(source : Qubit, target : Qubit) : Unit {
    using (qubit = Qubit()) {
        H(qubit);
        CNOT(qubit, target);
        CNOT(source, qubit);
        H(source);

        AssertProb([PauliZ], [source], Zero, 0.5, "Outcomes must be equally likely", 1e-5);
        AssertProb([PauliZ], [q], Zero, 0.5, "Outcomes must be equally likely", 1e-5);

        if (M(source) == One)  { Z(target); X(source); }
        if (M(q) == One) { X(target); X(q); }
    }
}
```

<span data-ttu-id="d6414-116">İzleme simülatörü `AssertProb` yürüttüğünde, bu `PauliZ` ölçümünü `source` üzerine kaydeder ve `q` değerine 0,5 olasılıkla `Zero` sonucu verilmelidir.</span><span class="sxs-lookup"><span data-stu-id="d6414-116">When the trace simulator executes `AssertProb` it will record that measuring `PauliZ` on `source` and `q` should be given an outcome of `Zero` with probability 0.5.</span></span> <span data-ttu-id="d6414-117">Simülatör daha sonra `M` yürüttüğünde, sonuç olasılıklarının kayıtlı değerlerini bulur ve `M` ölçümü 0,5 olasılıkla `Zero` veya `One` döndürür.</span><span class="sxs-lookup"><span data-stu-id="d6414-117">When the simulator executes `M` later, it will find the recorded values of the outcome probabilities and `M` will return `Zero` or `One` with probability 0.5.</span></span> <span data-ttu-id="d6414-118">Aynı kod, kuantum halini takip eden bir simülatör üzerinde yürütüldüğünde, bu simülatör `AssertProb` içinde belirtilen olasılıkların doğru olup olmadığını kontrol eder.</span><span class="sxs-lookup"><span data-stu-id="d6414-118">When the same code is executed on a simulator that keeps track of the quantum state, such a simulator will check that the provided probabilities in `AssertProb` are correct.</span></span>

## <a name="running-your-program-with-the-quantum-computer-trace-simulator"></a><span data-ttu-id="d6414-119">Programınızı Kuantum Bilgisayarı İzleme Simülatörü ile Çalıştırma</span><span class="sxs-lookup"><span data-stu-id="d6414-119">Running your Program with the Quantum Computer Trace Simulator</span></span> 

<span data-ttu-id="d6414-120">Kuantum bilgisayarı izleme simülatörü başka bir hedef makine olarak görüntülenebilir.</span><span class="sxs-lookup"><span data-stu-id="d6414-120">The quantum computer trace simulator may be viewed as just another target machine.</span></span> <span data-ttu-id="d6414-121">Onu kullanmaya yarayan C# sürücü programı ise başka bir kuantum simülatörünün sürücü programına benzer:</span><span class="sxs-lookup"><span data-stu-id="d6414-121">The C# driver program for using it is very similar to the one for any other quantum Simulator:</span></span> 

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
            var res = MyQuantumProgram.Run().Result;
            System.Console.WriteLine("Press any key to continue...");
            System.Console.ReadKey();
        }
    }
}
```

<span data-ttu-id="d6414-122">`AssertProb` kullanılarak not eklenmemiş en az bir ölçüm varsa simülatör `Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators` ad alanından `UnconstrainedMeasurementException` oluşturur.</span><span class="sxs-lookup"><span data-stu-id="d6414-122">Note that if there is at least one measurement not annotated using `AssertProb`, the simulator will throw `UnconstrainedMeasurementException` from the `Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators` namespace.</span></span> <span data-ttu-id="d6414-123">Daha fazla bilgi için [UnconstrainedMeasurementException](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.UnconstrainedMeasurementException) üzerindeki API belgelerine bakın.</span><span class="sxs-lookup"><span data-stu-id="d6414-123">See the API documentation on [UnconstrainedMeasurementException](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.UnconstrainedMeasurementException) for more details.</span></span>

<span data-ttu-id="d6414-124">Kuantum programlarını çalıştırmaya ek olarak, izleme simülatörü programlardaki hataları algılamaya ve kuantum programı kaynak tahminlerini gerçekleştirmeye yönelik beş bileşen içerir:</span><span class="sxs-lookup"><span data-stu-id="d6414-124">In addition to running quantum programs, the trace simulator comes with five components for detecting bugs in programs and performing quantum program resource estimates:</span></span> 

* [<span data-ttu-id="d6414-125">Ayrı Giriş Denetleyicisi</span><span class="sxs-lookup"><span data-stu-id="d6414-125">Distinct Inputs Checker</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs)
* [<span data-ttu-id="d6414-126">Geçersiz Kılınan Kuantum Bit Kullanımı Denetleyicisi</span><span class="sxs-lookup"><span data-stu-id="d6414-126">Invalidated Qubits Use Checker</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits)
* [<span data-ttu-id="d6414-127">Temel İşlem Sayacı</span><span class="sxs-lookup"><span data-stu-id="d6414-127">Primitive Operations Counter</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.primitive-counter)
* [<span data-ttu-id="d6414-128">Devre Derinliği Sayacı</span><span class="sxs-lookup"><span data-stu-id="d6414-128">Circuit Depth Counter</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter)
* [<span data-ttu-id="d6414-129">Devre Genişliği Sayacı</span><span class="sxs-lookup"><span data-stu-id="d6414-129">Circuit Width Counter</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter)

<span data-ttu-id="d6414-130">Bu bileşenlerin her biri, `QCTraceSimulatorConfiguration` içinde uygun bayraklar ayarlanarak etkinleştirilebilir.</span><span class="sxs-lookup"><span data-stu-id="d6414-130">Each of these components may be enabled by setting appropriate flags in `QCTraceSimulatorConfiguration`.</span></span> <span data-ttu-id="d6414-131">Bu bileşenlerin her birini kullanma hakkında daha ayrıntılı bilgi, ilgili başvuru dosyalarında verilmiştir.</span><span class="sxs-lookup"><span data-stu-id="d6414-131">More details about using each of these components are provided in the corresponding reference files.</span></span> <span data-ttu-id="d6414-132">Daha ayrıntılı bilgi için [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration) üzerindeki API belgelerine bakın.</span><span class="sxs-lookup"><span data-stu-id="d6414-132">See the API documentation on [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration) for specific details.</span></span>

## <a name="see-also"></a><span data-ttu-id="d6414-133">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="d6414-133">See also</span></span>
<span data-ttu-id="d6414-134">Kuantum bilgisayar [izleme simülatörü](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) C# başvurusu</span><span class="sxs-lookup"><span data-stu-id="d6414-134">The quantum computer [trace simulator](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) C# reference</span></span> 

