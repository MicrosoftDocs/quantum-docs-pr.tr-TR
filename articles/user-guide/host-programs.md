---
title: 'Q # programını çalıştırma yolları'
description: 'Q # programlarını çalıştırmanın farklı yollarına genel bakış. Komut satırından, Q # jupi Not defterleri ve Python veya bir .NET dilinde klasik ana bilgisayar programları.'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 05/15/2020
ms.topic: article
uid: microsoft.quantum.guide.host-programs
ms.openlocfilehash: 132c138d7c392ed2b4bd3d0079180b68adae4cfc
ms.sourcegitcommit: a3775921db1dc5c653c97b8fa8fe2c0ddd5261ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/02/2020
ms.locfileid: "85887763"
---
# <a name="ways-to-run-a-q-program"></a><span data-ttu-id="5d38f-104">Q # programını çalıştırma yolları</span><span class="sxs-lookup"><span data-stu-id="5d38f-104">Ways to run a Q# program</span></span>

<span data-ttu-id="5d38f-105">Hisse geliştirme setinin en büyük güçlerinden biri, platformlar ve geliştirme ortamları arasında esneklik sağlar.</span><span class="sxs-lookup"><span data-stu-id="5d38f-105">One of the Quantum Development Kit's greatest strengths is its flexibility across platforms and development environments.</span></span>
<span data-ttu-id="5d38f-106">Bununla birlikte, bu durum, yeni Q # kullanıcılarının, kendi kendini karıştırarak veya daha fazla bilgi edinmek için, bkz. [Install kılavuzunda](xref:microsoft.quantum.install)bulunan çok sayıda seçenek.</span><span class="sxs-lookup"><span data-stu-id="5d38f-106">However, this also means that new Q# users may find themselves confused or overwhelmed by the numerous options found in the [install guide](xref:microsoft.quantum.install).</span></span>
<span data-ttu-id="5d38f-107">Bu sayfada, bir Q # programı çalıştırıldığında ne olduğunu açıkladık ve kullanıcıların bunu yapabilecekleri farklı yollarla karşılaştırıyoruz.</span><span class="sxs-lookup"><span data-stu-id="5d38f-107">On this page, we explain what happens when a Q# program is run, and compare the different ways in which users can do so.</span></span>

<span data-ttu-id="5d38f-108">Birincil ayrım, Q # ' ın çalıştırılamadır:</span><span class="sxs-lookup"><span data-stu-id="5d38f-108">A primary distinction is that Q# can be run:</span></span>
- <span data-ttu-id="5d38f-109">tek başına bir uygulama olarak, burada Q #, söz konusu tek dildir ve program doğrudan çağırılır.</span><span class="sxs-lookup"><span data-stu-id="5d38f-109">as a standalone application, where Q# is the only language involved and the program is invoked directly.</span></span> <span data-ttu-id="5d38f-110">Bu kategoriye aslında iki yöntem yer almalıdır:</span><span class="sxs-lookup"><span data-stu-id="5d38f-110">Two methods actually fall in this category:</span></span>
  - <span data-ttu-id="5d38f-111">komut satırı arabirimi</span><span class="sxs-lookup"><span data-stu-id="5d38f-111">the command line interface</span></span>
  - <span data-ttu-id="5d38f-112">Q# Jupyter Notebook’ları</span><span class="sxs-lookup"><span data-stu-id="5d38f-112">Q# Jupyter Notebooks</span></span>
- <span data-ttu-id="5d38f-113">daha sonra programı çağıran ve döndürülen sonuçları daha sonra işlemek için Python veya .NET dilinde (ör. C# veya F #) yazılmış ek bir *ana bilgisayar programı*ile.</span><span class="sxs-lookup"><span data-stu-id="5d38f-113">with an additional *host program*, written in Python or a .NET language (e.g. C# or F#), which then invokes the program and can further process returned results.</span></span>

<span data-ttu-id="5d38f-114">Bu işlemlerin ve bunların farklarının en iyi şekilde anlaşılması için, basit bir Q # programı ele alalım ve bunların yürütülme yollarını karşılaştırıyoruz.</span><span class="sxs-lookup"><span data-stu-id="5d38f-114">To best understand these processes and their differences, we consider a simple Q# program and compare the ways it can be executed.</span></span>

## <a name="basic-q-program"></a><span data-ttu-id="5d38f-115">Temel Q # programı</span><span class="sxs-lookup"><span data-stu-id="5d38f-115">Basic Q# program</span></span>

<span data-ttu-id="5d38f-116">Temel bir hisse, durumlardan biri olan $ \ket $ ve $ \tus$ gibi büyük bir üst konumda qubit hazırlamaktan ve {0} {1} Bu iki durumdan eşit olasılığa sahip olarak rastgele olacak.</span><span class="sxs-lookup"><span data-stu-id="5d38f-116">A basic quantum program might consist of preparing a qubit in an equal superposition of states $\ket{0}$ and $\ket{1}$, measuring it, and returning the result, which will be randomly either one of these two states with equal probability.</span></span>
<span data-ttu-id="5d38f-117">Aslında bu işlem, [hisse rastgele numara Oluşturucu](xref:microsoft.quantum.quickstarts.qrng) hızlı başlangıcı 'nın çekirdeğisidir.</span><span class="sxs-lookup"><span data-stu-id="5d38f-117">Indeed, this process is at the core of the [quantum random number generator](xref:microsoft.quantum.quickstarts.qrng) quickstart.</span></span>

<span data-ttu-id="5d38f-118">Q # içinde bu, aşağıdaki kod tarafından gerçekleştirilir:</span><span class="sxs-lookup"><span data-stu-id="5d38f-118">In Q#, this would be performed by the following code:</span></span>

```qsharp
        using (q = Qubit()) {    // allocates qubit for use (automatically in |0>)
            H(q);                // puts qubit in superposition of |0> and |1>
            return MResetZ(q);   // measures qubit, returns result (and resets it to |0> before deallocation)
        }
```

<span data-ttu-id="5d38f-119">Ancak, bu kod yalnızca Q # tarafından yürütülemez.</span><span class="sxs-lookup"><span data-stu-id="5d38f-119">However, this code alone can't be executed by Q#.</span></span>
<span data-ttu-id="5d38f-120">Bunun için, doğrudan ya da başka bir işlem tarafından---çağrıldığında yürütülen bir [işlemin](xref:microsoft.quantum.guide.basics#q-operations-and-functions)gövdesini yapması gerekir.</span><span class="sxs-lookup"><span data-stu-id="5d38f-120">For that, it needs to make up the body of an [operation](xref:microsoft.quantum.guide.basics#q-operations-and-functions), which is then executed when called---either directly or by another operation.</span></span> <span data-ttu-id="5d38f-121">Bu nedenle, aşağıdaki biçimde bir işlem yazabilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="5d38f-121">Hence, you can write an operation of the following form:</span></span>
```qsharp
    operation MeasureSuperposition() : Result {
        using (q = Qubit()) {
            H(q);
            return MResetZ(q);
        }
    }
```
<span data-ttu-id="5d38f-122">Bir işlem tanımladınız, ancak `MeasureSuperposition` hiçbir giriş yapılmaz ve [sonuç](xref:microsoft.quantum.guide.types)türünde bir değer döndürmez.</span><span class="sxs-lookup"><span data-stu-id="5d38f-122">You have defined an operation, `MeasureSuperposition`, which takes no inputs and returns a value of type [Result](xref:microsoft.quantum.guide.types).</span></span>

<span data-ttu-id="5d38f-123">Bu sayfadaki örnekler yalnızca Q # *işlemleri*içerirken, tartıştığımız tüm kavramlar, q # *işlevlerine*eşit olarak değineceğiz ve bu nedenle bunlara toplu olarak *callables*olarak başvuracağız.</span><span class="sxs-lookup"><span data-stu-id="5d38f-123">While the examples on this page only consist of Q# *operations*, all of the concepts we will discuss pertain equally to Q# *functions*, and therefore we refer to them collectively as *callables*.</span></span> <span data-ttu-id="5d38f-124">Farkları, [s # temel kavramları: işlemler ve işlevler](xref:microsoft.quantum.guide.basics#q-operations-and-functions)ve bunları tanımlama hakkında daha fazla ayrıntı, [işlemler ve işlevlerde](xref:microsoft.quantum.guide.operationsfunctions)bulunabilir.</span><span class="sxs-lookup"><span data-stu-id="5d38f-124">Their differences are discussed at [Q# basics: operations and functions](xref:microsoft.quantum.guide.basics#q-operations-and-functions), and more details on defining them can be found at [Operations and functions](xref:microsoft.quantum.guide.operationsfunctions).</span></span>

### <a name="callable-defined-in-a-q-file"></a><span data-ttu-id="5d38f-125">Bir Q # dosyasında tanımlanmış çağrılabilir</span><span class="sxs-lookup"><span data-stu-id="5d38f-125">Callable defined in a Q# file</span></span>

<span data-ttu-id="5d38f-126">Çağrılabilir özelliği, Q # tarafından çağrılarak ve çalıştırılmıştı.</span><span class="sxs-lookup"><span data-stu-id="5d38f-126">The callable is precisely what's called and run by Q#.</span></span>
<span data-ttu-id="5d38f-127">Ancak, tam bir Q # dosyası için daha fazla ek ekleme gerektirir `*.qs` .</span><span class="sxs-lookup"><span data-stu-id="5d38f-127">However, it requires a few more additions to comprise a full `*.qs` Q# file.</span></span>

<span data-ttu-id="5d38f-128">Tüm Q # türleri ve callables (hem tanımladığınız hem de dile özgü olanlar), *ad alanları*içinde tanımlanır ve bu da başvurulabilen her bir tam ad sağlar.</span><span class="sxs-lookup"><span data-stu-id="5d38f-128">All Q# types and callables (both those you define and those intrinsic to the language) are defined within *namespaces*, which provide each a full name that can then be referenced.</span></span>

<span data-ttu-id="5d38f-129">Örneğin, [`H`](xref:microsoft.quantum.intrinsic.h) ve işlemleri, [`MResetZ`](xref:microsoft.quantum.measurement.mresetz) [`Microsoft.Quantum.Instrinsic`](xref:microsoft.quantum.intrinsic) ve [`Microsoft.Quantum.Measurement`](xref:microsoft.quantum.measurement) ad alanlarında ( [Q # standart kitaplıklarının](xref:microsoft.quantum.qsharplibintro)bir parçası) bulunur.</span><span class="sxs-lookup"><span data-stu-id="5d38f-129">For example, the [`H`](xref:microsoft.quantum.intrinsic.h) and [`MResetZ`](xref:microsoft.quantum.measurement.mresetz) operations are found in the [`Microsoft.Quantum.Instrinsic`](xref:microsoft.quantum.intrinsic) and [`Microsoft.Quantum.Measurement`](xref:microsoft.quantum.measurement) namespaces (part of the [Q# Standard Libraries](xref:microsoft.quantum.qsharplibintro)).</span></span>
<span data-ttu-id="5d38f-130">Bu nedenle, her zaman *tam* adlarıyla çağrılabilir, `Microsoft.Quantum.Intrinsic.H(<qubit>)` `Microsoft.Quantum.Measurement.MResetZ(<qubit>)` ancak her zaman bunu yapmanız çok karışık koda yol açabilir.</span><span class="sxs-lookup"><span data-stu-id="5d38f-130">As such, they can always be called via their *full* names, `Microsoft.Quantum.Intrinsic.H(<qubit>)` and `Microsoft.Quantum.Measurement.MResetZ(<qubit>)`, but always doing this would lead to very cluttered code.</span></span>

<span data-ttu-id="5d38f-131">Bunun yerine, `open` deyimler, yukarıdaki işlem gövdesinde yaptığımız gibi, callables 'e daha kısa toplu ile başvurulmalıdır.</span><span class="sxs-lookup"><span data-stu-id="5d38f-131">Instead, `open` statements allow callables to be referenced with more concise shorthand, as we've done in the operation body above.</span></span>
<span data-ttu-id="5d38f-132">Operasyonumuzu içeren tam Q # dosyası bu nedenle kendi ad boşluğumuzu tanımlamayı, işlediğimiz bu callabler için ad alanlarını açmayı ve sonra işleminizi içerir:</span><span class="sxs-lookup"><span data-stu-id="5d38f-132">The full Q# file containing our operation would therefore consist of defining our own namespace, opening the namespaces for those callables our operation uses, and then our operation:</span></span>

```qsharp
namespace NamespaceName {
    open Microsoft.Quantum.Intrinsic;     // for the H operation
    open Microsoft.Quantum.Measurement;   // for MResetZ

    operation MeasureSuperposition() : Result {
        using (q = Qubit()) { 
            H(q);
            return MResetZ(q);
        }
    }
}
```

> [!NOTE]
> <span data-ttu-id="5d38f-133">Ayrıca, iki ad alanındaki çağrılabilir/tür adları çakışıyorsa yararlı olabilecek ad alanları açıldıklarında da *diğer* ad olabilir.</span><span class="sxs-lookup"><span data-stu-id="5d38f-133">Namespaces can also be *aliased* when opened, which can be helpful if callable/type names in two namespaces conflict.</span></span>
> <span data-ttu-id="5d38f-134">Örneğin, `open Microsoft.Quantum.Instrinsic as NamespaceWithH;` Yukarıdaki ' ı kullanabilir ve ardından `H` aracılığıyla çağırabilirsiniz `NamespaceWithH.H(<qubit>)` .</span><span class="sxs-lookup"><span data-stu-id="5d38f-134">For example, we could instead use `open Microsoft.Quantum.Instrinsic as NamespaceWithH;` above, and then call `H` via `NamespaceWithH.H(<qubit>)`.</span></span>

> [!NOTE]
> <span data-ttu-id="5d38f-135">Tüm bu tek istisna, [`Microsoft.Quantum.Core`](xref:microsoft.quantum.core) her zaman otomatik olarak açılan bir ad alanıdır.</span><span class="sxs-lookup"><span data-stu-id="5d38f-135">One exception to all of this is the [`Microsoft.Quantum.Core`](xref:microsoft.quantum.core) namespace, which is always automatically opened.</span></span>
> <span data-ttu-id="5d38f-136">Bu nedenle, callables, [`Length`](xref:microsoft.quantum.core.length) her zaman doğrudan kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="5d38f-136">Therefore, callables like [`Length`](xref:microsoft.quantum.core.length) can always be used directly.</span></span>

### <a name="execution-on-target-machines"></a><span data-ttu-id="5d38f-137">Hedef makinelerde yürütme</span><span class="sxs-lookup"><span data-stu-id="5d38f-137">Execution on target machines</span></span>

<span data-ttu-id="5d38f-138">Artık bir Q # programının genel yürütme modeli açık hale gelir.</span><span class="sxs-lookup"><span data-stu-id="5d38f-138">Now the general execution model of a Q# program becomes clear.</span></span>

<br/>
<img src="../media/hostprograms_general_execution_model.png" alt="Q# program execution diagram" width="400">

<span data-ttu-id="5d38f-139">İlk olarak, yürütülecek özel çağrılabilir, aynı ad alanında tanımlanan diğer tüm callables ve türlerine erişebilir.</span><span class="sxs-lookup"><span data-stu-id="5d38f-139">Firstly, the specific callable to be executed has access to any other callables and types defined in the same namespace.</span></span>
<span data-ttu-id="5d38f-140">Ayrıca, bunlara herhangi bir [Q # kitaplığı](xref:microsoft.quantum.libraries)'ndan erişin, ancak bunların tam adlarıyla veya yukarıda açıklanan deyimlerin kullanımı aracılığıyla başvurulmalıdır `open` .</span><span class="sxs-lookup"><span data-stu-id="5d38f-140">It also access those from any of the [Q# libraries](xref:microsoft.quantum.libraries), but those must be referenced either via their full name, or through the use of `open` statements described above.</span></span>

<span data-ttu-id="5d38f-141">Çağrılabilir kendisi bir *[hedef makinede](xref:microsoft.quantum.machines)* yürütülür.</span><span class="sxs-lookup"><span data-stu-id="5d38f-141">The callable itself is then executed on a *[target machine](xref:microsoft.quantum.machines)*.</span></span>
<span data-ttu-id="5d38f-142">Bu tür hedef makineler gerçek hisse donanımı veya QDK 'nin bir parçası olarak kullanılabilir birden çok simülatörleri olabilir.</span><span class="sxs-lookup"><span data-stu-id="5d38f-142">Such target machines can be actual quantum hardware or the multiple simulators available as part of the QDK.</span></span>
<span data-ttu-id="5d38f-143">Burada, bizim için en faydalı hedef makine, [full-state simulator](xref:microsoft.quantum.machines.full-state-simulator) `QuantumSimulator` bir gürültü ücretsiz hisse bilgisayarında yürütülene gibi programın davranışını hesaplayan tam durum simülatörü örneğidir.</span><span class="sxs-lookup"><span data-stu-id="5d38f-143">For our purposes here, the most useful target machine is an instance of the [full-state simulator](xref:microsoft.quantum.machines.full-state-simulator), `QuantumSimulator`, which calculates the program's behavior as if it were being executed on a noise-free quantum computer.</span></span>

<span data-ttu-id="5d38f-144">Şimdiye kadar, belirli bir Q # çağrılabilir yürütüldüğünde ne olduğunu açıklıyoruz.</span><span class="sxs-lookup"><span data-stu-id="5d38f-144">So far, we've described what happens when a specific Q# callable is being executed.</span></span>
<span data-ttu-id="5d38f-145">Q # ' ın tek başına bir uygulamada mı yoksa bir konak programı ile mi kullanıldığına bakılmaksızın, bu genel işlem daha fazla veya daha az---, bu nedenle QDK 'nin esnekliği de aynıdır.</span><span class="sxs-lookup"><span data-stu-id="5d38f-145">Regardless of whether Q# is used in a standalone application or with a host program, this general process is more or less the same---hence the QDK's flexibility.</span></span>
<span data-ttu-id="5d38f-146">Bu nedenle, hisse geliştirme paketine çağrı yapmak için farklı yollar arasındaki farklılıklar, kendileri için Q # çağrılabilir olarak *nasıl* çağrıldığına ve sonuçların ne şekilde döndürüldüğünden ortaya çıkar.</span><span class="sxs-lookup"><span data-stu-id="5d38f-146">The differences between the different ways of calling into the Quantum Development Kit therefore reveal themselves in *how* that Q# callable is called to be executed, and in what manner any results are returned.</span></span>
<span data-ttu-id="5d38f-147">Daha belirgin olarak, farklar ve etrafında</span><span class="sxs-lookup"><span data-stu-id="5d38f-147">More specifically, the differences revolve around</span></span> 
1. <span data-ttu-id="5d38f-148">Hangi Q çağrılabilir çağrılabilir çalıştırılacağını belirtir,</span><span class="sxs-lookup"><span data-stu-id="5d38f-148">indicating which Q# callable is to be executed,</span></span>
2. <span data-ttu-id="5d38f-149">çağrılabilir olabilecek bağımsız değişkenlerin nasıl sağlandığı</span><span class="sxs-lookup"><span data-stu-id="5d38f-149">how potential callable arguments are provided,</span></span>
3. <span data-ttu-id="5d38f-150">üzerinde yürütüleceği hedef makineyi belirtme ve</span><span class="sxs-lookup"><span data-stu-id="5d38f-150">specifying the target machine on which to execute it, and</span></span>
4. <span data-ttu-id="5d38f-151">sonuçların nasıl döndürüldüğü.</span><span class="sxs-lookup"><span data-stu-id="5d38f-151">how any results are returned.</span></span>

<span data-ttu-id="5d38f-152">İlk olarak, komut satırından Q # tek başına uygulamasıyla bunun nasıl yapıldığını anladık ve Python ve C# ana bilgisayar programlarını kullanmaya devam ediyoruz.</span><span class="sxs-lookup"><span data-stu-id="5d38f-152">First, we discuss how this is done with the Q# standalone application from the command line, and then proceed to using Python and C# host programs.</span></span>
<span data-ttu-id="5d38f-153">İlk üçünün aksine, birincil işlevselliği yerel bir Q # dosyası etrafında ortalamadığından, en son Q # jupi Not defterlerinin tek başına uygulamasını ayırdık.</span><span class="sxs-lookup"><span data-stu-id="5d38f-153">We reserve the standalone application of Q# Jupyter Notebooks for last, because unlike the first three, it's primary functionality does not center around a local Q# file.</span></span>

> [!NOTE]
> <span data-ttu-id="5d38f-154">Bu örneklerde açıklanmadığımızda, yürütme yöntemleriyle ilgili bir genel durumda, Q # programının içinden yazdırılan tüm iletiler ( [`Message`](xref:microsoft.quantum.intrinsic.message) [`DumpMachine`](xref:microsoft.quantum.diagnostics.dumpmachine) Örneğin, veya gibi), her zaman ilgili konsola yazdırılır.</span><span class="sxs-lookup"><span data-stu-id="5d38f-154">Although we don't illustrate it in these examples, one commonality between the execution methods is that any messages printed from inside the Q# program (by way of [`Message`](xref:microsoft.quantum.intrinsic.message) or [`DumpMachine`](xref:microsoft.quantum.diagnostics.dumpmachine), for example) will typically always be printed to the respective console.</span></span>

## <a name="q-from-the-command-line"></a><span data-ttu-id="5d38f-155">Q # komut satırından</span><span class="sxs-lookup"><span data-stu-id="5d38f-155">Q# from the command line</span></span>
<span data-ttu-id="5d38f-156">Q # programlarını yazmaya başlamanın en kolay yollarından biri, ayrı dosyalar ve ikinci bir dilin tamamen kaygılanmasından kaçınmaktır.</span><span class="sxs-lookup"><span data-stu-id="5d38f-156">One of the easiest ways to get started writing Q# programs is to avoid worrying about separate files and a second language altogether.</span></span>
<span data-ttu-id="5d38f-157">Visual Studio Code veya Visual Studio 'Yu QDK uzantısıyla kullanmak, yalnızca tek bir Q # dosyasından Q # callables çalıştıran sorunsuz bir iş akışına olanak sağlar.</span><span class="sxs-lookup"><span data-stu-id="5d38f-157">Using Visual Studio Code or Visual Studio with the QDK extension allows for a seamless work flow in which we run Q# callables from only a single Q# file.</span></span>

<span data-ttu-id="5d38f-158">Bunun için, son olarak programın yürütmesini şunu girerek çağıracağız</span><span class="sxs-lookup"><span data-stu-id="5d38f-158">For this, we will ultimately invoke the program's execution by entering</span></span>
```dotnetcli
dotnet run
```
<span data-ttu-id="5d38f-159">komut satırında.</span><span class="sxs-lookup"><span data-stu-id="5d38f-159">in the command line.</span></span>
<span data-ttu-id="5d38f-160">En basit iş akışı, terminalin Dizin konumunun, VS Code ' deki tümleşik Terminal kullanılarak, Q # dosyası düzenlemeyle birlikte kolayca işlenebilen Q # dosyası ile aynı olduğu durumlarda kullanılır.</span><span class="sxs-lookup"><span data-stu-id="5d38f-160">The simplest workflow is when the terminal's directory location is the same as the Q# file, which can be easily handled alongside Q# file editing by using the integrated terminal in VS Code, for example.</span></span>
<span data-ttu-id="5d38f-161">Ancak, [ `dotnet run` komut](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) çok sayıda seçenek kabul eder ve ayrıca, aynı zamanda `--project <PATH>` Q # dosyasının konumuyla birlikte, program farklı bir konumdan da çalıştırılabilir.</span><span class="sxs-lookup"><span data-stu-id="5d38f-161">However, the [`dotnet run` command](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) accepts numerous options, and the program can also be run from a different location by simply providing `--project <PATH>` with the location of the Q# file.</span></span>


### <a name="add-entry-point-to-q-file"></a><span data-ttu-id="5d38f-162">Q # dosyasına giriş noktası ekle</span><span class="sxs-lookup"><span data-stu-id="5d38f-162">Add entry point to Q# file</span></span>

<span data-ttu-id="5d38f-163">Çoğu Q # dosyası birden fazla çağrılabilir içerir, bu yüzden doğal olarak, komut sağlamamız durumunda derleyicinin *hangi* çağrılabilir yürütme yapacağını bilmesini sağlamamız gerekir `dotnet run` .</span><span class="sxs-lookup"><span data-stu-id="5d38f-163">Most Q# files will contain more than one callable, so naturally we need to let the compiler know *which* callable to execute when we provide the `dotnet run` command.</span></span>
<span data-ttu-id="5d38f-164">Bu, Q # dosyasının kendisinde basit bir değişiklik ile yapılır:</span><span class="sxs-lookup"><span data-stu-id="5d38f-164">This is done with a simple change to the Q# file itself:</span></span> 
    - <span data-ttu-id="5d38f-165">`@EntryPoint()`çağrılabilir öğesinden hemen önce gelen bir satır ekleyin.</span><span class="sxs-lookup"><span data-stu-id="5d38f-165">add a line with `@EntryPoint()` directly preceding the callable.</span></span>

<span data-ttu-id="5d38f-166">Yukarıdaki dosya bundan böyle olur</span><span class="sxs-lookup"><span data-stu-id="5d38f-166">Our file from above would therefore become</span></span>
```qsharp
namespace NamespaceName {
    open Microsoft.Quantum.Intrinsic;     // for the H operation
    open Microsoft.Quantum.Measurement;   // for MResetZ

    @EntryPoint()
    operation MeasureSuperposition() : Result {
        using (q = Qubit()) { 
            H(q);
            return MResetZ(q);
        }
    }
}
```

<span data-ttu-id="5d38f-167">Şimdi, `dotnet run` komut satırından bir çağrısı `MeasureSuperposition` çalıştırılmakta ve döndürülen değer daha sonra doğrudan terminale yazdırılır.</span><span class="sxs-lookup"><span data-stu-id="5d38f-167">Now, a call of `dotnet run` from the command line leads to `MeasureSuperposition` being run, and the returned value is then printed directly to the terminal.</span></span>
<span data-ttu-id="5d38f-168">Bu nedenle, ya da `One` yazdırılmış görürsünüz `Zero` .</span><span class="sxs-lookup"><span data-stu-id="5d38f-168">So, you will see either `One` or `Zero` printed.</span></span> 

<span data-ttu-id="5d38f-169">Aşağıda, daha fazla callabaldığınıza bakılmaksızın yalnızca `MeasureSuperposition` çalıştırılacağını unutmayın.</span><span class="sxs-lookup"><span data-stu-id="5d38f-169">Note that it doesn't matter if you have more callables defined below it, only `MeasureSuperposition` will be run.</span></span>
<span data-ttu-id="5d38f-170">Buna ek olarak, çağrılabilir bir sorun değildir. Bu, çağrılabilir bir [belge açıklamalarını](xref:microsoft.quantum.guide.filestructure#documentation-comments) kendi bildiriminden önce içeriyorsa, `@EntryPoint()` öznitelik üzerine basitçe eklenebilir.</span><span class="sxs-lookup"><span data-stu-id="5d38f-170">Additionally, it's no problem if your callable includes [documentation comments](xref:microsoft.quantum.guide.filestructure#documentation-comments) before its declaration, the `@EntryPoint()` attribute can be simply placed above them.</span></span>

### <a name="callable-arguments"></a><span data-ttu-id="5d38f-171">Çağrılabilir bağımsız değişkenler</span><span class="sxs-lookup"><span data-stu-id="5d38f-171">Callable arguments</span></span>

<span data-ttu-id="5d38f-172">Şimdiye kadar, yalnızca giriş içermeyen bir işlem kabul ediyoruz.</span><span class="sxs-lookup"><span data-stu-id="5d38f-172">So far, we've only considered an operation that takes no inputs.</span></span>
<span data-ttu-id="5d38f-173">Benzer bir işlem gerçekleştirmek istediğinizi varsayalım, ancak birden fazla qubit üzerinde---bağımsız değişken olarak sunulan sayı.</span><span class="sxs-lookup"><span data-stu-id="5d38f-173">Suppose we wanted to perform a similar operation, but on multiple qubits---the number of which is provided as an argument.</span></span>
<span data-ttu-id="5d38f-174">Bu tür bir işlem şöyle yazılabilir</span><span class="sxs-lookup"><span data-stu-id="5d38f-174">Such an operation could be written as</span></span>
```qsharp
    operation MeasureSuperpositionArray(n : Int) : Result[] {
        using (qubits = Qubit[n]) {              // allocate a register of n qubits
            ApplyToEach(H, qubits);              // apply H to each qubit in the register
            return ForEach(MResetZ, qubits);     // perform MResetZ on each qubit, returns the resulting array
        }
    }
```
<span data-ttu-id="5d38f-175">döndürülen değer ölçüm sonuçlarının bir dizisidir.</span><span class="sxs-lookup"><span data-stu-id="5d38f-175">where the returned value is an array of the measurement results.</span></span>
<span data-ttu-id="5d38f-176">Ve [`ApplyToEach`](xref:microsoft.quantum.canon.applytoeach) [`ForEach`](xref:microsoft.quantum.arrays.foreach) ad alanlarında olduğunu ve [`Microsoft.Quantum.Canon`](xref:microsoft.quantum.canon) [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) `open` her biri için ek deyimler kullanılmasını unutmayın.</span><span class="sxs-lookup"><span data-stu-id="5d38f-176">Note that [`ApplyToEach`](xref:microsoft.quantum.canon.applytoeach) and [`ForEach`](xref:microsoft.quantum.arrays.foreach) are in the [`Microsoft.Quantum.Canon`](xref:microsoft.quantum.canon) and [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) namespaces, requiring additional `open` statements for each.</span></span>

<span data-ttu-id="5d38f-177">`@EntryPoint()`Özniteliği bu yeni işlemden önce taşıdığımızda (bir dosyada yalnızca bir satır olabilir), çalıştırmayı denemek yalnızca `dotnet run` ek komut satırı seçeneklerinin gerekli olduğunu ve bunları nasıl ifade ettiğine ilişkin bir hata mesajı sonucu olarak sonuçlanır.</span><span class="sxs-lookup"><span data-stu-id="5d38f-177">If we move the `@EntryPoint()` attribute to precede this new operation (note there can only be one such line in a file), attempting to run it with simply `dotnet run` results in an error message which indicates what additional command line options are required, and how to express them.</span></span>

<span data-ttu-id="5d38f-178">Komut satırı için genel biçim aslında olur `dotnet run [options]` ve çağrılabilir bağımsız değişkenler burada sağlanır.</span><span class="sxs-lookup"><span data-stu-id="5d38f-178">The general format for the command line is actually `dotnet run [options]`, and callable arguments are provided there.</span></span>
<span data-ttu-id="5d38f-179">Bu durumda, bağımsız değişkeni `n` eksik olur ve seçeneğini sağlamaları gerektiğini gösterir `-n <n>` .</span><span class="sxs-lookup"><span data-stu-id="5d38f-179">In this case, the argument `n` is missing, and it shows that we need to provide the option `-n <n>`.</span></span> <span data-ttu-id="5d38f-180">`MeasureSuperpositionArray` `n=4` Bu nedenle, qubit 'i çalıştırmak için</span><span class="sxs-lookup"><span data-stu-id="5d38f-180">To run `MeasureSuperpositionArray` for `n=4` qubits, we therefore use</span></span>

```dotnetcli
dotnet run -n 4
```

<span data-ttu-id="5d38f-181">aşağıdakine benzer bir çıktı oluşturma</span><span class="sxs-lookup"><span data-stu-id="5d38f-181">yielding an output similar to</span></span>

```output
[Zero,One,One,One]
```

<span data-ttu-id="5d38f-182">Bu kurs birden çok bağımsız değişkene genişletilir.</span><span class="sxs-lookup"><span data-stu-id="5d38f-182">This of course extends to multiple arguments.</span></span>

> [!NOTE]
> <span data-ttu-id="5d38f-183">' Da tanımlanan bağımsız değişken adları `camelCase` , derleyici tarafından, Q # girişi olarak kabul edilmesi için biraz değişmiş.</span><span class="sxs-lookup"><span data-stu-id="5d38f-183">Argument names defined in `camelCase` are slightly altered by the compiler to be accepted as Q# inputs.</span></span> <span data-ttu-id="5d38f-184">Örneğin, yerine `n` Yukarıdaki adı kullandık, `numQubits` Bu giriş, komut satırında yerine kullanılarak sağlanacaktır `--num-qubits 4` `-n 4` .</span><span class="sxs-lookup"><span data-stu-id="5d38f-184">For example, if instead of `n`, we used the name `numQubits` above, then this input would be provided in the command line via `--num-qubits 4` instead of `-n 4`.</span></span>

<span data-ttu-id="5d38f-185">Hata iletisi ayrıca, hedef makinenin nasıl değiştirileceği dahil olmak üzere kullanılabilecek diğer seçenekleri de sağlar.</span><span class="sxs-lookup"><span data-stu-id="5d38f-185">The error message also provides other options which can be used, including how to change the target machine.</span></span>

### <a name="different-target-machines"></a><span data-ttu-id="5d38f-186">Farklı hedef makineler</span><span class="sxs-lookup"><span data-stu-id="5d38f-186">Different target machines</span></span>

<span data-ttu-id="5d38f-187">İşlemlerimizin çıkışları gerçek qubit üzerinde eylemin beklenen sonuçları olduğundan, komut satırından varsayılan hedef makinenin tam durum çıkarkileri simülatörü `QuantumSimulator` ,</span><span class="sxs-lookup"><span data-stu-id="5d38f-187">As the outputs from our operations thus far have been the expected results of their action on real qubits, it's clear that the default target machine from the command line is the full-state quauntum simulator, `QuantumSimulator`.</span></span>
<span data-ttu-id="5d38f-188">Ancak, callables ' i `--simulator` (veya toplu) belirli bir hedef makinede çalıştırmayı söyleyebilirsiniz `-s` .</span><span class="sxs-lookup"><span data-stu-id="5d38f-188">However, we can instruct callables to be run on a specific target machine with the option `--simulator` (or the shorthand `-s`).</span></span>

<span data-ttu-id="5d38f-189">Örneğin, şunu üzerinde çalıştırabiliriz [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) :</span><span class="sxs-lookup"><span data-stu-id="5d38f-189">For example, we could run it on [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator):</span></span>

```dotnetcli
dotnet run -n 4 -s ResourcesEstimator
```

<span data-ttu-id="5d38f-190">Yazdırılan çıkış daha sonra</span><span class="sxs-lookup"><span data-stu-id="5d38f-190">The printed output is then</span></span>

```output
Metric          Sum
CNOT            0
QubitClifford   4
R               0
Measure         4
T               0
Depth           0
Width           4
BorrowedWidth   0
```

<span data-ttu-id="5d38f-191">Bu ölçümlerin neleri belirtebileceği hakkında ayrıntılı bilgi için bkz. [kaynak tahmini: raporlanan ölçümler](xref:microsoft.quantum.machines.resources-estimator#metrics-reported).</span><span class="sxs-lookup"><span data-stu-id="5d38f-191">For details on what these metrics indicate, see [Resource estimator: metrics reported](xref:microsoft.quantum.machines.resources-estimator#metrics-reported).</span></span>

### <a name="command-line-execution-summary"></a><span data-ttu-id="5d38f-192">Komut satırı yürütme Özeti</span><span class="sxs-lookup"><span data-stu-id="5d38f-192">Command line execution summary</span></span>
<br/>
<img src="../media/hostprograms_command_line_diagram.png" alt="Q# program from command line" width="700">

### <a name="non-q-dotnet-run-options"></a><span data-ttu-id="5d38f-193">Q olmayan `dotnet run` Seçenekler</span><span class="sxs-lookup"><span data-stu-id="5d38f-193">Non-Q# `dotnet run` options</span></span>

<span data-ttu-id="5d38f-194">Bu seçenekte kısaca bahsedildiği gibi `--project` , [ `dotnet run` komut](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) , Q # çağrılabilir bağımsız değişkenleriyle ilgisi olmayan seçenekleri de kabul eder.</span><span class="sxs-lookup"><span data-stu-id="5d38f-194">As we briefly mentioned above with the `--project` option, the [`dotnet run` command](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) also accepts options unrelated to the Q# callable arguments.</span></span>
<span data-ttu-id="5d38f-195">Her iki tür seçeneği de sağladıysanız, `dotnet` önce özel seçeneklerin önce sağlanması ve ardından bir delil `--` ve ardından Q # 'a özgü seçenekleri sağlaması gerekir.</span><span class="sxs-lookup"><span data-stu-id="5d38f-195">If providing both kinds of options, the `dotnet`-specific options must be provided first, followed by a delimeter `--`, and then the Q#-specific options.</span></span>
<span data-ttu-id="5d38f-196">Örneğin, yukarıdaki işlem için bir sayı ile birlikte bir yolu belirtir, aracılığıyla yürütülür `dotnet run --project <PATH> -- -n <n>` .</span><span class="sxs-lookup"><span data-stu-id="5d38f-196">For example, specifiying a path along with a number qubits for the operation above would be executed via `dotnet run --project <PATH> -- -n <n>`.</span></span>

## <a name="q-with-host-programs"></a><span data-ttu-id="5d38f-197">Ana bilgisayar programları ile Q #</span><span class="sxs-lookup"><span data-stu-id="5d38f-197">Q# with host programs</span></span>

<span data-ttu-id="5d38f-198">Q # dosyası birlikte, doğrudan komut satırından bir işlem veya işlev çağırma alternatifi, bir *konak programını* başka bir klasik dilde kullanmaktır.</span><span class="sxs-lookup"><span data-stu-id="5d38f-198">With our Q# file in hand, an alternative to calling an operation or function directly from the command line is to use a *host program* in another classical language.</span></span> <span data-ttu-id="5d38f-199">Özellikle, bu, Python veya C# ya da F # gibi bir .NET diliyle yapılabilir (breçların sake 'ı için burada yalnızca c# ayrıntı alınacaktır).</span><span class="sxs-lookup"><span data-stu-id="5d38f-199">Specifically, this can be done with either Python or a .NET language such as C# or F# (for the sake of brevity we will only detail C# here).</span></span>
<span data-ttu-id="5d38f-200">Birlikte çalışabilirliği etkinleştirmek için biraz daha fazla kurulum gerekir, ancak bu Ayrıntılar [yükleme kılavuzlarında](xref:microsoft.quantum.install)bulunabilir.</span><span class="sxs-lookup"><span data-stu-id="5d38f-200">A little more setup is required to enable the interoperability, but those details can be found in the [install guides](xref:microsoft.quantum.install).</span></span>

<span data-ttu-id="5d38f-201">Bir Nutshell 'de, durum artık `*.py` `*.cs` Q # dosyası ile aynı konumdaki bir ana bilgisayar program dosyası (ör. veya) içeriyor.</span><span class="sxs-lookup"><span data-stu-id="5d38f-201">In a nutshell, the situation now includes a host program file (e.g. `*.py` or `*.cs`) in the same location as our Q# file.</span></span>
<span data-ttu-id="5d38f-202">Şimdi çalıştırılan *ana bilgisayar* programı ve yürütme işlemi sırasında, q # dosyasındaki belirli Q # işlemlerini ve işlevleri çağırabilir.</span><span class="sxs-lookup"><span data-stu-id="5d38f-202">It's now the *host* program that gets run, and in the course of its execution it can call specific Q# operations and functions from the Q# file.</span></span>
<span data-ttu-id="5d38f-203">Birlikte çalışabilirliğin çekirdeği,, çağrılabilmesi için Q # dosyasının içeriğini ana bilgisayar programına erişilebilir hale getiren Q # derleyicisini temel alır.</span><span class="sxs-lookup"><span data-stu-id="5d38f-203">The core of the interoperability is based on the Q# compiler making the contents of the Q# file accessible to the host program so that they can be called.</span></span>

<span data-ttu-id="5d38f-204">Ana bilgisayar programı kullanmanın başlıca avantajlarından biri, Q # programı tarafından döndürülen klasik verilerin daha sonra konak dilinde işlenebilmesi olabilir.</span><span class="sxs-lookup"><span data-stu-id="5d38f-204">One of the main benefits of using a host program is that the classical data returned by the Q# program can then be further processed in the host language.</span></span>
<span data-ttu-id="5d38f-205">Bu, bazı gelişmiş veri işlemeden (örneğin, Q # ' da dahili olarak gerçekleştirilemediği bir şey) ve ardından bu sonuçlara göre daha fazla soru-cevap veya Q # sonuçlarını çizmek kadar basit bir şey olabilir.</span><span class="sxs-lookup"><span data-stu-id="5d38f-205">This could consist of some advanced data processing (e.g. something that can't be performed internally in Q#), and then calling further Q# actions based on those results, or something as simple as plotting the Q# results.</span></span>

<span data-ttu-id="5d38f-206">Genel düzen burada gösterilmektedir ve aşağıda Python ve C# için özel uygulamalar tartışıyoruz.</span><span class="sxs-lookup"><span data-stu-id="5d38f-206">The general scheme is shown here, and we discuss the specific implementations for Python and C# below.</span></span> <span data-ttu-id="5d38f-207">F # ana bilgisayar programını kullanan bir örnek, [.net birlikte çalışabilirlik örneklerinde](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet)bulunabilir.</span><span class="sxs-lookup"><span data-stu-id="5d38f-207">A sample using an F# host program can be found at the [.NET interoperability samples](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet).</span></span>

<br/>
<img src="../media/hostprograms_host_program_diagram.png" alt="Q# program from a host program" width="700">

> [!NOTE]
> <span data-ttu-id="5d38f-208">`@EntryPoint()`Q # komut satırı uygulamaları için kullanılan öznitelik konak programlarıyla birlikte kullanılamaz.</span><span class="sxs-lookup"><span data-stu-id="5d38f-208">The `@EntryPoint()` attribute used for Q# command line applications cannot be used with host programs.</span></span>
> <span data-ttu-id="5d38f-209">Bir ana bilgisayar tarafından çağrılan Q # dosyasında varsa bir hata oluşur.</span><span class="sxs-lookup"><span data-stu-id="5d38f-209">An error will be raised if it is present in the Q# file being called by a host.</span></span> 

<span data-ttu-id="5d38f-210">Farklı ana bilgisayar programlarıyla çalışmak için, bir Q # dosyasında gerekli değişiklik yoktur `*.qs` .</span><span class="sxs-lookup"><span data-stu-id="5d38f-210">To work with different host programs, there are no changes required to a `*.qs` Q# file.</span></span>
<span data-ttu-id="5d38f-211">Aşağıdaki konak program uygulamalarının hepsi aynı Q # dosyasıyla çalışır:</span><span class="sxs-lookup"><span data-stu-id="5d38f-211">The following host program implementations all work with the same Q# file:</span></span>

```qsharp
namespace NamespaceName {
    open Microsoft.Quantum.Intrinsic;     // contains H
    open Microsoft.Quantum.Measurement;   // MResetZ
    open Microsoft.Quantum.Canon;         // ApplyToEach
    open Microsoft.Quantum.Arrays;        // ForEach

    operation MeasureSuperposition() : Result {
        using (q = Qubit()) { 
            H(q);
            return MResetZ(q);
        }
    }

    operation MeasureSuperpositionArray(n : Int) : Result[] {
        using (qubits = Qubit[n]) {  
            ApplyToEach(H, qubits); 
            return ForEach(MResetZ, qubits);    
        }
    }
}
```

<span data-ttu-id="5d38f-212">İlgilendiğiniz ana bilgisayar dilinize karşılık gelen sekmeyi seçin.</span><span class="sxs-lookup"><span data-stu-id="5d38f-212">Select the tab corresponding to your host language of interest.</span></span>

### <a name="python"></a>[<span data-ttu-id="5d38f-213">Python</span><span class="sxs-lookup"><span data-stu-id="5d38f-213">Python</span></span>](#tab/tabid-python)
<span data-ttu-id="5d38f-214">Bir Python ana bilgisayar programı şu şekilde oluşturulur:</span><span class="sxs-lookup"><span data-stu-id="5d38f-214">A Python host program is constructed as follows:</span></span>
1. <span data-ttu-id="5d38f-215">`qsharp`Q # birlikte çalışabilirlik için modül yükleyicisini kaydeden modülünü içeri aktarın.</span><span class="sxs-lookup"><span data-stu-id="5d38f-215">Import the `qsharp` module, which registers the module loader for Q# interoperability.</span></span> 
    <span data-ttu-id="5d38f-216">Bu, Q # ad alanlarının Python modülleri olarak görünmesine izin verir, buradan "içeri aktarabilir".</span><span class="sxs-lookup"><span data-stu-id="5d38f-216">This allows Q# namespaces to appear as Python modules, from which we can "import" Q# callables.</span></span>
    <span data-ttu-id="5d38f-217">Teknik olarak içeri aktarılan ve bunlara çağırmaya izin veren Python saplamalarının kendisine Teknik olarak olmadığını unutmayın.</span><span class="sxs-lookup"><span data-stu-id="5d38f-217">Note that it is technically not the Q# callables themselves which are imported, but rather Python stubs which allow calling into them.</span></span>
    <span data-ttu-id="5d38f-218">Bunlar daha sonra Python sınıflarının nesneleri olarak davranır, bu durumda, yürütme için işlemi gönderecek hedef makineleri belirtmek için yöntemler kullanıyoruz.</span><span class="sxs-lookup"><span data-stu-id="5d38f-218">These then behave as objects of Python classes, on which we use methods to specify the target machines to send the operation to for execution.</span></span>

2. <span data-ttu-id="5d38f-219">Bu durumda---doğrudan çağıracağız Bu Q # callables 'i içeri aktarın `MeasureSuperposition` ve `MeasureSuperpositionArray` .</span><span class="sxs-lookup"><span data-stu-id="5d38f-219">Import those Q# callables which we will directly invoke---in this case, `MeasureSuperposition` and `MeasureSuperpositionArray`.</span></span>
    ```python
    import qsharp
    from NamespaceName import MeasureSuperposition, MeasureSuperpositionArray
    ```
    <span data-ttu-id="5d38f-220">`qsharp`Modül içeri aktarılmışsa Ayrıca, doğrudan Q # kitaplığı ad alanlarından callables 'yi içeri aktarabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="5d38f-220">With the `qsharp` module imported, you can also import callables directly from the Q# library namespaces.</span></span>

3. <span data-ttu-id="5d38f-221">Diğer herhangi bir Python kodu arasında, artık bu callabları belirli hedef makinelere çağırabilir ve geri dönüşlerini, daha fazla kullanım için (bir değer döndürdüler) değişkenlere atayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="5d38f-221">Among any other Python code, you can now call those callables on specific target machines, and assign their returns to variables (if they return a value) for further use.</span></span>

#### <a name="specifying-target-machines"></a><span data-ttu-id="5d38f-222">Hedef makineleri belirtme</span><span class="sxs-lookup"><span data-stu-id="5d38f-222">Specifying target machines</span></span>
<span data-ttu-id="5d38f-223">Belirli bir hedef makinede çalıştırılacak bir işlemin çağrılması, içeri aktarılan nesnede farklı Python yöntemleri aracılığıyla yapılır.</span><span class="sxs-lookup"><span data-stu-id="5d38f-223">Calling an operation to be run on a specific target machine is done via different Python methods on the imported object.</span></span>
<span data-ttu-id="5d38f-224">Örneğin, `.simulate(<args>)` `QuantumSimulator` işlemini çalıştırmak için öğesini kullanır, ancak `.estimate_resources(<args>)` bunu yapar `ResourcesEstimator` .</span><span class="sxs-lookup"><span data-stu-id="5d38f-224">For example, `.simulate(<args>)`, uses the `QuantumSimulator` to run the operation, whereas `.estimate_resources(<args>)` does so on the `ResourcesEstimator`.</span></span>

#### <a name="passing-inputs-to-q"></a><span data-ttu-id="5d38f-225">Girdileri Q 'a geçirme\#</span><span class="sxs-lookup"><span data-stu-id="5d38f-225">Passing inputs to Q\#</span></span>
<span data-ttu-id="5d38f-226">Q # çağrılabilir bağımsız değişkenleri, anahtar sözcüğünün Q # çağrılabilir tanımında bağımsız değişken adı olduğu anahtar sözcük bağımsız değişkeni biçiminde sağlanmalıdır.</span><span class="sxs-lookup"><span data-stu-id="5d38f-226">Arguments for the Q# callable should be provided in the form of a keyword argument, where the keyword is the argument name in the Q# callable definition.</span></span>
<span data-ttu-id="5d38f-227">Yani, `MeasureSuperpositionArray.simulate(n=4)` geçerlidir, ancak `MeasureSuperpositionArray.simulate(4)` bir hata oluşturur.</span><span class="sxs-lookup"><span data-stu-id="5d38f-227">That is, `MeasureSuperpositionArray.simulate(n=4)` is valid, whereas `MeasureSuperpositionArray.simulate(4)` would throw an error.</span></span>

<span data-ttu-id="5d38f-228">Bu nedenle, Python ana bilgisayar programı</span><span class="sxs-lookup"><span data-stu-id="5d38f-228">Therefore, the Python host program</span></span> 

```python
import qsharp
from NamespaceName import MeasureSuperposition, MeasureSuperpositionArray

single_qubit_result = MeasureSuperposition.simulate()
single_qubit_resources = MeasureSuperposition.estimate_resources()

multi_qubit_result = MeasureSuperpositionArray.simulate(n=4)
multi_qubit_resources = MeasureSuperpositionArray.estimate_resources(n=4)

print('Single qubit:\n' + str(single_qubit_result))
print(single_qubit_resources)

print('\nMultiple qubits:\n' + str(multi_qubit_result))
print(multi_qubit_resources)
```

<span data-ttu-id="5d38f-229">aşağıdakine benzer bir çıktı oluşur:</span><span class="sxs-lookup"><span data-stu-id="5d38f-229">results in an output like the following:</span></span>

```python
Single qubit:
1
{'CNOT': 0, 'QubitClifford': 1, 'R': 0, 'Measure': 1, 'T': 0, 'Depth': 0, 'Width': 1, 'BorrowedWidth': 0}

Multiple qubits:
[0, 1, 1, 1]
{'CNOT': 0, 'QubitClifford': 4, 'R': 0, 'Measure': 4, 'T': 0, 'Depth': 0, 'Width': 4, 'BorrowedWidth': 0}
```

### <a name="c"></a>[<span data-ttu-id="5d38f-230">C#</span><span class="sxs-lookup"><span data-stu-id="5d38f-230">C#</span></span>](#tab/tabid-csharp)

<span data-ttu-id="5d38f-231">C# ana bilgisayar programında birden çok bileşen vardır ve bunlar, c# üzerinde oluşturulan simülatörleri gibi bazı QDK bileşenleriyle çok daha yakından çalışmaktadır.</span><span class="sxs-lookup"><span data-stu-id="5d38f-231">A C# host program has multiple components, and works very closely with some components of the QDK, such as the simulators, which are themselves built on C#.</span></span>

<span data-ttu-id="5d38f-232">Q # derleyicisi, Q # dosyanızdaki Q # ad alanından bir equivalently adlı C# ad alanı oluşturarak burada işe yarar.</span><span class="sxs-lookup"><span data-stu-id="5d38f-232">The Q# compiler works here by generating an equivalently named C# namespace from the Q# namespace in our Q# file.</span></span>
<span data-ttu-id="5d38f-233">Daha sonra, her Q # callables veya içinde tanımlanan türler için bir equivalently adlandırılmış C# sınıfı oluşturur.</span><span class="sxs-lookup"><span data-stu-id="5d38f-233">It further generates an equivalently named C# class for each of the Q# callables or types defined therein.</span></span>

<span data-ttu-id="5d38f-234">İlk olarak, ana programımızda `using` , `open` Q # dosyanızdaki deyimler için kabaca bir şekilde olan deyimlerle kullanılabilen tüm sınıfları sunuyoruz:</span><span class="sxs-lookup"><span data-stu-id="5d38f-234">First, we make any classes used in our host program available with `using` statements, which are roughly analagous to the `open` statements in our Q# file:</span></span>

```csharp
using System;
using System.Threading.Tasks;
using Microsoft.Quantum.Simulation.Simulators;    // contains the target machines (e.g. QuantumSimulator, ResourcesEstimator)
using NamespaceName;                              // make the Q# namespace available
```

<span data-ttu-id="5d38f-235">Daha sonra C# ad boşluğumuzu, diğer birkaç bit ve parçadan (örneğin, Q # callables için bilgi işlem bağımsız değişkenleri) bildiririz.</span><span class="sxs-lookup"><span data-stu-id="5d38f-235">Next, we declare our C# namespace, a few other bits and pieces (see the full code block below), and then any classical programming we would like (e.g. computing arguments for the Q# callables).</span></span>
<span data-ttu-id="5d38f-236">İkinci durumda gerekli değildir, ancak bu tür bir örnek [.net birlikte çalışabilirlik örneğinde](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet)bulunabilir.</span><span class="sxs-lookup"><span data-stu-id="5d38f-236">The latter isn't necessary in our case, but an example of such usage can be found at the  [.NET interoperability sample](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet).</span></span>

#### <a name="target-machines"></a><span data-ttu-id="5d38f-237">Hedef makineler</span><span class="sxs-lookup"><span data-stu-id="5d38f-237">Target machines</span></span>

<span data-ttu-id="5d38f-238">Q # ' a geri döndüğünüzde, operasyonlarımızı yürütediğimiz hedef makinenin bir örneğini oluşturmamız gerekir.</span><span class="sxs-lookup"><span data-stu-id="5d38f-238">Getting back to Q#, we must create an instance of whatever target machine we will execute our operations on.</span></span>

```csharp
            using var sim = new QuantumSimulator();
```

<span data-ttu-id="5d38f-239">Diğer hedef makinelerin kullanılması, farklı bir örnek oluşturmak kadar basittir, ancak bunu yapmanın ve döndürmesinin işlem biçimi biraz farklı olabilir.</span><span class="sxs-lookup"><span data-stu-id="5d38f-239">Using other target machines is as simple as instantiating a different one, although the manner of doing so and processing the returns can be slightly different.</span></span>
<span data-ttu-id="5d38f-240">Kısaltma için, şu an için ' i kullanıma sunuyoruz [`QuantumSimulator`](xref:microsoft.quantum.machines.full-state-simulator) ve aşağıdakileri dahil ediyoruz [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) [below](#including-the-resources-estimator).</span><span class="sxs-lookup"><span data-stu-id="5d38f-240">For brevity, we stick to the [`QuantumSimulator`](xref:microsoft.quantum.machines.full-state-simulator) for now, and include the [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) [below](#including-the-resources-estimator).</span></span>

<span data-ttu-id="5d38f-241">Q # işlemlerinden oluşturulan her C# sınıfının `Run` , hedef makine örneği olması gereken ilk bağımsız değişkeni olan bir yöntemi vardır.</span><span class="sxs-lookup"><span data-stu-id="5d38f-241">Each C# class generated from the Q# operations have a `Run` method, the first argument of which must be the target machine instance.</span></span>
<span data-ttu-id="5d38f-242">Bu nedenle, `MeasureSuperposition` üzerinde çalıştırmak için `QuantumSimulator` kullanırız `MeasureSuperposition.Run(sim)` .</span><span class="sxs-lookup"><span data-stu-id="5d38f-242">So, to run `MeasureSuperposition` on the `QuantumSimulator`, we use `MeasureSuperposition.Run(sim)`.</span></span>
<span data-ttu-id="5d38f-243">Döndürülen sonuçlar daha sonra C# dilinde değişkenlere atanabilir:</span><span class="sxs-lookup"><span data-stu-id="5d38f-243">The returned results can then be assigned to variables in C#:</span></span>

```csharp
            var singleQubitResult = await MeasureSuperposition.Run(sim);
```

> [!NOTE]
> <span data-ttu-id="5d38f-244">`Run`Bu, gerçek hisse donanımı için durum olacağı için zaman uyumsuz olarak yürütülür ve bu nedenle `await` anahtar sözcüğü, görev tamamlanana kadar daha fazla yürütmeyi engeller.</span><span class="sxs-lookup"><span data-stu-id="5d38f-244">The `Run` method is executed asynchronously because this will be the case for real quantum hardware, and therefore the `await` keyword blocks further execution until the task completes.</span></span>

<span data-ttu-id="5d38f-245">Q # çağrılabilir değeri herhangi bir dönüşe sahip değilse (örneğin, dönüş türüne sahipse `Unit` ), yürütme yine de bir değişkene atamadan aynı şekilde yapılabilir.</span><span class="sxs-lookup"><span data-stu-id="5d38f-245">If the Q# callable does not have any returns (i.e. has return type `Unit`), then the execution can still be done in the same manner without assigning it to a variable.</span></span>
<span data-ttu-id="5d38f-246">Bu durumda, tüm satır yalnızca</span><span class="sxs-lookup"><span data-stu-id="5d38f-246">In that case, the entire line would simply consist of</span></span> 
```csharp
await <callable>.Run(<simulator>);
```

#### <a name="arguments"></a><span data-ttu-id="5d38f-247">Arguments</span><span class="sxs-lookup"><span data-stu-id="5d38f-247">Arguments</span></span>

<span data-ttu-id="5d38f-248">İstenen Q # çağrılabilir bağımsız değişkenleri, hedef makineyi afleyici ek bağımsız değişkenler olarak geçirilir.</span><span class="sxs-lookup"><span data-stu-id="5d38f-248">Any arguments to the Q# callable are simply passed as additional arguments afer the target machine.</span></span>
<span data-ttu-id="5d38f-249">Bu nedenle, `MeasureSuperpositionArray` `n=4` qubits 'in sonuçları aracılığıyla getirilir</span><span class="sxs-lookup"><span data-stu-id="5d38f-249">Hence the results of `MeasureSuperpositionArray` on `n=4` qubits would fetched via</span></span> 

```csharp
            var multiQubitResult = await MeasureSuperpositionArray.Run(sim, 4);
```

<span data-ttu-id="5d38f-250">Böylece tam bir C# ana bilgisayar programı şöyle görünebilir</span><span class="sxs-lookup"><span data-stu-id="5d38f-250">A full C# host program could thus look like</span></span>

```csharp
using System;
using System.Threading.Tasks;
using Microsoft.Quantum.Simulation.Simulators;
using NamespaceName;

namespace host
{
    static class Program
    {
        static async Task Main(string[] args)
        {
            using var sim = new QuantumSimulator();

            var singleQubitResult = await MeasureSuperposition.Run(sim);
            var multiQubitResult = await MeasureSuperpositionArray.Run(sim, 4);

            Console.WriteLine($"Single qubit result: {singleQubitResult}");
            Console.WriteLine($"Multiple qubit result: {multiQubitResult}");
        }
    }
}
```

<span data-ttu-id="5d38f-251">C# dosyasının konumunda, ana bilgisayar programı komut satırından şunu girerek çalıştırılabilir:</span><span class="sxs-lookup"><span data-stu-id="5d38f-251">At the location of the C# file, the host program can be run from the command line by entering</span></span>
```dotnetcli
dotnet run
```
<span data-ttu-id="5d38f-252">Bu durumda, şuna benzer şekilde konsola yazılan çıktıyı görürsünüz:</span><span class="sxs-lookup"><span data-stu-id="5d38f-252">and in this case you will see output written to the console similar to</span></span> 
```output
Single qubit result: One
Multiple qubit result: [One,One,Zero,Zero]
```

> [!NOTE]
> <span data-ttu-id="5d38f-253">Derleyicinin ad alanları ile birlikte çalışabilirliği nedeniyle, bildirim olmadan Q # callablımlarımızı de kullanılabilir hale getirir `using NamespaceName;` ve C# ad alanı başlığını bununla eşleştirmeniz yeterlidir.</span><span class="sxs-lookup"><span data-stu-id="5d38f-253">Due to the compiler's interoperability with namespaces, we could alternatively make our Q# callables available without the `using NamespaceName;` statement, and simply matching the C# namespace title to it.</span></span>
> <span data-ttu-id="5d38f-254">Diğer bir deyişle, `namespace host` ile değiştirin `namespace NamespaceName` .</span><span class="sxs-lookup"><span data-stu-id="5d38f-254">That is, by replacing `namespace host` with `namespace NamespaceName`.</span></span>

#### <a name="including-the-resources-estimator"></a><span data-ttu-id="5d38f-255">Kaynak tahmin aracı dahil</span><span class="sxs-lookup"><span data-stu-id="5d38f-255">Including the resources estimator</span></span>

<span data-ttu-id="5d38f-256">, [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) Çıktıyı almak için biraz farklı bir uygulama gerektirir.</span><span class="sxs-lookup"><span data-stu-id="5d38f-256">The [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) requires a slightly different implementation to retrieve the output.</span></span>

<span data-ttu-id="5d38f-257">İlk olarak, bunları bir ifadesiyle bir değişken olarak Örneklemek yerine `using` (ile yaptığımız gibi `QuantumSimulator` ), ile sınıfın nesnelerini doğrudan örnekliyoruz</span><span class="sxs-lookup"><span data-stu-id="5d38f-257">Firstly, instead of instantiating them as a variable with a `using` statement (as we do with the `QuantumSimulator`), we more directly instantiate objects of the class via</span></span>

```csharp
            var estimatorSingleQ = new ResourcesEstimator();
            var estimatorMultiQ = new ResourcesEstimator();
```

<span data-ttu-id="5d38f-258">Tek bir hedef Benzetici yerine birden çok Q # işlemi tarafından kullanılacak şekilde, her biri için bir tane örnekliyoruz.</span><span class="sxs-lookup"><span data-stu-id="5d38f-258">Notice that instead of a single target simulator to be used by multiple Q# operations, we have instantiated one for each.</span></span> <span data-ttu-id="5d38f-259">Bunun nedeni, nesnelerin kendisi hedef makineler olarak kullanıldığında değiştirilmektedir ve sonuçları daha sonra sınıf yöntemiyle elde edilebilir `.ToTSV()` .</span><span class="sxs-lookup"><span data-stu-id="5d38f-259">This is because the objects themselves are modified when used as target machines, and their results can then be retrieved afterwards with the class method `.ToTSV()`.</span></span>

<span data-ttu-id="5d38f-260">Kaynakları kaynak estimators üzerinde çalıştırmak için şunu kullanıyoruz</span><span class="sxs-lookup"><span data-stu-id="5d38f-260">To run the operations on the resource estimators, we use</span></span>

```csharp
            await MeasureSuperposition.Run(estimatorSingleQ);
            await MeasureSuperpositionArray.Run(estimatorMultiQ, 4);
```
<span data-ttu-id="5d38f-261">ardından sonuçları ve ile sekmeyle ayrılmış değerler (TSV) olarak getirin `estimatorSingleQ.ToTSV()` `estimatorMultiQ.ToTSV()` .</span><span class="sxs-lookup"><span data-stu-id="5d38f-261">and then fetch the results as tab-separated-values (TSV) with `estimatorSingleQ.ToTSV()` and `estimatorMultiQ.ToTSV()`.</span></span>

<span data-ttu-id="5d38f-262">Bu nedenle, hem hem de kullanan tam bir C# ana bilgisayar `QuantumSimulator` programı `ResourcesEstimator` şu biçimde olabilir:</span><span class="sxs-lookup"><span data-stu-id="5d38f-262">So, a full C# host program making use of both the `QuantumSimulator` and `ResourcesEstimator` could take the form:</span></span>

```csharp
using System;
using System.Threading.Tasks;
using Microsoft.Quantum.Simulation.Simulators;
using NamespaceName;

namespace host
{
    static class Program
    {
        static async Task Main(string[] args)
        {
            using var sim = new QuantumSimulator();
            var estimatorSingleQ = new ResourcesEstimator();
            var estimatorMultiQ = new ResourcesEstimator();

            var singleQubitResult = await MeasureSuperposition.Run(sim);
            var multiQubitResult = await MeasureSuperpositionArray.Run(sim, 4);

            await MeasureSuperposition.Run(estimatorSingleQ);
            await MeasureSuperpositionArray.Run(estimatorMultiQ, 4);

            Console.WriteLine($"Single qubit result: {singleQubitResult}");
            Console.WriteLine("Single qubit resources:");
            Console.WriteLine(estimatorSingleQ.ToTSV());

            Console.WriteLine($"\nMultiple qubit result: {multiQubitResult}");
            Console.WriteLine("Multiple qubit resources:");
            Console.WriteLine(estimatorMultiQ.ToTSV());
        }
    }
}
```


<span data-ttu-id="5d38f-263">aşağıdakine benzer bir çıktı verecek</span><span class="sxs-lookup"><span data-stu-id="5d38f-263">which would yield output similar to</span></span>

```output
Single qubit result: One
Single qubit resources:
Metric          Sum
CNOT            0
QubitClifford   1
R               0
Measure         1
T               0
Depth           0
Width           1
BorrowedWidth   0

Multiple qubit result: [One,One,One,Zero]
Multiple qubit resources:
Metric          Sum
CNOT            0
QubitClifford   4
R               0
Measure         4
T               0
Depth           0
Width           4
BorrowedWidth   0
```

***

## <a name="q-jupyter-notebooks"></a><span data-ttu-id="5d38f-264">Q# Jupyter Notebook’ları</span><span class="sxs-lookup"><span data-stu-id="5d38f-264">Q# Jupyter Notebooks</span></span>
<span data-ttu-id="5d38f-265">S # Jupyter Not defterleri, tek bir not defterinde soru, Not ve diğer içeriklerden oluşan---Q # callables 'i tanımlamanızı, derlemenize ve çalıştırmanıza olanak tanıyan IQ # çekirdeğini kullanır.</span><span class="sxs-lookup"><span data-stu-id="5d38f-265">Q# Jupyter Notebooks make use of the IQ# kernel, which allows you to define, compile, and run Q# callables in a single notebook---all alongside instructions, notes, and other content.</span></span>
<span data-ttu-id="5d38f-266">Diğer bir deyişle, Q # dosyalarının içeriğini içeri ve dışarı aktarmak mümkün olsa `*.qs` da, bunlar yürütme modelinde gerekli değildir.</span><span class="sxs-lookup"><span data-stu-id="5d38f-266">This means that while it is possible to import and use the contents of `*.qs` Q# files, they are not necessary in the execution model.</span></span>

<span data-ttu-id="5d38f-267">Burada, yukarıda tanımlanan Q # işlemlerini nasıl çalıştıracağınızı ayrıntılarız, ancak q # Jupyıter not defterlerini kullanmaya yönelik daha geniş bir giriş, [q # ve jupi not defterlerine giriş olarak](https://github.com/microsoft/Quantum/blob/master/samples/getting-started/intro-to-iqsharp/Notebook.ipynb)sunulmaktadır.</span><span class="sxs-lookup"><span data-stu-id="5d38f-267">Here, we will detail how to run the Q# operations defined above, but a more broad introduction to using Q# Jupyter Notebooks is provided at [Intro to Q# and Jupyter Notebooks](https://github.com/microsoft/Quantum/blob/master/samples/getting-started/intro-to-iqsharp/Notebook.ipynb).</span></span>

### <a name="defining-operations"></a><span data-ttu-id="5d38f-268">İşlemleri tanımlama</span><span class="sxs-lookup"><span data-stu-id="5d38f-268">Defining operations</span></span>

<span data-ttu-id="5d38f-269">Bir Q # Jupyter Notebook, bir q # dosyasının ad alanının içinden yaptığımız gibi Q # kodunu girersiniz.</span><span class="sxs-lookup"><span data-stu-id="5d38f-269">In a Q# Jupyter Notebook, you enter Q# code just as we would from inside the namespace of a Q# file.</span></span>

<span data-ttu-id="5d38f-270">Bu nedenle, ilgili ad alanları için deyimlerle [Q # standart kitaplıklarından](xref:microsoft.quantum.qsharplibintro) callables 'e erişimi etkinleştirebiliriz `open` .</span><span class="sxs-lookup"><span data-stu-id="5d38f-270">So, we can enable access to callables from the [Q# standard libraries](xref:microsoft.quantum.qsharplibintro) with `open` statements for their respective namespaces.</span></span>
<span data-ttu-id="5d38f-271">Bu tür bir deyime sahip bir hücreyi çalıştırırken, bu ad alanlarından alınan tanımlar çalışma alanı boyunca kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="5d38f-271">Upon running a cell with such a statement, the definitions from those namespaces are available throughout the workspace.</span></span>

> [!NOTE]
> <span data-ttu-id="5d38f-272">[Microsoft. hisse. iç](xref:microsoft.quantum.intrinsic) ve [Microsoft. hisse. Canon](xref:microsoft.quantum.canon) (örn.) ile Callables [`H`](xref:microsoft.quantum.intrinsic.h) [`ApplyToEach`](xref:microsoft.quantum.canon.applytoeach) , Q # jupi Not defterlerindeki hücrelerde tanımlanan işlemler için otomatik olarak kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="5d38f-272">Callables from [Microsoft.Quantum.Intrinsic](xref:microsoft.quantum.intrinsic) and [Microsoft.Quantum.Canon](xref:microsoft.quantum.canon) (e.g. [`H`](xref:microsoft.quantum.intrinsic.h) and [`ApplyToEach`](xref:microsoft.quantum.canon.applytoeach)) are automatically available to operations defined within cells in Q# Jupyter Notebooks.</span></span>
> <span data-ttu-id="5d38f-273">Ancak, bu, dış Q # kaynak dosyalarından alınan kod için (örneğin, [Q # ve jupi not defterlerine giriş olarak](https://github.com/microsoft/Quantum/blob/master/samples/getting-started/intro-to-iqsharp/Notebook.ipynb)gösterilen bir işlem) doğru değildir.</span><span class="sxs-lookup"><span data-stu-id="5d38f-273">However, this is not true for code brought in from external Q# source files (a process shown at [Intro to Q# and Jupyter Notebooks](https://github.com/microsoft/Quantum/blob/master/samples/getting-started/intro-to-iqsharp/Notebook.ipynb)).</span></span> 
> 

<span data-ttu-id="5d38f-274">Benzer şekilde, tanımlama işlemleri yalnızca Q # kodu yazmak ve hücreyi çalıştırmak için gereklidir.</span><span class="sxs-lookup"><span data-stu-id="5d38f-274">Similarly, defining operations requires only writing the Q# code and running the cell.</span></span>

<img src="../media/hostprograms_jupyter_op_def_crop.png" alt="Jupyter cell defining Q# operations" width="600">

<span data-ttu-id="5d38f-275">Daha sonra çıktı bu işlemleri listeler, daha sonra gelecekteki hücrelerden çağrılabilir.</span><span class="sxs-lookup"><span data-stu-id="5d38f-275">The output then lists those operations, which can then be called from future cells.</span></span>

### <a name="target-machines"></a><span data-ttu-id="5d38f-276">Hedef makineler</span><span class="sxs-lookup"><span data-stu-id="5d38f-276">Target machines</span></span>

<span data-ttu-id="5d38f-277">Belirli hedef makinelerde işlem çalıştırma işlevselliği [IQ # Magic komutları](xref:microsoft.quantum.guide.quickref.iqsharp)aracılığıyla sağlanır.</span><span class="sxs-lookup"><span data-stu-id="5d38f-277">The functionality to run operations on specific target machines is provided via [IQ# Magic Commands](xref:microsoft.quantum.guide.quickref.iqsharp).</span></span>
<span data-ttu-id="5d38f-278">Örneğin, `%simulate` `QuantumSimulator` öğesini kullanır ve şunları `%estimate` kullanır `ResourcesEstimator` :</span><span class="sxs-lookup"><span data-stu-id="5d38f-278">For example, `%simulate` makes use of the `QuantumSimulator`, and `%estimate` uses the `ResourcesEstimator`:</span></span>

<img src="../media/hostprograms_jupyter_no_args_sim_est_crop.png" alt="Simulate and estimate resources Jupyter cell" width="500">

### <a name="passing-inputs-to-functions-and-operations"></a><span data-ttu-id="5d38f-279">İşlevlere ve işlemlere giriş geçirme</span><span class="sxs-lookup"><span data-stu-id="5d38f-279">Passing inputs to functions and operations</span></span>

<span data-ttu-id="5d38f-280">Şu anda yürütme Magic komutları yalnızca bağımsız değişken içermeyen işlemlerle birlikte kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="5d38f-280">Currently the execution magic commands can only be used with operations that take no arguments.</span></span> <span data-ttu-id="5d38f-281">Bu nedenle, çalıştırmak için `MeasureSuperpositionArray` bir "sarmalayıcı" işlemi tanımlamamız gerekir ve bu işlemden sonra işlemi bağımsız değişkenlerle çağırır:</span><span class="sxs-lookup"><span data-stu-id="5d38f-281">So, to run `MeasureSuperpositionArray`, we need to define a "wrapper" operation which then calls the operation with the arguments:</span></span>

<img src="../media/hostprograms_jupyter_wrapper_def_sim_crop.png" alt="Wrapper function and simulate Jupyter cell" width="550">

<span data-ttu-id="5d38f-282">Bu işlem, `%estimate` ve diğer yürütme komutlarıyla benzer şekilde kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="5d38f-282">This operation can of course be used similarly with `%estimate` and other execution commands.</span></span>