---
title: Q# programlarını test etme ve hata ayıklama
description: Kuantum programlarını test etmek ve hata ayıklamak için birim testlerini, olguları ve iddiaları ve döküm işlevlerini nasıl kullanacağınızı öğrenin.
author: tcNickolas
ms.author: mamykhai@microsoft.com
uid: microsoft.quantum.techniques.testing-and-debugging
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: caf15b7273b7efed1da87a2edd62c06cd4357593
ms.sourcegitcommit: b6b8459eb654040f1e19f66411b29fc9e48e95c9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "82030591"
---
# <a name="testing-and-debugging"></a><span data-ttu-id="99f7e-103">Test ve Hata Ayıklama</span><span class="sxs-lookup"><span data-stu-id="99f7e-103">Testing and Debugging</span></span>

<span data-ttu-id="99f7e-104">Klasik programlamada olduğu gibi, kuantum programlarının amaçlandığı gibi hareket ettiğini kontrol edebilmek ve yanlış olan bir kuantum programını tanılayabilmek esastır.</span><span class="sxs-lookup"><span data-stu-id="99f7e-104">As with classical programming, it is essential to be able to check that quantum programs act as intended, and to be able to diagnose a quantum program that is incorrect.</span></span>
<span data-ttu-id="99f7e-105">Bu bölümde, kuantum programlarını test etmek ve hata ayıklamak için Q# tarafından sunulan araçları kapsamaktayız.</span><span class="sxs-lookup"><span data-stu-id="99f7e-105">In this section, we cover the tools offered by Q# for testing and debugging quantum programs.</span></span>

## <a name="unit-tests"></a><span data-ttu-id="99f7e-106">Ünite Testleri</span><span class="sxs-lookup"><span data-stu-id="99f7e-106">Unit Tests</span></span>

<span data-ttu-id="99f7e-107">Klasik programları sınamak için yaygın bir yaklaşım, bir kitaplıkta kod çalıştıran *birim testleri* adı verilen küçük programlar yazmak ve çıktısını beklenen bazı çıktılarla karşılaştırmaktır.</span><span class="sxs-lookup"><span data-stu-id="99f7e-107">One common approach to testing classical programs is to write small programs called *unit tests* which run code in a library and compare its output to some expected output.</span></span>
<span data-ttu-id="99f7e-108">Örneğin, *biz bir priori* `4`bildiğimiz `Square(2)` için, bu döner sağlamak isteyebilirsiniz $ 2 ^2 = 4 $.</span><span class="sxs-lookup"><span data-stu-id="99f7e-108">For instance, we may want to ensure that `Square(2)` returns `4`, since we know *a priori* that $2^2 = 4$.</span></span>

<span data-ttu-id="99f7e-109">Q#, kuantum programları için birim testler oluşturmayı destekler ve [xUnit](https://xunit.github.io/) birim test çerçevesi içinde test olarak yürütülebilir.</span><span class="sxs-lookup"><span data-stu-id="99f7e-109">Q# supports creating unit tests for quantum programs, and which can be executed as tests within the [xUnit](https://xunit.github.io/) unit testing framework.</span></span>

### <a name="creating-a-test-project"></a><span data-ttu-id="99f7e-110">Test Projesi Oluşturma</span><span class="sxs-lookup"><span data-stu-id="99f7e-110">Creating a Test Project</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="99f7e-111">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="99f7e-111">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="99f7e-112">Görsel Stüdyo 2019'u açın.</span><span class="sxs-lookup"><span data-stu-id="99f7e-112">Open Visual Studio 2019.</span></span> <span data-ttu-id="99f7e-113">`File` Menüye gidin ve `New`seçin.  >  `Project...`</span><span class="sxs-lookup"><span data-stu-id="99f7e-113">Go to the `File` menu and select `New` > `Project...`.</span></span>
<span data-ttu-id="99f7e-114">Sağ üst köşede şablonu `Q#` `Q# Test Project` arayın ve seçin.</span><span class="sxs-lookup"><span data-stu-id="99f7e-114">In the upper right corner, search for `Q#`, and select the `Q# Test Project` template.</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="99f7e-115">Komut Satırı / Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="99f7e-115">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="99f7e-116">Sık kullanılan komut satırından aşağıdaki komutu çalıştırın:</span><span class="sxs-lookup"><span data-stu-id="99f7e-116">From your favorite command line, run the following command:</span></span>
```bash
$ dotnet new xunit -lang Q# -o Tests
$ cd Tests
$ code . # To open in Visual Studio Code
```

****

<span data-ttu-id="99f7e-117">Yeni projenizde, yeni `Tests.qs`Q# birim testlerini tanımlamak için uygun bir yer sağlayan tek bir dosya olacaktır.</span><span class="sxs-lookup"><span data-stu-id="99f7e-117">Your new project will have a single file `Tests.qs`, which provides a convenient place to define new Q# unit tests.</span></span>
<span data-ttu-id="99f7e-118">Başlangıçta bu dosya, yeni `AllocateQubit` tahsis edilen bir qubit'in $\ket{0}$ durumunda olduğunu denetleyen ve bir iletiyi yazdıran bir örnek birim testi içerir:</span><span class="sxs-lookup"><span data-stu-id="99f7e-118">Initially this file contains one sample unit test `AllocateQubit` which checks that a newly allocated qubit is in the $\ket{0}$ state and prints a message:</span></span>

```qsharp
    @Test("QuantumSimulator")
    operation AllocateQubit () : Unit {

        using (qubit = Qubit()) {
            Assert([PauliZ], [qubit], Zero, "Newly allocated qubit must be in the |0⟩ state.");
        }
        
        Message("Test passed");
    }
```

:yeni: <span data-ttu-id="99f7e-119">Tür `Unit` ve döndürme `Unit` bağımsız değişkeni alan herhangi bir Q# `@Test("...")` işlemi veya işlevi öznitelik üzerinden birim testi olarak işaretlenebilir.</span><span class="sxs-lookup"><span data-stu-id="99f7e-119">Any Q# operation or function that takes an argument of type `Unit` and returns `Unit` can be marked as a unit test via the `@Test("...")` attribute.</span></span> <span data-ttu-id="99f7e-120">Bu öznitelik için `"QuantumSimulator"` argüman, yukarıda, test yürütüldedilir hedef belirtir.</span><span class="sxs-lookup"><span data-stu-id="99f7e-120">The argument to that attribute, `"QuantumSimulator"` above, specifies the target on which the test is executed.</span></span> <span data-ttu-id="99f7e-121">Tek bir test birden çok hedefüzerinde yürütülebilir.</span><span class="sxs-lookup"><span data-stu-id="99f7e-121">A single test can be executed on multiple targets.</span></span> <span data-ttu-id="99f7e-122">Örneğin, yukarıdaki `AllocateQubit`bir `@Test("ResourcesEstimator")` öznitelik ekleyin.</span><span class="sxs-lookup"><span data-stu-id="99f7e-122">For example, add an attribute `@Test("ResourcesEstimator")` above `AllocateQubit`.</span></span> 
```qsharp
    @Test("QuantumSimulator")
    @Test("ResourcesEstimator")
    operation AllocateQubit () : Unit {
        ...
```
<span data-ttu-id="99f7e-123">Dosyayı kaydedin ve tüm testleri çalıştırın.</span><span class="sxs-lookup"><span data-stu-id="99f7e-123">Save the file and execute all tests.</span></span> <span data-ttu-id="99f7e-124">Şimdi iki birim testleri olmalıdır, biri AllocateQubit QuantumSimulator üzerinde yürütülür, ve bir nerede ResourceEstimator yürütülür.</span><span class="sxs-lookup"><span data-stu-id="99f7e-124">There should now be two unit tests, one where AllocateQubit is executed on the QuantumSimulator, and one where it is executed in the ResourceEstimator.</span></span> 

<span data-ttu-id="99f7e-125">Q# derleyicisi yerleşik hedefleri tanır "QuantumSimulator", "ToffoliSimulator" ve "ResourcesEstimator" birim testleri için geçerli yürütme hedefleri olarak.</span><span class="sxs-lookup"><span data-stu-id="99f7e-125">The Q# compiler recognizes the built-in targets "QuantumSimulator", "ToffoliSimulator", and "ResourcesEstimator" as valid execution targets for unit tests.</span></span> <span data-ttu-id="99f7e-126">Özel bir yürütme hedefi tanımlamak için tam nitelikli bir ad belirtmek de mümkündür.</span><span class="sxs-lookup"><span data-stu-id="99f7e-126">It is also possible to specify any fully qualified name to define a custom execution target.</span></span> 

### <a name="running-q-unit-tests"></a><span data-ttu-id="99f7e-127">Koşu Q# Birim Testleri</span><span class="sxs-lookup"><span data-stu-id="99f7e-127">Running Q# Unit Tests</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="99f7e-128">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="99f7e-128">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="99f7e-129">Çözüm başına tek seferlik kurulum olarak, `Test` menüye gidin ve seçin. `Test Settings`  >  `Default Processor Architecture`  >  `X64`</span><span class="sxs-lookup"><span data-stu-id="99f7e-129">As a one-time per-solution setup, go to `Test` menu and select `Test Settings` > `Default Processor Architecture` > `X64`.</span></span>

> [!TIP]
> <span data-ttu-id="99f7e-130">Visual Studio için varsayılan işlemci mimarisi ayarı,`.suo`her çözüm için çözüm seçenekleri ( ) dosyasında depolanır.</span><span class="sxs-lookup"><span data-stu-id="99f7e-130">The default processor architecture setting for Visual Studio is stored in the solution options (`.suo`) file for each solution.</span></span>
> <span data-ttu-id="99f7e-131">Bu dosyayı silerseniz, işlemci `X64` mimariniz olarak yeniden seçmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="99f7e-131">If you delete this file, then you will need to select `X64` as your processor architecture again.</span></span>

<span data-ttu-id="99f7e-132">Projeyi `Test` oluşturun, menüye gidin `Windows`  >  `Test Explorer`ve seçin.</span><span class="sxs-lookup"><span data-stu-id="99f7e-132">Build the project, go to the `Test` menu and select `Windows` > `Test Explorer`.</span></span> <span data-ttu-id="99f7e-133">`AllocateQubit``Not Run Tests` gruptaki testler listesinde gösterecektir.</span><span class="sxs-lookup"><span data-stu-id="99f7e-133">`AllocateQubit` will show up in the list of tests in the `Not Run Tests` group.</span></span> <span data-ttu-id="99f7e-134">Bu `Run All` bireysel testi seçin veya çalıştırın ve geçmesi gerekir!</span><span class="sxs-lookup"><span data-stu-id="99f7e-134">Select `Run All` or run this individual test, and it should pass!</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="99f7e-135">Komut Satırı / Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="99f7e-135">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="99f7e-136">Testleri çalıştırmak için proje klasörüne (klasör) `Tests.csproj`gidin ve komutu çalıştırın:</span><span class="sxs-lookup"><span data-stu-id="99f7e-136">To run tests, navigate to the project folder (the folder which contains `Tests.csproj`), and execute the command:</span></span>

```bash
$ dotnet restore
$ dotnet test
```

<span data-ttu-id="99f7e-137">Aşağıdakilere benzer çıktı almalısınız:</span><span class="sxs-lookup"><span data-stu-id="99f7e-137">You should get output similar to the following:</span></span>

```
Build started, please wait...
Build completed.

Test run for C:\Users\chgranad.REDMOND\tmp\Tests\bin\Debug\netcoreapp2.0\Tests.dll(.NETCoreApp,Version=v2.0)
Microsoft (R) Test Execution Command Line Tool Version 15.3.0-preview-20170628-02
Copyright (c) Microsoft Corporation.  All rights reserved.

Starting test execution, please wait...
[xUnit.net 00:00:00.5864002]   Discovering: Tests
[xUnit.net 00:00:00.7073844]   Discovered:  Tests
[xUnit.net 00:00:00.7453826]   Starting:    Tests
[xUnit.net 00:00:00.9590439]   Finished:    Tests

Total tests: 1. Passed: 1. Failed: 0. Skipped: 0.
Test Run Successful.
Test execution time: 1.9607 Seconds
```

<span data-ttu-id="99f7e-138">Birim testleri adlarına ve/veya yürütme hedefine göre filtrelenebilir:</span><span class="sxs-lookup"><span data-stu-id="99f7e-138">Unit tests can be filtered according to their name and/or the execution target:</span></span>

```bash 
$ dotnet test --filter "Target=QuantumSimulator"
$ dotnet test --filter "Name=AllocateQubit"
```


***

<span data-ttu-id="99f7e-139">İçsel işlev <xref:microsoft.quantum.intrinsic.message> türüne `(String -> Unit)` sahiptir ve tanılama iletilerinin oluşturulmasını sağlar.</span><span class="sxs-lookup"><span data-stu-id="99f7e-139">The intrinsic function <xref:microsoft.quantum.intrinsic.message> has type `(String -> Unit)` and enables the creation of diagnostic messages.</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="99f7e-140">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="99f7e-140">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="99f7e-141">Test Gezgini'nde bir test çalıştırDıktan ve teste tıkladıktan sonra, test yürütmesi hakkında bilgi içeren bir panel görünür: Geçirilen/Başarısız olan durum, geçen süre ve bir "Çıktı" bağlantısı.</span><span class="sxs-lookup"><span data-stu-id="99f7e-141">After you execute a test in Test Explorer and click on the test, a panel will appear with information about test execution: Passed/Failed status, elapsed time and an "Output" link.</span></span> <span data-ttu-id="99f7e-142">"Çıktı" bağlantısını tıklattığınızda, test çıktısı yeni bir pencerede açılır.</span><span class="sxs-lookup"><span data-stu-id="99f7e-142">If you click the "Output" link, test output will open in a new window.</span></span>

![test çıktısı](~/media/unit-test-output.png)

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="99f7e-144">Komut Satırı / Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="99f7e-144">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="99f7e-145">Her testin geçme/başarısız durumu konsola `dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="99f7e-145">The pass/fail status for each test is printed to the console by `dotnet test`.</span></span>
<span data-ttu-id="99f7e-146">Başarısız testler için çıktılar da başarısızlığı tanılamaya yardımcı olmak için konsola yazdırılır.</span><span class="sxs-lookup"><span data-stu-id="99f7e-146">For failing tests, the outputs are also printed to the console to help diagnose the failure.</span></span>

***

## <a name="facts-and-assertions"></a><span data-ttu-id="99f7e-147">Gerçekler ve İddialar</span><span class="sxs-lookup"><span data-stu-id="99f7e-147">Facts and Assertions</span></span>

<span data-ttu-id="99f7e-148">Q# işlevlerinin _mantıksal_ yan etkileri olmadığından, çıkış türü boş olan bir işlevi yürütmenin _diğer_ `()` etkileri hiçbir zaman Q# programı içinde gözlemlenmez.</span><span class="sxs-lookup"><span data-stu-id="99f7e-148">Because functions in Q# have no _logical_ side effects, any _other kinds_ of effects of executing a function whose output type is the empty tuple `()` can never be observed from within a Q# program.</span></span>
<span data-ttu-id="99f7e-149">Diğer bir diğer, bir hedef makine, bu `()` ihmalin aşağıdaki Q# kodunun davranışını değiştirmeyeceğini garanti ederek dönen herhangi bir işlevi yürütmemeyi seçebilir.</span><span class="sxs-lookup"><span data-stu-id="99f7e-149">That is, a target machine can choose not to execute any function which returns `()` with the guarantee that this omission will not modify the behavior of any following Q# code.</span></span>
<span data-ttu-id="99f7e-150">Bu, dönen `()` işlevleri `Unit`(yani) iddiaları katıştırma ve mantık hata ayıklama için yararlı bir araç yapar.</span><span class="sxs-lookup"><span data-stu-id="99f7e-150">This makes functions returning `()` (i.e. `Unit`) a useful tool for embedding assertions and debugging logic into Q# programs.</span></span> 

<span data-ttu-id="99f7e-151">Basit bir örnek ele alalım:</span><span class="sxs-lookup"><span data-stu-id="99f7e-151">Let's consider a simple example:</span></span>

```qsharp
function PositivityFact(value : Double) : Unit 
{
    if (value <= 0) 
    {
        fail "Expected a positive number.";
    }
}
```

<span data-ttu-id="99f7e-152">Burada, anahtar `fail` kelime hesaplama devam etmemelidir gösterir, Q # programı çalıştıran hedef makinede bir özel durum yükselterek.</span><span class="sxs-lookup"><span data-stu-id="99f7e-152">Here, the keyword `fail` indicates that the computation should not proceed, raising an exception in the target machine running the Q# program.</span></span>
<span data-ttu-id="99f7e-153">Tanım olarak, bir deyim ebeden sonra başka Bir Q# kodu çalıştırılmadığı için, Bu tür bir `fail` hata Q#'ın içinden gözlemlenemez.</span><span class="sxs-lookup"><span data-stu-id="99f7e-153">By definition, a failure of this kind cannot be observed from within Q#, as no further Q# code is run after a `fail` statement is reached.</span></span>
<span data-ttu-id="99f7e-154">Bu nedenle, bir çağrının `PositivityFact`ötesine geçersek, girişinin olumlu olduğundan emin olabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="99f7e-154">Thus, if we proceed past a call to `PositivityFact`, we can be assured by that its input was positive.</span></span>

<span data-ttu-id="99f7e-155">Ad alanından `PositivityFact` [`Fact`](xref:microsoft.quantum.diagnostics.fact) işlevi kullanarak aynı davranışı uygulayabileceğimizi <xref:microsoft.quantum.diagnostics> unutmayın:</span><span class="sxs-lookup"><span data-stu-id="99f7e-155">Note that we can implement the same behavior as `PositivityFact` using the [`Fact`](xref:microsoft.quantum.diagnostics.fact) function from the <xref:microsoft.quantum.diagnostics> namespace:</span></span>

```qsharp
    Fact(value > 0, "Expected a positive number.");
```

<span data-ttu-id="99f7e-156">*İddialar,* diğer taraftan, gerçeklere benzer şekilde kullanılır, ancak hedef makinenin durumuna bağlı olabilir.</span><span class="sxs-lookup"><span data-stu-id="99f7e-156">*Assertions*, on the other hand, are used similarly to facts, but may be dependent on the state of the target machine.</span></span> <span data-ttu-id="99f7e-157">Buna karşılık, bunlar operasyon olarak tanımlanırken, olgular işlevler (yukarıdaki gibi) olarak tanımlanır.</span><span class="sxs-lookup"><span data-stu-id="99f7e-157">Correspondingly, they are defined as operations, whereas facts are defined as functions (as above).</span></span>
<span data-ttu-id="99f7e-158">Ayrımı anlamak için, bir iddia içinde bir gerçeğin aşağıdaki kullanımını göz önünde bulundurun:</span><span class="sxs-lookup"><span data-stu-id="99f7e-158">To understand the distinction, consider the following use of a fact within an assertion:</span></span>

```qsharp
operation AssertQubitsAreAvailable() : Unit
{
     Fact(GetQubitsAvailableToUse() > 0, "No qubits were actually available");
}
```

<span data-ttu-id="99f7e-159">Burada, kullanabileceğimiz qubit sayısını döndürmek için işlemi <xref:microsoft.quantum.environment.getqubitsavailabletouse> kullanıyoruz.</span><span class="sxs-lookup"><span data-stu-id="99f7e-159">Here, we are using the operation <xref:microsoft.quantum.environment.getqubitsavailabletouse> to return the number of qubits available to use.</span></span>
<span data-ttu-id="99f7e-160">Bu açıkça programın küresel durumuna ve yürütme ortamına `AssertQubitsAreAvailable` bağlı olduğu için, bizim tanımımız da bir operasyon olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="99f7e-160">As this clearly depends on the global state of the program and its execution environment, our definition of  `AssertQubitsAreAvailable` must be an operation as well.</span></span>
<span data-ttu-id="99f7e-161">Ancak, bu küresel `Bool` `Fact` durumu, işleve girdi olarak basit bir değer sağlamak için kullanabiliriz.</span><span class="sxs-lookup"><span data-stu-id="99f7e-161">However, we can use that global state to yield a simple `Bool` value as input to the `Fact` function.</span></span>

<span data-ttu-id="99f7e-162">Bu fikirler üzerine bina, [prelüd](xref:microsoft.quantum.libraries.standard.prelude) iki özellikle <xref:microsoft.quantum.intrinsic.assert> <xref:microsoft.quantum.intrinsic.assertprob> yararlı iddialar sunuyor, `()`ve her ikisi de üzerine operasyon olarak modellenmiştir.</span><span class="sxs-lookup"><span data-stu-id="99f7e-162">Building on these ideas, [the prelude](xref:microsoft.quantum.libraries.standard.prelude) offers two especially useful assertions, <xref:microsoft.quantum.intrinsic.assert> and <xref:microsoft.quantum.intrinsic.assertprob> both modeled as operations onto `()`.</span></span> <span data-ttu-id="99f7e-163">Bu iddiaların her biri, belirli bir ilgi ölçüsünü, ölçümün yapılacağı kuantum kaydını ve varsayımsal bir sonucu açıklayan bir Pauli operatöralır.</span><span class="sxs-lookup"><span data-stu-id="99f7e-163">These assertions each take a Pauli operator describing a particular measurement of interest, a quantum register on which a measurement is to be performed, and a hypothetical outcome.</span></span>
<span data-ttu-id="99f7e-164">Simülasyon ile çalışan hedef makinelerde, [klonlamasız teoremi](https://en.wikipedia.org/wiki/No-cloning_theorem)ile bağlı değiliz ve bu tür iddialara aktarılan kaydı bozmadan bu ölçümleri gerçekleştirebiliyoruz.</span><span class="sxs-lookup"><span data-stu-id="99f7e-164">On target machines which work by simulation, we are not bound by [the no-cloning theorem](https://en.wikipedia.org/wiki/No-cloning_theorem), and can perform such measurements without disturbing the register passed to such assertions.</span></span>
<span data-ttu-id="99f7e-165">Bir simülatör daha sonra, yukarıdaki `PositivityFact` fonksiyona benzer, varsayımsal sonuç pratikte gözlenen olmaz eğer hesaplama iptal edebilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="99f7e-165">A simulator can then, similar to the `PositivityFact` function above, abort computation if the hypothetical outcome would not be observed in practice:</span></span>

```qsharp
using (register = Qubit()) 
{
    H(register);
    Assert([PauliX], [register], Zero);
    // Even though we do not have access to states in Q#,
    // we know by the anthropic principle that the state
    // of register at this point is |+〉.
}
```

<span data-ttu-id="99f7e-166">Fiziksel kuantum donanım, nerede no-klonlama teoremi kuantum durumunun `Assert` incelenmesini engeller, ve `AssertProb` işlemler sadece başka bir etkisi ile dönmek. `()`</span><span class="sxs-lookup"><span data-stu-id="99f7e-166">On physical quantum hardware, where the no-cloning theorem prevents examination of quantum state, the `Assert` and `AssertProb` operations simply return `()` with no other effect.</span></span>

<span data-ttu-id="99f7e-167">Ad <xref:microsoft.quantum.diagnostics> alanı bize daha gelişmiş `Assert` koşulları kontrol etmek için izin ailenin birkaç daha fazla işlevleri sağlar.</span><span class="sxs-lookup"><span data-stu-id="99f7e-167">The <xref:microsoft.quantum.diagnostics> namespace provides several more functions of the `Assert` family which allow us to check more advanced conditions.</span></span> 

## <a name="dump-functions"></a><span data-ttu-id="99f7e-168">Döküm Fonksiyonları</span><span class="sxs-lookup"><span data-stu-id="99f7e-168">Dump Functions</span></span>

<span data-ttu-id="99f7e-169">Kuantum programlarını sorun gidermeye <xref:microsoft.quantum.diagnostics> yardımcı olmak için, ad alanı bir dosyaya hedef <xref:microsoft.quantum.diagnostics.dumpmachine> makinenin geçerli durumunu dökümü iki işlev sunar: ve <xref:microsoft.quantum.diagnostics.dumpregister>.</span><span class="sxs-lookup"><span data-stu-id="99f7e-169">To help troubleshooting quantum programs, the <xref:microsoft.quantum.diagnostics> namespace offers two functions that can dump into a file the current status of the target machine: <xref:microsoft.quantum.diagnostics.dumpmachine> and <xref:microsoft.quantum.diagnostics.dumpregister>.</span></span> <span data-ttu-id="99f7e-170">Her birinin üretilen çıktısı hedef makineye bağlıdır.</span><span class="sxs-lookup"><span data-stu-id="99f7e-170">The generated output of each depends on the target machine.</span></span>

### <a name="dumpmachine"></a><span data-ttu-id="99f7e-171">DumpMachine</span><span class="sxs-lookup"><span data-stu-id="99f7e-171">DumpMachine</span></span>

<span data-ttu-id="99f7e-172">Kuantum Gelişim Kiti'nin bir parçası olarak dağıtılan tam devlet kuantum simülatörü dosyaya tüm kuantum sisteminin [dalga fonksiyonunu,](https://en.wikipedia.org/wiki/Wave_function) karmaşık sayıların tek boyutlu bir dizi olarak yazar, her öğe hesaplamasal temel durumu ölçme olasılığının genliğini temsil eder $\ket{n}$, burada $ket{n} = \ket{b_{n-n}... b_1b_0}$ bit için\{\}$ b_i $.</span><span class="sxs-lookup"><span data-stu-id="99f7e-172">The full-state quantum simulator distributed as part of the Quantum Development Kit writes into the file the [wave function](https://en.wikipedia.org/wiki/Wave_function) of the entire quantum system, as a one-dimensional array of complex numbers, in which each element represents the amplitude of the probability of measuring the computational basis state $\ket{n}$, where $\ket{n} = \ket{b_{n-1}...b_1b_0}$ for bits $\{b_i\}$.</span></span> <span data-ttu-id="99f7e-173">Örneğin, yalnızca iki qubit ayrılmış bir makinede ve kuantum durumunda $$ \begin{align}{1}\ket{\psi} ={2}\frac{00} {\sqrt } \ket{2} -{10}\frac{(1 + <xref:microsoft.quantum.diagnostics.dumpmachine> i)} \ket , \end{align} $$ arama bu çıktıyı oluşturur:</span><span class="sxs-lookup"><span data-stu-id="99f7e-173">For example, on a machine with only two qubits allocated and in the quantum state $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10}, \end{align} $$ calling <xref:microsoft.quantum.diagnostics.dumpmachine> generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 0;1
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣2❭:    -0.500000 + -0.500000 i  ==     **********           [ 0.500000 ]   /     [ -2.35619 rad ]
∣3❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

<span data-ttu-id="99f7e-174">İlk satır, ilgili qubit'lerin kimliklerini önemli sırayla içeren bir yorum sağlar.</span><span class="sxs-lookup"><span data-stu-id="99f7e-174">The first row provides a comment with the IDs of the corresponding qubits in their significant order.</span></span>
<span data-ttu-id="99f7e-175">Satırların geri kalanı, kartezyen ve kutupbiçimlerinde $\ket{n}$ temel durum vektörünün ölçülmesi nin olasılık genliğini açıklar.</span><span class="sxs-lookup"><span data-stu-id="99f7e-175">The rest of the rows describe the probability amplitude of measuring the basis state vector $\ket{n}$ in both Cartesian and polar formats.</span></span> <span data-ttu-id="99f7e-176">İlk satır için ayrıntılı olarak:</span><span class="sxs-lookup"><span data-stu-id="99f7e-176">In detail for the first row:</span></span>

* <span data-ttu-id="99f7e-177">**`∣0❭:`** bu satır `0` hesaplama temel durumuna karşılık gelir</span><span class="sxs-lookup"><span data-stu-id="99f7e-177">**`∣0❭:`** this row corresponds to the `0` computational basis state</span></span>
* <span data-ttu-id="99f7e-178">**`0.707107 +  0.000000 i`**: Kartezyen formatında olasılık genliği.</span><span class="sxs-lookup"><span data-stu-id="99f7e-178">**`0.707107 +  0.000000 i`**: the probability amplitude in Cartesian format.</span></span>
* <span data-ttu-id="99f7e-179">**` == `**: `equal` işaret her iki eşdeğer temsili de ayırıyor.</span><span class="sxs-lookup"><span data-stu-id="99f7e-179">**` == `**: the `equal` sign seperates both equivalent representations.</span></span>
* <span data-ttu-id="99f7e-180">**`**********  `**: Büyüklüğün grafiksel gösterimi, `*` sayısı bu durum vektörünün ölçülmesi olasılığı ile orantılıdır.</span><span class="sxs-lookup"><span data-stu-id="99f7e-180">**`**********  `**: A graphical representation of the magnitude, the number of `*` is proportionate to the probability of measuring this state vector.</span></span>
* <span data-ttu-id="99f7e-181">**`[ 0.500000 ]`**: büyüklüğün sayısal değeri</span><span class="sxs-lookup"><span data-stu-id="99f7e-181">**`[ 0.500000 ]`**: the numeric value of the magnitude</span></span>
* <span data-ttu-id="99f7e-182">**`    ---`**: Genlik evresinin grafiksel gösterimi (aşağıya bakınız).</span><span class="sxs-lookup"><span data-stu-id="99f7e-182">**`    ---`**: A graphical representation of the amplitude's phase (see below).</span></span>
* <span data-ttu-id="99f7e-183">**`[ 0.0000 rad ]`**: fazın sayısal değeri (radyanlarda).</span><span class="sxs-lookup"><span data-stu-id="99f7e-183">**`[ 0.0000 rad ]`**: the numeric value of the phase (in radians).</span></span>

<span data-ttu-id="99f7e-184">Hem büyüklük hem de faz grafik gösterimi ile görüntülenir.</span><span class="sxs-lookup"><span data-stu-id="99f7e-184">Both the magnitude and the phase are displayed with a graphical representation.</span></span> <span data-ttu-id="99f7e-185">Büyüklük gösterimi doğrudan ileri: bir çubuk `*`gösterir , büyük olasılık bar olacak.</span><span class="sxs-lookup"><span data-stu-id="99f7e-185">The magnitude representation is straight-forward: it shows a bar of `*`, the bigger the probability the bigger the bar will be.</span></span> <span data-ttu-id="99f7e-186">Faz için, aralıklara dayalı açıyı temsil edecek aşağıdaki sembolleri gösteririz:</span><span class="sxs-lookup"><span data-stu-id="99f7e-186">For the phase, we show the following symbols to represent the angle based on ranges:</span></span>

```
[ -π/16,   π/16)       ---
[  π/16,  3π/16)        /-
[ 3π/16,  5π/16)        / 
[ 5π/16,  7π/16)       +/ 
[ 7π/16,  9π/16)      ↑   
[ 8π/16, 11π/16)    \-    
[ 7π/16, 13π/16)    \     
[ 7π/16, 15π/16)   +\     
[15π/16, 19π/16)   ---    
[17π/16, 19π/16)   -/     
[19π/16, 21π/16)    /     
[21π/16, 23π/16)    /+    
[23π/16, 25π/16)      ↓   
[25π/16, 27π/16)       -\ 
[27π/16, 29π/16)        \ 
[29π/16, 31π/16)        \+
[31π/16,   π/16)       ---
```

<span data-ttu-id="99f7e-187">Aşağıdaki örnekler `DumpMachine` bazı ortak durumlar için gösterilmektedir:</span><span class="sxs-lookup"><span data-stu-id="99f7e-187">The following examples show `DumpMachine` for some common states:</span></span>

### `∣0❭`

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

### `∣1❭`

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣1❭:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
```

### `∣+❭`

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]      --- [  0.00000 rad ]
∣1❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]      --- [  0.00000 rad ]
```

### `∣-❭`

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]      --- [  0.00000 rad ]
∣1❭:    -0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]  ---     [  3.14159 rad ]
```


  > [!NOTE]
  > <span data-ttu-id="99f7e-188">Bir qubit id runtime atanır ve mutlaka qubit tahsis edildiği sırayla veya bir qubit kayıt içinde konumu ile uyumlu değildir.</span><span class="sxs-lookup"><span data-stu-id="99f7e-188">The id of a qubit is assigned at runtime and it's not necessarily aligned with the order in which the qubit was allocated or its position within a qubit register.</span></span>


#### <a name="visual-studio-2019"></a>[<span data-ttu-id="99f7e-189">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="99f7e-189">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

  > [!TIP]
  > <span data-ttu-id="99f7e-190">Visual Studio'da kodunuza bir kesme noktası koyarak ve bir qubit değişkeninin değerini inceleyerek bir qubit id'i çözebilirsiniz, örneğin:</span><span class="sxs-lookup"><span data-stu-id="99f7e-190">You can figure out a qubit id in Visual Studio by putting a breakpoint in your code and inspecting the value of a qubit variable, for example:</span></span>
  > 
  > ![Visual Studio'da qubit id göster](~/media/qubit_id.png)
  >
  > <span data-ttu-id="99f7e-192">`0` indeksi olan `register2` qubit`3`id= , dizinli `1` `2`qubit id= .</span><span class="sxs-lookup"><span data-stu-id="99f7e-192">the qubit with index `0` on `register2` has id=`3`, the qubit with index `1` has id=`2`.</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="99f7e-193">Komut Satırı / Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="99f7e-193">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

  > [!TIP]
  > <span data-ttu-id="99f7e-194"><xref:microsoft.quantum.intrinsic.message> İşlevi kullanarak ve iletideki qubit değişkenini geçerek bir qubit id'i çözebilirsiniz, örneğin:</span><span class="sxs-lookup"><span data-stu-id="99f7e-194">You can figure out a qubit id by using the <xref:microsoft.quantum.intrinsic.message> function and passing the qubit variable in the message, for example:</span></span>
  >
  > ```qsharp
  > Message($"0={register2[0]}; 1={register2[1]}");
  > ```
  > 
  > <span data-ttu-id="99f7e-195">bu çıktıyı oluşturabilir:</span><span class="sxs-lookup"><span data-stu-id="99f7e-195">which could generate this output:</span></span>
  >```
  > 0=q:3; 1=q:2
  >```
  > <span data-ttu-id="99f7e-196">yani `0` dizin li qubit `register2` id=`3`, dizinli `1` qubit`2`id= .</span><span class="sxs-lookup"><span data-stu-id="99f7e-196">which means that the qubit with index `0` on `register2` has id=`3`, the qubit with index `1` has id=`2`.</span></span>


***

<span data-ttu-id="99f7e-197"><xref:microsoft.quantum.diagnostics.dumpmachine>ad alanının <xref:microsoft.quantum.diagnostics> bir parçasıdır, bu nedenle kullanmak için `open` bir deyim eklemeniz gerekir:</span><span class="sxs-lookup"><span data-stu-id="99f7e-197"><xref:microsoft.quantum.diagnostics.dumpmachine> is part of the  <xref:microsoft.quantum.diagnostics> namespace, so in order to use it you must add an `open` statement:</span></span>

```qsharp
namespace Samples {
    open Microsoft.Quantum.Intrinsic;
    open Microsoft.Quantum.Diagnostics;

    operation Operation () : Unit {
        using (qubits = Qubit[2]) {
            H(qubits[1]);
            DumpMachine("dump.txt");
        }
    }
}
```


### <a name="dumpregister"></a><span data-ttu-id="99f7e-198">DumpRegister</span><span class="sxs-lookup"><span data-stu-id="99f7e-198">DumpRegister</span></span>

<span data-ttu-id="99f7e-199"><xref:microsoft.quantum.diagnostics.dumpregister>gibi <xref:microsoft.quantum.diagnostics.dumpmachine>çalışır , aynı zamanda sadece ilgili qubits ile ilgili bilgi miktarını sınırlamak için qubits bir dizi alır dışında.</span><span class="sxs-lookup"><span data-stu-id="99f7e-199"><xref:microsoft.quantum.diagnostics.dumpregister> works like <xref:microsoft.quantum.diagnostics.dumpmachine>, except it also takes an array of qubits to limit the amount of information to only that relevant to the corresponding qubits.</span></span>

<span data-ttu-id="99f7e-200">Olduğu <xref:microsoft.quantum.diagnostics.dumpmachine>gibi , tarafından <xref:microsoft.quantum.diagnostics.dumpregister> oluşturulan bilgiler hedef makineye bağlıdır.</span><span class="sxs-lookup"><span data-stu-id="99f7e-200">As with <xref:microsoft.quantum.diagnostics.dumpmachine>, the information generated by <xref:microsoft.quantum.diagnostics.dumpregister> depends on the target machine.</span></span> <span data-ttu-id="99f7e-201">Tam hal kuantum simülatörü için dosyaya dalga fonksiyonu kadar kuantum alt sisteminin küresel bir faz olarak aynı formatta sağlanan qubits tarafından oluşturulan yazar <xref:microsoft.quantum.diagnostics.dumpmachine>.</span><span class="sxs-lookup"><span data-stu-id="99f7e-201">For the full-state quantum simulator it writes into the file the wave function up to a global phase of the quantum sub-system generated by the provided qubits in the same format as <xref:microsoft.quantum.diagnostics.dumpmachine>.</span></span>  <span data-ttu-id="99f7e-202">Örneğin, sadece iki{1}qubit ayrılmış bir makine almak ve kuantum durumunda $$ \begin{align} \ket{\psi} ={2}\frac{00} {\sqrt } \ket{2} -{10} \frac{(1 + i)} \ket{1}= e^{-i\pi/4 } ( (\frac {\sqrt{2}} \ket{0} - \frac{(1 + i)}{2} \ket{1} ) \otimes \frac{-(1 + i)}{\sqrt{2}} \ket){0} , \end{align} $$ arama <xref:microsoft.quantum.diagnostics.dumpregister> `qubit[0]` bu çıktıyı oluşturur:</span><span class="sxs-lookup"><span data-stu-id="99f7e-202">For example, take again a machine with only two qubits allocated and in the quantum state $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10} = - e^{-i\pi/4} ( (\frac{1}{\sqrt{2}} \ket{0} - \frac{(1 + i)}{2} \ket{1} ) \otimes \frac{-(1 + i)}{\sqrt{2}} \ket{0} ) , \end{align} $$ calling <xref:microsoft.quantum.diagnostics.dumpregister> for `qubit[0]` generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:    -0.707107 + -0.707107 i  ==     ******************** [ 1.000000 ]  /      [ -2.35619 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

<span data-ttu-id="99f7e-203">ve <xref:microsoft.quantum.diagnostics.dumpregister> bu `qubit[1]` çıktıyı oluşturmak için çağrı:</span><span class="sxs-lookup"><span data-stu-id="99f7e-203">and calling <xref:microsoft.quantum.diagnostics.dumpregister> for `qubit[1]` generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 1
∣0❭:     0.707107 +  0.000000 i  ==     ***********          [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:    -0.500000 + -0.500000 i  ==     ***********          [ 0.500000 ]  /      [ -2.35619 rad ]
```

<span data-ttu-id="99f7e-204">Genel olarak, başka bir kayıtla dolaşmış bir kaydın durumu, saf bir durumdan çok karışık bir durumdur.</span><span class="sxs-lookup"><span data-stu-id="99f7e-204">In general, the state of a register that is entangled with another register is a mixed state rather than a pure state.</span></span> <span data-ttu-id="99f7e-205">Bu durumda, <xref:microsoft.quantum.diagnostics.dumpregister> aşağıdaki iletiyi çıktırın:</span><span class="sxs-lookup"><span data-stu-id="99f7e-205">In this case, <xref:microsoft.quantum.diagnostics.dumpregister> outputs the following message:</span></span>

```
Qubits provided (0;) are entangled with some other qubit.
```

<span data-ttu-id="99f7e-206">Aşağıdaki örnek, her ikisini de <xref:microsoft.quantum.diagnostics.dumpregister> <xref:microsoft.quantum.diagnostics.dumpmachine> ve Q# kodunuzda nasıl kullanabileceğinizi gösterir:</span><span class="sxs-lookup"><span data-stu-id="99f7e-206">The following example shows you how you can use both <xref:microsoft.quantum.diagnostics.dumpregister> and <xref:microsoft.quantum.diagnostics.dumpmachine> in your Q# code:</span></span>

```qsharp
namespace app
{
    open Microsoft.Quantum.Intrinsic;
    open Microsoft.Quantum.Diagnostics;

    operation Operation () : Unit {

        using (qubits = Qubit[2]) {
            X(qubits[1]);
            H(qubits[1]);
            R1Frac(1, 2, qubits[1]);
            
            DumpMachine("dump.txt");
            DumpRegister("q0.txt", qubits[0..0]);
            DumpRegister("q1.txt", qubits[1..1]);

            ResetAll(qubits);
        }
    }
}
```

## <a name="debugging"></a><span data-ttu-id="99f7e-207">Hata ayıklama</span><span class="sxs-lookup"><span data-stu-id="99f7e-207">Debugging</span></span>

<span data-ttu-id="99f7e-208">`Assert` Üstüne ve `Dump` işlevleri ve işlemleri, Q # standart Visual Studio hata ayıklama yetenekleri bir alt kümesi destekler: satır kesme noktaları [ayarlama,](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints) [F10 kullanarak kod üzerinden adım](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger) ve klasik [değişkenlerin değerlerini inceleyerek](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) simülatörde kod yürütme sırasında tüm mümkündür.</span><span class="sxs-lookup"><span data-stu-id="99f7e-208">On top of `Assert` and `Dump` functions and operations, Q# supports a subset of standard Visual Studio debugging capabilities: [setting line breakpoints](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints), [stepping through code using F10](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger) and [inspecting values of classic variables](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) are all possible during code execution on the simulator.</span></span>

<span data-ttu-id="99f7e-209">Visual Studio Code hata ayıklama OmniSharp tarafından desteklenen Visual Studio Code uzantısı için C # tarafından sağlanan hata ayıklama yetenekleri yararlanır ve [en son sürümünü](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp)yüklemeyi gerektirir.</span><span class="sxs-lookup"><span data-stu-id="99f7e-209">Debugging in Visual Studio Code leverages the debugging capabilities provided by the C# for Visual Studio Code extension powered by OmniSharp and requires installing the [latest version](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp).</span></span> 
