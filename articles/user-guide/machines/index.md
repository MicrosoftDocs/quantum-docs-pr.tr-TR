---
title: Kuantum simülatörleri ve konak uygulamaları | Microsoft Docs
description: Genellikle C# veya Q# olmak üzere klasik bir bilgi işlem .NET dili ile kuantum simülatörleri çalıştırmayı açıklar.
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines
ms.openlocfilehash: 14aed75ed0ed192f88699b1c7dbacfae23f74642
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85273810"
---
# <a name="quantum-simulators-and-host-applications"></a><span data-ttu-id="a31ed-103">Kuantum simülatörleri ve konak uygulamaları</span><span class="sxs-lookup"><span data-stu-id="a31ed-103">Quantum simulators and host applications</span></span>

## <a name="what-youll-learn"></a><span data-ttu-id="a31ed-104">Öğrenecekleriniz</span><span class="sxs-lookup"><span data-stu-id="a31ed-104">What You'll Learn</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="a31ed-105">Kuantum algoritmalar nasıl yürütülür?</span><span class="sxs-lookup"><span data-stu-id="a31ed-105">How quantum algorithms are executed</span></span>
> * <span data-ttu-id="a31ed-106">Bu sürüme dahil olan kuantum simülatörler</span><span class="sxs-lookup"><span data-stu-id="a31ed-106">What quantum simulators are included in this release</span></span>
> * <span data-ttu-id="a31ed-107">Kuantum algoritmanız için bir C# sürücüsü yazma</span><span class="sxs-lookup"><span data-stu-id="a31ed-107">How to write a C# driver for your quantum algorithm</span></span>

## <a name="the-quantum-development-kit-execution-model"></a><span data-ttu-id="a31ed-108">Kuantum Geliştirme Seti Yürütme Modeli</span><span class="sxs-lookup"><span data-stu-id="a31ed-108">The Quantum Development Kit Execution Model</span></span>

<span data-ttu-id="a31ed-109">[Kuantum program yazma](xref:microsoft.quantum.write-program) bölümünde bir `QuantumSimulator` nesnesini algoritma sınıfının `Run` yöntemine geçirerek kuantum algoritmamızı yürüttük.</span><span class="sxs-lookup"><span data-stu-id="a31ed-109">In [Writing a quantum program](xref:microsoft.quantum.write-program), we executed our quantum algorithm by passing a `QuantumSimulator` object to the algorithm class's `Run` method.</span></span>
<span data-ttu-id="a31ed-110">`QuantumSimulator` sınıfı, `Teleport` çalıştırmak ve test etmek için mükemmel olan kuantum durum vektörünü tamamen taklit ederek kuantum algoritmasını yürütür.</span><span class="sxs-lookup"><span data-stu-id="a31ed-110">The `QuantumSimulator` class executes the quantum algorithm by fully simulating the quantum state vector, which is perfect for running and testing `Teleport`.</span></span>
<span data-ttu-id="a31ed-111">Kuantum durum vektörleri hakkında daha fazla bilgi için bkz. [Kavramlar kılavuzu](xref:microsoft.quantum.concepts.intro).</span><span class="sxs-lookup"><span data-stu-id="a31ed-111">See the [Concepts guide](xref:microsoft.quantum.concepts.intro) for more on quantum state vectors.</span></span>

<span data-ttu-id="a31ed-112">Diğer hedef makineler bir kuantum algoritması çalıştırmak için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="a31ed-112">Other target machines may be used to run a quantum algorithm.</span></span>
<span data-ttu-id="a31ed-113">Makine, algoritma için kuantum temel elemanlarının uygulamasını sağlamaktan sorumludur.</span><span class="sxs-lookup"><span data-stu-id="a31ed-113">The machine is responsible for providing implementations of quantum primitives for the algorithm.</span></span>
<span data-ttu-id="a31ed-114">Buna H, CNOT ve Measure gibi temel eleman işlemlerinin yanı sıra kuantum bit yönetimi ve izlemesi dahildir.</span><span class="sxs-lookup"><span data-stu-id="a31ed-114">This includes primitive operations such as H, CNOT, and Measure, as well as qubit management and tracking.</span></span>
<span data-ttu-id="a31ed-115">Farklı kuantum makine sınıfları, aynı kuantum algoritması için farklı yürütme modellerini temsil eder.</span><span class="sxs-lookup"><span data-stu-id="a31ed-115">Different classes of quantum machines represent different execution models for the same quantum algorithm.</span></span>

<span data-ttu-id="a31ed-116">Her kuantum makine türü, bu temel elemanların farklı uygulamalarını sağlayabilir.</span><span class="sxs-lookup"><span data-stu-id="a31ed-116">Each type of quantum machine may provide different implementations of these primitives.</span></span>
<span data-ttu-id="a31ed-117">Örneğin, geliştirme setine dahil olan kuantum bilgisayar iz simülatörü hiçbir simülasyon yapmaz.</span><span class="sxs-lookup"><span data-stu-id="a31ed-117">For instance, the quantum computer trace simulator included in the development kit doesn't do any simulation at all.</span></span>
<span data-ttu-id="a31ed-118">Bunun yerine algoritmaya ait geçit, kuantum bit ve diğer kaynak kullanımını izler.</span><span class="sxs-lookup"><span data-stu-id="a31ed-118">Rather, it tracks gate, qubit, and other resource usage for the algorithm.</span></span>

### <a name="quantum-machines"></a><span data-ttu-id="a31ed-119">Kuantum Makineler</span><span class="sxs-lookup"><span data-stu-id="a31ed-119">Quantum Machines</span></span>

<span data-ttu-id="a31ed-120">Gelecekte diğer simülasyon türlerini destekleyen ve topolojik kuantum bilgisayarlar üzerinde yürütmeyi destekleyen başka kuantum makine sınıfları tanımlayacağız.</span><span class="sxs-lookup"><span data-stu-id="a31ed-120">In the future, we will define additional quantum machine classes to support other types of simulation and to support execution on topological quantum computers.</span></span>
<span data-ttu-id="a31ed-121">Temel alınan makine uygulamasını değiştirirken algoritmanın sabit kalmasına izin vermek, simülasyondaki bir algoritmayı test etme ve hata ayıklama işlemlerini kolaylaştırır ve sonra algoritmanın değişmediğinden emin olarak gerçek donanım üzerinde rahatça çalıştırılır.</span><span class="sxs-lookup"><span data-stu-id="a31ed-121">Allowing the algorithm to stay constant while varying the underlying machine implementation makes it easy to test and debug an algorithm in simulation and then run it on real hardware with confidence that the algorithm hasn't changed.</span></span>

### <a name="whats-included-in-this-release"></a><span data-ttu-id="a31ed-122">Bu Yayına Dahil Olan Özellikler</span><span class="sxs-lookup"><span data-stu-id="a31ed-122">What's Included in this Release</span></span>

<span data-ttu-id="a31ed-123">Kuantum geliştirici setinin bu yayını birkaç kuantum makine sınıfı içerir.</span><span class="sxs-lookup"><span data-stu-id="a31ed-123">This release of the quantum developer kit includes several quantum machine classes.</span></span>
<span data-ttu-id="a31ed-124">Bu sınıfların tümü `Microsoft.Quantum.Simulation.Simulators` ad alanında tanımlanmıştır.</span><span class="sxs-lookup"><span data-stu-id="a31ed-124">All of them are defined in the `Microsoft.Quantum.Simulation.Simulators` namespace.</span></span>

* <span data-ttu-id="a31ed-125">Bir [tam durum vektör simülatörü](xref:microsoft.quantum.machines.full-state-simulator), `QuantumSimulator` sınıfı.</span><span class="sxs-lookup"><span data-stu-id="a31ed-125">A [full state vector simulator](xref:microsoft.quantum.machines.full-state-simulator), the `QuantumSimulator` class.</span></span>
* <span data-ttu-id="a31ed-126">Bir [basit kaynak tahmin aracı](xref:microsoft.quantum.machines.resources-estimator), `ResourcesEstimator` sınıfı. Bir kuantum algoritmasını çalıştırmak için gereken kaynakların üst düzey analizini yapmaya olanak tanır.</span><span class="sxs-lookup"><span data-stu-id="a31ed-126">A [simple resources estimator](xref:microsoft.quantum.machines.resources-estimator), the `ResourcesEstimator` class, it allows a top level analysis of the resources needed to run a quantum algorithm.</span></span>
* <span data-ttu-id="a31ed-127">[İzleme tabanlı kaynak tahmin aracı](xref:microsoft.quantum.machines.qc-trace-simulator.intro), `QCTraceSimulator` sınıfı. Algoritmanın tüm çağrı grafı için kaynak tüketiminin gelişmiş analizini yapmaya olanak tanır.</span><span class="sxs-lookup"><span data-stu-id="a31ed-127">A [trace-based resource estimator](xref:microsoft.quantum.machines.qc-trace-simulator.intro), the `QCTraceSimulator` class, it allows advanced analysis of resources consumptions for the algorithm's entire call-graph.</span></span>
* <span data-ttu-id="a31ed-128">Bir [Toffoli simülatörü](xref:microsoft.quantum.machines.toffoli-simulator), `ToffoliSimulator` sınıfı.</span><span class="sxs-lookup"><span data-stu-id="a31ed-128">A [Toffoli simulator](xref:microsoft.quantum.machines.toffoli-simulator), the `ToffoliSimulator` class.</span></span>

## <a name="writing-a-host-application"></a><span data-ttu-id="a31ed-129">Konak uygulama yazma</span><span class="sxs-lookup"><span data-stu-id="a31ed-129">Writing a host application</span></span>

<span data-ttu-id="a31ed-130">[Kuantum program yazma](xref:microsoft.quantum.write-program) bölümünde teleport algoritmamız için basit bir C# sürücüsü yazmıştık.</span><span class="sxs-lookup"><span data-stu-id="a31ed-130">In [Writing a quantum program](xref:microsoft.quantum.write-program), we wrote a simple C# driver for our teleport algorithm.</span></span> <span data-ttu-id="a31ed-131">Bir C# sürücüsünün başlıca 4 amacı vardır:</span><span class="sxs-lookup"><span data-stu-id="a31ed-131">A C# driver has 4 main purposes:</span></span>

* <span data-ttu-id="a31ed-132">Hedef makineyi oluşturma</span><span class="sxs-lookup"><span data-stu-id="a31ed-132">Constructing the target machine</span></span>
* <span data-ttu-id="a31ed-133">Kuantum algoritması için gereken tüm bağımsız değişkenleri hesaplama</span><span class="sxs-lookup"><span data-stu-id="a31ed-133">Computing any arguments required for the quantum algorithm</span></span>
* <span data-ttu-id="a31ed-134">Simülatörü kullanarak kuantum algoritması çalıştırma</span><span class="sxs-lookup"><span data-stu-id="a31ed-134">Running the quantum algorithm using the simulator</span></span>
* <span data-ttu-id="a31ed-135">İşlemin sonucunu işleme</span><span class="sxs-lookup"><span data-stu-id="a31ed-135">Processing the result of the operation</span></span>

<span data-ttu-id="a31ed-136">Burada her adımı daha ayrıntılı olarak ele alacağız.</span><span class="sxs-lookup"><span data-stu-id="a31ed-136">Here we'll discuss each step in more detail.</span></span>

### <a name="constructing-the-target-machine"></a><span data-ttu-id="a31ed-137">Hedef Makineyi Oluşturma</span><span class="sxs-lookup"><span data-stu-id="a31ed-137">Constructing the Target Machine</span></span>

<span data-ttu-id="a31ed-138">Kuantum makineler normal .NET sınıfı örnekleridir, bu nedenle herhangi bir .NET sınıfı gibi oluşturucularını çağırarak oluşturulurlar.</span><span class="sxs-lookup"><span data-stu-id="a31ed-138">Quantum machines are instances of normal .NET classes, so they are created by invoking their constructor, just like any .NET class.</span></span>
<span data-ttu-id="a31ed-139">`QuantumSimulator` dahil bazı simülatörler .NET <xref:System.IDisposable?displayProperty=nameWithType> arabirimini uygular ve bu yüzden bir C# `using` deyimine sarmalanmalıdır.</span><span class="sxs-lookup"><span data-stu-id="a31ed-139">Some simulators, including the `QuantumSimulator`, implement the .NET <xref:System.IDisposable?displayProperty=nameWithType> interface, and so should be wrapped in a C# `using` statement.</span></span>

### <a name="computing-arguments-for-the-algorithm"></a><span data-ttu-id="a31ed-140">Algoritma Bağımsız Değişkenlerini Hesaplama</span><span class="sxs-lookup"><span data-stu-id="a31ed-140">Computing Arguments for the Algorithm</span></span>

<span data-ttu-id="a31ed-141">`Teleport` örneğimizde, kuantum algoritmamıza geçirilecek bazı görece yapay bağımsız değişkenleri hesaplandık.</span><span class="sxs-lookup"><span data-stu-id="a31ed-141">In our `Teleport` example, we computed some relatively artificial arguments to pass to our quantum algorithm.</span></span>
<span data-ttu-id="a31ed-142">Bununla birlikte, genellikle kuantum algoritması önemli veriler gerektirir ve bu verileri klasik sürücüden sağlamak en kolay yoldur.</span><span class="sxs-lookup"><span data-stu-id="a31ed-142">More typically, however, there is significant data required by the quantum algorithm, and it is easiest to provide it from the classical driver.</span></span>

<span data-ttu-id="a31ed-143">Örneğin, kimyasal simülasyonlar yaparken kuantum algoritması büyük bir moleküler orbital etkileşim tam sayıları tablosu gerektirir.</span><span class="sxs-lookup"><span data-stu-id="a31ed-143">For instance, when doing chemical simulations, the quantum algorithm requires a large table of molecular orbital interaction integrals.</span></span>
<span data-ttu-id="a31ed-144">Bunlar genellikle algoritma çalıştırılırken sağlanan bir dosyadan okunurlar.</span><span class="sxs-lookup"><span data-stu-id="a31ed-144">Generally these are read in from a file that is provided when running the algorithm.</span></span>
<span data-ttu-id="a31ed-145">Q# dilinin dosya sistemine erişmeye yönelik bir mekanizması bulunmadığı için, bu tür verileri toplamanın en iyi yolu klasik sürücüdür ve bu veriler kuantum algoritmasının `Run` yöntemine geçirilir.</span><span class="sxs-lookup"><span data-stu-id="a31ed-145">Since Q# does not have a mechanism for accessing the file system, this sort of data is best collected by the classical driver and then passed to the quantum algorithm's `Run` method.</span></span>

<span data-ttu-id="a31ed-146">Klasik sürücünün anahtar rol oynadığı başka bir durum ise değişimli yöntemlerde yaşanır.</span><span class="sxs-lookup"><span data-stu-id="a31ed-146">Another case where the classical driver plays a key role is in variational methods.</span></span>
<span data-ttu-id="a31ed-147">Bu algoritma sınıfında bazı klasik parametreler temel alınarak bir kuantum durumu hazırlanır ve bu durum, bazı ilgili değerleri hesaplamak için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="a31ed-147">In this class of algorithms, a quantum state is prepared based on some classical parameters, and that state is used to compute some value of interest.</span></span>
<span data-ttu-id="a31ed-148">Parametreler bazı tırmanma veya makine öğrenmesi algoritması türleri temel alınarak ayarlanır ve kuantum algoritması tekrar çalışır.</span><span class="sxs-lookup"><span data-stu-id="a31ed-148">The parameters are adjusted based on some type of hill climbing or machine learning algorithm and the quantum algorithm run again.</span></span>
<span data-ttu-id="a31ed-149">Bu tür algoritmalar için tırmanma algoritmasını uygulamanın en iyi yolu, klasik sürücü tarafından çağrılan tamamen klasik bir işlev olarak uygulamaktır. Tırmanma sonuçları daha sonra kuantum algoritmasının sonraki yürütme işlemine geçirilir.</span><span class="sxs-lookup"><span data-stu-id="a31ed-149">For such algorithms, the hill climbing algorithm itself is best implemented as a purely classical function that is called by the classical driver; the results of the hill climbing are then passed to the next execution of the quantum algorithm.</span></span>

### <a name="running-the-quantum-algorithm"></a><span data-ttu-id="a31ed-150">Kuantum Algoritmasını Çalıştırma</span><span class="sxs-lookup"><span data-stu-id="a31ed-150">Running the Quantum Algorithm</span></span>

<span data-ttu-id="a31ed-151">Bu bölüm genellikle çok basittir.</span><span class="sxs-lookup"><span data-stu-id="a31ed-151">This part is generally very straightforward.</span></span>
<span data-ttu-id="a31ed-152">Her Q# işlemi statik bir `Run` yöntemi sağlayan bir sınıfta derlenir.</span><span class="sxs-lookup"><span data-stu-id="a31ed-152">Each Q# operation is compiled into a class that provides a static `Run` method.</span></span>
<span data-ttu-id="a31ed-153">Bu yöntemin bağımsız değişkenleri, işlemin düzleştirilmiş bağımsız değişken demeti tarafından verilir ve ek olarak, yürütülecek simülatörü oluşturan bir birinci bağımsız değişken daha bulunur.</span><span class="sxs-lookup"><span data-stu-id="a31ed-153">The arguments to this method are given by the flattened argument tuple of the operation itself, plus an additional first argument which is the simulator to execute with.</span></span> <span data-ttu-id="a31ed-154">`(a: String, (b: Double, c: Double))` türünde adlandırılmış demeti bekleyen bir işlemin düzleştirilmiş karşılığı `(String a, Double b, Double c)` türündedir.</span><span class="sxs-lookup"><span data-stu-id="a31ed-154">For an operation that expects the named tuple of type `(a: String, (b: Double, c: Double))` its flattened counterpart is of type `(String a, Double b, Double c)`.</span></span>


<span data-ttu-id="a31ed-155">Bağımsız değişkenleri bir `Run` yöntemine geçirirken uygulanacak bazı incelikler vardır:</span><span class="sxs-lookup"><span data-stu-id="a31ed-155">There are some subtleties when passing arguments to a `Run` method:</span></span>

* <span data-ttu-id="a31ed-156">Diziler bir `Microsoft.Quantum.Simulation.Core.QArray<T>` nesnesine sarmalanmış olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="a31ed-156">Arrays must be wrapped in a `Microsoft.Quantum.Simulation.Core.QArray<T>` object.</span></span>
    <span data-ttu-id="a31ed-157">`QArray` sınıfı, uygun nesnelerin sıralanmış herhangi bir koleksiyonunu (`IEnumerable<T>`) alabilen bir oluşturucuya sahiptir.</span><span class="sxs-lookup"><span data-stu-id="a31ed-157">A `QArray` class has a constructor that can take any ordered collection (`IEnumerable<T>`) of appropriate objects.</span></span>
* <span data-ttu-id="a31ed-158">Q# dilinde `()` olan boş demet, C# dilinde `QVoid.Instance` ile temsil edilir.</span><span class="sxs-lookup"><span data-stu-id="a31ed-158">The empty tuple, `()` in Q#, is represented by `QVoid.Instance` in C#.</span></span>
* <span data-ttu-id="a31ed-159">Boş olmayan demetler .NET `ValueTuple` örnekleri olarak temsil edilir.</span><span class="sxs-lookup"><span data-stu-id="a31ed-159">Non-empty tuples are represented as .NET `ValueTuple` instances.</span></span>
* <span data-ttu-id="a31ed-160">Kullanıcı tanımlı Q# türleri, temel tür olarak geçirilir.</span><span class="sxs-lookup"><span data-stu-id="a31ed-160">Q# user-defined types are passed as their base type.</span></span>
* <span data-ttu-id="a31ed-161">Bir işlemi veya işlevi `Run` yöntemine geçirmek için, simülatörün `Get<>` yöntemini kullanarak işlemin veya işlevin sınıfının bir örneğini elde etmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="a31ed-161">To pass an operation or a function to a `Run` method, you have to obtain an   instance of the operation's or function's class, using the simulator's `Get<>` method.</span></span>

### <a name="processing-the-results"></a><span data-ttu-id="a31ed-162">Sonuçları İşleme</span><span class="sxs-lookup"><span data-stu-id="a31ed-162">Processing the Results</span></span>

<span data-ttu-id="a31ed-163">Kuantum algoritmasının sonuçları `Run` yönteminden döndürülür.</span><span class="sxs-lookup"><span data-stu-id="a31ed-163">The results of the quantum algorithm are returned from the `Run` method.</span></span>
<span data-ttu-id="a31ed-164">`Run` yöntemi zaman uyumsuz olarak yürütülür, bu nedenle bir <xref:System.Threading.Tasks.Task`1> örneği döndürür.</span><span class="sxs-lookup"><span data-stu-id="a31ed-164">The `Run` method executes asynchronously thus it returns an instance of <xref:System.Threading.Tasks.Task`1>.</span></span>
<span data-ttu-id="a31ed-165">Gerçek işlemin sonuçlarını almanın birden çok yolu vardır.</span><span class="sxs-lookup"><span data-stu-id="a31ed-165">There are multiple ways to get the actual operation's results.</span></span> <span data-ttu-id="a31ed-166">En basit yol, `Task` yönteminin [`Result` özelliğini](https://docs.microsoft.com/dotnet/api/system.threading.tasks.task-1.result) kullanmaktır:</span><span class="sxs-lookup"><span data-stu-id="a31ed-166">The simplest is by using the `Task`'s [`Result` property](https://docs.microsoft.com/dotnet/api/system.threading.tasks.task-1.result):</span></span>

```csharp
    var res = BellTest.Run(sim, 1000, initial).Result;
```
<span data-ttu-id="a31ed-167">Ancak [`Wait` yöntemini](https://docs.microsoft.com/dotnet/api/system.threading.tasks.task.wait) veya C# [`await` anahtar sözcüğünü](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/await) kullanmak gibi diğer teknikler de işe yarar.</span><span class="sxs-lookup"><span data-stu-id="a31ed-167">but other techniques, like using the [`Wait` method](https://docs.microsoft.com/dotnet/api/system.threading.tasks.task.wait) or C# [`await` keyword](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/await) will also work.</span></span>

<span data-ttu-id="a31ed-168">Bağımsız değişkenlerde olduğu gibi, Q# demetleri `ValueTuple` örnekleri ve Q# dizileri `QArray` örnekleri olarak temsil edilir.</span><span class="sxs-lookup"><span data-stu-id="a31ed-168">As with arguments, Q# tuples are represented as `ValueTuple` instances and Q# arrays are represented as `QArray` instances.</span></span>
<span data-ttu-id="a31ed-169">Kullanıcı tanımlı türler, temel türleri olarak döndürülür.</span><span class="sxs-lookup"><span data-stu-id="a31ed-169">User-defined types are returned as their base types.</span></span>
<span data-ttu-id="a31ed-170">`()` boş demeti, `QVoid` sınıfının bir örneği olarak döndürülür.</span><span class="sxs-lookup"><span data-stu-id="a31ed-170">The empty tuple, `()`, is returned as an instance of the `QVoid` class.</span></span>

<span data-ttu-id="a31ed-171">Birçok kuantum algoritması yararlı yanıtlar elde etmek için önemli miktarda son işlem gerektirir.</span><span class="sxs-lookup"><span data-stu-id="a31ed-171">Many quantum algorithms require substantial post-processing to derive useful answers.</span></span>
<span data-ttu-id="a31ed-172">Örneğin, Shor algoritmasının kuantum kısmı, bir sayının faktörlerini bulan hesaplamanın yalnızca başlangıcıdır.</span><span class="sxs-lookup"><span data-stu-id="a31ed-172">For instance, the quantum part of Shor's algorithm is just the beginning of a computation that finds the factors of a number.</span></span>

<span data-ttu-id="a31ed-173">Çoğu durumda, bu son işlemi klasik sürücüde yapmak daha basit ve kolaydır.</span><span class="sxs-lookup"><span data-stu-id="a31ed-173">In most cases, it is simplest and easiest to do this sort of post-processing in the classical driver.</span></span>
<span data-ttu-id="a31ed-174">Yalnızca klasik sürücü sonuçları kullanıcıya bildirebilir veya diske yazabilir.</span><span class="sxs-lookup"><span data-stu-id="a31ed-174">Only the classical driver can report results to the user or write them to disk.</span></span>
<span data-ttu-id="a31ed-175">Klasik sürücü, analitik kitaplıklara ve Q# içinde gösterilmeyen diğer matematiksel işlevlere erişebilir.</span><span class="sxs-lookup"><span data-stu-id="a31ed-175">The classical driver will have access to analytical libraries and other mathematical functions that are not exposed in Q#.</span></span>


## <a name="failures"></a><span data-ttu-id="a31ed-176">Hatalar</span><span class="sxs-lookup"><span data-stu-id="a31ed-176">Failures</span></span>

<span data-ttu-id="a31ed-177">Bir işlemin yürütülmesi sırasında Q# `fail` deyimine ulaşıldığında bir `ExecutionFailException` oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="a31ed-177">When the Q# `fail` statement is reached during the execution of an operation, an `ExecutionFailException` is thrown.</span></span>

<span data-ttu-id="a31ed-178">`Run` yönteminde `System.Task` kullanılması nedeniyle, `fail` deyiminin sonucu olarak oluşturulan özel durum bir `System.AggregateException` içine sarmalanmalıdır.</span><span class="sxs-lookup"><span data-stu-id="a31ed-178">Due to the use of `System.Task` in the `Run` method, the exception thrown as a result of a `fail` statement will be wrapped into a `System.AggregateException`.</span></span>
<span data-ttu-id="a31ed-179">Hatanın gerçek nedenini bulmak için `AggregateException` 
`InnerExceptions`içinde tekrarlamanız gerekir, örneğin:</span><span class="sxs-lookup"><span data-stu-id="a31ed-179">To find the actual reason for the failure, you need to iterate into the `AggregateException` 
`InnerExceptions`, for example:</span></span>

```csharp

            try
            {
                using(var sim = new QuantumSimulator())
                {
                    /// call your operations here...
                }
            }
            catch (AggregateException e)
            {
                // Unwrap AggregateException to get the message from Q# fail statement.
                // Go through all inner exceptions.
                foreach (Exception inner in e.InnerExceptions)
                {
                    // If the exception of type ExecutionFailException
                    if (inner is ExecutionFailException failException)
                    {
                        // Print the message it contains
                        Console.WriteLine($" {failException.Message}");
                    }
                }
            }
```

## <a name="other-classical-languages"></a><span data-ttu-id="a31ed-180">Diğer Klasik Diller</span><span class="sxs-lookup"><span data-stu-id="a31ed-180">Other Classical Languages</span></span>

<span data-ttu-id="a31ed-181">Sağladığımız örnekler C#, F# ve Python dillerinde olsa da Kuantum Geliştirme Seti diğer dillerde klasik ana bilgisayar programları yazmayı da destekler.</span><span class="sxs-lookup"><span data-stu-id="a31ed-181">While the samples we have provided are in C#, F#, and Python, the Quantum Development Kit also supports writing classical host programs in other languages.</span></span>
<span data-ttu-id="a31ed-182">Örneğin, Visual Basic’te bir ana bilgisayar programı yazmak istiyorsanız [sorunsuzca çalışmalıdır](https://github.com/tcNickolas/MiscQSharp/blob/master/Quantum_VBNet/README.md#using-q-with-visual-basic-net).</span><span class="sxs-lookup"><span data-stu-id="a31ed-182">For example, if you want to write a host program in Visual Basic, [it should work just fine](https://github.com/tcNickolas/MiscQSharp/blob/master/Quantum_VBNet/README.md#using-q-with-visual-basic-net).</span></span>
