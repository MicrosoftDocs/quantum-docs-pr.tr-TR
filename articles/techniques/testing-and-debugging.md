---
title: 'Q # programlarını test etme ve hata ayıklama'
description: Birim testlerini, olguları ve onayları ve döküm işlevlerini kullanarak hisse programlarını test etme ve hata ayıklama hakkında bilgi edinin.
author: tcNickolas
ms.author: mamykhai@microsoft.com
uid: microsoft.quantum.techniques.testing-and-debugging
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 8131c2ec9320b5075c37370e12ad39a4df5bd3d5
ms.sourcegitcommit: d61b388651351e5abd4bfe7a672e88b84a6697f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/10/2020
ms.locfileid: "79022854"
---
# <a name="testing-and-debugging"></a><span data-ttu-id="a9019-103">Test ve hata ayıklama</span><span class="sxs-lookup"><span data-stu-id="a9019-103">Testing and Debugging</span></span>

<span data-ttu-id="a9019-104">Klasik programlamada olduğu gibi, hisse anlık programlarının amaçlanan gibi davranmasına ve yanlış bir hisse veya hatalı bir program tanılamasına olanak tanımak önemlidir.</span><span class="sxs-lookup"><span data-stu-id="a9019-104">As with classical programming, it is essential to be able to check that quantum programs act as intended, and to be able to diagnose a quantum program that is incorrect.</span></span>
<span data-ttu-id="a9019-105">Bu bölümde, test ve hata ayıklama için Q # tarafından sunulan araçlar ele alınmaktadır.</span><span class="sxs-lookup"><span data-stu-id="a9019-105">In this section, we cover the tools offered by Q# for testing and debugging quantum programs.</span></span>

## <a name="unit-tests"></a><span data-ttu-id="a9019-106">Birim testleri</span><span class="sxs-lookup"><span data-stu-id="a9019-106">Unit Tests</span></span>

<span data-ttu-id="a9019-107">Klasik programları test etmeye yönelik yaygın bir yaklaşım, bir kitaplıktaki kodu çalıştıran ve çıktısını beklenen bir çıktı ile karşılaştıran *birim testleri* adlı küçük programları yazmaktır.</span><span class="sxs-lookup"><span data-stu-id="a9019-107">One common approach to testing classical programs is to write small programs called *unit tests* which run code in a library and compare its output to some expected output.</span></span>
<span data-ttu-id="a9019-108">Örneğin, $2 ^ 2 = $4 olan *bir priorı* öğrendiğimiz için `Square(2)` `4`döndürdüğünden emin olmak istiyoruz.</span><span class="sxs-lookup"><span data-stu-id="a9019-108">For instance, we may want to ensure that `Square(2)` returns `4`, since we know *a priori* that $2^2 = 4$.</span></span>

<span data-ttu-id="a9019-109">S #, hisse programları için birim testleri oluşturmayı destekler ve bu, [xUnit](https://xunit.github.io/) birim test çerçevesi içinde testler olarak yürütülenebilir.</span><span class="sxs-lookup"><span data-stu-id="a9019-109">Q# supports creating unit tests for quantum programs, and which can be executed as tests within the [xUnit](https://xunit.github.io/) unit testing framework.</span></span>

### <a name="creating-a-test-project"></a><span data-ttu-id="a9019-110">Test projesi oluşturma</span><span class="sxs-lookup"><span data-stu-id="a9019-110">Creating a Test Project</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="a9019-111">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="a9019-111">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="a9019-112">Visual Studio 2019 ' i açın.</span><span class="sxs-lookup"><span data-stu-id="a9019-112">Open Visual Studio 2019.</span></span> <span data-ttu-id="a9019-113">`File` menüsüne gidin ve `New` > `Project...`' yı seçin.</span><span class="sxs-lookup"><span data-stu-id="a9019-113">Go to the `File` menu and select `New` > `Project...`.</span></span>
<span data-ttu-id="a9019-114">Sağ üst köşede `Q#`arayın ve `Q# Test Project` şablonunu seçin.</span><span class="sxs-lookup"><span data-stu-id="a9019-114">In the upper right corner, search for `Q#`, and select the `Q# Test Project` template.</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="a9019-115">Komut Satırı / Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="a9019-115">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="a9019-116">En sevdiğiniz komut satırınızdan aşağıdaki komutu çalıştırın:</span><span class="sxs-lookup"><span data-stu-id="a9019-116">From your favorite command line, run the following command:</span></span>
```bash
$ dotnet new xunit -lang Q# -o Tests
$ cd Tests
$ code . # To open in Visual Studio Code
```

****

<span data-ttu-id="a9019-117">Yeni projenizin yeni Q # birim testlerini tanımlamak için uygun bir yer sağlayan tek bir dosya `Tests.qs`olacaktır.</span><span class="sxs-lookup"><span data-stu-id="a9019-117">Your new project will have a single file `Tests.qs`, which provides a convenient place to define new Q# unit tests.</span></span>
<span data-ttu-id="a9019-118">Başlangıçta bu dosya, yeni ayrılmış bir qubitin $ \ket{0}$ durumunda olduğunu denetleyen ve bir ileti yazdıran bir örnek birim testi `AllocateQubit` içerir:</span><span class="sxs-lookup"><span data-stu-id="a9019-118">Initially this file contains one sample unit test `AllocateQubit` which checks that a newly allocated qubit is in the $\ket{0}$ state and prints a message:</span></span>

```qsharp
    @Test("QuantumSimulator")
    operation AllocateQubit () : Unit {

        using (qubit = Qubit()) {
            Assert([PauliZ], [qubit], Zero, "Newly allocated qubit must be in the |0⟩ state.");
        }
        
        Message("Test passed");
    }
```

<span data-ttu-id="a9019-119">: New: `Unit` türünde bir bağımsız değişken alan ve `Unit` döndüren tüm Q # işlemleri veya işlevi `@Test("...")` özniteliği aracılığıyla birim testi olarak işaretlenebilir.</span><span class="sxs-lookup"><span data-stu-id="a9019-119">:new: Any Q# operation or function that takes an argument of type `Unit` and returns `Unit` can be marked as a unit test via the `@Test("...")` attribute.</span></span> <span data-ttu-id="a9019-120">Bu özniteliğin bağımsız değişkeni, yukarıdaki `"QuantumSimulator"`, testin yürütüldüğü hedefi belirtir.</span><span class="sxs-lookup"><span data-stu-id="a9019-120">The argument to that attribute, `"QuantumSimulator"` above, specifies the target on which the test is executed.</span></span> <span data-ttu-id="a9019-121">Birden çok hedef üzerinde tek bir test yürütülebilir.</span><span class="sxs-lookup"><span data-stu-id="a9019-121">A single test can be executed on multiple targets.</span></span> <span data-ttu-id="a9019-122">Örneğin, `AllocateQubit``@Test("ResourcesEstimator")` bir öznitelik ekleyin.</span><span class="sxs-lookup"><span data-stu-id="a9019-122">For example, add an attribute `@Test("ResourcesEstimator")` above `AllocateQubit`.</span></span> 
```qsharp
    @Test("QuantumSimulator")
    @Test("ResourcesEstimator")
    operation AllocateQubit () : Unit {
        ...
```
<span data-ttu-id="a9019-123">Dosyayı kaydedin ve tüm testleri yürütün.</span><span class="sxs-lookup"><span data-stu-id="a9019-123">Save the file and execute all tests.</span></span> <span data-ttu-id="a9019-124">Şimdi, AllocateQubit 'in miktar simülatör üzerinde yürütüldüğü ve ResourceEstimator 'da yürütüldüğü bir tane olmak üzere iki birim testi olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="a9019-124">There should now be two unit tests, one where AllocateQubit is executed on the QuantumSimulator, and one where it is executed in the ResourceEstimator.</span></span> 

<span data-ttu-id="a9019-125">Q # derleyicisi yerleşik hedefleri "niceleyici simülatörü", "Toffkaysimülatör" ve "ResourcesEstimator" değerini birim testleri için geçerli yürütme hedefleri olarak tanır.</span><span class="sxs-lookup"><span data-stu-id="a9019-125">The Q# compiler recognizes the built-in targets "QuantumSimulator", "ToffoliSimulator", and "ResourcesEstimator" as valid execution targets for unit tests.</span></span> <span data-ttu-id="a9019-126">Özel bir yürütme hedefi tanımlamak için herhangi bir tam adı belirtmek de mümkündür.</span><span class="sxs-lookup"><span data-stu-id="a9019-126">It is also possible to specify any fully qualified name to define a custom execution target.</span></span> 

### <a name="running-q-unit-tests"></a><span data-ttu-id="a9019-127">Q # birim testlerini çalıştırma</span><span class="sxs-lookup"><span data-stu-id="a9019-127">Running Q# Unit Tests</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="a9019-128">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="a9019-128">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="a9019-129">Tek seferlik çözüm başına kurulum olarak `Test` menüsüne gidin ve `Test Settings` > `Default Processor Architecture` > `X64`' nı seçin.</span><span class="sxs-lookup"><span data-stu-id="a9019-129">As a one-time per-solution setup, go to `Test` menu and select `Test Settings` > `Default Processor Architecture` > `X64`.</span></span>

> [!TIP]
> <span data-ttu-id="a9019-130">Visual Studio için varsayılan işlemci mimarisi ayarı, her çözüm için çözüm seçenekleri (`.suo`) dosyasında depolanır.</span><span class="sxs-lookup"><span data-stu-id="a9019-130">The default processor architecture setting for Visual Studio is stored in the solution options (`.suo`) file for each solution.</span></span>
> <span data-ttu-id="a9019-131">Bu dosyayı silerseniz, İşlemci mimariniz olarak `X64` yeniden seçmeniz gerekecektir.</span><span class="sxs-lookup"><span data-stu-id="a9019-131">If you delete this file, then you will need to select `X64` as your processor architecture again.</span></span>

<span data-ttu-id="a9019-132">Projeyi derleyin, `Test` menüsüne gidin ve `Windows` > `Test Explorer`' yı seçin.</span><span class="sxs-lookup"><span data-stu-id="a9019-132">Build the project, go to the `Test` menu and select `Windows` > `Test Explorer`.</span></span> <span data-ttu-id="a9019-133">`AllocateQubit`, `Not Run Tests` grubundaki testlerin listesinde görünür.</span><span class="sxs-lookup"><span data-stu-id="a9019-133">`AllocateQubit` will show up in the list of tests in the `Not Run Tests` group.</span></span> <span data-ttu-id="a9019-134">`Run All` seçin veya bu testi çalıştırın ve başarılı olur!</span><span class="sxs-lookup"><span data-stu-id="a9019-134">Select `Run All` or run this individual test, and it should pass!</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="a9019-135">Komut Satırı / Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="a9019-135">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="a9019-136">Testleri çalıştırmak için proje klasörüne (`Tests.csproj`içeren klasör) gidin ve komutu yürütün:</span><span class="sxs-lookup"><span data-stu-id="a9019-136">To run tests, navigate to the project folder (the folder which contains `Tests.csproj`), and execute the command:</span></span>

```bash
$ dotnet restore
$ dotnet test
```

<span data-ttu-id="a9019-137">Aşağıdakine benzer bir çıktı almalısınız:</span><span class="sxs-lookup"><span data-stu-id="a9019-137">You should get output similar to the following:</span></span>

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

<span data-ttu-id="a9019-138">Birim testleri adına ve/veya yürütme hedefine göre filtrelenebilir:</span><span class="sxs-lookup"><span data-stu-id="a9019-138">Unit tests can be filtered according to their name and/or the execution target:</span></span>

```bash 
$ dotnet test --filter "Target=QuantumSimulator"
$ dotnet test --filter "Name=AllocateQubit"
```


***

<span data-ttu-id="a9019-139"><xref:microsoft.quantum.intrinsic.message> iç işlev `(String -> Unit)` türüne sahiptir ve tanılama iletilerinin oluşturulmasına izin vermez.</span><span class="sxs-lookup"><span data-stu-id="a9019-139">The intrinsic function <xref:microsoft.quantum.intrinsic.message> has type `(String -> Unit)` and enables the creation of diagnostic messages.</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="a9019-140">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="a9019-140">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="a9019-141">Test Gezgini 'nde bir testi yürütmeden ve teste tıkladığınızda, test yürütmesi hakkında bilgi içeren bir panel görüntülenir: başarılı/başarısız durum, geçen süre ve "çıktı" bağlantısı.</span><span class="sxs-lookup"><span data-stu-id="a9019-141">After you execute a test in Test Explorer and click on the test, a panel will appear with information about test execution: Passed/Failed status, elapsed time and an "Output" link.</span></span> <span data-ttu-id="a9019-142">"Çıkış" bağlantısına tıklarsanız, test çıktısı yeni bir pencerede açılır.</span><span class="sxs-lookup"><span data-stu-id="a9019-142">If you click the "Output" link, test output will open in a new window.</span></span>

![test çıktısı](~/media/unit-test-output.png)

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="a9019-144">Komut Satırı / Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="a9019-144">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="a9019-145">Her bir testin geçiş/başarısızlık durumu konsola `dotnet test`göre yazdırılır.</span><span class="sxs-lookup"><span data-stu-id="a9019-145">The pass/fail status for each test is printed to the console by `dotnet test`.</span></span>
<span data-ttu-id="a9019-146">Başarısız testler için çıktılar, hatanın tanılanmasına yardımcı olmak üzere konsola da yazdırılır.</span><span class="sxs-lookup"><span data-stu-id="a9019-146">For failing tests, the outputs are also printed to the console to help diagnose the failure.</span></span>

***

## <a name="facts-and-assertions"></a><span data-ttu-id="a9019-147">Olgular ve Onaylamalar</span><span class="sxs-lookup"><span data-stu-id="a9019-147">Facts and Assertions</span></span>

<span data-ttu-id="a9019-148">Q # içindeki işlevlerin _mantıksal_ yan etkileri olmadığından, çıkış türü boş olan bir işlevi yürütmenin _diğer_ etkileri, `()` hiçbir zaman bir Q # programı içinden gözlemlenemez.</span><span class="sxs-lookup"><span data-stu-id="a9019-148">Because functions in Q# have no _logical_ side effects, any _other kinds_ of effects of executing a function whose output type is the empty tuple `()` can never be observed from within a Q# program.</span></span>
<span data-ttu-id="a9019-149">Diğer bir deyişle, bir hedef makine, bu atlama 'nin aşağıdaki Q # kodunun davranışını değiştirmeyeceği garantisi ile `()` döndüren herhangi bir işlevi yürütmemelidir.</span><span class="sxs-lookup"><span data-stu-id="a9019-149">That is, a target machine can choose not to execute any function which returns `()` with the guarantee that this omission will not modify the behavior of any following Q# code.</span></span>
<span data-ttu-id="a9019-150">Bu işlem, soru-cevap ve hata ayıklama mantığını Q # programlarına eklemek için `()` (yani `Unit`) işlevlerini döndüren işlevlerin yararlı bir araç olmasını sağlar.</span><span class="sxs-lookup"><span data-stu-id="a9019-150">This makes functions returning `()` (i.e. `Unit`) a useful tool for embedding assertions and debugging logic into Q# programs.</span></span> 

<span data-ttu-id="a9019-151">Basit bir örnek ele alalım:</span><span class="sxs-lookup"><span data-stu-id="a9019-151">Let's consider a simple example:</span></span>

```qsharp
function PositivityFact(value : Double) : Unit 
{
    if (value <= 0) 
    {
        fail "Expected a positive number.";
    }
}
```

<span data-ttu-id="a9019-152">Burada, anahtar sözcüğü `fail` hesaplamanın devam etmesi gerektiğini belirtir ve Q # programını çalıştıran hedef makinede bir özel durum ortaya koyar.</span><span class="sxs-lookup"><span data-stu-id="a9019-152">Here, the keyword `fail` indicates that the computation should not proceed, raising an exception in the target machine running the Q# program.</span></span>
<span data-ttu-id="a9019-153">Tanım olarak, bu tür bir hata, `fail` deyiminden sonra başka bir Q # kodu çalıştırılıncaya kadar, Q # içinden gözlemlenemez.</span><span class="sxs-lookup"><span data-stu-id="a9019-153">By definition, a failure of this kind cannot be observed from within Q#, as no further Q# code is run after a `fail` statement is reached.</span></span>
<span data-ttu-id="a9019-154">Bu nedenle, `PositivityFact`bir çağrıyı aşdığımızda, girişi pozitif olduğundan emin olabilir.</span><span class="sxs-lookup"><span data-stu-id="a9019-154">Thus, if we proceed past a call to `PositivityFact`, we can be assured by that its input was positive.</span></span>

<span data-ttu-id="a9019-155"><xref:microsoft.quantum.diagnostics> ad alanından [`Fact`](xref:microsoft.quantum.diagnostics.fact) işlevini kullanarak `PositivityFact` aynı davranışı uygulayabileceğinizi unutmayın:</span><span class="sxs-lookup"><span data-stu-id="a9019-155">Note that we can implement the same behavior as `PositivityFact` using the [`Fact`](xref:microsoft.quantum.diagnostics.fact) function from the <xref:microsoft.quantum.diagnostics> namespace:</span></span>

```qsharp
    Fact(value <= 0, "Expected a positive number.");
```

<span data-ttu-id="a9019-156">Diğer yandan *onaylar,* olgulara benzer şekilde kullanılır, ancak hedef makinenin durumuna bağlı olabilir.</span><span class="sxs-lookup"><span data-stu-id="a9019-156">*Assertions*, on the other hand, are used similarly to facts, but may be dependent on the state of the target machine.</span></span> <span data-ttu-id="a9019-157">Bunlar işlem olarak tanımlandıklarında, olgular işlev olarak tanımlanır (yukarıdaki gibi).</span><span class="sxs-lookup"><span data-stu-id="a9019-157">Correspondingly, they are defined as operations, whereas facts are defined as functions (as above).</span></span>
<span data-ttu-id="a9019-158">Ayrımı anlamak için, bir onaylama içinde aşağıdaki olgunun kullanımını göz önünde bulundurun:</span><span class="sxs-lookup"><span data-stu-id="a9019-158">To understand the distinction, consider the following use of a fact within an assertion:</span></span>

```qsharp
operation AssertQubitsAreAvailable() : Unit
{
     Fact(GetQubitsAvailableToUse() > 0, "No qubits were actually available");
}
```

<span data-ttu-id="a9019-159">Burada, kullanılabilecek qubits sayısını döndürmek için <xref:microsoft.quantum.environment.getqubitsavailabletouse> işlemini kullanıyoruz.</span><span class="sxs-lookup"><span data-stu-id="a9019-159">Here, we are using the operation <xref:microsoft.quantum.environment.getqubitsavailabletouse> to return the number of qubits available to use.</span></span>
<span data-ttu-id="a9019-160">Bu açıkça programın ve yürütme ortamının genel durumuna bağlı olduğundan `AssertQubitsAreAvailable` tanımımız da bir işlem olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="a9019-160">As this clearly depends on the global state of the program and its execution environment, our definition of  `AssertQubitsAreAvailable` must be an operation as well.</span></span>
<span data-ttu-id="a9019-161">Ancak, bu genel durumu, `Fact` işlevine giriş olarak basit bir `Bool` değeri sunacak şekilde kullanabiliriz.</span><span class="sxs-lookup"><span data-stu-id="a9019-161">However, we can use that global state to yield a simple `Bool` value as input to the `Fact` function.</span></span>

<span data-ttu-id="a9019-162">Bu fikirlere yönelik olarak, [Prelude](xref:microsoft.quantum.libraries.standard.prelude) , <xref:microsoft.quantum.intrinsic.assert> ve <xref:microsoft.quantum.intrinsic.assertprob> her ikisi de `()`üzerinde işlem olarak modellenen iki daha kullanışlı onaylama sağlar.</span><span class="sxs-lookup"><span data-stu-id="a9019-162">Building on these ideas, [the prelude](xref:microsoft.quantum.libraries.standard.prelude) offers two especially useful assertions, <xref:microsoft.quantum.intrinsic.assert> and <xref:microsoft.quantum.intrinsic.assertprob> both modeled as operations onto `()`.</span></span> <span data-ttu-id="a9019-163">Bu onayların her biri, belirli bir ölçümü, ölçümün gerçekleştirileceği bir hisse izini ve kuramsal bir sonucu açıklayan bir Pauli işleci alır.</span><span class="sxs-lookup"><span data-stu-id="a9019-163">These assertions each take a Pauli operator describing a particular measurement of interest, a quantum register on which a measurement is to be performed, and a hypothetical outcome.</span></span>
<span data-ttu-id="a9019-164">Simülasyonu tarafından çalışan hedef makinelerde, [hiçbir kopyalama işlemi yapılmaz](https://en.wikipedia.org/wiki/No-cloning_theorem)ve bu tür ölçümlere, bu tür onayları geçen kaydı etkilemeden bu ölçümleri gerçekleştirebilir.</span><span class="sxs-lookup"><span data-stu-id="a9019-164">On target machines which work by simulation, we are not bound by [the no-cloning theorem](https://en.wikipedia.org/wiki/No-cloning_theorem), and can perform such measurements without disturbing the register passed to such assertions.</span></span>
<span data-ttu-id="a9019-165">Daha sonra bir simülatör, yukarıdaki `PositivityFact` işleve benzer şekilde, kuramsal sonuç uygulamada gözlemlenmese hesaplamayı iptal edebilir:</span><span class="sxs-lookup"><span data-stu-id="a9019-165">A simulator can then, similar to the `PositivityFact` function above, abort computation if the hypothetical outcome would not be observed in practice:</span></span>

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

<span data-ttu-id="a9019-166">Kopya olmaması gereken fiziksel hisse donanımı, `Assert` ve `AssertProb` işlemleri yalnızca başka bir efekt olmadan `()` geri dönmeyecektir.</span><span class="sxs-lookup"><span data-stu-id="a9019-166">On physical quantum hardware, where the no-cloning theorem prevents examination of quantum state, the `Assert` and `AssertProb` operations simply return `()` with no other effect.</span></span>

<span data-ttu-id="a9019-167"><xref:microsoft.quantum.diagnostics> ad alanı, daha gelişmiş koşulları denetmamıza izin veren `Assert` aile işlevlerinin daha birçok işlevini sağlar.</span><span class="sxs-lookup"><span data-stu-id="a9019-167">The <xref:microsoft.quantum.diagnostics> namespace provides several more functions of the `Assert` family which allow us to check more advanced conditions.</span></span> 

## <a name="dump-functions"></a><span data-ttu-id="a9019-168">Döküm Işlevleri</span><span class="sxs-lookup"><span data-stu-id="a9019-168">Dump Functions</span></span>

<span data-ttu-id="a9019-169"><xref:microsoft.quantum.diagnostics> ad alanı, hisse programları sorunlarını gidermeye yardımcı olmak için, hedef makinenin geçerli durumu bir dosyaya döküm veren iki işlev sunar: <xref:microsoft.quantum.diagnostics.dumpmachine> ve <xref:microsoft.quantum.diagnostics.dumpregister>.</span><span class="sxs-lookup"><span data-stu-id="a9019-169">To help troubleshooting quantum programs, the <xref:microsoft.quantum.diagnostics> namespace offers two functions that can dump into a file the current status of the target machine: <xref:microsoft.quantum.diagnostics.dumpmachine> and <xref:microsoft.quantum.diagnostics.dumpregister>.</span></span> <span data-ttu-id="a9019-170">Her birinin üretilen çıktısı, hedef makineye bağlıdır.</span><span class="sxs-lookup"><span data-stu-id="a9019-170">The generated output of each depends on the target machine.</span></span>

### <a name="dumpmachine"></a><span data-ttu-id="a9019-171">DumpMachine</span><span class="sxs-lookup"><span data-stu-id="a9019-171">DumpMachine</span></span>

<span data-ttu-id="a9019-172">Hisse geliştirme seti 'nin bir parçası olarak dağıtılan tam eyalet hisse simülatörü, tüm hisse sisteminin [Wave işlevini](https://en.wikipedia.org/wiki/Wave_function) dosyaya yazar. tek boyutlu karmaşık sayıların dizisi olarak her bir öğenin hesaplama tabanlı durumu $ \ket{n} $ ölçü olasılığını temsil eden, $ \ket{n} = \ket{B_ {n-1}... BITS $\{b_i\}$ için b_1b_0} $.</span><span class="sxs-lookup"><span data-stu-id="a9019-172">The full-state quantum simulator distributed as part of the Quantum Development Kit writes into the file the [wave function](https://en.wikipedia.org/wiki/Wave_function) of the entire quantum system, as a one-dimensional array of complex numbers, in which each element represents the amplitude of the probability of measuring the computational basis state $\ket{n}$, where $\ket{n} = \ket{b_{n-1}...b_1b_0}$ for bits $\{b_i\}$.</span></span> <span data-ttu-id="a9019-173">Örneğin, yalnızca iki qubit ayrılmış bir makinede ve hisse durumu $ $ \begin{hizalaması} \ket{\psı} = \frac{1}{\sqrt{2}} \ment{00}-\frac{(1 + ı)}{2} \tus{10}, \end{hizalaması} $ $ çağıran <xref:microsoft.quantum.diagnostics.dumpmachine> bu çıktıyı oluşturur:</span><span class="sxs-lookup"><span data-stu-id="a9019-173">For example, on a machine with only two qubits allocated and in the quantum state $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10}, \end{align} $$ calling <xref:microsoft.quantum.diagnostics.dumpmachine> generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 0;1
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣2❭:    -0.500000 + -0.500000 i  ==     **********           [ 0.500000 ]   /     [ -2.35619 rad ]
∣3❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

<span data-ttu-id="a9019-174">İlk satır, karşılık gelen qubits kimlikleri için önemli sırayla bir açıklama sağlar.</span><span class="sxs-lookup"><span data-stu-id="a9019-174">The first row provides a comment with the IDs of the corresponding qubits in their significant order.</span></span>
<span data-ttu-id="a9019-175">Satırların geri kalanı, hem Kartezyen hem de kutupsal biçimlerdeki temel eyalet vektörü $ \ket{n} $ ölçgenin olasılığını anlatmaktadır.</span><span class="sxs-lookup"><span data-stu-id="a9019-175">The rest of the rows describe the probability amplitude of measuring the basis state vector $\ket{n}$ in both Cartesian and polar formats.</span></span> <span data-ttu-id="a9019-176">İlk satır için ayrıntılı:</span><span class="sxs-lookup"><span data-stu-id="a9019-176">In detail for the first row:</span></span>

* <span data-ttu-id="a9019-177">Bu satır **`∣0❭:`** `0` hesaplama esası durumuna karşılık gelir</span><span class="sxs-lookup"><span data-stu-id="a9019-177">**`∣0❭:`** this row corresponds to the `0` computational basis state</span></span>
* <span data-ttu-id="a9019-178">**`0.707107 +  0.000000 i`** : Kartezyen biçimdeki olasılık genliği.</span><span class="sxs-lookup"><span data-stu-id="a9019-178">**`0.707107 +  0.000000 i`**: the probability amplitude in Cartesian format.</span></span>
* <span data-ttu-id="a9019-179">**` == `** : `equal` işareti her iki denk gösterimi ayırır.</span><span class="sxs-lookup"><span data-stu-id="a9019-179">**` == `**: the `equal` sign seperates both equivalent representations.</span></span>
* <span data-ttu-id="a9019-180">**`**********  `** : büyüklük grafik gösterimi, `*` sayısı bu durum vektörünü ölçme olasılığının müşterinizin istekleriyle orantılı.</span><span class="sxs-lookup"><span data-stu-id="a9019-180">**`**********  `**: A graphical representation of the magnitude, the number of `*` is proportionate to the probability of measuring this state vector.</span></span>
* <span data-ttu-id="a9019-181">**`[ 0.500000 ]`** : büyüklük sayısal değeri</span><span class="sxs-lookup"><span data-stu-id="a9019-181">**`[ 0.500000 ]`**: the numeric value of the magnitude</span></span>
* <span data-ttu-id="a9019-182">**`    ---`** : genin aşamasının grafik gösterimi (aşağıya bakın).</span><span class="sxs-lookup"><span data-stu-id="a9019-182">**`    ---`**: A graphical representation of the amplitude's phase (see below).</span></span>
* <span data-ttu-id="a9019-183">**`[ 0.0000 rad ]`** : aşamanın sayısal değeri (radyan cinsinden).</span><span class="sxs-lookup"><span data-stu-id="a9019-183">**`[ 0.0000 rad ]`**: the numeric value of the phase (in radians).</span></span>

<span data-ttu-id="a9019-184">Büyüklük ve aşama bir grafik gösterimiyle birlikte görüntülenir.</span><span class="sxs-lookup"><span data-stu-id="a9019-184">Both the magnitude and the phase are displayed with a graphical representation.</span></span> <span data-ttu-id="a9019-185">Büyüklük temsili düz bir işlemdir: `*`bir çubuk gösterir, çubuğun ne kadar büyük olduğu büyük olasılıkla daha büyük olur.</span><span class="sxs-lookup"><span data-stu-id="a9019-185">The magnitude representation is straight-forward: it shows a bar of `*`, the bigger the probability the bigger the bar will be.</span></span> <span data-ttu-id="a9019-186">Aşama için, aralıklara göre açıyı temsil etmek üzere aşağıdaki sembolleri göstereceğiz:</span><span class="sxs-lookup"><span data-stu-id="a9019-186">For the phase, we show the following symbols to represent the angle based on ranges:</span></span>

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

<span data-ttu-id="a9019-187">Aşağıdaki örneklerde bazı yaygın durumlar için `DumpMachine` gösterilmektedir:</span><span class="sxs-lookup"><span data-stu-id="a9019-187">The following examples show `DumpMachine` for some common states:</span></span>

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
  > <span data-ttu-id="a9019-188">Bir qubit kimliği çalışma zamanında atanır ve qubitin ayrıldığı sıra veya bir qubit yazmaç içindeki konumu ile hizalı değildir.</span><span class="sxs-lookup"><span data-stu-id="a9019-188">The id of a qubit is assigned at runtime and it's not necessarily aligned with the order in which the qubit was allocated or its position within a qubit register.</span></span>


#### <a name="visual-studio-2019"></a>[<span data-ttu-id="a9019-189">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="a9019-189">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

  > [!TIP]
  > <span data-ttu-id="a9019-190">Kodunuzda bir kesme noktası yerleştirerek ve bir qubit değişkeninin değerini inceleyerek, Visual Studio 'da bir qubit kimliği belirleyebilirsiniz, örneğin:</span><span class="sxs-lookup"><span data-stu-id="a9019-190">You can figure out a qubit id in Visual Studio by putting a breakpoint in your code and inspecting the value of a qubit variable, for example:</span></span>
  > 
  > ![Visual Studio 'da qubit kimliği göster](~/media/qubit_id.png)
  >
  > <span data-ttu-id="a9019-192">`register2` üzerindeki Dizin `0` olan qubit, ID =`3`, Index `1` ile qubit, ID =`2`içerir.</span><span class="sxs-lookup"><span data-stu-id="a9019-192">the qubit with index `0` on `register2` has id=`3`, the qubit with index `1` has id=`2`.</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="a9019-193">Komut Satırı / Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="a9019-193">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

  > [!TIP]
  > <span data-ttu-id="a9019-194"><xref:microsoft.quantum.intrinsic.message> işlevini kullanarak bir qubit Kimliği belirleyebilir ve qubit değişkenini iletiye geçirerek, örneğin:</span><span class="sxs-lookup"><span data-stu-id="a9019-194">You can figure out a qubit id by using the <xref:microsoft.quantum.intrinsic.message> function and passing the qubit variable in the message, for example:</span></span>
  >
  > ```qsharp
  > Message($"0={register2[0]}; 1={register2[1]}");
  > ```
  > 
  > <span data-ttu-id="a9019-195">Bu çıktıyı üreten:</span><span class="sxs-lookup"><span data-stu-id="a9019-195">which could generate this output:</span></span>
  >```
  > 0=q:3; 1=q:2
  >```
  > <span data-ttu-id="a9019-196">Yani, Dizin `0` `register2` üzerindeki qubit 'in ID =`3`olduğu, Index `1` ile qubit 'in ID =`2`olduğu anlamına gelir.</span><span class="sxs-lookup"><span data-stu-id="a9019-196">which means that the qubit with index `0` on `register2` has id=`3`, the qubit with index `1` has id=`2`.</span></span>


***

<span data-ttu-id="a9019-197"><xref:microsoft.quantum.diagnostics.dumpmachine>, <xref:microsoft.quantum.diagnostics> ad alanının bir parçası olduğundan, bunu kullanabilmeniz için bir `open` ifadesini eklemeniz gerekir:</span><span class="sxs-lookup"><span data-stu-id="a9019-197"><xref:microsoft.quantum.diagnostics.dumpmachine> is part of the  <xref:microsoft.quantum.diagnostics> namespace, so in order to use it you must add an `open` statement:</span></span>

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


### <a name="dumpregister"></a><span data-ttu-id="a9019-198">DumpRegister</span><span class="sxs-lookup"><span data-stu-id="a9019-198">DumpRegister</span></span>

<span data-ttu-id="a9019-199"><xref:microsoft.quantum.diagnostics.dumpregister>, <xref:microsoft.quantum.diagnostics.dumpmachine>gibi çalışarak, yalnızca ilgili qubits ile ilgili bilgi miktarını sınırlamak için de bir qubit dizisi alır.</span><span class="sxs-lookup"><span data-stu-id="a9019-199"><xref:microsoft.quantum.diagnostics.dumpregister> works like <xref:microsoft.quantum.diagnostics.dumpmachine>, except it also takes an array of qubits to limit the amount of information to only that relevant to the corresponding qubits.</span></span>

<span data-ttu-id="a9019-200"><xref:microsoft.quantum.diagnostics.dumpmachine>olduğu gibi, <xref:microsoft.quantum.diagnostics.dumpregister> tarafından oluşturulan bilgiler hedef makineye göre değişir.</span><span class="sxs-lookup"><span data-stu-id="a9019-200">As with <xref:microsoft.quantum.diagnostics.dumpmachine>, the information generated by <xref:microsoft.quantum.diagnostics.dumpregister> depends on the target machine.</span></span> <span data-ttu-id="a9019-201">Tam eyalet hisse simülatörü için, Wave işlevi, <xref:microsoft.quantum.diagnostics.dumpmachine>ile aynı biçimde oluşturulan qubits tarafından oluşturulan küresel bir aşamaya kadar dosya içine yazar.</span><span class="sxs-lookup"><span data-stu-id="a9019-201">For the full-state quantum simulator it writes into the file the wave function up to a global phase of the quantum sub-system generated by the provided qubits in the same format as <xref:microsoft.quantum.diagnostics.dumpmachine>.</span></span>  <span data-ttu-id="a9019-202">Örneğin, yalnızca iki qubit ile ayrılmış bir makine alın ve hisse durumu $ $ \begin{hizalaması} \ket{\psı} = \frac{1}{\sqrt{2}} \ment{00}-\frac{(1 + ı)}{2} \tus{10} =-e ^ {-i \ Pi/4} ((\frac{1}{\sqrt{2}} \ayraç{0}-\frac{(1 + ı)}{2} \ayraç{1}) \otimes \frac{-(1 + ı)} {\sqrt{2}} \tus{0}), \end{hizalaması} $ $ `qubit[0]` için <xref:microsoft.quantum.diagnostics.dumpregister> çağrısı bu çıktıyı oluşturuyor :</span><span class="sxs-lookup"><span data-stu-id="a9019-202">For example, take again a machine with only two qubits allocated and in the quantum state $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10} = - e^{-i\pi/4} ( (\frac{1}{\sqrt{2}} \ket{0} - \frac{(1 + i)}{2} \ket{1} ) \otimes \frac{-(1 + i)}{\sqrt{2}} \ket{0} ) , \end{align} $$ calling <xref:microsoft.quantum.diagnostics.dumpregister> for `qubit[0]` generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:    -0.707107 + -0.707107 i  ==     ******************** [ 1.000000 ]  /      [ -2.35619 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

<span data-ttu-id="a9019-203">ve `qubit[1]` için <xref:microsoft.quantum.diagnostics.dumpregister> çağrısı bu çıktıyı oluşturur:</span><span class="sxs-lookup"><span data-stu-id="a9019-203">and calling <xref:microsoft.quantum.diagnostics.dumpregister> for `qubit[1]` generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 1
∣0❭:     0.707107 +  0.000000 i  ==     ***********          [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:    -0.500000 + -0.500000 i  ==     ***********          [ 0.500000 ]  /      [ -2.35619 rad ]
```

<span data-ttu-id="a9019-204">Genel olarak, başka bir yazmaç ile ayrılmış bir kaydın durumu saf bir durum değil, karışık bir durumdur.</span><span class="sxs-lookup"><span data-stu-id="a9019-204">In general, the state of a register that is entangled with another register is a mixed state rather than a pure state.</span></span> <span data-ttu-id="a9019-205">Bu durumda <xref:microsoft.quantum.diagnostics.dumpregister> aşağıdaki iletiyi verir:</span><span class="sxs-lookup"><span data-stu-id="a9019-205">In this case, <xref:microsoft.quantum.diagnostics.dumpregister> outputs the following message:</span></span>

```
Qubits provided (0;) are entangled with some other qubit.
```

<span data-ttu-id="a9019-206">Aşağıdaki örnek, Q # kodunuzda hem <xref:microsoft.quantum.diagnostics.dumpregister> hem de <xref:microsoft.quantum.diagnostics.dumpmachine> nasıl kullanabileceğinizi gösterir:</span><span class="sxs-lookup"><span data-stu-id="a9019-206">The following example shows you how you can use both <xref:microsoft.quantum.diagnostics.dumpregister> and <xref:microsoft.quantum.diagnostics.dumpmachine> in your Q# code:</span></span>

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

## <a name="debugging"></a><span data-ttu-id="a9019-207">Hata ayıklama</span><span class="sxs-lookup"><span data-stu-id="a9019-207">Debugging</span></span>

<span data-ttu-id="a9019-208">`Assert` ve `Dump` işlevlerinin ve işlemlerinin üstünde, Q #, standart Visual Studio hata ayıklama özellikleri alt kümesini destekler: [satır kesme noktaları ayarlama](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints), [F10 kullanarak kod üzerinden atlama](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger) ve [Klasik değişkenlerin değerlerini inceleme](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) işlemi, simülatör üzerinde kod yürütme sırasında mümkün değildir.</span><span class="sxs-lookup"><span data-stu-id="a9019-208">On top of `Assert` and `Dump` functions and operations, Q# supports a subset of standard Visual Studio debugging capabilities: [setting line breakpoints](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints), [stepping through code using F10](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger) and [inspecting values of classic variables](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) are all possible during code execution on the simulator.</span></span>

<span data-ttu-id="a9019-209">Visual Studio Code hata ayıklaması, C# OmniSharp tarafından desteklenen Visual Studio Code uzantısı için sağlanan hata ayıklama yeteneklerini kullanır ve [en son sürümü](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp)yüklemeyi gerektirir.</span><span class="sxs-lookup"><span data-stu-id="a9019-209">Debugging in Visual Studio Code leverages the debugging capabilities provided by the C# for Visual Studio Code extension powered by OmniSharp and requires installing the [latest version](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp).</span></span> 
