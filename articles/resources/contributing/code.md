---
title: Microsoft QDK 'ye katkıda bulunan kod
description: Örnek ve kitaplık kodunun Microsoft Quantum Development Kit (QDK) ile nasıl katkıda bulunabileceğinizi öğrenin.
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.code
ms.openlocfilehash: edc52dc4434e91258bece28812fd76b66329c6f9
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275487"
---
# <a name="contributing-code"></a><span data-ttu-id="24ffb-103">Koda Katkıda Bulunma</span><span class="sxs-lookup"><span data-stu-id="24ffb-103">Contributing Code</span></span>

<span data-ttu-id="24ffb-104">Sorunları raporlamaya ve belgelerin geliştirilmesine ek olarak, hisse geliştirme seti 'ne katkıda bulunan kod, hisse programlama topluluğundaki eşlere yardımcı olmanın çok doğrudan bir yolu olabilir.</span><span class="sxs-lookup"><span data-stu-id="24ffb-104">In addition to reporting issues and improving documentation, contributing code to the Quantum Development Kit can be a very direct way to help your peers in the quantum programming community.</span></span>
<span data-ttu-id="24ffb-105">Kod katkısından, sorunları gidermeye, yeni örnekler sağlamanıza, var olan kitaplıkların kullanımını daha kolay hale getirmenize veya hatta tamamen yeni özellikler eklemenize yardımcı olabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="24ffb-105">By contributing code, you can help to fix issues, provide new examples, make existing libraries easier to use, or even add entirely new features.</span></span>

<span data-ttu-id="24ffb-106">Bu kılavuzda, katkıınızın en iyi şekilde faydalanmaya yardımcı olmak için çekme isteklerini gözden geçirdiğimiz sırada baktığımız bir şeyi ayrıntılandırıyoruz.</span><span class="sxs-lookup"><span data-stu-id="24ffb-106">In this guide, we'll detail a bit of what we look for when we review pull requests to help your contribution do the most good.</span></span>

## <a name="what-we-look-for"></a><span data-ttu-id="24ffb-107">Şuna baktık</span><span class="sxs-lookup"><span data-stu-id="24ffb-107">What We Look For</span></span>

<span data-ttu-id="24ffb-108">İdeal bir kod katkısı, sorunları gidermek, mevcut özellikleri genişletmek veya bir deponun kapsamı içinde olan yeni özellikler eklemek için bir hisse geliştirme seti deposundaki mevcut çalışmayı oluşturur.</span><span class="sxs-lookup"><span data-stu-id="24ffb-108">An ideal code contribution builds on the existing work in a Quantum Development Kit repository to fix issues, expand existing features, or to add new features that are within the scope of a repository.</span></span>
<span data-ttu-id="24ffb-109">Bir kod katkısı kabul ettiğimiz zaman, bu, hisse geliştirme setinin bir parçası haline gelir. bu şekilde, yeni özellikler ücretlendirilecektir, tutulur ve, hisse geliştirme setinin geri kalanı ile aynı şekilde geliştirilir.</span><span class="sxs-lookup"><span data-stu-id="24ffb-109">When we accept a code contribution, it becomes a part of the Quantum Development Kit itself, such that new features will be released, maintained, and developed in the same way as the rest of the Quantum Development Kit.</span></span>
<span data-ttu-id="24ffb-110">Bu nedenle, bir katkı tarafından eklenen işlevlerin iyi test edildiğini ve belgelendirildiğine yardımcı olur.</span><span class="sxs-lookup"><span data-stu-id="24ffb-110">Thus, it is helpful when functionality added by a contribution is well-tested and is documented.</span></span>

### <a name="unit-tests"></a><span data-ttu-id="24ffb-111">Birim testleri</span><span class="sxs-lookup"><span data-stu-id="24ffb-111">Unit Tests</span></span>

<span data-ttu-id="24ffb-112">Canon gibi kitaplıkları oluşturan Q # işlevleri, işlemler ve Kullanıcı tanımlı türler, [**Microsoft/Histumlibraries**](https://github.com/Microsoft/QuantumLibraries/) deposunda geliştirmenin bir parçası olarak otomatik olarak test edilir.</span><span class="sxs-lookup"><span data-stu-id="24ffb-112">The Q# functions, operations, and user-defined types that make up libraries such as the canon are automatically tested as a part of development on the [**Microsoft/QuantumLibraries**](https://github.com/Microsoft/QuantumLibraries/) repository.</span></span>
<span data-ttu-id="24ffb-113">Örneğin, yeni bir çekme isteği açıldığında, [Azure Pipelines](https://azure.microsoft.com/services/devops/pipelines/) yapılandırmanızla, çekme isteğindeki değişikliklerin, hisse programlama topluluğunun bağlı olduğu mevcut işlevleri bozmadığını kontrol eder.</span><span class="sxs-lookup"><span data-stu-id="24ffb-113">When a new pull request is opened, for instance, our [Azure Pipelines](https://azure.microsoft.com/services/devops/pipelines/) configuration will check that the changes in the pull request do not break any existing functionality that the quantum programming community depends on.</span></span>

<span data-ttu-id="24ffb-114">En son Q # sürümü ile birim testi özniteliği kullanılarak tanımlanır `@Test("QuantumSimulator")` .</span><span class="sxs-lookup"><span data-stu-id="24ffb-114">With the latest Q# version, unit test are defined using the `@Test("QuantumSimulator")` attribute.</span></span> <span data-ttu-id="24ffb-115">Bağımsız değişken, "Histumsimülatör", "Toffzeytin", "Tracesimülatör" veya yürütme hedefini belirten tam nitelikli bir ad olabilir.</span><span class="sxs-lookup"><span data-stu-id="24ffb-115">The argument may be either "QuantumSimulator", "ToffoliSimulator", "TraceSimulator", or any fully qualified name specifying the execution target.</span></span> <span data-ttu-id="24ffb-116">Farklı yürütme hedeflerini tanımlayan birkaç öznitelik aynı çağrılabilir öğesine iliştirilebilir.</span><span class="sxs-lookup"><span data-stu-id="24ffb-116">Several attributes defining different execution targets may be attached to the same callable.</span></span> <span data-ttu-id="24ffb-117">Bazı testlerimizde, xUnit çerçevesine biten tüm Q # işlevlerini ve işlemlerini kullanıma sunan kullanım dışı [Microsoft. hisse. xUnit](https://www.nuget.org/packages/Microsoft.Quantum.Xunit/) paketini kullanmaya devam edersiniz `Test` . [xUnit](https://xunit.github.io/)</span><span class="sxs-lookup"><span data-stu-id="24ffb-117">Some of our tests still use the deprecated [Microsoft.Quantum.Xunit](https://www.nuget.org/packages/Microsoft.Quantum.Xunit/) package that exposes all Q# functions and operations ending in `Test` to the [xUnit](https://xunit.github.io/) framework.</span></span> <span data-ttu-id="24ffb-118">Bu paket artık birim testlerini tanımlamak için gerekli değildir.</span><span class="sxs-lookup"><span data-stu-id="24ffb-118">This package is no longer needed for defining unit tests.</span></span> 

<span data-ttu-id="24ffb-119">Aşağıdaki işlev, <xref:microsoft.quantum.canon.fst> ve <xref:microsoft.quantum.canon.snd> işlevlerinin her ikisinin de bir temsilci örneğinde doğru çıkışları döndürmesini sağlamak için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="24ffb-119">The following function is used to ensure that the <xref:microsoft.quantum.canon.fst> and <xref:microsoft.quantum.canon.snd> functions both return the right outputs in a representative example.</span></span>
<span data-ttu-id="24ffb-120">`Fst`Veya çıkışı `Snd` yanlışsa, `fail` test başarısız olmasına neden olması için ifade kullanılır.</span><span class="sxs-lookup"><span data-stu-id="24ffb-120">If the output of `Fst` or `Snd` is incorrect, the `fail` statement is used to cause the test to fail.</span></span>

```qsharp
@Test("QuantumSimulator")
function PairTest () : Unit {
    let pair = (12, PauliZ);

    if (Fst(pair) != 12) {
        let actual = Fst(pair);
        fail $"Expected 12, actual {actual}.";
    }

    if (Snd(pair) != PauliZ) {
        let actual = Snd(pair);
        fail $"Expected PauliZ, actual {actual}.";
    }
}
```

<span data-ttu-id="24ffb-121">Standart kitaplıklar kılavuzunun [Test bölümündeki](xref:microsoft.quantum.libraries.diagnostics) teknikler kullanılarak daha karmaşık koşullar denetlenebilir.</span><span class="sxs-lookup"><span data-stu-id="24ffb-121">More complicated conditions can be checked using the techniques in the [testing section](xref:microsoft.quantum.libraries.diagnostics) of the standard libraries guide.</span></span>
<span data-ttu-id="24ffb-122">Örneğin, aşağıdaki test `H(q); X(q); H(q);` tarafından çağrılışını <xref:microsoft.quantum.canon.applywith> , ile aynı şeyi yapar `Z(q)` .</span><span class="sxs-lookup"><span data-stu-id="24ffb-122">For instance, the following test checks that `H(q); X(q); H(q);` as called by <xref:microsoft.quantum.canon.applywith> does the same thing as `Z(q)`.</span></span>

```Q#
@Test("QuantumSimulator")
operation TestApplyWith() : Unit {
    let actual = ApplyWith(H, X, _);
    let expected = Z;
    AssertOperationsEqualReferenced(ApplyToEach(actual, _), ApplyToEachA(expected, _), 4);
}
```

<span data-ttu-id="24ffb-123">Yeni özellikler eklerken, katkınızın beklenen şeyi kullandığından emin olmak için yeni testler de eklemek iyi bir fikirdir.</span><span class="sxs-lookup"><span data-stu-id="24ffb-123">When adding new features, it's a good idea to also add new tests to make sure that your contribution does what it's supposed to.</span></span>
<span data-ttu-id="24ffb-124">Bu, topluluğun geri kalanında özelliği bakımını ve geliştirmeyi sağlar ve özellikle de diğer geliştiricilerin özelliğinizin güvenebileceklerini bilmesini sağlar.</span><span class="sxs-lookup"><span data-stu-id="24ffb-124">This helps the rest of the community to maintain and develop your feature, and in particular helps other developers know that they can rely on your feature.</span></span>

> [!NOTE]
> <span data-ttu-id="24ffb-125">Bu, etrafında çok farklı bir şekilde çalışmaktadır!</span><span class="sxs-lookup"><span data-stu-id="24ffb-125">This works the other way around, too!</span></span>
> <span data-ttu-id="24ffb-126">Bazı testleri eksik olan bir özellik varsa, test kapsamı ekleyememize yardımcı olmak topluluğa harika bir katkı sağlar.</span><span class="sxs-lookup"><span data-stu-id="24ffb-126">If there's an existing feature that's missing some tests, helping us add test coverage would make a great contribution to the community.</span></span>

<span data-ttu-id="24ffb-127">Yerel olarak, `dotnet test` bir çekme isteği açmadan önce katkılarınızı kontrol edebilmeniz Için Visual Studio Test Gezgini veya komutu kullanılarak birim testleri çalıştırılabilir.</span><span class="sxs-lookup"><span data-stu-id="24ffb-127">Locally, unit tests can be run using the Visual Studio Test Explorer or the `dotnet test` command, so that you can check your contribution before opening up a pull request.</span></span>

<!-- TODO:
### Comments and Documentation ###

### Citations and References ### -->


## <a name="when-well-reject-a-pull-request"></a><span data-ttu-id="24ffb-128">Çekme Isteğini reddedeceğiz</span><span class="sxs-lookup"><span data-stu-id="24ffb-128">When We'll Reject a Pull Request</span></span>

<span data-ttu-id="24ffb-129">Bazen bir katkı için çekme isteğini reddedeceğiz.</span><span class="sxs-lookup"><span data-stu-id="24ffb-129">Sometimes, we'll reject the pull request for a contribution.</span></span>
<span data-ttu-id="24ffb-130">Bu sizin için söz konusu olduğunda, belirli bir katkıyı kabul edemediğimiz bir kaç nedenden dolayı bu durum kötü olduğu anlamına gelmez.</span><span class="sxs-lookup"><span data-stu-id="24ffb-130">If this happens to you, it doesn't mean that it's bad, as there's a number of reasons why we might not be able to accept a particular contribution.</span></span>
<span data-ttu-id="24ffb-131">En yaygın olarak, hisse programlama topluluğu için bir katkı gerçekten iyi bir yoldur, ancak hisse geliştirme seti depoları bu uygulamayı geliştirmek için doğru yerde değildir.</span><span class="sxs-lookup"><span data-stu-id="24ffb-131">Perhaps most commonly, a contribution to the quantum programming community is a really good one, but the Quantum Development Kit repositories aren't the right place to develop it.</span></span>
<span data-ttu-id="24ffb-132">Bu gibi durumlarda, her ne kadar kendi deponuzu, hisse geliştirme setinin kuvvetinin bir parçası olan---, GitHub ve NuGet.org kullanarak kendi kitaplıklarınızı kolayca oluşturmanın ve dağıtmanın yanı sıra Canon ve kimya kitaplıklarını dağıtdığımız şekilde sizin de kolayca dağıtmanızı öneririz.</span><span class="sxs-lookup"><span data-stu-id="24ffb-132">In such cases, we strongly encourage you to make your own repository --- part of the strength of the Quantum Development Kit is that it's easy to make and distribute your own libraries using GitHub and NuGet.org, the same way that we distribute the canon and chemistry libraries today.</span></span>

<span data-ttu-id="24ffb-133">Diğer zamanlarda, henüz bakımını yapmaya ve geliştirmeye hazır olmadığınızdan, iyi bir katkıyı reddedebiliriz.</span><span class="sxs-lookup"><span data-stu-id="24ffb-133">At other times, we may reject a good contribution simply because we aren't yet ready to maintain and develop it.</span></span>
<span data-ttu-id="24ffb-134">Her şeyi yapmak zor olabilir. bu nedenle, bir yol haritası olarak hangi özelliklerin en iyi şekilde çalışabileceklerini planlıyoruz.</span><span class="sxs-lookup"><span data-stu-id="24ffb-134">It can be difficult to do everything, so we plan out what features we're best able to work on as a roadmap.</span></span>
<span data-ttu-id="24ffb-135">Bu, bir özelliğin üçüncü taraf bir kitaplık olarak bırakılması çok daha anlamlı hale geçirebileceği bir durum olabilir.</span><span class="sxs-lookup"><span data-stu-id="24ffb-135">This can be another case where releasing a feature as a third-party library can make a lot of sense.</span></span>
<span data-ttu-id="24ffb-136">Alternatif olarak, bununla ilgili en iyi işi yapabilmemiz için bir özelliği, yol etiketimize daha iyi uyum sağlayacak şekilde değiştirme konusunda yardım almak için sorun yaşayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="24ffb-136">Alternatively, we may ask for your help in modifying a feature to better fit into our roadmap so that we can do the best work we can with it.</span></span>

<span data-ttu-id="24ffb-137">Ayrıca, bunu kullanmamıza yardımcı olmak üzere daha fazla belge veya birim testi gerektiriyorsa veya bir çekme isteğinde, kullanıcıların özelliğinizi bulmasını zortacağından, daha fazla bilgi almak için bir çekme isteğinde de değişiklik yapmanızı isteyeceğiz.</span><span class="sxs-lookup"><span data-stu-id="24ffb-137">We'll also ask for changes to a pull request if it requires more documentation or unit tests to help us make use of it, or if it differs enough in style from the rest of the Q# libraries that it will make it harder for users to find your feature.</span></span>
<span data-ttu-id="24ffb-138">Bu durumlarda, katkılarınızın dahil etmemizi kolaylaştırmak için nelerin eklenebileceği veya değiştirilebilecek hakkında kod incelemelerinde bazı tavsiyeler sunmaya çalışacaktır.</span><span class="sxs-lookup"><span data-stu-id="24ffb-138">In these cases, we'll try to offer some advice in code reviews about what can be added or changed to make your contribution easier for us to include.</span></span>

<span data-ttu-id="24ffb-139">Son olarak, [Microsoft açık kaynak kullanım kuralları](https://opensource.microsoft.com/codeofconduct/)' nda açıklandığı gibi hisse bilgi işlem Topluluğu ' na zarar veren katkılarını kabul edemedik.</span><span class="sxs-lookup"><span data-stu-id="24ffb-139">Finally, we cannot accept contributions that cause harm the quantum computing community, as outlined in the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/).</span></span>
<span data-ttu-id="24ffb-140">Katkıların tüm hisse bilgi işlem topluluğuna, hem geçerli harika çeşitliliğe hem de daha da fazla bir şekilde büyümeye devam ettiğinden emin olmak istiyoruz.</span><span class="sxs-lookup"><span data-stu-id="24ffb-140">We want to ensure that contributions serve the entire quantum computing community, both in its current wonderful diversity, and in the future as it grows to become still more inclusive.</span></span>
<span data-ttu-id="24ffb-141">Bu hedefi gerçekleştirme konusunda yardımımız olduğunu biliyoruz.</span><span class="sxs-lookup"><span data-stu-id="24ffb-141">We appreciate your help in realizing this goal.</span></span>

## <a name="next-steps"></a><span data-ttu-id="24ffb-142">Sonraki adımlar</span><span class="sxs-lookup"><span data-stu-id="24ffb-142">Next steps</span></span>

<span data-ttu-id="24ffb-143">Hisse geliştirme setini tüm hisse programlama topluluğu için harika bir kaynak haline getirmek için teşekkürler!</span><span class="sxs-lookup"><span data-stu-id="24ffb-143">Thanks for helping to make the Quantum Development Kit a great resource for the entire quantum programming community!</span></span>
<span data-ttu-id="24ffb-144">Daha fazla bilgi edinmek için lütfen Q # stilinde aşağıdaki kılavuzla devam edin.</span><span class="sxs-lookup"><span data-stu-id="24ffb-144">To learn more, please continue with the following guide on Q# style.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="24ffb-145">Q # stil yönergeleri hakkında bilgi edinin</span><span class="sxs-lookup"><span data-stu-id="24ffb-145">Learn about Q# style guidelines</span></span>](xref:microsoft.quantum.contributing.style)

<span data-ttu-id="24ffb-146">Katkıda bulunduğunuz kod türüne bağlı olarak, katkılarınızı mümkün olduğunca çok iyi hale getirmenize yardımcı olabilecek başka şeyler de olabilir.</span><span class="sxs-lookup"><span data-stu-id="24ffb-146">Depending on what kind of code you're contributing, there may be additional things to keep in mind that can help you make your contribution do as much good for the community as possible.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="24ffb-147">Katkıda bulunan örnekler hakkında bilgi edinin</span><span class="sxs-lookup"><span data-stu-id="24ffb-147">Learn about contributing samples</span></span>](xref:microsoft.quantum.contributing.samples)