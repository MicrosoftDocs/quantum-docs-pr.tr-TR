---
title: Test etme ve hata ayıklama
description: Birim testlerini, olguları ve onayları ve döküm işlevlerini kullanarak hisse programlarını test etme ve hata ayıklama hakkında bilgi edinin.
author: tcNickolas
ms.author: mamykhai
ms.date: 06/01/2020
ms.topic: article
uid: microsoft.quantum.guide.testingdebugging
no-loc:
- Q#
- $$v
ms.openlocfilehash: 2f2181d388a59c1c6c5a0f13c9aa49d5fa1e51ae
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/21/2020
ms.locfileid: "90833169"
---
# <a name="testing-and-debugging"></a><span data-ttu-id="9657f-103">Test etme ve hata ayıklama</span><span class="sxs-lookup"><span data-stu-id="9657f-103">Testing and debugging</span></span>

<span data-ttu-id="9657f-104">Klasik programlamada olduğu gibi, hisse ve yanlış davranışı tanılamanıza olanak tanımak için, bu program tarafından tasarlanan bir işlem olup olmadığını denetlemek önemlidir.</span><span class="sxs-lookup"><span data-stu-id="9657f-104">As with classical programming, it is essential to be able to check that quantum programs act as intended, and to be able to diagnose incorrect behavior.</span></span>
<span data-ttu-id="9657f-105">Bu bölümde, Q# test ve hata ayıklama için tarafından sunulan araçları ele aldık.</span><span class="sxs-lookup"><span data-stu-id="9657f-105">In this section, we cover the tools offered by Q# for testing and debugging quantum programs.</span></span>

## <a name="unit-tests"></a><span data-ttu-id="9657f-106">Birim testleri</span><span class="sxs-lookup"><span data-stu-id="9657f-106">Unit Tests</span></span>

<span data-ttu-id="9657f-107">Klasik programları test etmeye yönelik yaygın bir yaklaşım, bir kitaplıktaki kodu çalıştıran ve çıktısını beklenen bir çıktı ile karşılaştıran *birim testleri*adlı küçük programları yazmaktır.</span><span class="sxs-lookup"><span data-stu-id="9657f-107">One common approach to testing classical programs is to write small programs called *unit tests*, which run code in a library and compare its output to some expected output.</span></span>
<span data-ttu-id="9657f-108">Örneğin, `Square(2)` `4` $2 ^ 2 = $4 olan *bir priorı* öğrendiğinizden emin olabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="9657f-108">For example, you can ensure that `Square(2)` returns `4` since you know *a priori* that $2^2 = 4$.</span></span>

<span data-ttu-id="9657f-109">Q# hisse programları için birim testleri oluşturmayı destekler ve bu, [xUnit](https://xunit.github.io/) birim test çerçevesi içinde testler olarak çalıştırılabilir.</span><span class="sxs-lookup"><span data-stu-id="9657f-109">Q# supports creating unit tests for quantum programs, and which can run as tests within the [xUnit](https://xunit.github.io/) unit testing framework.</span></span>

### <a name="creating-a-test-project"></a><span data-ttu-id="9657f-110">Test projesi oluşturma</span><span class="sxs-lookup"><span data-stu-id="9657f-110">Creating a Test Project</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="9657f-111">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="9657f-111">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="9657f-112">Visual Studio 2019 ' i açın.</span><span class="sxs-lookup"><span data-stu-id="9657f-112">Open Visual Studio 2019.</span></span> <span data-ttu-id="9657f-113">**Dosya** menüsüne gidin ve **Yeni > proje...** öğesini seçin. Sağ üst köşede, `Q#` öğesini arayın ve \*\* Q# test projesi\*\* şablonunu seçin.</span><span class="sxs-lookup"><span data-stu-id="9657f-113">Go to the **File** menu and select **New > Project...**. In the upper right corner, search for `Q#`, and select the **Q# Test Project** template.</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="9657f-114">Komut Satırı / Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="9657f-114">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="9657f-115">En sevdiğiniz komut satırınızdan aşağıdaki komutu çalıştırın:</span><span class="sxs-lookup"><span data-stu-id="9657f-115">From your favorite command line, run the following command:</span></span>
```dotnetcli
$ dotnet new xunit -lang Q# -o Tests
$ cd Tests
$ code . # To open in Visual Studio Code
```

****

<span data-ttu-id="9657f-116">Yeni projenizin `Tests.qs` Yeni birim testlerini tanımlamak için uygun bir yer sağlayan tek bir dosyası vardır Q# .</span><span class="sxs-lookup"><span data-stu-id="9657f-116">Your new project has a single file `Tests.qs`, which provides a convenient place to define new Q# unit tests.</span></span>
<span data-ttu-id="9657f-117">Başlangıçta bu dosya, `AllocateQubit` yeni ayrılmış bir qubitin $ \ket {0} $ durumunda olduğunu denetleyen ve bir ileti yazdıran bir örnek birim testi içerir:</span><span class="sxs-lookup"><span data-stu-id="9657f-117">Initially, this file contains one sample unit test `AllocateQubit` which checks that a newly allocated qubit is in the $\ket{0}$ state and prints a message:</span></span>

```qsharp
    @Test("QuantumSimulator")
    operation AllocateQubit () : Unit {

        using (qubit = Qubit()) {
            AssertMeasurement([PauliZ], [qubit], Zero, "Newly allocated qubit must be in the |0⟩ state.");
        }
        
        Message("Test passed");
    }
```

<span data-ttu-id="9657f-118">Q#Ve döndürmelerinin bağımsız değişkenini alan herhangi bir işlem veya işlev `Unit` `Unit` , özniteliği aracılığıyla birim testi olarak işaretlenebilir `@Test("...")` .</span><span class="sxs-lookup"><span data-stu-id="9657f-118">Any Q# operation or function that takes an argument of type `Unit` and returns `Unit` can be marked as a unit test via the `@Test("...")` attribute.</span></span> <span data-ttu-id="9657f-119">Önceki örnekte, bu özniteliğin bağımsız değişkeni, `"QuantumSimulator"` testin çalıştırıldığı hedefi belirtir.</span><span class="sxs-lookup"><span data-stu-id="9657f-119">In the previous example, the argument to that attribute, `"QuantumSimulator"`, specifies the target on which the test runs.</span></span> <span data-ttu-id="9657f-120">Tek bir test birden çok hedef üzerinde çalıştırılabilir.</span><span class="sxs-lookup"><span data-stu-id="9657f-120">A single test can run on multiple targets.</span></span> <span data-ttu-id="9657f-121">Örneğin, öğesinden önce bir öznitelik `@Test("ResourcesEstimator")` ekleyin `AllocateQubit` .</span><span class="sxs-lookup"><span data-stu-id="9657f-121">For example, add an attribute `@Test("ResourcesEstimator")` before `AllocateQubit`.</span></span> 
```qsharp
    @Test("QuantumSimulator")
    @Test("ResourcesEstimator")
    operation AllocateQubit () : Unit {
        ...
```
<span data-ttu-id="9657f-122">Dosyayı kaydedin ve tüm testleri çalıştırın.</span><span class="sxs-lookup"><span data-stu-id="9657f-122">Save the file and run all tests.</span></span> <span data-ttu-id="9657f-123">Artık iki birim testi olmalıdır, biri `AllocateQubit` üzerinde çalışır `QuantumSimulator` ve biri içinde çalıştığı yerdir `ResourcesEstimator` .</span><span class="sxs-lookup"><span data-stu-id="9657f-123">There should now be two unit tests, one where `AllocateQubit` runs on the `QuantumSimulator`, and one where it runs in the `ResourcesEstimator`.</span></span> 

<span data-ttu-id="9657f-124">Q#Derleyici, `"QuantumSimulator"` birim testleri için yerleşik hedefleri, `"ToffoliSimulator"` ve `"ResourcesEstimator"` geçerli çalıştırma hedeflerini tanır.</span><span class="sxs-lookup"><span data-stu-id="9657f-124">The Q# compiler recognizes the built-in targets `"QuantumSimulator"`, `"ToffoliSimulator"`, and `"ResourcesEstimator"` as valid run targets for unit tests.</span></span> <span data-ttu-id="9657f-125">Özel bir çalışma hedefi tanımlamak için herhangi bir tam nitelikli ad belirtmek de mümkündür.</span><span class="sxs-lookup"><span data-stu-id="9657f-125">It is also possible to specify any fully qualified name to define a custom run target.</span></span> 

### <a name="running-no-locq-unit-tests"></a><span data-ttu-id="9657f-126">Q#Birim testlerini çalıştırma</span><span class="sxs-lookup"><span data-stu-id="9657f-126">Running Q# Unit Tests</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="9657f-127">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="9657f-127">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="9657f-128">Tek seferlik çözüm başına kurulum olarak, **Test** menüsüne gidin ve **x64 > varsayılan Işlemci mimarisi > test ayarları**' nı seçin.</span><span class="sxs-lookup"><span data-stu-id="9657f-128">As a one-time per-solution setup, go to the **Test** menu and select **Test Settings > Default Processor Architecture > X64**.</span></span>

> [!TIP]
> <span data-ttu-id="9657f-129">Visual Studio için varsayılan işlemci mimarisi ayarı, `.suo` her çözüm için çözüm seçenekleri () dosyasında depolanır.</span><span class="sxs-lookup"><span data-stu-id="9657f-129">The default processor architecture setting for Visual Studio is stored in the solution options (`.suo`) file for each solution.</span></span>
> <span data-ttu-id="9657f-130">Bu dosyayı silerseniz, İşlemci mimariniz olarak **x64** ' u yeniden seçmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="9657f-130">If you delete this file, then you need to select **X64** as your processor architecture again.</span></span>

<span data-ttu-id="9657f-131">Projeyi derleyin, **Test** menüsünü açın ve **Windows > test Gezgini**' ni seçin.</span><span class="sxs-lookup"><span data-stu-id="9657f-131">Build the project, open the **Test** menu, and select **Windows > Test Explorer**.</span></span> <span data-ttu-id="9657f-132">**Allocatequbit** , **çalıştırma testleri** grubundaki test listesinde görüntülenir.</span><span class="sxs-lookup"><span data-stu-id="9657f-132">**AllocateQubit** displays in the list of tests in the **Not Run Tests** group.</span></span> <span data-ttu-id="9657f-133">**Tümünü Çalıştır** ' ı veya bu bireysel Testi Çalıştır ' ı seçin.</span><span class="sxs-lookup"><span data-stu-id="9657f-133">Select **Run All** or run this individual test.</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="9657f-134">Komut Satırı / Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="9657f-134">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="9657f-135">Testleri çalıştırmak için proje klasörüne (içeren klasör `Tests.csproj` ) gidin ve şu komutu çalıştırın:</span><span class="sxs-lookup"><span data-stu-id="9657f-135">To run tests, navigate to the project folder (the folder which contains `Tests.csproj`), and run the command:</span></span>

```bash
$ dotnet restore
$ dotnet test
```

<span data-ttu-id="9657f-136">Aşağıdakine benzer bir çıktı almalısınız:</span><span class="sxs-lookup"><span data-stu-id="9657f-136">You should get output similar to the following:</span></span>

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

<span data-ttu-id="9657f-137">Birim testleri adına veya çalışma hedefine göre filtrelenebilir:</span><span class="sxs-lookup"><span data-stu-id="9657f-137">Unit tests can be filtered according to their name or the run target:</span></span>

```bash 
$ dotnet test --filter "Target=QuantumSimulator"
$ dotnet test --filter "Name=AllocateQubit"
```


***

<span data-ttu-id="9657f-138">İç işlevin <xref:microsoft.quantum.intrinsic.message> türü vardır `(String -> Unit)` ve tanılama iletilerinin oluşturulmasına izin vermez.</span><span class="sxs-lookup"><span data-stu-id="9657f-138">The intrinsic function <xref:microsoft.quantum.intrinsic.message> has type `(String -> Unit)` and enables the creation of diagnostic messages.</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="9657f-139">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="9657f-139">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="9657f-140">Test Gezgini 'nde bir testi çalıştırdıktan ve teste tıkladığınızda, test çalıştırması hakkında bilgi içeren bir panel görüntülenir: geçiş/başarısızlık durumu, geçen süre ve çıktının bağlantısı.</span><span class="sxs-lookup"><span data-stu-id="9657f-140">After you run a test in Test Explorer and click on the test, a panel displays with information about test run: Pass/fail status, elapsed time, and a link to the output.</span></span> <span data-ttu-id="9657f-141">Test çıkışını yeni bir pencerede açmak için **Çıkış** ' a tıklayın.</span><span class="sxs-lookup"><span data-stu-id="9657f-141">Click **Output** to open the test output in a new window.</span></span>

![test çıktısı](~/media/unit-test-output.png)

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="9657f-143">Komut Satırı / Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="9657f-143">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="9657f-144">Her test için başarılı/başarısız durumu konsola tarafından yazdırılır `dotnet test` .</span><span class="sxs-lookup"><span data-stu-id="9657f-144">The pass/fail status for each test is printed to the console by `dotnet test`.</span></span>
<span data-ttu-id="9657f-145">Başarısız testler için çıktılar, hatanın tanılanmasına yardımcı olmak üzere konsola da yazdırılır.</span><span class="sxs-lookup"><span data-stu-id="9657f-145">For failing tests, the outputs are also printed to the console to help diagnose the failure.</span></span>

***

## <a name="facts-and-assertions"></a><span data-ttu-id="9657f-146">Olgular ve Onaylamalar</span><span class="sxs-lookup"><span data-stu-id="9657f-146">Facts and Assertions</span></span>

<span data-ttu-id="9657f-147">İçindeki işlevlerin Q# _mantıksal_ yan etkileri olmadığından, bir program içinden hiçbir daha gözlemleyebilirsiniz, Q# Çıkış türü boş tanımlama grubu olan bir işlevi çalıştırmanın diğer etkileri vardır `()` .</span><span class="sxs-lookup"><span data-stu-id="9657f-147">Because functions in Q# have no _logical_ side effects, you can never observe, from within a Q# program, any other kinds of effects from running a function whose output type is the empty tuple `()`.</span></span>
<span data-ttu-id="9657f-148">Diğer bir deyişle, bir hedef makine, `()` Bu atlama 'nin aşağıdaki kodun davranışını değiştirmeyeceği garantisi ile döndürülen hiçbir işlevi çalıştırmayabilir Q# .</span><span class="sxs-lookup"><span data-stu-id="9657f-148">That is, a target machine can choose not to run any function which returns `()` with the guarantee that this omission will not modify the behavior of any following Q# code.</span></span>
<span data-ttu-id="9657f-149">Bu davranış `()` `Unit` , programları (gibi), programlara onaylar ve hata ayıklama mantığı eklemek için yararlı bir araç sağlar Q# .</span><span class="sxs-lookup"><span data-stu-id="9657f-149">This behavior makes functions returning `()` (such as `Unit`) a useful tool for embedding assertions and debugging logic into Q# programs.</span></span> 

<span data-ttu-id="9657f-150">Basit bir örnek ele alalım:</span><span class="sxs-lookup"><span data-stu-id="9657f-150">Let's consider a simple example:</span></span>

```qsharp
function PositivityFact(value : Double) : Unit 
{
    if (value <= 0) 
    {
        fail "Expected a positive number.";
    }
}
```

<span data-ttu-id="9657f-151">Burada anahtar sözcüğü, `fail` hesaplamanın devam olmayacağını ve programı çalıştıran hedef makinede bir özel durum harekete geçirdiğini gösterir Q# .</span><span class="sxs-lookup"><span data-stu-id="9657f-151">Here, the keyword `fail` indicates that the computation should not proceed, and raises an exception in the target machine running the Q# program.</span></span>
<span data-ttu-id="9657f-152">Tanım olarak, Q# hedef makine artık Q# bir deyime ulaştıktan sonra kodu çalıştırmayacak olduğundan, bu türden bir hata içinden gözlemlenemez `fail` .</span><span class="sxs-lookup"><span data-stu-id="9657f-152">By definition, a failure of this kind cannot be observed from within Q#, as the target machine no longer runs the Q# code after reaching a `fail` statement.</span></span>
<span data-ttu-id="9657f-153">Bu nedenle, çağrısına bir çağrı geçmemiz durumunda `PositivityFact` girişinin pozitif olduğundan emin olabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="9657f-153">Thus, if we proceed past a call to `PositivityFact`, we can be assured that its input was positive.</span></span>

<span data-ttu-id="9657f-154">`PositivityFact`Ad alanından işlevini kullanarak aynı davranışı uygulayabileceğinizi unutmayın [`Fact`](xref:microsoft.quantum.diagnostics.fact) <xref:microsoft.quantum.diagnostics> :</span><span class="sxs-lookup"><span data-stu-id="9657f-154">Note that we can implement the same behavior as `PositivityFact` using the [`Fact`](xref:microsoft.quantum.diagnostics.fact) function from the <xref:microsoft.quantum.diagnostics> namespace:</span></span>

```qsharp
    Fact(value > 0, "Expected a positive number.");
```

<span data-ttu-id="9657f-155">Diğer yandan *onaylar,* olgulara benzer şekilde kullanılır ancak hedef makinenin durumuna bağlı olabilir.</span><span class="sxs-lookup"><span data-stu-id="9657f-155">*Assertions*, on the other hand, are used similarly to facts but may depend on the state of the target machine.</span></span> <span data-ttu-id="9657f-156">Bunlar işlem olarak tanımlandıklarında, olgular işlev olarak tanımlanır (önceki örnekte olduğu gibi).</span><span class="sxs-lookup"><span data-stu-id="9657f-156">Correspondingly, they are defined as operations, whereas facts are defined as functions (as in the previous example).</span></span>
<span data-ttu-id="9657f-157">Ayrımı anlamak için, bir onaylama içinde aşağıdaki olgunun kullanımını göz önünde bulundurun:</span><span class="sxs-lookup"><span data-stu-id="9657f-157">To understand the distinction, consider the following use of a fact within an assertion:</span></span>

```qsharp
operation AssertQubitsAreAvailable() : Unit
{
     Fact(GetQubitsAvailableToUse() > 0, "No qubits were actually available");
}
```

<span data-ttu-id="9657f-158">Burada, <xref:microsoft.quantum.environment.getqubitsavailabletouse> kullanılabilecek qubits sayısını döndürmek için işlemini kullanıyoruz.</span><span class="sxs-lookup"><span data-stu-id="9657f-158">Here, we are using the operation <xref:microsoft.quantum.environment.getqubitsavailabletouse> to return the number of qubits available to use.</span></span>
<span data-ttu-id="9657f-159">Bu, programın ve çalışma ortamının genel durumuna bağlı olduğundan, tanımımız da `AssertQubitsAreAvailable` bir işlem olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="9657f-159">As this depends on the global state of the program and its run environment, our definition of `AssertQubitsAreAvailable` must be an operation as well.</span></span>
<span data-ttu-id="9657f-160">Ancak, işleve giriş olarak basit bir değer sağlamak için bu genel durumu kullanabiliriz `Bool` `Fact` .</span><span class="sxs-lookup"><span data-stu-id="9657f-160">However, we can use that global state to yield a simple `Bool` value as input to the `Fact` function.</span></span>

<span data-ttu-id="9657f-161">[Prelude](xref:microsoft.quantum.libraries.standard.prelude), bu fikirleri oluşturmak için iki özellikle yararlı onay sağlar <xref:microsoft.quantum.diagnostics.assertmeasurement> ve <xref:microsoft.quantum.diagnostics.assertmeasurementprobability> her ikisi de üzerinde işlem olarak modellenir `()` .</span><span class="sxs-lookup"><span data-stu-id="9657f-161">[The prelude](xref:microsoft.quantum.libraries.standard.prelude), building on these ideas, offers two especially useful assertions, <xref:microsoft.quantum.diagnostics.assertmeasurement> and <xref:microsoft.quantum.diagnostics.assertmeasurementprobability> both modeled as operations onto `()`.</span></span> <span data-ttu-id="9657f-162">Bu onayların her biri, belirli bir ölçümü, ölçümün gerçekleştirildiği bir hisse izini ve kuramsal bir sonucu açıklayan bir Pauli işleci alır.</span><span class="sxs-lookup"><span data-stu-id="9657f-162">These assertions each take a Pauli operator describing a particular measurement of interest, a quantum register on which a measurement is performed, and a hypothetical outcome.</span></span>
<span data-ttu-id="9657f-163">Simülasyonu tarafından çalışan hedef makineler, [hiçbir kopya](https://en.wikipedia.org/wiki/No-cloning_theorem)olmayan kopyalarla bağlantılı değildir ve bu tür ölçümlere, bu tür onayları geçen kaydı etkilemeden gerçekleştirebilir.</span><span class="sxs-lookup"><span data-stu-id="9657f-163">Target machines which work by simulation are not bound by [the no-cloning theorem](https://en.wikipedia.org/wiki/No-cloning_theorem), and can perform such measurements without disturbing the register that passes to such assertions.</span></span>
<span data-ttu-id="9657f-164">Daha sonra bir Benzetici, `PositivityFact` önceki işleve benzer şekilde, kuramsal sonuç uygulamada gözlemlenmeyen hesaplamayı durdurabilir:</span><span class="sxs-lookup"><span data-stu-id="9657f-164">A simulator can then, similar to the `PositivityFact` function previous, stop computation if the hypothetical outcome is not observed in practice:</span></span>

```qsharp
using (register = Qubit()) 
{
    H(register);
    AssertMeasurement([PauliX], [register], Zero);
    // Even though we do not have access to states in Q#,
    // we know by the anthropic principle that the state
    // of register at this point is |+〉.
}
```

<span data-ttu-id="9657f-165">Fiziksel hisse donanımı ' nde, hiçbir kopya olmaması durumunda bir hisse durumunun incelediği, `AssertMeasurement` ve `AssertMeasurementProbability` işlemleri yalnızca `()` başka bir etkisi olmadan döndürülür.</span><span class="sxs-lookup"><span data-stu-id="9657f-165">On physical quantum hardware, where the no-cloning theorem prevents examination of a quantum state, the `AssertMeasurement` and `AssertMeasurementProbability` operations simply return `()` with no other effect.</span></span>

<span data-ttu-id="9657f-166"><xref:microsoft.quantum.diagnostics>Ad alanı, `Assert` ailede daha fazla gelişmiş koşul için daha fazla sayıda işlev sağlar.</span><span class="sxs-lookup"><span data-stu-id="9657f-166">The <xref:microsoft.quantum.diagnostics> namespace provides several more functions of the `Assert` family, with which you can check more advanced conditions.</span></span> 

## <a name="dump-functions"></a><span data-ttu-id="9657f-167">Döküm Işlevleri</span><span class="sxs-lookup"><span data-stu-id="9657f-167">Dump Functions</span></span>

<span data-ttu-id="9657f-168">Ad alanı, hisse programlarının sorunlarını gidermeye yardımcı olmak için, <xref:microsoft.quantum.diagnostics> hedef makinenin geçerli durumu ile bir dosyanın dökümünü yapan iki işlev sunar: <xref:microsoft.quantum.diagnostics.dumpmachine> ve <xref:microsoft.quantum.diagnostics.dumpregister> .</span><span class="sxs-lookup"><span data-stu-id="9657f-168">To help troubleshooting quantum programs, the <xref:microsoft.quantum.diagnostics> namespace offers two functions that can dump into a file the current status of the target machine: <xref:microsoft.quantum.diagnostics.dumpmachine> and <xref:microsoft.quantum.diagnostics.dumpregister>.</span></span> <span data-ttu-id="9657f-169">Her birinin üretilen çıktısı, hedef makineye bağlıdır.</span><span class="sxs-lookup"><span data-stu-id="9657f-169">The generated output of each depends on the target machine.</span></span>

### <a name="dumpmachine"></a><span data-ttu-id="9657f-170">DumpMachine</span><span class="sxs-lookup"><span data-stu-id="9657f-170">DumpMachine</span></span>

<span data-ttu-id="9657f-171">Hisse geliştirme seti 'nin bir parçası olarak dağıtılan tam eyalet hisse simülatörü, tüm hisse sisteminin [Wave işlevini](https://en.wikipedia.org/wiki/Wave_function) dosyaya yazar. tek boyutlu karmaşık sayıların dizisi olarak her bir öğenin hesaplama tabanlı durumu $ \ket{n} $ ölçü olasılığını temsil eden, $ \ket{n} = \ket{B_ {n-1}... BITS $ b_i $ için b_1b_0} $ \{ \} .</span><span class="sxs-lookup"><span data-stu-id="9657f-171">The full-state quantum simulator distributed as part of the Quantum Development Kit writes into the file the [wave function](https://en.wikipedia.org/wiki/Wave_function) of the entire quantum system, as a one-dimensional array of complex numbers, in which each element represents the amplitude of the probability of measuring the computational basis state $\ket{n}$, where $\ket{n} = \ket{b_{n-1}...b_1b_0}$ for bits $\{b_i\}$.</span></span> <span data-ttu-id="9657f-172">Örneğin, yalnızca iki qubit ayrılmış bir makinede ve hisse durumu $ $ \begin{hizalaması} \ket{\psı} = \frac {1} {\sqrt {2} } {00} \tus-\frac{(1 + ı)} {2} {10} \tus, \end{hizalaması} $ $ çağıran <xref:microsoft.quantum.diagnostics.dumpmachine> Bu çıktıyı oluşturur:</span><span class="sxs-lookup"><span data-stu-id="9657f-172">For example, on a machine with only two qubits allocated and in the quantum state $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10}, \end{align} $$ calling <xref:microsoft.quantum.diagnostics.dumpmachine> generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 0;1
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣2❭:    -0.500000 + -0.500000 i  ==     **********           [ 0.500000 ]   /     [ -2.35619 rad ]
∣3❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

<span data-ttu-id="9657f-173">İlk satır, karşılık gelen qubits kimlikleri için önemli sırayla bir açıklama sağlar.</span><span class="sxs-lookup"><span data-stu-id="9657f-173">The first row provides a comment with the ids of the corresponding qubits in their significant order.</span></span>
<span data-ttu-id="9657f-174">Satırların geri kalanı, hem Kartezyen hem de kutupsal biçimlerdeki temel eyalet vektörü $ \ket{n} $ ölçgenin olasılığını anlatmaktadır.</span><span class="sxs-lookup"><span data-stu-id="9657f-174">The rest of the rows describe the probability amplitude of measuring the basis state vector $\ket{n}$ in both Cartesian and polar formats.</span></span> <span data-ttu-id="9657f-175">İlk satır için ayrıntılı:</span><span class="sxs-lookup"><span data-stu-id="9657f-175">In detail for the first row:</span></span>

* <span data-ttu-id="9657f-176">**`∣0❭:`** Bu satır `0` Hesaplama esası durumuna karşılık gelir</span><span class="sxs-lookup"><span data-stu-id="9657f-176">**`∣0❭:`** this row corresponds to the `0` computational basis state</span></span>
* <span data-ttu-id="9657f-177">**`0.707107 +  0.000000 i`**: Kartezyen biçiminde olasılık genliği.</span><span class="sxs-lookup"><span data-stu-id="9657f-177">**`0.707107 +  0.000000 i`**: the probability amplitude in Cartesian format.</span></span>
* <span data-ttu-id="9657f-178">**` == `**: `equal` işaret, her iki eşdeğer temsili de ayırır.</span><span class="sxs-lookup"><span data-stu-id="9657f-178">**` == `**: the `equal` sign separates both equivalent representations.</span></span>
* <span data-ttu-id="9657f-179">**`**********  `**: Büyüklük grafik gösterimi, sayısı `*` Bu durum vektörünü ölçme olasılığının müşterinizin istekleriyle orantılı.</span><span class="sxs-lookup"><span data-stu-id="9657f-179">**`**********  `**: A graphical representation of the magnitude, the number of `*` is proportionate to the probability of measuring this state vector.</span></span>
* <span data-ttu-id="9657f-180">**`[ 0.500000 ]`**: büyüklük sayısal değeri</span><span class="sxs-lookup"><span data-stu-id="9657f-180">**`[ 0.500000 ]`**: the numeric value of the magnitude</span></span>
* <span data-ttu-id="9657f-181">**`    ---`**: Genin aşamasının grafik gösterimi (aşağıdaki çıktıya bakın).</span><span class="sxs-lookup"><span data-stu-id="9657f-181">**`    ---`**: A graphical representation of the amplitude's phase (see the following output).</span></span>
* <span data-ttu-id="9657f-182">**`[ 0.0000 rad ]`**: aşamanın sayısal değeri (radyan cinsinden).</span><span class="sxs-lookup"><span data-stu-id="9657f-182">**`[ 0.0000 rad ]`**: the numeric value of the phase (in radians).</span></span>

<span data-ttu-id="9657f-183">Büyüklük ve aşama bir grafik gösterimiyle birlikte görüntülenir.</span><span class="sxs-lookup"><span data-stu-id="9657f-183">Both the magnitude and the phase are displayed with a graphical representation.</span></span> <span data-ttu-id="9657f-184">Büyüklük temsili düz bir şekilde görünür: bir çubuğunu gösterir, çubuğun ne kadar büyük olacağını daha `*` büyük hale gelir.</span><span class="sxs-lookup"><span data-stu-id="9657f-184">The magnitude representation is straight-forward: it shows a bar of `*`, the bigger the probability the bigger the bar will be.</span></span> <span data-ttu-id="9657f-185">Aşama için, aralıklara göre açıyı temsil etmek üzere aşağıdaki sembolleri göstereceğiz:</span><span class="sxs-lookup"><span data-stu-id="9657f-185">For the phase, we show the following symbols to represent the angle based on ranges:</span></span>

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

<span data-ttu-id="9657f-186">Aşağıdaki örneklerde `DumpMachine` bazı yaygın durumlar gösterilmektedir:</span><span class="sxs-lookup"><span data-stu-id="9657f-186">The following examples show `DumpMachine` for some common states:</span></span>

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
  > <span data-ttu-id="9657f-187">Bir qubit kimliği çalışma zamanında atanır ve qubitin ayrıldığı sıra veya bir qubit yazmaç içindeki konumu ile hizalı değildir.</span><span class="sxs-lookup"><span data-stu-id="9657f-187">The id of a qubit is assigned at runtime and is not necessarily aligned with the order in which the qubit was allocated or its position within a qubit register.</span></span>


#### <a name="visual-studio-2019"></a>[<span data-ttu-id="9657f-188">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="9657f-188">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

  > [!TIP]
  > <span data-ttu-id="9657f-189">Kodunuzda bir kesme noktası yerleştirerek ve bir qubit değişkeninin değerini inceleyerek, Visual Studio 'da bir qubit kimliği bulabilirsiniz, örneğin:</span><span class="sxs-lookup"><span data-stu-id="9657f-189">You can locate a qubit id in Visual Studio by putting a breakpoint in your code and inspecting the value of a qubit variable, for example:</span></span>
  > 
  > ![Visual Studio 'da qubit kimliği göster](~/media/qubit_id.png)
  >
  > <span data-ttu-id="9657f-191">dizininde bulunan qubit, `0` `register2` ID = `3` , index ile qubit ise `1` ID = `2` .</span><span class="sxs-lookup"><span data-stu-id="9657f-191">the qubit with index `0` on `register2` has id=`3`, the qubit with index `1` has id=`2`.</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="9657f-192">Komut Satırı / Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="9657f-192">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

  > [!TIP]
  > <span data-ttu-id="9657f-193">İşlevi kullanarak bir qubit kimliği bulabilir <xref:microsoft.quantum.intrinsic.message> ve qubit değişkenini iletiye geçirerek, örneğin:</span><span class="sxs-lookup"><span data-stu-id="9657f-193">You can locate a qubit id by using the <xref:microsoft.quantum.intrinsic.message> function and passing the qubit variable in the message, for example:</span></span>
  >
  > ```qsharp
  > Message($"0={register2[0]}; 1={register2[1]}");
  > ```
  > 
  > <span data-ttu-id="9657f-194">Bu çıktıyı üreten:</span><span class="sxs-lookup"><span data-stu-id="9657f-194">which could generate this output:</span></span>
  >```
  > 0=q:3; 1=q:2
  >```
  > <span data-ttu-id="9657f-195">Yani, dizinindeki qubit, `0` `register2` ID = `3` , index ile qubit 'in `1` ID = `2` olduğu anlamına gelir.</span><span class="sxs-lookup"><span data-stu-id="9657f-195">which means that the qubit with index `0` on `register2` has id=`3`, the qubit with index `1` has id=`2`.</span></span>


***

<span data-ttu-id="9657f-196"><xref:microsoft.quantum.diagnostics.dumpmachine> <xref:microsoft.quantum.diagnostics> Ad alanının bir parçası olduğundan, `open` ona erişmek için bir ifade eklemeniz gerekir:</span><span class="sxs-lookup"><span data-stu-id="9657f-196">Since <xref:microsoft.quantum.diagnostics.dumpmachine> is part of the  <xref:microsoft.quantum.diagnostics> namespace, you must add an `open` statement to access it:</span></span>

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


### <a name="dumpregister"></a><span data-ttu-id="9657f-197">DumpRegister</span><span class="sxs-lookup"><span data-stu-id="9657f-197">DumpRegister</span></span>

<span data-ttu-id="9657f-198"><xref:microsoft.quantum.diagnostics.dumpregister> gibi çalışarak <xref:microsoft.quantum.diagnostics.dumpmachine> , bilgi miktarını yalnızca ilgili qubits ile ilgili olarak sınırlamak için bir qubit dizisi de alır.</span><span class="sxs-lookup"><span data-stu-id="9657f-198"><xref:microsoft.quantum.diagnostics.dumpregister> works like <xref:microsoft.quantum.diagnostics.dumpmachine>, except that it also takes an array of qubits to limit the amount of information to only that relevant to the corresponding qubits.</span></span>

<span data-ttu-id="9657f-199">İle olduğu gibi <xref:microsoft.quantum.diagnostics.dumpmachine> , tarafından oluşturulan bilgiler <xref:microsoft.quantum.diagnostics.dumpregister> hedef makineye göre değişir.</span><span class="sxs-lookup"><span data-stu-id="9657f-199">As with <xref:microsoft.quantum.diagnostics.dumpmachine>, the information generated by <xref:microsoft.quantum.diagnostics.dumpregister> depends on the target machine.</span></span> <span data-ttu-id="9657f-200">Tam eyalet hisse simülatörü için, Wave işlevine, ile aynı biçimde belirtilen qubits tarafından oluşturulan küresel bir aşamaya kadar yazar <xref:microsoft.quantum.diagnostics.dumpmachine> .</span><span class="sxs-lookup"><span data-stu-id="9657f-200">For the full-state quantum simulator it writes into the file the wave function up to a global phase of the quantum sub-system generated by the provided qubits in the same format as <xref:microsoft.quantum.diagnostics.dumpmachine>.</span></span>  <span data-ttu-id="9657f-201">Örneğin, yalnızca iki qubit ayrılmış bir makineye ve hisse durumu $ $ \begin{hizalaması} \ket{\psı} = \frac {1} {\sqrt {2} } {00} \tus-\frac{(1 + ı)} {2} {10} \tus=-e ^ {-i \ Pi/4} ((\frac {1} {\sqrt {2} } {0} \tus-\frac{(1 + i)} {2} \ket {1} ) \otimes \frac{-(1 + ı)} {\sqrt {2} } {0} \tus), \end{hizalaması} $ $ çağrısı <xref:microsoft.quantum.diagnostics.dumpregister> `qubit[0]` Bu çıktıyı oluşturur:</span><span class="sxs-lookup"><span data-stu-id="9657f-201">For example, take again a machine with only two qubits allocated and in the quantum state $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10} = - e^{-i\pi/4} ( (\frac{1}{\sqrt{2}} \ket{0} - \frac{(1 + i)}{2} \ket{1} ) \otimes \frac{-(1 + i)}{\sqrt{2}} \ket{0} ) , \end{align} $$ calling <xref:microsoft.quantum.diagnostics.dumpregister> for `qubit[0]` generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:    -0.707107 + -0.707107 i  ==     ******************** [ 1.000000 ]  /      [ -2.35619 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

<span data-ttu-id="9657f-202">ve <xref:microsoft.quantum.diagnostics.dumpregister> için çağrı `qubit[1]` Bu çıktıyı oluşturur:</span><span class="sxs-lookup"><span data-stu-id="9657f-202">and calling <xref:microsoft.quantum.diagnostics.dumpregister> for `qubit[1]` generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 1
∣0❭:     0.707107 +  0.000000 i  ==     ***********          [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:    -0.500000 + -0.500000 i  ==     ***********          [ 0.500000 ]  /      [ -2.35619 rad ]
```

<span data-ttu-id="9657f-203">Genel olarak, başka bir yazmaç ile ayrılmış bir kaydın durumu saf bir durum değil, karışık bir durumdur.</span><span class="sxs-lookup"><span data-stu-id="9657f-203">In general, the state of a register that is entangled with another register is a mixed state rather than a pure state.</span></span> <span data-ttu-id="9657f-204">Bu durumda, <xref:microsoft.quantum.diagnostics.dumpregister> aşağıdaki iletiyi verir:</span><span class="sxs-lookup"><span data-stu-id="9657f-204">In this case, <xref:microsoft.quantum.diagnostics.dumpregister> outputs the following message:</span></span>

```
Qubits provided (0;) are entangled with some other qubit.
```

<span data-ttu-id="9657f-205">Aşağıdaki örnek, kodunuzda ve birlikte nasıl kullanabileceğinizi gösterir <xref:microsoft.quantum.diagnostics.dumpregister> <xref:microsoft.quantum.diagnostics.dumpmachine> Q# :</span><span class="sxs-lookup"><span data-stu-id="9657f-205">The following example shows you how you can use both <xref:microsoft.quantum.diagnostics.dumpregister> and <xref:microsoft.quantum.diagnostics.dumpmachine> in your Q# code:</span></span>

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

## <a name="debugging"></a><span data-ttu-id="9657f-206">Hata Ayıklama</span><span class="sxs-lookup"><span data-stu-id="9657f-206">Debugging</span></span>

<span data-ttu-id="9657f-207">`Assert`Ve `Dump` işlevleri ve işlemleri üzerinde, Q# Standart Visual Studio hata ayıklama özellikleri alt kümesini destekler: [satır kesme noktaları ayarlama](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints), [F10 kullanarak kod üzerinden atlama](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger)ve [Klasik değişkenlerin değerlerini inceleme](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) , kod simülatörü üzerinde çalışırken mümkündür.</span><span class="sxs-lookup"><span data-stu-id="9657f-207">On top of `Assert` and `Dump` functions and operations, Q# supports a subset of standard Visual Studio debugging capabilities: [setting line breakpoints](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints), [stepping through code using F10](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger), and [inspecting values of classic variables](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) are all possible when running your code on the simulator.</span></span>

<span data-ttu-id="9657f-208">Visual Studio Code hata ayıklaması, C# tarafından desteklenen ve OmniSharp tarafından desteklenen Visual Studio Code uzantısı Için sağlanan hata ayıklama yeteneklerini kullanır ve [en son sürümü](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp)yüklemeyi gerektirir.</span><span class="sxs-lookup"><span data-stu-id="9657f-208">Debugging in Visual Studio Code leverages the debugging capabilities provided by the C# for Visual Studio Code extension powered by OmniSharp and requires installing the [latest version](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp).</span></span> 
