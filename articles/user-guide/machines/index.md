---
title: Kuantum simülatörleri ve Q# programları
description: Q# programları için hedef makineler olarak kullanılabilen kuantum simülatörlerini açıklar.
author: QuantumWriter
ms.author: v-benbra
ms.date: 6/17/2020
ms.topic: conceptual
uid: microsoft.quantum.machines
no-loc:
- Q#
- $$v
ms.openlocfilehash: 408c636d5383cf594e7ebec6ab2edd66e20ffb82
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858778"
---
# <a name="quantum-simulators"></a><span data-ttu-id="8ba59-103">Kuantum simülatörleri</span><span class="sxs-lookup"><span data-stu-id="8ba59-103">Quantum simulators</span></span>

<span data-ttu-id="8ba59-104">Kuantum simülatörleri, klasik bilgisayarlarda çalışıp bir Q# programı için *hedef makine* işlevi görerek, kubitlerin farklı işlemlere nasıl tepki vereceğini tahmin eden bir ortamda kuantum programları çalıştırıp test etmeyi mümkün hale getiren yazılım programlarıdır.</span><span class="sxs-lookup"><span data-stu-id="8ba59-104">Quantum simulators are software programs that run on classical computers and act as the *target machine* for a Q# program, making it possible to run and test quantum programs in an environment that predicts how qubits will react to different operations.</span></span> <span data-ttu-id="8ba59-105">Bu makalede, Quantum geliştirme seti’ne (QDK) dahil edilen kuantum simülatörleri ve bir Q# programını kuantum simülatörlerine geçirmenin farklı yolları (örneğin komut satırı aracılığıyla veya klasik bir dilde yazılmış sürücü kodunun kullanılması gibi) açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="8ba59-105">This article describes which quantum simulators are included with the Quantum Development Kit (QDK), and different ways that you can pass a Q# program to the quantum simulators, for example, via the command line or by using driver code written in a classical language.</span></span>  



## <a name="the-quantum-development-kit-qdk-quantum-simulators"></a><span data-ttu-id="8ba59-106">Quantum geliştirme seti (QDK) kuantum simülatörleri</span><span class="sxs-lookup"><span data-stu-id="8ba59-106">The Quantum Development Kit (QDK) quantum simulators</span></span>

<span data-ttu-id="8ba59-107">Kuantum simülatörü, algoritma için kuantum temel elemanlarının uygulanmasını sağlamaktan sorumludur.</span><span class="sxs-lookup"><span data-stu-id="8ba59-107">The quantum simulator is responsible for providing implementations of quantum primitives for an algorithm.</span></span> <span data-ttu-id="8ba59-108">Buna `H`, `CNOT` ve `Measure` gibi temel eleman işlemlerinin yanı sıra kubit yönetimi ve izlemesi de dahildir.</span><span class="sxs-lookup"><span data-stu-id="8ba59-108">This includes primitive operations such as `H`, `CNOT`, and `Measure`, as well as qubit management and tracking.</span></span> <span data-ttu-id="8ba59-109">QDK, aynı kuantum algoritması için farklı simülasyon yöntemlerini temsil eden farklı kuantum simülatörü sınıflarını içerir.</span><span class="sxs-lookup"><span data-stu-id="8ba59-109">The QDK includes different classes of quantum simulators representing different ways of simulating the same quantum algorithm.</span></span> 


<span data-ttu-id="8ba59-110">Her kuantum simülatörü türü, bu temel elemanların farklı uygulamalarını sağlayabilir.</span><span class="sxs-lookup"><span data-stu-id="8ba59-110">Each type of quantum simulator can provide different implementations of these primitives.</span></span> <span data-ttu-id="8ba59-111">Örneğin, [tam durum simülatörü](xref:microsoft.quantum.machines.full-state-simulator), [kuantum durum vektörünün](xref:microsoft.quantum.glossary#quantum-state) tam simülasyonunu yaparak kuantum algoritmasını çalıştırırken, [kuantum bilgisayar izleme simülatörü](xref:microsoft.quantum.machines.qc-trace-simulator.intro) gerçek kuantum durumunu değerlendirmez.</span><span class="sxs-lookup"><span data-stu-id="8ba59-111">For example, the [full state simulator](xref:microsoft.quantum.machines.full-state-simulator) runs the quantum algorithm by fully simulating the [quantum state vector](xref:microsoft.quantum.glossary#quantum-state), whereas the [quantum computer trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) doesn't consider the actual quantum state at all.</span></span> <span data-ttu-id="8ba59-112">Bunun yerine algoritmaya ait geçit, kuantum bit ve diğer kaynak kullanımını izler.</span><span class="sxs-lookup"><span data-stu-id="8ba59-112">Rather, it tracks gate, qubit, and other resource usage for the algorithm.</span></span>

### <a name="quantum-machine-classes"></a><span data-ttu-id="8ba59-113">Kuantum makine sınıfları</span><span class="sxs-lookup"><span data-stu-id="8ba59-113">Quantum machine classes</span></span>

<span data-ttu-id="8ba59-114">Gelecekte QDK, diğer simülasyon türlerini ve kuantum donanım üzerinde çalıştırmayı destekleyen başka kuantum makine sınıfları tanımlayacak.</span><span class="sxs-lookup"><span data-stu-id="8ba59-114">In the future, the QDK will define additional quantum machine classes to support other types of simulation and to support running on quantum hardware.</span></span> <span data-ttu-id="8ba59-115">Temel alınan makine uygulamasını değiştirirken algoritmanın sabit kalmasına izin vermek, simülasyondaki bir algoritmayı test etme ve hata ayıklama işlemlerini kolaylaştırır ve sonra algoritmanın değişmediğinden emin olarak gerçek donanım üzerinde rahatça çalıştırılır.</span><span class="sxs-lookup"><span data-stu-id="8ba59-115">Allowing the algorithm to stay constant while varying the underlying machine implementation makes it easy to test and debug an algorithm in simulation and then run it on real hardware with confidence that the algorithm hasn't changed.</span></span>

<span data-ttu-id="8ba59-116">QDK, hepsi `Microsoft.Quantum.Simulation.Simulators` ad alanında tanımlanan çeşitli kuantum makine sınıfları içerir.</span><span class="sxs-lookup"><span data-stu-id="8ba59-116">The QDK includes several quantum machine classes, all defined in the `Microsoft.Quantum.Simulation.Simulators` namespace.</span></span>

|<span data-ttu-id="8ba59-117">Simülatör</span><span class="sxs-lookup"><span data-stu-id="8ba59-117">Simulator</span></span> |<span data-ttu-id="8ba59-118">Sınıf</span><span class="sxs-lookup"><span data-stu-id="8ba59-118">Class</span></span>|<span data-ttu-id="8ba59-119">Açıklama</span><span class="sxs-lookup"><span data-stu-id="8ba59-119">Description</span></span>|
|-----|------|---|
|[<span data-ttu-id="8ba59-120">Tam durum simülatörü</span><span class="sxs-lookup"><span data-stu-id="8ba59-120">Full state simulator</span></span>](xref:microsoft.quantum.machines.full-state-simulator)| `QuantumSimulator` | <span data-ttu-id="8ba59-121">Kuantum algoritmalarını çalıştırıp bunların hatalarını ayıklar ve yaklaşık 30 kubitle sınırlıdır.</span><span class="sxs-lookup"><span data-stu-id="8ba59-121">Runs and debugs quantum algorithms, and is limited to about 30 qubits.</span></span> |
|[<span data-ttu-id="8ba59-122">Basit kaynak tahmin aracı</span><span class="sxs-lookup"><span data-stu-id="8ba59-122">Simple resources estimator</span></span>](xref:microsoft.quantum.machines.resources-estimator)| `ResourcesEstimator` | <span data-ttu-id="8ba59-123">Bir kuantum algoritmasını çalıştırmak için gereken kaynakların üst düzey analizini gerçekleştirir ve binlerce kubiti destekler.</span><span class="sxs-lookup"><span data-stu-id="8ba59-123">Performs a top level analysis of the resources needed to run a quantum algorithm, and supports thousands of qubits.</span></span>|
|[<span data-ttu-id="8ba59-124">İzleme tabanlı kaynak tahmin aracı</span><span class="sxs-lookup"><span data-stu-id="8ba59-124">Trace-based resource estimator</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.intro)|  `QCTraceSimulator` |<span data-ttu-id="8ba59-125">Algoritmanın tüm çağrı grafı için kaynak tüketiminin gelişmiş analizini çalıştırır ve binlerce kubiti destekler.</span><span class="sxs-lookup"><span data-stu-id="8ba59-125">Runs advanced analysis of resources consumptions for the algorithm's entire call-graph, and supports thousands of qubits.</span></span>|
|[<span data-ttu-id="8ba59-126">Toffoli simülatörü</span><span class="sxs-lookup"><span data-stu-id="8ba59-126">Toffoli simulator</span></span>](xref:microsoft.quantum.machines.toffoli-simulator)| `ToffoliSimulator` |<span data-ttu-id="8ba59-127">`X`, `CNOT` ve çok denetimli `X` kuantum işlemleriyle sınırlı olan kuantum algoritmalarının simülasyonunu yapar ve milyonlarca kubiti destekler.</span><span class="sxs-lookup"><span data-stu-id="8ba59-127">Simulates quantum algorithms that are limited to `X`, `CNOT`, and multi-controlled `X` quantum operations, and supports million of qubits.</span></span> |

## <a name="invoking-the-quantum-simulator"></a><span data-ttu-id="8ba59-128">Kuantum simülatörünü çağırma</span><span class="sxs-lookup"><span data-stu-id="8ba59-128">Invoking the quantum simulator</span></span>

<span data-ttu-id="8ba59-129">[Q# programı çalıştırmanın yolları](xref:microsoft.quantum.guide.host-programs) bölümünde, Q# kodunu kuantum simülatörüne geçirmenin üç yolu gösterilmektedir:</span><span class="sxs-lookup"><span data-stu-id="8ba59-129">In [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs), three ways of passing the Q# code to the quantum simulator are demonstrated:</span></span> 

* <span data-ttu-id="8ba59-130">Komut satırını girme</span><span class="sxs-lookup"><span data-stu-id="8ba59-130">Using the command line</span></span>
* <span data-ttu-id="8ba59-131">Python konak programı kullanma</span><span class="sxs-lookup"><span data-stu-id="8ba59-131">Using a Python host program</span></span>
* <span data-ttu-id="8ba59-132">C# konak programı kullanma</span><span class="sxs-lookup"><span data-stu-id="8ba59-132">Using a C# host program</span></span>

<span data-ttu-id="8ba59-133">Kuantum makineler normal .NET sınıfı örnekleridir, bu nedenle herhangi bir .NET sınıfı gibi oluşturucularını çağırarak oluşturulurlar.</span><span class="sxs-lookup"><span data-stu-id="8ba59-133">Quantum machines are instances of normal .NET classes, so they are created by invoking their constructor, just like any .NET class.</span></span> <span data-ttu-id="8ba59-134">Bunu yapma şekliniz, Q# programını nasıl çalıştırdığınıza bağlıdır.</span><span class="sxs-lookup"><span data-stu-id="8ba59-134">How you do this depends on how you run the Q# program.</span></span>

## <a name="next-steps"></a><span data-ttu-id="8ba59-135">Sonraki adımlar</span><span class="sxs-lookup"><span data-stu-id="8ba59-135">Next steps</span></span>

* <span data-ttu-id="8ba59-136">Farklı ortamlarda Q# programlarına yönelik hedef makineleri çağırma hakkındaki ayrıntılar için bkz. [Q# programı çalıştırmanın yolları](xref:microsoft.quantum.guide.host-programs).</span><span class="sxs-lookup"><span data-stu-id="8ba59-136">For details about how to invoke target machines for Q# programs in different environments, see [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>
