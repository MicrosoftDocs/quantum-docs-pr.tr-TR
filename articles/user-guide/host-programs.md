---
title: Program çalıştırma yolları Q#
description: Programları çalıştırmanın farklı yollarına genel bakış Q# . Komut isteminden, Q# jupi Not defterleri ve Python veya bir .net dilinde klasik ana bilgisayar programları.
author: gillenhaalb
ms.author: a-gibec
ms.date: 05/15/2020
ms.topic: article
uid: microsoft.quantum.guide.host-programs
no-loc:
- Q#
- $$v
ms.openlocfilehash: 2c5bdebc826bb85f6d7e0ade6232e15e29e8fb19
ms.sourcegitcommit: b930bb59a1ba8f41d2edc9ed98197109aa8c7f1b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96231698"
---
# <a name="ways-to-run-a-no-locq-program"></a><span data-ttu-id="c8e20-104">Program çalıştırma yolları Q#</span><span class="sxs-lookup"><span data-stu-id="c8e20-104">Ways to run a Q# program</span></span>

<span data-ttu-id="c8e20-105">Hisse geliştirme setinin en büyük güçlerinden biri, platformlar ve geliştirme ortamları arasında esneklik sağlar.</span><span class="sxs-lookup"><span data-stu-id="c8e20-105">One of the Quantum Development Kit's greatest strengths is its flexibility across platforms and development environments.</span></span>
<span data-ttu-id="c8e20-106">Bununla birlikte, bu durum, yeni Q# kullanıcıların kendi kendini karıştırarak veya daha fazla bilgi edinmek için, bkz. [Install kılavuzunda](xref:microsoft.quantum.install)bulunan çok sayıda seçenek.</span><span class="sxs-lookup"><span data-stu-id="c8e20-106">However, this also means that new Q# users may find themselves confused or overwhelmed by the numerous options found in the [install guide](xref:microsoft.quantum.install).</span></span>
<span data-ttu-id="c8e20-107">Bu sayfada, bir program çalıştırıldığında ne olduğunu açıkladık Q# ve kullanıcıların bunu yapabilecekleri farklı yollarla karşılaştırıyoruz.</span><span class="sxs-lookup"><span data-stu-id="c8e20-107">On this page, we explain what happens when a Q# program is run, and compare the different ways in which users can do so.</span></span>

<span data-ttu-id="c8e20-108">Birincil ayrım, çalıştırılabilir bir değer olabilir Q# :</span><span class="sxs-lookup"><span data-stu-id="c8e20-108">A primary distinction is that Q# can be run:</span></span>
- <span data-ttu-id="c8e20-109">tek başına bir uygulama olarak, Q# söz konusu tek dildir ve program doğrudan çağırılır.</span><span class="sxs-lookup"><span data-stu-id="c8e20-109">as a standalone application, where Q# is the only language involved and the program is invoked directly.</span></span> <span data-ttu-id="c8e20-110">Bu kategoriye aslında iki yöntem yer almalıdır:</span><span class="sxs-lookup"><span data-stu-id="c8e20-110">Two methods actually fall in this category:</span></span>
  - <span data-ttu-id="c8e20-111">komut satırı arabirimi</span><span class="sxs-lookup"><span data-stu-id="c8e20-111">the command-line interface</span></span>
  - <span data-ttu-id="c8e20-112">Q# Jupyıter Not defterleri</span><span class="sxs-lookup"><span data-stu-id="c8e20-112">Q# Jupyter Notebooks</span></span>
- <span data-ttu-id="c8e20-113">ek bir *ana bilgisayar programıyla*, Python veya bir .net dilinde (örneğin, C# veya F #) yazılmış, daha sonra programı çağıran ve döndürülen sonuçları daha fazla işleyebilir.</span><span class="sxs-lookup"><span data-stu-id="c8e20-113">with an additional *host program*, written in Python or a .NET language (for example, C# or F#), which then invokes the program and can further process returned results.</span></span>

<span data-ttu-id="c8e20-114">Bu işlemlerin ve bunların farklarının en iyi şekilde anlaşılması için, basit bir programı göz önünde bulunduruyoruz Q# ve çalıştırılabildikleri yolları karşılaştırıyoruz.</span><span class="sxs-lookup"><span data-stu-id="c8e20-114">To best understand these processes and their differences, we consider a simple Q# program and compare the ways it can be run.</span></span>

## <a name="basic-no-locq-program"></a><span data-ttu-id="c8e20-115">Temel Q# Program</span><span class="sxs-lookup"><span data-stu-id="c8e20-115">Basic Q# program</span></span>

<span data-ttu-id="c8e20-116">Temel bir hisse, durumlardan biri olan $ \ket $ ve $ \tus$ gibi büyük bir üst konumda qubit hazırlamaktan ve {0} {1} Bu iki durumdan eşit olasılığa sahip olarak rastgele olacak.</span><span class="sxs-lookup"><span data-stu-id="c8e20-116">A basic quantum program might consist of preparing a qubit in an equal superposition of states $\ket{0}$ and $\ket{1}$, measuring it, and returning the result, which will be randomly either one of these two states with equal probability.</span></span>
<span data-ttu-id="c8e20-117">Aslında bu işlem, [hisse rastgele numara Oluşturucu](xref:microsoft.quantum.quickstarts.qrng) hızlı başlangıcı 'nın çekirdeğisidir.</span><span class="sxs-lookup"><span data-stu-id="c8e20-117">Indeed, this process is at the core of the [quantum random number generator](xref:microsoft.quantum.quickstarts.qrng) quickstart.</span></span>

<span data-ttu-id="c8e20-118">Q#' De, bu, aşağıdaki kod tarafından gerçekleştirilir:</span><span class="sxs-lookup"><span data-stu-id="c8e20-118">In Q#, this would be performed by the following code:</span></span>

```qsharp
        using (q = Qubit()) {    // allocates qubit for use (automatically in |0>)
            H(q);                // puts qubit in superposition of |0> and |1>
            return MResetZ(q);   // measures qubit, returns result (and resets it to |0> before deallocation)
        }
```

<span data-ttu-id="c8e20-119">Ancak, bu kod yalnızca tarafından çalıştırılamaz Q# .</span><span class="sxs-lookup"><span data-stu-id="c8e20-119">However, this code alone can't be run by Q#.</span></span>
<span data-ttu-id="c8e20-120">Bunun için, doğrudan veya başka bir işlem tarafından---çağrıldığında çalıştırılan bir [işlemin](xref:microsoft.quantum.qsharp.operationsandfunctions)gövdesini yapması gerekir.</span><span class="sxs-lookup"><span data-stu-id="c8e20-120">For that, it needs to make up the body of an [operation](xref:microsoft.quantum.qsharp.operationsandfunctions), which is then run when called---either directly or by another operation.</span></span> <span data-ttu-id="c8e20-121">Bu nedenle, aşağıdaki biçimde bir işlem yazabilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="c8e20-121">Hence, you can write an operation of the following form:</span></span>
```qsharp
    operation MeasureSuperposition() : Result {
        using (q = Qubit()) {
            H(q);
            return MResetZ(q);
        }
    }
```
<span data-ttu-id="c8e20-122">Bir işlem tanımladınız, ancak `MeasureSuperposition` hiçbir giriş yapılmaz ve [sonuç](xref:microsoft.quantum.qsharp.typesystem-index#available-types)türünde bir değer döndürmez.</span><span class="sxs-lookup"><span data-stu-id="c8e20-122">You have defined an operation, `MeasureSuperposition`, which takes no inputs and returns a value of type [Result](xref:microsoft.quantum.qsharp.typesystem-index#available-types).</span></span>

<span data-ttu-id="c8e20-123">İşlemlere ek olarak, Q# belirleyici hesaplamaları işlevlere de kapsüllemek de sağlar.</span><span class="sxs-lookup"><span data-stu-id="c8e20-123">In addition to operations, Q# also allows to encapsulate deterministic computations into functions.</span></span> <span data-ttu-id="c8e20-124">Qubits üzerinde işlem yapan hesaplamaların işlevler yerine işlemlere kapsüllenmesi gerektiğini belirten belirleyici garantiden farklı olarak, işlemler ve işlevler arasında küçük bir farklılık vardır.</span><span class="sxs-lookup"><span data-stu-id="c8e20-124">Aside from the determinism guarantee that implies that computations that act on qubits need to be encapsulated into operations rather than functions, there is little difference between operations and function.</span></span> <span data-ttu-id="c8e20-125">Bunlara toplu olarak *callables* olarak başvurduk.</span><span class="sxs-lookup"><span data-stu-id="c8e20-125">We refer to them collectively as *callables*.</span></span>

### <a name="callable-defined-in-a-no-locq-file"></a><span data-ttu-id="c8e20-126">Bir dosyada tanımlanmış çağrılabilir Q#</span><span class="sxs-lookup"><span data-stu-id="c8e20-126">Callable defined in a Q# file</span></span>

<span data-ttu-id="c8e20-127">Çağrılabilir, tam olarak aranan ve tarafından çalıştırılan şeydir Q# .</span><span class="sxs-lookup"><span data-stu-id="c8e20-127">The callable is precisely what's called and run by Q#.</span></span>
<span data-ttu-id="c8e20-128">Ancak, tam bir dosyayı oluşturacak birkaç ekleme daha vardır `*.qs` Q# .</span><span class="sxs-lookup"><span data-stu-id="c8e20-128">However, it requires a few more additions to comprise a full `*.qs` Q# file.</span></span>

<span data-ttu-id="c8e20-129">Tüm Q# türler ve callables (hem tanımladığınız hem de dile özgü olan) *ad alanları* içinde tanımlanır ve bu, daha sonra başvurulabilen her bir tam adı sağlar.</span><span class="sxs-lookup"><span data-stu-id="c8e20-129">All Q# types and callables (both those you define and those intrinsic to the language) are defined within *namespaces*, which provide each a full name that can then be referenced.</span></span>

<span data-ttu-id="c8e20-130">Örneğin, [`H`](xref:Microsoft.Quantum.Intrinsic.H) ve işlemleri, [`MResetZ`](xref:Microsoft.Quantum.Measurement.MResetZ) [`Microsoft.Quantum.Instrinsic`](xref:Microsoft.Quantum.Intrinsic) ve [`Microsoft.Quantum.Measurement`](xref:Microsoft.Quantum.Measurement) ad alanlarında ( [ Q# standart kitaplıkların](xref:microsoft.quantum.libraries.standard.intro)bir parçası) bulunur.</span><span class="sxs-lookup"><span data-stu-id="c8e20-130">For example, the [`H`](xref:Microsoft.Quantum.Intrinsic.H) and [`MResetZ`](xref:Microsoft.Quantum.Measurement.MResetZ) operations are found in the [`Microsoft.Quantum.Instrinsic`](xref:Microsoft.Quantum.Intrinsic) and [`Microsoft.Quantum.Measurement`](xref:Microsoft.Quantum.Measurement) namespaces (part of the [Q# Standard Libraries](xref:microsoft.quantum.libraries.standard.intro)).</span></span>
<span data-ttu-id="c8e20-131">Bu nedenle, her zaman *tam* adlarıyla çağrılabilir, `Microsoft.Quantum.Intrinsic.H(<qubit>)` `Microsoft.Quantum.Measurement.MResetZ(<qubit>)` ancak her zaman bunu yapmanız çok karışık koda yol açabilir.</span><span class="sxs-lookup"><span data-stu-id="c8e20-131">As such, they can always be called via their *full* names, `Microsoft.Quantum.Intrinsic.H(<qubit>)` and `Microsoft.Quantum.Measurement.MResetZ(<qubit>)`, but always doing this would lead to very cluttered code.</span></span>

<span data-ttu-id="c8e20-132">Bunun yerine, `open` deyimler, yukarıdaki işlem gövdesinde yaptığımız gibi, callables 'e daha kısa toplu ile başvurulmalıdır.</span><span class="sxs-lookup"><span data-stu-id="c8e20-132">Instead, `open` statements allow callables to be referenced with more concise shorthand, as we've done in the operation body above.</span></span>
<span data-ttu-id="c8e20-133">Q#Bu nedenle, işlemizi içeren tam dosya, kendi ad alanımızın tanımlanmasından, işlediğimiz bu callabların ad alanlarını açmaya ve sonra işleyimize neden olacak:</span><span class="sxs-lookup"><span data-stu-id="c8e20-133">The full Q# file containing our operation would therefore consist of defining our own namespace, opening the namespaces for those callables our operation uses, and then our operation:</span></span>

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
> <span data-ttu-id="c8e20-134">Ayrıca, iki ad alanındaki çağrılabilir/tür adları çakışıyorsa yararlı olabilecek ad alanları açıldıklarında da *diğer* ad olabilir.</span><span class="sxs-lookup"><span data-stu-id="c8e20-134">Namespaces can also be *aliased* when opened, which can be helpful if callable/type names in two namespaces conflict.</span></span>
> <span data-ttu-id="c8e20-135">Örneğin, `open Microsoft.Quantum.Instrinsic as NamespaceWithH;` Yukarıdaki ' ı kullanabilir ve ardından `H` aracılığıyla çağırabilirsiniz `NamespaceWithH.H(<qubit>)` .</span><span class="sxs-lookup"><span data-stu-id="c8e20-135">For example, we could instead use `open Microsoft.Quantum.Instrinsic as NamespaceWithH;` above, and then call `H` via `NamespaceWithH.H(<qubit>)`.</span></span>

> [!NOTE]
> <span data-ttu-id="c8e20-136">Tüm bu tek istisna, [`Microsoft.Quantum.Core`](xref:Microsoft.Quantum.Core) her zaman otomatik olarak açılan bir ad alanıdır.</span><span class="sxs-lookup"><span data-stu-id="c8e20-136">One exception to all of this is the [`Microsoft.Quantum.Core`](xref:Microsoft.Quantum.Core) namespace, which is always automatically opened.</span></span>
> <span data-ttu-id="c8e20-137">Bu nedenle, callables, [`Length`](xref:Microsoft.Quantum.Core.Length) her zaman doğrudan kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="c8e20-137">Therefore, callables like [`Length`](xref:Microsoft.Quantum.Core.Length) can always be used directly.</span></span>

### <a name="running-on-target-machines"></a><span data-ttu-id="c8e20-138">Hedef makinelerde çalıştırma</span><span class="sxs-lookup"><span data-stu-id="c8e20-138">Running on target machines</span></span>

<span data-ttu-id="c8e20-139">Artık bir programın genel çalıştırma modeli Q# açık hale gelir.</span><span class="sxs-lookup"><span data-stu-id="c8e20-139">Now the general run model of a Q# program becomes clear.</span></span>

<br/>
<img src="../media/hostprograms_general_execution_model.png" alt="Q# program execution diagram" width="400">

<span data-ttu-id="c8e20-140">İlk olarak, çalıştırılacak olan özel çağrılabilir, aynı ad alanında tanımlanan diğer tüm callables ve türlerine erişim sağlar.</span><span class="sxs-lookup"><span data-stu-id="c8e20-140">Firstly, the specific callable to be run has access to any other callables and types defined in the same namespace.</span></span>
<span data-ttu-id="c8e20-141">Ayrıca, [ Q# kütüphanelerin](xref:microsoft.quantum.libraries)herhangi birinden bunlara erişir, ancak bunların tam adlarıyla veya yukarıda açıklanan deyimlerin kullanımı aracılığıyla başvurulmalıdır `open` .</span><span class="sxs-lookup"><span data-stu-id="c8e20-141">It also access those from any of the [Q# libraries](xref:microsoft.quantum.libraries), but those must be referenced either via their full name, or through the use of `open` statements described above.</span></span>

<span data-ttu-id="c8e20-142">Çağrılabilir bir *[hedef makine](xref:microsoft.quantum.machines)* üzerinde çalıştırılır.</span><span class="sxs-lookup"><span data-stu-id="c8e20-142">The callable itself is then run on a *[target machine](xref:microsoft.quantum.machines)*.</span></span>
<span data-ttu-id="c8e20-143">Bu tür hedef makineler gerçek hisse donanımı veya QDK 'nin bir parçası olarak kullanılabilir birden çok simülatörleri olabilir.</span><span class="sxs-lookup"><span data-stu-id="c8e20-143">Such target machines can be actual quantum hardware or the multiple simulators available as part of the QDK.</span></span>
<span data-ttu-id="c8e20-144">Burada, bizim için en faydalı hedef makine, [full-state simulator](xref:microsoft.quantum.machines.full-state-simulator) `QuantumSimulator` bir gürültü ücretsiz hisse bilgisayarında çalıştırılmakta gibi programın davranışını hesaplayan tam durum benzeticisinin bir örneğidir.</span><span class="sxs-lookup"><span data-stu-id="c8e20-144">For our purposes here, the most useful target machine is an instance of the [full-state simulator](xref:microsoft.quantum.machines.full-state-simulator), `QuantumSimulator`, which calculates the program's behavior as if it were being run on a noise-free quantum computer.</span></span>

<span data-ttu-id="c8e20-145">Şimdiye kadar, belirli bir çağrılabilir çalıştırıldığında ne olduğunu açıklıyoruz Q# .</span><span class="sxs-lookup"><span data-stu-id="c8e20-145">So far, we've described what happens when a specific Q# callable is being run.</span></span>
<span data-ttu-id="c8e20-146">Q#Tek başına bir uygulamada veya bir konak programıyla kullanılıp kullanılmadığına bakılmaksızın, bu genel işlem daha fazla veya daha az---, bu nedenle QDK 'nin esnekliği de aynıdır.</span><span class="sxs-lookup"><span data-stu-id="c8e20-146">Regardless of whether Q# is used in a standalone application or with a host program, this general process is more or less the same---hence the QDK's flexibility.</span></span>
<span data-ttu-id="c8e20-147">*Bu nedenle* , hisse alma geliştirme paketine çağırma yolları arasındaki farklılıklar Q# , bunların çağrılabilir şekilde çağrılması ve sonuçların ne şekilde döndürüldüğünden ortaya çıkar.</span><span class="sxs-lookup"><span data-stu-id="c8e20-147">The differences between the ways of calling into the Quantum Development Kit therefore reveal themselves in *how* that Q# callable is called to be run, and in what manner any results are returned.</span></span>
<span data-ttu-id="c8e20-148">Daha belirgin olarak, farklar şu şekilde döner:</span><span class="sxs-lookup"><span data-stu-id="c8e20-148">More specifically, the differences revolve around:</span></span>

- <span data-ttu-id="c8e20-149">Hangi Q# çağrılabilir çalıştırılacak olduğunu belirtir</span><span class="sxs-lookup"><span data-stu-id="c8e20-149">Indicating which Q# callable is to be run</span></span>
- <span data-ttu-id="c8e20-150">Çağrılabilir olabilecek bağımsız değişkenlerin nasıl sağlandığı</span><span class="sxs-lookup"><span data-stu-id="c8e20-150">How potential callable arguments are provided</span></span>
- <span data-ttu-id="c8e20-151">Üzerinde çalıştırılacağı hedef makineyi belirtme</span><span class="sxs-lookup"><span data-stu-id="c8e20-151">Specifying the target machine on which to run it</span></span>
- <span data-ttu-id="c8e20-152">Sonuçların nasıl döndürüldüğü</span><span class="sxs-lookup"><span data-stu-id="c8e20-152">How any results are returned</span></span>

<span data-ttu-id="c8e20-153">İlk olarak, komut isteminden tek başına uygulama ile bunun nasıl yapıldığını anladık Q# ve Python ve C# ana bilgisayar programlarını kullanmaya devam ediyoruz.</span><span class="sxs-lookup"><span data-stu-id="c8e20-153">First, we discuss how this is done with the Q# standalone application from the command prompt, and then proceed to using Python and C# host programs.</span></span>
<span data-ttu-id="c8e20-154">Q#İlk üçünün aksine, birincil işlevselliği yerel bir dosya etrafında ortalamadığından, en son jupi Not defterlerinin tek başına uygulamasını ayırdık Q# .</span><span class="sxs-lookup"><span data-stu-id="c8e20-154">We reserve the standalone application of Q# Jupyter Notebooks for last, because unlike the first three, it's primary functionality does not center around a local Q# file.</span></span>

> [!NOTE]
> <span data-ttu-id="c8e20-155">Bu örneklerde anlamadığımızda, çalıştırma yöntemleri arasındaki bir genel durumda, programın içinden yazdırılan tüm iletiler Q# ( [`Message`](xref:Microsoft.Quantum.Intrinsic.Message) [`DumpMachine`](xref:Microsoft.Quantum.Diagnostics.DumpMachine) Örneğin, veya) her zaman ilgili konsola yazdırılır.</span><span class="sxs-lookup"><span data-stu-id="c8e20-155">Although we don't illustrate it in these examples, one commonality between the run methods is that any messages printed from inside the Q# program (by way of [`Message`](xref:Microsoft.Quantum.Intrinsic.Message) or [`DumpMachine`](xref:Microsoft.Quantum.Diagnostics.DumpMachine), for example) will typically always be printed to the respective console.</span></span>

## <a name="no-locq-from-the-command-prompt"></a><span data-ttu-id="c8e20-156">Q# komut isteminden</span><span class="sxs-lookup"><span data-stu-id="c8e20-156">Q# from the command prompt</span></span>
<span data-ttu-id="c8e20-157">Programları yazmaya başlamanın en kolay yollarından biri Q# , ayrı dosyalar ve ikinci bir dilin tamamen kaygılanmasından kaçınmaktır.</span><span class="sxs-lookup"><span data-stu-id="c8e20-157">One of the easiest ways to get started writing Q# programs is to avoid worrying about separate files and a second language altogether.</span></span>
<span data-ttu-id="c8e20-158">Visual Studio Code veya Visual Studio 'Yu QDK uzantısıyla kullanmak, Q# tek bir dosyadan callables çalıştırdığımız sorunsuz bir iş akışına olanak sağlar Q# .</span><span class="sxs-lookup"><span data-stu-id="c8e20-158">Using Visual Studio Code or Visual Studio with the QDK extension allows for a seamless work flow in which we run Q# callables from only a single Q# file.</span></span>

<span data-ttu-id="c8e20-159">Bunun için, bu programı sonunda şunu girerek çalıştırın</span><span class="sxs-lookup"><span data-stu-id="c8e20-159">For this, we will ultimately run the program by entering</span></span>

```dotnetcli
dotnet run
```

<span data-ttu-id="c8e20-160">komut isteminde.</span><span class="sxs-lookup"><span data-stu-id="c8e20-160">at the command prompt.</span></span>
<span data-ttu-id="c8e20-161">En basit iş akışı, terminalin Dizin konumunun dosyayla aynı olduğu Q# , Q# Örneğin vs Code ' deki tümleşik Terminal kullanılarak dosya düzenlemeyle birlikte kolayca işlenebilen bir dosyadır.</span><span class="sxs-lookup"><span data-stu-id="c8e20-161">The simplest workflow is when the terminal's directory location is the same as the Q# file, which can be easily handled alongside Q# file editing by using the integrated terminal in VS Code, for example.</span></span>
<span data-ttu-id="c8e20-162">Ancak, [ `dotnet run` komut](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) çok sayıda seçenek kabul eder ve yalnızca `--project <PATH>` dosyanın konumuyla birlikte sağlanarak program farklı bir konumdan da çalıştırılabilir Q# .</span><span class="sxs-lookup"><span data-stu-id="c8e20-162">However, the [`dotnet run` command](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) accepts numerous options, and the program can also be run from a different location by simply providing `--project <PATH>` with the location of the Q# file.</span></span>


### <a name="add-entry-point-to-no-locq-file"></a><span data-ttu-id="c8e20-163">Dosyaya giriş noktası Ekle Q#</span><span class="sxs-lookup"><span data-stu-id="c8e20-163">Add entry point to Q# file</span></span>

<span data-ttu-id="c8e20-164">Çoğu Q# dosya birden fazla çağrılabilir, *Bu* yüzden doğal olarak, komut sağlamamız durumunda derleyicinin hangi çağrılabilir çalıştırılacağını bilmesini sağlamamız gerekir `dotnet run` .</span><span class="sxs-lookup"><span data-stu-id="c8e20-164">Most Q# files will contain more than one callable, so naturally we need to let the compiler know *which* callable to run when we provide the `dotnet run` command.</span></span>
<span data-ttu-id="c8e20-165">Bu, dosyanın kendisinde basit bir değişiklik ile yapılır Q# :</span><span class="sxs-lookup"><span data-stu-id="c8e20-165">This is done with a simple change to the Q# file itself:</span></span> 
    - <span data-ttu-id="c8e20-166">`@EntryPoint()`çağrılabilir öğesinden hemen önce gelen bir satır ekleyin.</span><span class="sxs-lookup"><span data-stu-id="c8e20-166">add a line with `@EntryPoint()` directly preceding the callable.</span></span>

<span data-ttu-id="c8e20-167">Yukarıdaki dosya bundan böyle olur</span><span class="sxs-lookup"><span data-stu-id="c8e20-167">Our file from above would therefore become</span></span>
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

<span data-ttu-id="c8e20-168">Şimdi, `dotnet run` komut isteminden bir çağrısı `MeasureSuperposition` çalıştırılmakta ve döndürülen değer daha sonra doğrudan terminale yazdırılır.</span><span class="sxs-lookup"><span data-stu-id="c8e20-168">Now, a call of `dotnet run` from the command prompt leads to `MeasureSuperposition` being run, and the returned value is then printed directly to the terminal.</span></span>
<span data-ttu-id="c8e20-169">Bu nedenle, ya da `One` yazdırılmış görürsünüz `Zero` .</span><span class="sxs-lookup"><span data-stu-id="c8e20-169">So, you will see either `One` or `Zero` printed.</span></span> 

<span data-ttu-id="c8e20-170">Aşağıda, daha fazla callabaldığınıza bakılmaksızın yalnızca `MeasureSuperposition` çalıştırılacağını unutmayın.</span><span class="sxs-lookup"><span data-stu-id="c8e20-170">Note that it doesn't matter if you have more callables defined below it, only `MeasureSuperposition` will be run.</span></span>
<span data-ttu-id="c8e20-171">Buna ek olarak, çağrılabilir bir sorun değildir. Bu, çağrılabilir bir [belge açıklamalarını](xref:microsoft.quantum.qsharp.comments#documentation-comments) kendi bildiriminden önce içeriyorsa, `@EntryPoint()` öznitelik üzerine basitçe eklenebilir.</span><span class="sxs-lookup"><span data-stu-id="c8e20-171">Additionally, it's no problem if your callable includes [documentation comments](xref:microsoft.quantum.qsharp.comments#documentation-comments) before its declaration, the `@EntryPoint()` attribute can be simply placed above them.</span></span>

### <a name="callable-arguments"></a><span data-ttu-id="c8e20-172">Çağrılabilir bağımsız değişkenler</span><span class="sxs-lookup"><span data-stu-id="c8e20-172">Callable arguments</span></span>

<span data-ttu-id="c8e20-173">Şimdiye kadar, yalnızca giriş içermeyen bir işlem kabul ediyoruz.</span><span class="sxs-lookup"><span data-stu-id="c8e20-173">So far, we've only considered an operation that takes no inputs.</span></span>
<span data-ttu-id="c8e20-174">Benzer bir işlem gerçekleştirmek istediğinizi varsayalım, ancak birden fazla qubit üzerinde---bağımsız değişken olarak sunulan sayı.</span><span class="sxs-lookup"><span data-stu-id="c8e20-174">Suppose we wanted to perform a similar operation, but on multiple qubits---the number of which is provided as an argument.</span></span>
<span data-ttu-id="c8e20-175">Bu tür bir işlem şöyle yazılabilir</span><span class="sxs-lookup"><span data-stu-id="c8e20-175">Such an operation could be written as</span></span>
```qsharp
    operation MeasureSuperpositionArray(n : Int) : Result[] {
        using (qubits = Qubit[n]) {              // allocate a register of n qubits
            ApplyToEach(H, qubits);              // apply H to each qubit in the register
            return ForEach(MResetZ, qubits);     // perform MResetZ on each qubit, returns the resulting array
        }
    }
```
<span data-ttu-id="c8e20-176">döndürülen değer ölçüm sonuçlarının bir dizisidir.</span><span class="sxs-lookup"><span data-stu-id="c8e20-176">where the returned value is an array of the measurement results.</span></span>
<span data-ttu-id="c8e20-177">Ve [`ApplyToEach`](xref:Microsoft.Quantum.Canon.ApplyToEach) [`ForEach`](xref:Microsoft.Quantum.Arrays.ForEach) ad alanlarında olduğunu ve [`Microsoft.Quantum.Canon`](xref:Microsoft.Quantum.Canon) [`Microsoft.Quantum.Arrays`](xref:Microsoft.Quantum.Arrays) `open` her biri için ek deyimler kullanılmasını unutmayın.</span><span class="sxs-lookup"><span data-stu-id="c8e20-177">Note that [`ApplyToEach`](xref:Microsoft.Quantum.Canon.ApplyToEach) and [`ForEach`](xref:Microsoft.Quantum.Arrays.ForEach) are in the [`Microsoft.Quantum.Canon`](xref:Microsoft.Quantum.Canon) and [`Microsoft.Quantum.Arrays`](xref:Microsoft.Quantum.Arrays) namespaces, requiring additional `open` statements for each.</span></span>

<span data-ttu-id="c8e20-178">`@EntryPoint()`Özniteliği bu yeni işlemden önce (örneğin, bir dosyada yalnızca bir satır olabilir) taşıdığımızda, çalıştırmayı denemek yalnızca bir `dotnet run` hata mesajı ile sonuçlanmaya, hangi ek komut satırı seçeneklerinin gerekli olduğunu ve bunları nasıl ifade ettiğine ilişkin bir hata iletisiyle sonuçlanır.</span><span class="sxs-lookup"><span data-stu-id="c8e20-178">If we move the `@EntryPoint()` attribute to precede this new operation (note there can only be one such line in a file), attempting to run it with simply `dotnet run` results in an error message which indicates what additional command-line options are required, and how to express them.</span></span>

<span data-ttu-id="c8e20-179">Komut satırı için genel biçim aslında olur `dotnet run [options]` ve çağrılabilir bağımsız değişkenler burada sağlanır.</span><span class="sxs-lookup"><span data-stu-id="c8e20-179">The general format for the command line is actually `dotnet run [options]`, and callable arguments are provided there.</span></span>
<span data-ttu-id="c8e20-180">Bu durumda, bağımsız değişkeni `n` eksik olur ve seçeneğini sağlamaları gerektiğini gösterir `-n <n>` .</span><span class="sxs-lookup"><span data-stu-id="c8e20-180">In this case, the argument `n` is missing, and it shows that we need to provide the option `-n <n>`.</span></span> <span data-ttu-id="c8e20-181">`MeasureSuperpositionArray` `n=4` Bu nedenle, qubit 'i çalıştırmak için</span><span class="sxs-lookup"><span data-stu-id="c8e20-181">To run `MeasureSuperpositionArray` for `n=4` qubits, we therefore use</span></span>

```dotnetcli
dotnet run -n 4
```

<span data-ttu-id="c8e20-182">aşağıdakine benzer bir çıktı oluşturma</span><span class="sxs-lookup"><span data-stu-id="c8e20-182">yielding an output similar to</span></span>

```output
[Zero,One,One,One]
```

<span data-ttu-id="c8e20-183">Bu kurs birden çok bağımsız değişkene genişletilir.</span><span class="sxs-lookup"><span data-stu-id="c8e20-183">This of course extends to multiple arguments.</span></span>

> [!NOTE]
> <span data-ttu-id="c8e20-184">' Da tanımlanan bağımsız değişken adları `camelCase` , giriş olarak kabul edilmesi için derleyici tarafından biraz değişiklik gösterebilir Q# .</span><span class="sxs-lookup"><span data-stu-id="c8e20-184">Argument names defined in `camelCase` are slightly altered by the compiler to be accepted as Q# inputs.</span></span> <span data-ttu-id="c8e20-185">Örneğin, yerine `n` Yukarıdaki adı kullandık, `numQubits` Bu giriş, komut satırında yerine kullanılarak sağlanacaktır `--num-qubits 4` `-n 4` .</span><span class="sxs-lookup"><span data-stu-id="c8e20-185">For example, if instead of `n`, we used the name `numQubits` above, then this input would be provided in the command line via `--num-qubits 4` instead of `-n 4`.</span></span>

<span data-ttu-id="c8e20-186">Hata iletisi ayrıca, hedef makinenin nasıl değiştirileceği dahil olmak üzere kullanılabilecek diğer seçenekleri de sağlar.</span><span class="sxs-lookup"><span data-stu-id="c8e20-186">The error message also provides other options which can be used, including how to change the target machine.</span></span>

### <a name="different-target-machines"></a><span data-ttu-id="c8e20-187">Farklı hedef makineler</span><span class="sxs-lookup"><span data-stu-id="c8e20-187">Different target machines</span></span>

<span data-ttu-id="c8e20-188">İşlemlerimizin çıkışları gerçek qubit üzerinde eylemin beklenen sonuçları olduğundan, komut satırından varsayılan hedef makinenin tam durum hisse benzeticileri olduğunu temizler `QuantumSimulator` .</span><span class="sxs-lookup"><span data-stu-id="c8e20-188">As the outputs from our operations thus far have been the expected results of their action on real qubits, it's clear that the default target machine from the command line is the full-state quantum simulator, `QuantumSimulator`.</span></span>
<span data-ttu-id="c8e20-189">Ancak, callables ' i `--simulator` (veya toplu) belirli bir hedef makinede çalıştırmayı söyleyebilirsiniz `-s` .</span><span class="sxs-lookup"><span data-stu-id="c8e20-189">However, we can instruct callables to be run on a specific target machine with the option `--simulator` (or the shorthand `-s`).</span></span>

<span data-ttu-id="c8e20-190">Örneğin, şunu üzerinde çalıştırabiliriz [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) :</span><span class="sxs-lookup"><span data-stu-id="c8e20-190">For example, we could run it on [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator):</span></span>

```dotnetcli
dotnet run -n 4 -s ResourcesEstimator
```

<span data-ttu-id="c8e20-191">Yazdırılan çıkış daha sonra</span><span class="sxs-lookup"><span data-stu-id="c8e20-191">The printed output is then</span></span>

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

<span data-ttu-id="c8e20-192">Bu ölçümlerin neleri belirtebileceği hakkında ayrıntılı bilgi için bkz. [kaynak tahmini: raporlanan ölçümler](xref:microsoft.quantum.machines.resources-estimator#metrics-reported).</span><span class="sxs-lookup"><span data-stu-id="c8e20-192">For details on what these metrics indicate, see [Resource estimator: metrics reported](xref:microsoft.quantum.machines.resources-estimator#metrics-reported).</span></span>

### <a name="command-line-run-summary"></a><span data-ttu-id="c8e20-193">Komut satırı çalıştırma Özeti</span><span class="sxs-lookup"><span data-stu-id="c8e20-193">Command line run summary</span></span>
<br/>
<img src="../media/hostprograms_command_line_diagram.png" alt="Q# program from command line" width="700">

### <a name="non-no-locq-dotnet-run-options"></a><span data-ttu-id="c8e20-194">Seçenek olmayanlar Q# `dotnet run`</span><span class="sxs-lookup"><span data-stu-id="c8e20-194">Non-Q# `dotnet run` options</span></span>

<span data-ttu-id="c8e20-195">Bu seçenekte kısaca bahsedilen gibi `--project` , [ `dotnet run` komut](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) çağrılabilir bağımsız değişkenlerle ilgisi olmayan seçenekleri de kabul eder Q# .</span><span class="sxs-lookup"><span data-stu-id="c8e20-195">As we briefly mentioned above with the `--project` option, the [`dotnet run` command](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) also accepts options unrelated to the Q# callable arguments.</span></span>
<span data-ttu-id="c8e20-196">Her iki tür seçeneği de sağladıysanız, `dotnet` önce özel seçenekler önce, sonra da bir `--` Q# delil ve ardından özel seçenekler sağlanmalıdır.</span><span class="sxs-lookup"><span data-stu-id="c8e20-196">If providing both kinds of options, the `dotnet`-specific options must be provided first, followed by a delimeter `--`, and then the Q#-specific options.</span></span>
<span data-ttu-id="c8e20-197">Örneğin, yukarıdaki işlem için bir sayı ile birlikte bir yol belirtmek aracılığıyla çalıştırılabilir `dotnet run --project <PATH> -- -n <n>` .</span><span class="sxs-lookup"><span data-stu-id="c8e20-197">For example, specifying a path along with a number qubits for the operation above would be run via `dotnet run --project <PATH> -- -n <n>`.</span></span>

## <a name="no-locq-with-host-programs"></a><span data-ttu-id="c8e20-198">Q# Konak programları ile</span><span class="sxs-lookup"><span data-stu-id="c8e20-198">Q# with host programs</span></span>

<span data-ttu-id="c8e20-199">Dosya ile birlikte Q# , doğrudan komut isteminden bir işlem veya işlev çağırma alternatifi, bir *konak programını* başka bir klasik dilde kullanmaktır.</span><span class="sxs-lookup"><span data-stu-id="c8e20-199">With our Q# file in hand, an alternative to calling an operation or function directly from the command prompt is to use a *host program* in another classical language.</span></span> <span data-ttu-id="c8e20-200">Özellikle, bu, Python veya C# ya da F # gibi bir .NET diliyle yapılabilir (breçların sake 'ı için burada yalnızca c# ayrıntı alınacaktır).</span><span class="sxs-lookup"><span data-stu-id="c8e20-200">Specifically, this can be done with either Python or a .NET language such as C# or F# (for the sake of brevity we will only detail C# here).</span></span>
<span data-ttu-id="c8e20-201">Birlikte çalışabilirliği etkinleştirmek için biraz daha fazla kurulum gerekir, ancak bu Ayrıntılar [yükleme kılavuzlarında](xref:microsoft.quantum.install)bulunabilir.</span><span class="sxs-lookup"><span data-stu-id="c8e20-201">A little more setup is required to enable the interoperability, but those details can be found in the [install guides](xref:microsoft.quantum.install).</span></span>

<span data-ttu-id="c8e20-202">Bir Nutshell 'de, durum artık, `*.py` `*.cs` dosya ile aynı konumdaki bir ana bilgisayar program dosyası (örneğin, veya) içeriyor Q# .</span><span class="sxs-lookup"><span data-stu-id="c8e20-202">In a nutshell, the situation now includes a host program file (for example, `*.py` or `*.cs`) in the same location as our Q# file.</span></span>
<span data-ttu-id="c8e20-203">Şimdi çalıştırılan ve çalıştırılan bir *ana bilgisayar* programı olduğundan, Q# dosyadaki belirli işlemleri ve işlevleri çağırabilir Q# .</span><span class="sxs-lookup"><span data-stu-id="c8e20-203">It's now the *host* program that gets run, and while it is running, it can call specific Q# operations and functions from the Q# file.</span></span>
<span data-ttu-id="c8e20-204">Birlikte çalışabilirlik çekirdeği, Q# Q# bir dosyanın içeriğini ana bilgisayar programına erişilebilir hale getiren derleyiciye dayanır, böylece çağrılabilir.</span><span class="sxs-lookup"><span data-stu-id="c8e20-204">The core of the interoperability is based on the Q# compiler making the contents of the Q# file accessible to the host program so that they can be called.</span></span>

<span data-ttu-id="c8e20-205">Ana bilgisayar programı kullanmanın başlıca avantajlarından biri, program tarafından döndürülen klasik verilerin Q# daha sonra konak dilinde daha fazla işlenebilir olması olabilir.</span><span class="sxs-lookup"><span data-stu-id="c8e20-205">One of the main benefits of using a host program is that the classical data returned by the Q# program can then be further processed in the host language.</span></span>
<span data-ttu-id="c8e20-206">Bu, bazı gelişmiş veri işlemeden (örneğin, içinde yerleşik olarak gerçekleştirilemediği bir şey Q# ) ve ardından Q# Bu sonuçlara göre daha fazla eylem veya sonuçları çizmek kadar basit bir şey olabilir Q# .</span><span class="sxs-lookup"><span data-stu-id="c8e20-206">This could consist of some advanced data processing (for example, something that can't be performed internally in Q#), and then calling further Q# actions based on those results, or something as simple as plotting the Q# results.</span></span>

<span data-ttu-id="c8e20-207">Genel düzen burada gösterilmektedir ve aşağıda Python ve C# için özel uygulamalar tartışıyoruz.</span><span class="sxs-lookup"><span data-stu-id="c8e20-207">The general scheme is shown here, and we discuss the specific implementations for Python and C# below.</span></span> <span data-ttu-id="c8e20-208">F # ana bilgisayar programını kullanan bir örnek, [.net birlikte çalışabilirlik örneklerinde](https://github.com/microsoft/Quantum/tree/main/samples/interoperability/dotnet)bulunabilir.</span><span class="sxs-lookup"><span data-stu-id="c8e20-208">A sample using an F# host program can be found at the [.NET interoperability samples](https://github.com/microsoft/Quantum/tree/main/samples/interoperability/dotnet).</span></span>

<br/>
<img src="../media/hostprograms_host_program_diagram.png" alt="Q# program from a host program" width="700">

> [!NOTE]
> <span data-ttu-id="c8e20-209">`@EntryPoint()`Uygulamalar için kullanılan öznitelik Q# konak programlarıyla kullanılamaz.</span><span class="sxs-lookup"><span data-stu-id="c8e20-209">The `@EntryPoint()` attribute used for Q# applications cannot be used with host programs.</span></span>
> <span data-ttu-id="c8e20-210">Q#Bir ana bilgisayar tarafından çağrılan dosyada mevcutsa bir hata oluşur.</span><span class="sxs-lookup"><span data-stu-id="c8e20-210">An error will be raised if it is present in the Q# file being called by a host.</span></span> 

<span data-ttu-id="c8e20-211">Farklı ana bilgisayar programlarıyla çalışmak için, bir dosya için gerekli değişiklik yoktur `*.qs` Q# .</span><span class="sxs-lookup"><span data-stu-id="c8e20-211">To work with different host programs, there are no changes required to a `*.qs` Q# file.</span></span>
<span data-ttu-id="c8e20-212">Aşağıdaki konak program uygulamalarının hepsi aynı Q# dosyayla çalışır:</span><span class="sxs-lookup"><span data-stu-id="c8e20-212">The following host program implementations all work with the same Q# file:</span></span>

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

<span data-ttu-id="c8e20-213">İlgilendiğiniz ana bilgisayar dilinize karşılık gelen sekmeyi seçin.</span><span class="sxs-lookup"><span data-stu-id="c8e20-213">Select the tab corresponding to your host language of interest.</span></span>

### <a name="python"></a>[<span data-ttu-id="c8e20-214">Python</span><span class="sxs-lookup"><span data-stu-id="c8e20-214">Python</span></span>](#tab/tabid-python)
<span data-ttu-id="c8e20-215">Bir Python ana bilgisayar programı şu şekilde oluşturulur:</span><span class="sxs-lookup"><span data-stu-id="c8e20-215">A Python host program is constructed as follows:</span></span>
1. <span data-ttu-id="c8e20-216">Modül `qsharp` yükleyicisini birlikte çalışabilirlik için kaydeden modülünü içeri aktarın Q# .</span><span class="sxs-lookup"><span data-stu-id="c8e20-216">Import the `qsharp` module, which registers the module loader for Q# interoperability.</span></span> 
    <span data-ttu-id="c8e20-217">Bu Q# , ad alanlarının Python modülleri olarak görünmesine izin verir ve bu da "içeri aktarabilir" Q# .</span><span class="sxs-lookup"><span data-stu-id="c8e20-217">This allows Q# namespaces to appear as Python modules, from which we can "import" Q# callables.</span></span>
    <span data-ttu-id="c8e20-218">Teknik olarak Q# , içeri aktarılan ve bunlara çağrı sağlayan Python saplamalarının kendilerine ait olduğunu unutmayın.</span><span class="sxs-lookup"><span data-stu-id="c8e20-218">Note that it is technically not the Q# callables themselves which are imported, but rather Python stubs which allow calling into them.</span></span>
    <span data-ttu-id="c8e20-219">Bunlar, Python sınıflarının nesneleri gibi davranır.</span><span class="sxs-lookup"><span data-stu-id="c8e20-219">These behave as objects of Python classes.</span></span> <span data-ttu-id="c8e20-220">Programı çalıştırırken işlemi gönderdiğimiz hedef makineleri belirtmek için bu nesneler üzerinde yöntemler kullanıyoruz.</span><span class="sxs-lookup"><span data-stu-id="c8e20-220">We use methods on these objects to specify the target machines that we send the operation to when running the program.</span></span>

2. <span data-ttu-id="c8e20-221">Q#Bu durumda---doğrudan çağıracağız bu callables 'yi içeri aktarın `MeasureSuperposition` ve `MeasureSuperpositionArray` .</span><span class="sxs-lookup"><span data-stu-id="c8e20-221">Import those Q# callables which we will directly invoke---in this case, `MeasureSuperposition` and `MeasureSuperpositionArray`.</span></span>
    ```python
    import qsharp
    from NamespaceName import MeasureSuperposition, MeasureSuperpositionArray
    ```
    <span data-ttu-id="c8e20-222">`qsharp`Modül içeri aktarılmışsa, ayrıca doğrudan kitaplık ad alanlarından callables 'yi içeri aktarabilirsiniz Q# .</span><span class="sxs-lookup"><span data-stu-id="c8e20-222">With the `qsharp` module imported, you can also import callables directly from the Q# library namespaces.</span></span>

3. <span data-ttu-id="c8e20-223">Diğer herhangi bir Python kodu arasında, artık bu callabları belirli hedef makinelere çağırabilir ve geri dönüşlerini, daha fazla kullanım için (bir değer döndürdüler) değişkenlere atayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="c8e20-223">Among any other Python code, you can now call those callables on specific target machines, and assign their returns to variables (if they return a value) for further use.</span></span>

#### <a name="specifying-target-machines"></a><span data-ttu-id="c8e20-224">Hedef makineleri belirtme</span><span class="sxs-lookup"><span data-stu-id="c8e20-224">Specifying target machines</span></span>
<span data-ttu-id="c8e20-225">Belirli bir hedef makinede çalıştırılacak bir işlemin çağrılması, içeri aktarılan nesnede farklı Python yöntemleri aracılığıyla yapılır.</span><span class="sxs-lookup"><span data-stu-id="c8e20-225">Calling an operation to be run on a specific target machine is done via different Python methods on the imported object.</span></span>
<span data-ttu-id="c8e20-226">Örneğin, `.simulate(<args>)` `QuantumSimulator` işlemini çalıştırmak için öğesini kullanır, ancak `.estimate_resources(<args>)` bunu yapar `ResourcesEstimator` .</span><span class="sxs-lookup"><span data-stu-id="c8e20-226">For example, `.simulate(<args>)`, uses the `QuantumSimulator` to run the operation, whereas `.estimate_resources(<args>)` does so on the `ResourcesEstimator`.</span></span>

#### <a name="passing-inputs-to-q"></a><span data-ttu-id="c8e20-227">Girdileri Q 'a geçirme\#</span><span class="sxs-lookup"><span data-stu-id="c8e20-227">Passing inputs to Q\#</span></span>
<span data-ttu-id="c8e20-228">Çağrılabilir bağımsız değişkenleri Q# , anahtar sözcüğünün çağrılabilir tanımda bağımsız değişken adı olduğu anahtar sözcük bağımsız değişkeni biçiminde sağlanmalıdır Q# .</span><span class="sxs-lookup"><span data-stu-id="c8e20-228">Arguments for the Q# callable should be provided in the form of a keyword argument, where the keyword is the argument name in the Q# callable definition.</span></span>
<span data-ttu-id="c8e20-229">Yani, `MeasureSuperpositionArray.simulate(n=4)` geçerlidir, ancak `MeasureSuperpositionArray.simulate(4)` bir hata oluşturur.</span><span class="sxs-lookup"><span data-stu-id="c8e20-229">That is, `MeasureSuperpositionArray.simulate(n=4)` is valid, whereas `MeasureSuperpositionArray.simulate(4)` would throw an error.</span></span>

<span data-ttu-id="c8e20-230">Bu nedenle, Python ana bilgisayar programı</span><span class="sxs-lookup"><span data-stu-id="c8e20-230">Therefore, the Python host program</span></span> 

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

<span data-ttu-id="c8e20-231">aşağıdakine benzer bir çıktı oluşur:</span><span class="sxs-lookup"><span data-stu-id="c8e20-231">results in an output like the following:</span></span>

```output
Single qubit:
1
{'CNOT': 0, 'QubitClifford': 1, 'R': 0, 'Measure': 1, 'T': 0, 'Depth': 0, 'Width': 1, 'BorrowedWidth': 0}

Multiple qubits:
[0, 1, 1, 1]
{'CNOT': 0, 'QubitClifford': 4, 'R': 0, 'Measure': 4, 'T': 0, 'Depth': 0, 'Width': 4, 'BorrowedWidth': 0}
```

#### <a name="using-no-locq-code-from-other-projects-or-packages"></a><span data-ttu-id="c8e20-232">Q#Diğer projelerden veya paketlerdeki kodu kullanma</span><span class="sxs-lookup"><span data-stu-id="c8e20-232">Using Q# code from other projects or packages</span></span>

<span data-ttu-id="c8e20-233">Varsayılan olarak, `import qsharp` komut tüm `.qs` dosyaları geçerli klasöre yükler ve kendi Q# Işlemlerini ve işlevlerini Python betiği içinden kullanıma sunar.</span><span class="sxs-lookup"><span data-stu-id="c8e20-233">By default, the `import qsharp` command loads all of the `.qs` files in the current folder and makes their Q# operations and functions available for use from inside the Python script.</span></span>

<span data-ttu-id="c8e20-234">Başka bir Q# klasörden kod yüklemek için [ `qsharp.projects` API](https://docs.microsoft.com/python/qsharp-core/qsharp.projects.projects) , bir proje için bir dosyaya başvuru eklemek için kullanılabilir `.csproj` (yani Q# , başvuran bir proje `Microsoft.Quantum.Sdk` ).</span><span class="sxs-lookup"><span data-stu-id="c8e20-234">To load Q# code from another folder, the [`qsharp.projects` API](https://docs.microsoft.com/python/qsharp-core/qsharp.projects.projects) can be used to add a reference to a `.csproj` file for a Q# project (that is, a project that references `Microsoft.Quantum.Sdk`).</span></span>
<span data-ttu-id="c8e20-235">Bu komut `.qs` , ve alt klasörlerini içeren klasördeki tüm dosyaları derler `.csproj` .</span><span class="sxs-lookup"><span data-stu-id="c8e20-235">This command will compile any `.qs` files in the folder containing the `.csproj` and its subfolders.</span></span> <span data-ttu-id="c8e20-236">Ayrıca, `PackageReference` ya da Q# Bu dosyanın üzerinden başvurulan projeler aracılığıyla başvurulan paketleri yinelemeli olarak yükler `ProjectReference` `.csproj` .</span><span class="sxs-lookup"><span data-stu-id="c8e20-236">It will also recursively load any packages referenced via `PackageReference` or Q# projects referenced via `ProjectReference` in that `.csproj` file.</span></span>

<span data-ttu-id="c8e20-237">Örnek olarak, aşağıdaki Python kodu bir dış projeyi içeri aktarır ve geçerli klasöre göre yoluna başvurarak, işlemlerinden birini çağırır Q# :</span><span class="sxs-lookup"><span data-stu-id="c8e20-237">As an example, the following Python code imports an external project, referencing its path relative to the current folder, and invokes one of its Q# operations:</span></span>

```python
import qsharp
qsharp.projects.add("../qrng/Qrng.csproj")
from Qrng import SampleQuantumRandomNumberGenerator
print(f"Qrng result: {SampleQuantumRandomNumberGenerator.simulate()}")
```

<span data-ttu-id="c8e20-238">Bu, aşağıdakine benzer bir çıktı ile sonuçlanır:</span><span class="sxs-lookup"><span data-stu-id="c8e20-238">This results in output like the following:</span></span>

```output
Adding reference to project: ../qrng/Qrng.csproj
Qrng result: 0
```

<span data-ttu-id="c8e20-239">Kod içeren harici paketleri yüklemek için Q# [ `qsharp.packages` API](https://docs.microsoft.com/python/qsharp-core/qsharp.packages.packages)'yi kullanın.</span><span class="sxs-lookup"><span data-stu-id="c8e20-239">To load external packages containing Q# code, use the [`qsharp.packages` API](https://docs.microsoft.com/python/qsharp-core/qsharp.packages.packages).</span></span>

<span data-ttu-id="c8e20-240">Q#Geçerli klasördeki kod dış projelere veya paketlere bağımlıysa, `import qsharp` Bağımlılıklar henüz yüklenmediği için çalışırken hatalarla karşılaşabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="c8e20-240">If the Q# code in the current folder depends on external projects or packages, you may see errors when running `import qsharp`, since the dependencies have not yet been loaded.</span></span>
<span data-ttu-id="c8e20-241">Komut sırasında gerekli harici paketleri veya Q# projeleri yüklemek için `import qsharp` , Python betiğinin bulunduğu klasörde, başvuruda bulunan bir dosya bulunduğundan emin olun `.csproj` `Microsoft.Quantum.Sdk` .</span><span class="sxs-lookup"><span data-stu-id="c8e20-241">To load required external packages or Q# projects during the `import qsharp` command, ensure that the folder with the Python script contains a `.csproj` file which references `Microsoft.Quantum.Sdk`.</span></span> <span data-ttu-id="c8e20-242">Bu durumda, `.csproj` özelliğini öğesine ekleyin `<IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>` `<PropertyGroup>` .</span><span class="sxs-lookup"><span data-stu-id="c8e20-242">In that `.csproj`, add the property `<IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>` to the `<PropertyGroup>`.</span></span> <span data-ttu-id="c8e20-243">Bu, Q# `ProjectReference` `PackageReference` komutu sırasında ' de bulunan herhangi bir veya öğesini yinelemeli olarak yükleyemem talimatını verecektir `.csproj` `import qsharp` .</span><span class="sxs-lookup"><span data-stu-id="c8e20-243">This will instruct IQ# to recursively load any `ProjectReference` or `PackageReference` items found in that `.csproj` during the `import qsharp` command.</span></span>

<span data-ttu-id="c8e20-244">Örneğin, `.csproj` Q# paketi otomatik olarak yükleyemem neden olan basit bir dosya aşağıda verilmiştir `Microsoft.Quantum.Chemistry` :</span><span class="sxs-lookup"><span data-stu-id="c8e20-244">For example, here is a simple `.csproj` file that causes IQ# to automatically load the `Microsoft.Quantum.Chemistry` package:</span></span>

```xml
<Project Sdk="Microsoft.Quantum.Sdk/0.12.20072031">
    <PropertyGroup>
        <OutputType>Library</OutputType>
        <TargetFramework>netstandard2.1</TargetFramework>
        <IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>
    </PropertyGroup>
    <ItemGroup>
        <PackageReference Include="Microsoft.Quantum.Chemistry" Version="0.12.20072031" />
    </ItemGroup>
</Project>
```

> [!NOTE]
> <span data-ttu-id="c8e20-245">Şu anda bu özel `<IQSharpLoadAutomatically>` özellik Python konakları için gereklidir, ancak gelecekte bu, `.csproj` Python betiği ile aynı klasörde bulunan bir dosya için varsayılan davranış haline gelebilir.</span><span class="sxs-lookup"><span data-stu-id="c8e20-245">Currently this custom `<IQSharpLoadAutomatically>` property is required by Python hosts, but in the future, this may become the default behavior for a `.csproj` file located in the same folder as the Python script.</span></span>

> [!NOTE]
> <span data-ttu-id="c8e20-246">`<QsharpCompile>`' Deki ayarı, `.csproj` Python konakları tarafından yok sayılır ve `.qs` `.csproj` (alt klasörler dahil) klasöründeki tüm dosyalar yüklenir ve derlenir.</span><span class="sxs-lookup"><span data-stu-id="c8e20-246">Currently the `<QsharpCompile>` setting in the `.csproj` is ignored by Python hosts, and all `.qs` files in the folder of the `.csproj` (including subfolders) are loaded and compiled.</span></span> <span data-ttu-id="c8e20-247">`.csproj`Gelecekte ayarlar için destek sunulacaktır (daha fazla ayrıntı için bkz. [ıqsharp # 277](https://github.com/microsoft/iqsharp/issues/277) ).</span><span class="sxs-lookup"><span data-stu-id="c8e20-247">Support for `.csproj` settings will be improved in the future (see [iqsharp#277](https://github.com/microsoft/iqsharp/issues/277) for more details).</span></span>


### <a name="c"></a>[<span data-ttu-id="c8e20-248">C#</span><span class="sxs-lookup"><span data-stu-id="c8e20-248">C#</span></span>](#tab/tabid-csharp)

<span data-ttu-id="c8e20-249">C# ana bilgisayar programında birden çok bileşen vardır ve bunlar, c# üzerinde oluşturulan simülatörleri gibi bazı QDK bileşenleriyle çok daha yakından çalışmaktadır.</span><span class="sxs-lookup"><span data-stu-id="c8e20-249">A C# host program has multiple components, and works very closely with some components of the QDK, such as the simulators, which are themselves built on C#.</span></span>

<span data-ttu-id="c8e20-250">Q#Derleyici burada, dosyanızdaki ad alanından bir equivalently adlı C# ad alanı oluşturarak işe yarar Q# Q# .</span><span class="sxs-lookup"><span data-stu-id="c8e20-250">The Q# compiler works here by generating an equivalently named C# namespace from the Q# namespace in our Q# file.</span></span>
<span data-ttu-id="c8e20-251">Daha sonra, her bir Q# callables veya içinde tanımlanan türler için bir equivalently adlandırılmış C# sınıfı oluşturur.</span><span class="sxs-lookup"><span data-stu-id="c8e20-251">It further generates an equivalently named C# class for each of the Q# callables or types defined therein.</span></span>

<span data-ttu-id="c8e20-252">İlk olarak, bir ana bilgisayar programımızda `using` , `open` bizim dosyanızdaki deyimlerde kabaca bir şekilde olan deyimlerle kullanılabilir olan tüm sınıfları sunuyoruz Q# :</span><span class="sxs-lookup"><span data-stu-id="c8e20-252">First, we make any classes used in our host program available with `using` statements, which are roughly analagous to the `open` statements in our Q# file:</span></span>

```csharp
using System;
using System.Threading.Tasks;
using Microsoft.Quantum.Simulation.Simulators;    // contains the target machines (for example, QuantumSimulator, ResourcesEstimator)
using NamespaceName;                              // make the Q# namespace available
```

<span data-ttu-id="c8e20-253">Daha sonra C# ad boşluğumuzu, diğer birkaç bit ve parçadan (aşağıdaki tam kod bloğuna bakın) ve ardından beğendiğimiz tüm klasik programlama (örneğin, callables için işlem değişkenleri) bildiririz Q# .</span><span class="sxs-lookup"><span data-stu-id="c8e20-253">Next, we declare our C# namespace, a few other bits and pieces (see the full code block below), and then any classical programming we would like (for example, computing arguments for the Q# callables).</span></span>
<span data-ttu-id="c8e20-254">İkinci durumda gerekli değildir, ancak bu tür bir örnek  [.net birlikte çalışabilirlik örneğinde](https://github.com/microsoft/Quantum/tree/main/samples/interoperability/dotnet)bulunabilir.</span><span class="sxs-lookup"><span data-stu-id="c8e20-254">The latter isn't necessary in our case, but an example of such usage can be found at the  [.NET interoperability sample](https://github.com/microsoft/Quantum/tree/main/samples/interoperability/dotnet).</span></span>

#### <a name="target-machines"></a><span data-ttu-id="c8e20-255">Hedef makineler</span><span class="sxs-lookup"><span data-stu-id="c8e20-255">Target machines</span></span>

<span data-ttu-id="c8e20-256">Uygulamasına geri döndüğünüzde Q# , üzerinde operasyonlarımızı çalıştıracağız her türlü hedef makinenin bir örneğini oluşturmamız gerekir.</span><span class="sxs-lookup"><span data-stu-id="c8e20-256">Getting back to Q#, we must create an instance of whatever target machine we will run our operations on.</span></span>

```csharp
            using var sim = new QuantumSimulator();
```

<span data-ttu-id="c8e20-257">Diğer hedef makinelerin kullanılması, farklı bir örnek oluşturmak kadar basittir, ancak bunu yapmanın ve döndürmesinin işlem biçimi biraz farklı olabilir.</span><span class="sxs-lookup"><span data-stu-id="c8e20-257">Using other target machines is as simple as instantiating a different one, although the manner of doing so and processing the returns can be slightly different.</span></span>
<span data-ttu-id="c8e20-258">Kısaltma için, şu an için ' i kullanıma sunuyoruz [`QuantumSimulator`](xref:microsoft.quantum.machines.full-state-simulator) ve aşağıdakileri dahil ediyoruz [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) [below](#including-the-resources-estimator).</span><span class="sxs-lookup"><span data-stu-id="c8e20-258">For brevity, we stick to the [`QuantumSimulator`](xref:microsoft.quantum.machines.full-state-simulator) for now, and include the [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) [below](#including-the-resources-estimator).</span></span>

<span data-ttu-id="c8e20-259">İşlemlerden oluşturulan her C# sınıfının Q# `Run` , hedef makine örneği olması gereken ilk bağımsız değişkeni olan bir yöntemi vardır.</span><span class="sxs-lookup"><span data-stu-id="c8e20-259">Each C# class generated from the Q# operations have a `Run` method, the first argument of which must be the target machine instance.</span></span>
<span data-ttu-id="c8e20-260">Bu nedenle, `MeasureSuperposition` üzerinde çalıştırmak için `QuantumSimulator` kullanırız `MeasureSuperposition.Run(sim)` .</span><span class="sxs-lookup"><span data-stu-id="c8e20-260">So, to run `MeasureSuperposition` on the `QuantumSimulator`, we use `MeasureSuperposition.Run(sim)`.</span></span>
<span data-ttu-id="c8e20-261">Döndürülen sonuçlar daha sonra C# dilinde değişkenlere atanabilir:</span><span class="sxs-lookup"><span data-stu-id="c8e20-261">The returned results can then be assigned to variables in C#:</span></span>

```csharp
            var singleQubitResult = await MeasureSuperposition.Run(sim);
```

> [!NOTE]
> <span data-ttu-id="c8e20-262">`Run`Bu, gerçek hisse donanımı için durum olacağı ve bu nedenle `await` anahtar sözcüğünün, görev tamamlanana kadar daha fazla işlemeyi engellediği için zaman uyumsuz olarak çalıştırılır.</span><span class="sxs-lookup"><span data-stu-id="c8e20-262">The `Run` method is run asynchronously because this will be the case for real quantum hardware, and therefore the `await` keyword blocks further processing until the task completes.</span></span>

<span data-ttu-id="c8e20-263">Q#Çağrılabilir bir dönüşe sahip değilse (örneğin, dönüş türüne sahipse `Unit` ), çalıştırma yine de bir değişkene atamadan aynı şekilde yapılabilir.</span><span class="sxs-lookup"><span data-stu-id="c8e20-263">If the Q# callable does not have any returns (for example, it has return type `Unit`), then the run can still be done in the same manner without assigning it to a variable.</span></span>
<span data-ttu-id="c8e20-264">Bu durumda, tüm satır yalnızca</span><span class="sxs-lookup"><span data-stu-id="c8e20-264">In that case, the entire line would simply consist of</span></span> 
```csharp
await <callable>.Run(<simulator>);
```

#### <a name="arguments"></a><span data-ttu-id="c8e20-265">Arguments</span><span class="sxs-lookup"><span data-stu-id="c8e20-265">Arguments</span></span>

<span data-ttu-id="c8e20-266">Çağrılabilir bir bütün bağımsız değişkenler Q# , hedef makineden sonra ek bağımsız değişkenler olarak geçirilir.</span><span class="sxs-lookup"><span data-stu-id="c8e20-266">Any arguments to the Q# callable are simply passed as additional arguments after the target machine.</span></span>
<span data-ttu-id="c8e20-267">Bu nedenle, `MeasureSuperpositionArray` `n=4` qubits 'in sonuçları aracılığıyla getirilir</span><span class="sxs-lookup"><span data-stu-id="c8e20-267">Hence the results of `MeasureSuperpositionArray` on `n=4` qubits would fetched via</span></span> 

```csharp
            var multiQubitResult = await MeasureSuperpositionArray.Run(sim, 4);
```

<span data-ttu-id="c8e20-268">Böylece tam bir C# ana bilgisayar programı şöyle görünebilir</span><span class="sxs-lookup"><span data-stu-id="c8e20-268">A full C# host program could thus look like</span></span>

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

<span data-ttu-id="c8e20-269">C# dosyasının konumunda, ana bilgisayar programı komut isteminden şunu girerek çalıştırılabilir:</span><span class="sxs-lookup"><span data-stu-id="c8e20-269">At the location of the C# file, the host program can be run from the command prompt by entering</span></span>
```dotnetcli
dotnet run
```
<span data-ttu-id="c8e20-270">Bu durumda, şuna benzer şekilde konsola yazılan çıktıyı görürsünüz:</span><span class="sxs-lookup"><span data-stu-id="c8e20-270">and in this case you will see output written to the console similar to</span></span> 
```output
Single qubit result: One
Multiple qubit result: [One,One,Zero,Zero]
```

> [!NOTE]
> <span data-ttu-id="c8e20-271">Derleyicinin ad alanları ile birlikte çalışabilirliğine bağlı olarak, ayrıca Q# ıvgımlerimizi `using NamespaceName;` deyimsiz olarak kullanabilir ve C# ad alanı başlığını bununla eşleştirmeniz yeterlidir.</span><span class="sxs-lookup"><span data-stu-id="c8e20-271">Due to the compiler's interoperability with namespaces, we could alternatively make our Q# callables available without the `using NamespaceName;` statement, and simply matching the C# namespace title to it.</span></span>
> <span data-ttu-id="c8e20-272">Diğer bir deyişle, `namespace host` ile değiştirin `namespace NamespaceName` .</span><span class="sxs-lookup"><span data-stu-id="c8e20-272">That is, by replacing `namespace host` with `namespace NamespaceName`.</span></span>

#### <a name="including-the-resources-estimator"></a><span data-ttu-id="c8e20-273">Kaynak tahmin aracı dahil</span><span class="sxs-lookup"><span data-stu-id="c8e20-273">Including the resources estimator</span></span>

<span data-ttu-id="c8e20-274">, [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) Çıktıyı almak için biraz farklı bir uygulama gerektirir.</span><span class="sxs-lookup"><span data-stu-id="c8e20-274">The [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) requires a slightly different implementation to retrieve the output.</span></span>

<span data-ttu-id="c8e20-275">İlk olarak, bunları bir ifadesiyle bir değişken olarak Örneklemek yerine `using` (ile yaptığımız gibi `QuantumSimulator` ), ile sınıfın nesnelerini doğrudan örnekliyoruz</span><span class="sxs-lookup"><span data-stu-id="c8e20-275">Firstly, instead of instantiating them as a variable with a `using` statement (as we do with the `QuantumSimulator`), we more directly instantiate objects of the class via</span></span>

```csharp
            var estimatorSingleQ = new ResourcesEstimator();
            var estimatorMultiQ = new ResourcesEstimator();
```

<span data-ttu-id="c8e20-276">Tek bir hedef simülatörü yerine birden çok işlem tarafından kullanılacak şekilde Q# , her biri için bir tane örnekliyoruz.</span><span class="sxs-lookup"><span data-stu-id="c8e20-276">Notice that instead of a single target simulator to be used by multiple Q# operations, we have instantiated one for each.</span></span> <span data-ttu-id="c8e20-277">Bunun nedeni, nesnelerin kendisi hedef makineler olarak kullanıldığında değiştirilmektedir ve sonuçları daha sonra sınıf yöntemiyle elde edilebilir `.ToTSV()` .</span><span class="sxs-lookup"><span data-stu-id="c8e20-277">This is because the objects themselves are modified when used as target machines, and their results can then be retrieved afterwards with the class method `.ToTSV()`.</span></span>

<span data-ttu-id="c8e20-278">Kaynakları kaynak estimators üzerinde çalıştırmak için şunu kullanıyoruz</span><span class="sxs-lookup"><span data-stu-id="c8e20-278">To run the operations on the resource estimators, we use</span></span>

```csharp
            await MeasureSuperposition.Run(estimatorSingleQ);
            await MeasureSuperpositionArray.Run(estimatorMultiQ, 4);
```
<span data-ttu-id="c8e20-279">ardından sonuçları ve ile sekmeyle ayrılmış değerler (TSV) olarak getirin `estimatorSingleQ.ToTSV()` `estimatorMultiQ.ToTSV()` .</span><span class="sxs-lookup"><span data-stu-id="c8e20-279">and then fetch the results as tab-separated-values (TSV) with `estimatorSingleQ.ToTSV()` and `estimatorMultiQ.ToTSV()`.</span></span>

<span data-ttu-id="c8e20-280">Bu nedenle, hem hem de kullanan tam bir C# ana bilgisayar `QuantumSimulator` programı `ResourcesEstimator` şu biçimde olabilir:</span><span class="sxs-lookup"><span data-stu-id="c8e20-280">So, a full C# host program making use of both the `QuantumSimulator` and `ResourcesEstimator` could take the form:</span></span>

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


<span data-ttu-id="c8e20-281">aşağıdakine benzer bir çıktı verecek</span><span class="sxs-lookup"><span data-stu-id="c8e20-281">which would yield output similar to</span></span>

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

## <a name="no-locq-jupyter-notebooks"></a><span data-ttu-id="c8e20-282">Q# Jupyıter Not defterleri</span><span class="sxs-lookup"><span data-stu-id="c8e20-282">Q# Jupyter Notebooks</span></span>
<span data-ttu-id="c8e20-283">Q# Jupyter Not defterleri, Q# Q# tüm yönergeler, notlar ve diğer içeriklerden---tek bir not defterinde callables tanımlamanızı, derlemenize ve çalıştırmanıza olanak tanıyan ı çekirdeğini kullanır.</span><span class="sxs-lookup"><span data-stu-id="c8e20-283">Q# Jupyter Notebooks make use of the IQ# kernel, which allows you to define, compile, and run Q# callables in a single notebook---all alongside instructions, notes, and other content.</span></span>
<span data-ttu-id="c8e20-284">Bu, dosyaların içeriğini içeri ve dışarı aktarmak mümkün olsa `*.qs` Q# da, çalıştırma modelinde gerekli değildir anlamına gelir.</span><span class="sxs-lookup"><span data-stu-id="c8e20-284">This means that while it is possible to import and use the contents of `*.qs` Q# files, they are not necessary in the run model.</span></span>

<span data-ttu-id="c8e20-285">Burada, yukarıda tanımlanan işlemleri nasıl çalıştıracağınızı ayrıntılarız Q# , ancak Q# [giriş Q# ve jupi](https://github.com/microsoft/Quantum/blob/main/samples/getting-started/intro-to-iqsharp/Notebook.ipynb)Not defterleri Ile jupi not defterlerini kullanma hakkında daha geniş bir giriş sunulmaktadır.</span><span class="sxs-lookup"><span data-stu-id="c8e20-285">Here, we will detail how to run the Q# operations defined above, but a more broad introduction to using Q# Jupyter Notebooks is provided at [Intro to Q# and Jupyter Notebooks](https://github.com/microsoft/Quantum/blob/main/samples/getting-started/intro-to-iqsharp/Notebook.ipynb).</span></span>

### <a name="defining-operations"></a><span data-ttu-id="c8e20-286">İşlemleri tanımlama</span><span class="sxs-lookup"><span data-stu-id="c8e20-286">Defining operations</span></span>

<span data-ttu-id="c8e20-287">Bir Q# Jupyter Notebook, Q# kodu bir dosyanın ad alanının içinden yaptığımız gibi girersiniz Q# .</span><span class="sxs-lookup"><span data-stu-id="c8e20-287">In a Q# Jupyter Notebook, you enter Q# code just as we would from inside the namespace of a Q# file.</span></span>

<span data-ttu-id="c8e20-288">Bu nedenle, ilgili ad alanları için deyimlerle [ Q# Standart kitaplıklardan](xref:microsoft.quantum.libraries.standard.intro) callables 'e erişimi etkinleştirebiliriz `open` .</span><span class="sxs-lookup"><span data-stu-id="c8e20-288">So, we can enable access to callables from the [Q# standard libraries](xref:microsoft.quantum.libraries.standard.intro) with `open` statements for their respective namespaces.</span></span>
<span data-ttu-id="c8e20-289">Bu tür bir deyime sahip bir hücreyi çalıştırırken, bu ad alanlarından alınan tanımlar çalışma alanı boyunca kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="c8e20-289">Upon running a cell with such a statement, the definitions from those namespaces are available throughout the workspace.</span></span>

> [!NOTE]
> <span data-ttu-id="c8e20-290">[Microsoft. hisse. iç](xref:Microsoft.Quantum.Intrinsic) ve [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon) 'nin (örneğin, ve) callables, [`H`](xref:Microsoft.Quantum.Intrinsic.H) [`ApplyToEach`](xref:Microsoft.Quantum.Canon.ApplyToEach) Q# jupi Not defterlerindeki hücrelerde tanımlanan işlemler için otomatik olarak kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="c8e20-290">Callables from [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic) and [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon) (for example, [`H`](xref:Microsoft.Quantum.Intrinsic.H) and [`ApplyToEach`](xref:Microsoft.Quantum.Canon.ApplyToEach)) are automatically available to operations defined within cells in Q# Jupyter Notebooks.</span></span>
> <span data-ttu-id="c8e20-291">Ancak, bu, dış Q# kaynak dosyalarından ( [giriş Q# ve jupi not defterlerine](https://github.com/microsoft/Quantum/blob/main/samples/getting-started/intro-to-iqsharp/Notebook.ipynb)göre gösterilen bir işlem) getirilen kod için doğru değildir.</span><span class="sxs-lookup"><span data-stu-id="c8e20-291">However, this is not true for code brought in from external Q# source files (a process shown at [Intro to Q# and Jupyter Notebooks](https://github.com/microsoft/Quantum/blob/main/samples/getting-started/intro-to-iqsharp/Notebook.ipynb)).</span></span> 
> 

<span data-ttu-id="c8e20-292">Benzer şekilde, tanımlama işlemleri yalnızca kodu yazmak Q# ve hücreyi çalıştırmak için gereklidir.</span><span class="sxs-lookup"><span data-stu-id="c8e20-292">Similarly, defining operations requires only writing the Q# code and running the cell.</span></span>

<img src="../media/hostprograms_jupyter_op_def_crop.png" alt="Jupyter cell defining Q# operations" width="773">

<span data-ttu-id="c8e20-293">Daha sonra çıktı bu işlemleri listeler, daha sonra gelecekteki hücrelerden çağrılabilir.</span><span class="sxs-lookup"><span data-stu-id="c8e20-293">The output then lists those operations, which can then be called from future cells.</span></span>

### <a name="target-machines"></a><span data-ttu-id="c8e20-294">Hedef makineler</span><span class="sxs-lookup"><span data-stu-id="c8e20-294">Target machines</span></span>

<span data-ttu-id="c8e20-295">Belirli hedef makinelerde işlem çalıştırma işlevselliği [I Q# Magic komutları](xref:microsoft.quantum.guide.quickref.iqsharp)aracılığıyla sağlanır.</span><span class="sxs-lookup"><span data-stu-id="c8e20-295">The functionality to run operations on specific target machines is provided via [IQ# Magic Commands](xref:microsoft.quantum.guide.quickref.iqsharp).</span></span>
<span data-ttu-id="c8e20-296">Örneğin, `%simulate` `QuantumSimulator` öğesini kullanır ve şunları `%estimate` kullanır `ResourcesEstimator` :</span><span class="sxs-lookup"><span data-stu-id="c8e20-296">For example, `%simulate` makes use of the `QuantumSimulator`, and `%estimate` uses the `ResourcesEstimator`:</span></span>

<img src="../media/hostprograms_jupyter_no_args_sim_est_crop.png" alt="Jupyter cell simulating a Q# operation and running resource estimation" width="773">

### <a name="passing-inputs-to-functions-and-operations"></a><span data-ttu-id="c8e20-297">İşlevlere ve işlemlere giriş geçirme</span><span class="sxs-lookup"><span data-stu-id="c8e20-297">Passing inputs to functions and operations</span></span>

<span data-ttu-id="c8e20-298">Q#İşlemleri işlemlere geçirmek için bağımsız değişkenler bir `key=value` Magic komutunu Çalıştır komutuna çiftler olarak geçirilebilir.</span><span class="sxs-lookup"><span data-stu-id="c8e20-298">To pass inputs to the Q# operations, the arguments can be passed as `key=value` pairs to the run magic command.</span></span>
<span data-ttu-id="c8e20-299">Bu nedenle, `MeasureSuperpositionArray` dört qubit ile çalıştırmak için şunları çalıştırabiliriz `%simulate MeasureSuperpositionArray n=4` :</span><span class="sxs-lookup"><span data-stu-id="c8e20-299">So, to run `MeasureSuperpositionArray` with four qubits, we can run `%simulate MeasureSuperpositionArray n=4`:</span></span>

<img src="../media/hostprograms_jupyter_args_sim_crop.png" alt="Jupyter cell simulating a Q# operation with arguments" width="773">

<span data-ttu-id="c8e20-300">Bu model, `%estimate` ve diğer çalıştırma komutlarıyla benzer şekilde kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="c8e20-300">This pattern can be used similarly with `%estimate` and other run commands.</span></span>

### <a name="using-no-locq-code-from-other-projects-or-packages"></a><span data-ttu-id="c8e20-301">Q#Diğer projelerden veya paketlerdeki kodu kullanma</span><span class="sxs-lookup"><span data-stu-id="c8e20-301">Using Q# code from other projects or packages</span></span>

<span data-ttu-id="c8e20-302">Varsayılan olarak, bir Q# Jupyter Notebook tüm `.qs` dosyaları geçerli klasöre yükler ve Q# işlemlerini ve işlevlerini Not defterinin içinden kullanıma sunar.</span><span class="sxs-lookup"><span data-stu-id="c8e20-302">By default, a Q# Jupyter Notebook loads all of the `.qs` files in the current folder and makes their Q# operations and functions available for use from inside the notebook.</span></span> <span data-ttu-id="c8e20-303">[ `%who` MAGIC komutu](xref:microsoft.quantum.iqsharp.magic-ref.who) , mevcut olan tüm Q# işlemleri ve işlevleri listeler.</span><span class="sxs-lookup"><span data-stu-id="c8e20-303">The [`%who` magic command](xref:microsoft.quantum.iqsharp.magic-ref.who) lists all currently-available Q# operations and functions.</span></span>

<span data-ttu-id="c8e20-304">Başka bir Q# klasörden kod yüklemek için, [ `%project` MAGIC komutu](xref:microsoft.quantum.iqsharp.magic-ref.project) bir proje için bir dosyaya başvuru eklemek için kullanılabilir `.csproj` (yani Q# , başvuru yapan bir proje `Microsoft.Quantum.Sdk` ).</span><span class="sxs-lookup"><span data-stu-id="c8e20-304">To load Q# code from another folder, the [`%project` magic command](xref:microsoft.quantum.iqsharp.magic-ref.project) can be used to add a reference to a `.csproj` file for a Q# project (that is, a project that references `Microsoft.Quantum.Sdk`).</span></span> <span data-ttu-id="c8e20-305">Bu komut `.qs` , `.csproj` (ve alt klasörleri) içeren klasörde bulunan dosyaları derler.</span><span class="sxs-lookup"><span data-stu-id="c8e20-305">This command will compile any `.qs` files in the folder containing the `.csproj` (and subfolders).</span></span> <span data-ttu-id="c8e20-306">Ayrıca, `PackageReference` ya da Q# Bu dosyanın üzerinden başvurulan projeler aracılığıyla başvurulan paketleri yinelemeli olarak yükler `ProjectReference` `.csproj` .</span><span class="sxs-lookup"><span data-stu-id="c8e20-306">It will also recursively load any packages referenced via `PackageReference` or Q# projects referenced via `ProjectReference` in that `.csproj` file.</span></span> 

<span data-ttu-id="c8e20-307">Örnek olarak, aşağıdaki hücreler, Q# Proje yolunun geçerli klasöre göre başvurduğu bir dış projeden bir işlemin benzetimini yapar:</span><span class="sxs-lookup"><span data-stu-id="c8e20-307">As an example, the following cells simulate a Q# operation from an external project, where the project path is referenced relative to the current folder:</span></span>

<img src="../media/hostprograms_jupyter_project_crop.png" alt="Jupyter cell simulating a Q# operation from an external project" width="773">

<span data-ttu-id="c8e20-308">Kod içeren harici paketleri yüklemek için Q# [ `%package` Magic komutunu](xref:microsoft.quantum.iqsharp.magic-ref.package)kullanın.</span><span class="sxs-lookup"><span data-stu-id="c8e20-308">To load external packages containing Q# code, use the [`%package` magic command](xref:microsoft.quantum.iqsharp.magic-ref.package).</span></span>
<span data-ttu-id="c8e20-309">Bir paketin yüklenmesi, özel bir Magic komutu da kullanılabilir hale getirir veya paketin parçası olan tüm derlemelerde bulunan kodlayıcıları görüntüler.</span><span class="sxs-lookup"><span data-stu-id="c8e20-309">Loading a package will also make available any custom magic commands or display encoders that are contained in any assemblies that are part of the package.</span></span>

<span data-ttu-id="c8e20-310">Q#Not defteri başlatma zamanında dış paketleri veya projeleri yüklemek için Not defteri klasörünün başvuran bir dosya içerdiğinden emin olun `.csproj` `Microsoft.Quantum.Sdk` .</span><span class="sxs-lookup"><span data-stu-id="c8e20-310">To load external packages or Q# projects at notebook intialization time, ensure that the notebook folder contains a `.csproj` file which references `Microsoft.Quantum.Sdk`.</span></span> <span data-ttu-id="c8e20-311">Bu durumda, `.csproj` özelliğini öğesine ekleyin `<IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>` `<PropertyGroup>` .</span><span class="sxs-lookup"><span data-stu-id="c8e20-311">In that `.csproj`, add the property `<IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>` to the `<PropertyGroup>`.</span></span> <span data-ttu-id="c8e20-312">Bu, içinde bulunan Q# `ProjectReference` ve `PackageReference` `.csproj` Not defteri yükleme sırasında bulunan ' de bulunan her türlü öğeyi yinelemeli olarak yüklemeyi ister.</span><span class="sxs-lookup"><span data-stu-id="c8e20-312">This will instruct IQ# to recursively load any `ProjectReference` or `PackageReference` items found in that `.csproj` at notebook load time.</span></span>

<span data-ttu-id="c8e20-313">Örneğin, `.csproj` Q# paketi otomatik olarak yükleyemem neden olan basit bir dosya aşağıda verilmiştir `Microsoft.Quantum.Chemistry` :</span><span class="sxs-lookup"><span data-stu-id="c8e20-313">For example, here is a simple `.csproj` file that causes IQ# to automatically load the `Microsoft.Quantum.Chemistry` package:</span></span>

```xml
<Project Sdk="Microsoft.Quantum.Sdk/0.12.20072031">
    <PropertyGroup>
        <OutputType>Library</OutputType>
        <TargetFramework>netstandard2.1</TargetFramework>
        <IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>
    </PropertyGroup>
    <ItemGroup>
        <PackageReference Include="Microsoft.Quantum.Chemistry" Version="0.12.20072031" />
    </ItemGroup>
</Project>
```

> [!NOTE]
> <span data-ttu-id="c8e20-314">Şu anda bu özel `<IQSharpLoadAutomatically>` özellik Q# Jupyter Notebook konakları için gereklidir, ancak gelecekte bu durum, `.csproj` Not defteri dosyasıyla aynı klasörde bulunan bir dosya için varsayılan davranış haline gelebilir.</span><span class="sxs-lookup"><span data-stu-id="c8e20-314">Currently this custom `<IQSharpLoadAutomatically>` property is required by Q# Jupyter Notebook hosts, but in the future, this may become the default behavior for a `.csproj` file located in the same folder as the notebook file.</span></span>

> [!NOTE]
> <span data-ttu-id="c8e20-315">`<QsharpCompile>`' Deki ayarı şu anda `.csproj` Jupyter Notebook konakları tarafından yok sayılır Q# ve `.qs` `.csproj` (alt klasörler dahil) klasöründeki tüm dosyalar yüklenir ve derlenir.</span><span class="sxs-lookup"><span data-stu-id="c8e20-315">Currently the `<QsharpCompile>` setting in the `.csproj` is ignored by Q# Jupyter Notebook hosts, and all `.qs` files in the folder of the `.csproj` (including subfolders) are loaded and compiled.</span></span> <span data-ttu-id="c8e20-316">`.csproj`Gelecekte ayarlar için destek sunulacaktır (daha fazla ayrıntı için bkz. [ıqsharp # 277](https://github.com/microsoft/iqsharp/issues/277) ).</span><span class="sxs-lookup"><span data-stu-id="c8e20-316">Support for `.csproj` settings will be improved in the future (see [iqsharp#277](https://github.com/microsoft/iqsharp/issues/277) for more details).</span></span>
