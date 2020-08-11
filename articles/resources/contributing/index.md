---
title: Microsoft Quantum Geliştirme Seti’ne katkıda bulunma
description: Microsoft Quantum Geliştirme Seti’ne ve kuantum geliştirme topluluğuna nasıl katkıda bulunabileceğinizi öğrenin.
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing
no-loc:
- Q#
- $$v
ms.openlocfilehash: 0fbbe127b9f4c6b98bdc2cf0e46098bf40a816e3
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/06/2020
ms.locfileid: "87866868"
---
# <a name="contributing-to-the-quantum-development-kit"></a><span data-ttu-id="31c22-103">Quantum Development Kit’e katkı yapma</span><span class="sxs-lookup"><span data-stu-id="31c22-103">Contributing to the Quantum Development Kit</span></span>

<span data-ttu-id="31c22-104">Quantum Development Kit, kuantum programları yazmaya yönelik bir araç koleksiyonundan fazlasıdır.</span><span class="sxs-lookup"><span data-stu-id="31c22-104">The Quantum Development Kit is more than a collection of tools for writing quantum programs.</span></span>
<span data-ttu-id="31c22-105">Kuantum bilişimini keşfetmekte olan, kuantum algoritmalarında araştırma yapan, kuantum cihazlar için yeni uygulamalar geliştiren ve kuantum programlamadan en iyi şekilde yararlanmak için diğer şekillerde çalışan geniş bir insan topluluğunun parçasıdır.</span><span class="sxs-lookup"><span data-stu-id="31c22-105">It's part of a broad community of people discovering quantum computing, performing research in quantum algorithms, developing new applications for quantum devices, and otherwise working to make the most out of the quantum programming.</span></span>
<span data-ttu-id="31c22-106">Bu topluluğun bir parçası olarak Quantum Development Kit, kuantum geliştiricilerine ihtiyaç duydukları özelliklerle çok çeşitli arka planlar sunmayı amaçlamaktadır.</span><span class="sxs-lookup"><span data-stu-id="31c22-106">As a member of that community, the Quantum Development Kit aims to offer quantum developers across a wide range of backgrounds with the features they need.</span></span>
<span data-ttu-id="31c22-107">Quantum Development Kit’e yaptığınız katkılar, diğer kuantum geliştiriciler tarafından kullanılan araçları, bu araçların belgelenme yöntemlerini geliştirerek ve hatta tüm kuantum programlama topluluğunu keşfetmek ve içerik oluşturmak için daha iyi bir yer haline getirmeye yardımcı olan yeni özellik ve işlevler oluşturarak bu amacı gerçekleştirmeye yardımcı olur.</span><span class="sxs-lookup"><span data-stu-id="31c22-107">Your contributions to the Quantum Development Kit help in realizing that goal by improving the tools used by other quantum developers, how those tools are documented, and even by creating new features and functionality that helps make the entire quantum programming community a better place to discover and create.</span></span>
<span data-ttu-id="31c22-108">Nazik katkılarınız ve topluluğumuzu mümkün olan en iyi seviyeye getirirken birlikte çalışma fırsatı sunduğunuz için teşekkür ediyoruz.</span><span class="sxs-lookup"><span data-stu-id="31c22-108">We're very thankful for your kind contributions, and for the opportunity to work with you to make our community the best that it can be.</span></span> 

<span data-ttu-id="31c22-109">Bu kılavuzda, katkınızın kuantum programlama topluluğuna mümkün olduğunca yarar olmasıyla ilgili bazı önerilerde bulunacağız.</span><span class="sxs-lookup"><span data-stu-id="31c22-109">In this guide, we provide some advice on how to make your contribution as useful as possible to the broader quantum programming community.</span></span>

## <a name="building-community"></a><span data-ttu-id="31c22-110">Topluluk Oluşturma</span><span class="sxs-lookup"><span data-stu-id="31c22-110">Building Community</span></span>

<span data-ttu-id="31c22-111">Katkı yapmanın ilk adımı, katkıda bulunduğunuz topluluğu her zaman aklınızda bulundurmaktır.</span><span class="sxs-lookup"><span data-stu-id="31c22-111">The very first thing about making a contribution is to always keep in mind the community that you are contributing to.</span></span>
<span data-ttu-id="31c22-112">Kuantum programlama topluluğundaki akranlarınıza ve diğer kişilere karşı saygılı ve profesyonel bir şekilde davranarak, çalışmalarınızın mümkün olan en iyi ve en samimi topluluğu inşa etmesine yardımcı olabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="31c22-112">By acting respectfully and professionally towards your peers in the quantum programming community and more broadly, you can help to make sure that your efforts build the best and most welcoming community possible.</span></span>

<span data-ttu-id="31c22-113">Bu çabanın bir parçası olarak, tüm Quantum Development Kit projelerinde [Microsoft Açık Kaynak Davranış Kuralları](https://opensource.microsoft.com/codeofconduct/) benimsenmiştir.</span><span class="sxs-lookup"><span data-stu-id="31c22-113">As a part of that effort, all Quantum Development Kit projects have adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/).</span></span>
<span data-ttu-id="31c22-114">Daha fazla bilgi için lütfen [Davranış Kuralları Hakkında SSS](https://opensource.microsoft.com/codeofconduct/faq/) konusuna bakın veya sorularınızı ya da görüşlerinizi bildirmek için [opencode@microsoft.com](mailto:opencode@microsoft.com) ile iletişime geçin.</span><span class="sxs-lookup"><span data-stu-id="31c22-114">For more information, please see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.</span></span>

## <a name="what-kinds-of-contributions-help-the-community"></a><span data-ttu-id="31c22-115">Ne Tür Katkılar Topluluğa Yardımcı Olur?</span><span class="sxs-lookup"><span data-stu-id="31c22-115">What Kinds of Contributions Help the Community?</span></span>

<span data-ttu-id="31c22-116">Katkılarınızla kuantum programlama topluluğuna yardımcı olmanın birçok farklı yolu vardır.</span><span class="sxs-lookup"><span data-stu-id="31c22-116">There are lots of different ways to help the quantum programming community through your contributions.</span></span>
<span data-ttu-id="31c22-117">Bu kılavuzda özellikle Kuantum Geliştirme Kiti ile ilgili olan üç yönteme odaklanacağız.</span><span class="sxs-lookup"><span data-stu-id="31c22-117">In this guide, we'll focus on three ways that are especially relevant to the Quantum Development Kit.</span></span>
<span data-ttu-id="31c22-118">Bu yöntemlerin hepsi, kullanıcıları güçlendiren bir kuantum topluluğu inşa etmek için çok önemlidir.</span><span class="sxs-lookup"><span data-stu-id="31c22-118">All of these ways are critical to building a quantum community that empowers people.</span></span>
<span data-ttu-id="31c22-119">Bununla birlikte, bu kesinlikle kapsamlı bir liste değildir. Topluluğun kuantum programlama taahhüdüyle gelişmesine yardımcı olacak başka yollar da keşfetmenizi öneririz!</span><span class="sxs-lookup"><span data-stu-id="31c22-119">That said, this is definitely not an exhaustive list — we encourage you to explore other ways to help the community build on the promise of quantum programming!</span></span>

- <span data-ttu-id="31c22-120">**Hataları raporlama.**</span><span class="sxs-lookup"><span data-stu-id="31c22-120">**Reporting bugs.**</span></span> <span data-ttu-id="31c22-121">Hataları ve diğer türlü sorunları düzeltmenin birinci adımı, bunları belirlemektir.</span><span class="sxs-lookup"><span data-stu-id="31c22-121">The first step in fixing bugs and other kinds of problems is to identify them.</span></span> <span data-ttu-id="31c22-122">Quantum Development Kit’te bir hata bulduysanız bize bildirmeniz düzeltmemize ve kuantum programlama topluluğu için daha iyi bir araç seti haline getirmemize yardımcı olur.</span><span class="sxs-lookup"><span data-stu-id="31c22-122">If you've found a bug in the Quantum Development Kit, letting us know helps us fix it and make a better set of tools for the quantum programming community.</span></span>
- <span data-ttu-id="31c22-123">**Belgeleri iyileştirme.**</span><span class="sxs-lookup"><span data-stu-id="31c22-123">**Improving documentation.**</span></span> <span data-ttu-id="31c22-124">Bir belge kümesi her zaman daha iyi olabilir, daha fazla ayrıntıyı kapsayabilir ve daha erişilebilir hale getirilebilir.</span><span class="sxs-lookup"><span data-stu-id="31c22-124">Any documentation set can always be better, can cover more details, be made more accessible.</span></span>
- <span data-ttu-id="31c22-125">**Koda katkıda bulunma.**</span><span class="sxs-lookup"><span data-stu-id="31c22-125">**Contributing code.**</span></span> <span data-ttu-id="31c22-126">Elbette, katkıda bulunmak için en dolaysız yollardan biri Quantum Development Kit’e yeni kod eklemektir.</span><span class="sxs-lookup"><span data-stu-id="31c22-126">Of course, one of the most direct ways to contribute is by adding new code to the Quantum Development Kit.</span></span>

<span data-ttu-id="31c22-127">Bu farklı türdeki katkıların tümü çok değerlidir ve çok faydalı olacaktır.</span><span class="sxs-lookup"><span data-stu-id="31c22-127">These different kinds of contributions are all immensely valuable, and are greatly appreciated.</span></span>
<span data-ttu-id="31c22-128">Kılavuzun geri kalanında her bir katkı türü hakkında öneriler sunacağız.</span><span class="sxs-lookup"><span data-stu-id="31c22-128">In the rest of the guide, we'll offer advice on how to make each kind of contribution.</span></span>

## <a name="where-do-contributions-go"></a><span data-ttu-id="31c22-129">Katkıları Nereye Gidiyor?</span><span class="sxs-lookup"><span data-stu-id="31c22-129">Where Do Contributions Go?</span></span>

<span data-ttu-id="31c22-130">Quantum Development Kit, kuantum programları yazmaya yönelik bir platformu hayata geçirmek için hepsi birlikte çalışan birkaç farklı unsurdan oluşur.</span><span class="sxs-lookup"><span data-stu-id="31c22-130">The Quantum Development Kit includes a number of different pieces that all work together to realize a platform for writing quantum programs.</span></span>
<span data-ttu-id="31c22-131">Bu farklı parçaların her birinin ana unsuru farklı bir depoda bulunur; bu nedenle, ilk önce her katkının nereye ait olduğunu çözmek gerekir.</span><span class="sxs-lookup"><span data-stu-id="31c22-131">Each of these different pieces finds its home on a different repository, so the one of the earlier things to sort out is where each contribution best belongs.</span></span>

- <span data-ttu-id="31c22-132">[**microsoft/Quantum**](https://github.com/Microsoft/Quantum): Quantum Development Kit’i kullanmaya başlamanıza yardımcı olacak örnekler ve araçlar.</span><span class="sxs-lookup"><span data-stu-id="31c22-132">[**microsoft/Quantum**](https://github.com/Microsoft/Quantum): Samples and tools to help get started with the Quantum Development Kit.</span></span>
- <span data-ttu-id="31c22-133">[**microsoft/QuantumLibraries**](https://github.com/Microsoft/QuantumLibraries): Quantum Development Kit için standart ve etki alanına özel kitaplıklar.</span><span class="sxs-lookup"><span data-stu-id="31c22-133">[**microsoft/QuantumLibraries**](https://github.com/Microsoft/QuantumLibraries): Standard and domain-specific libraries for the Quantum Development Kit.</span></span>
- <span data-ttu-id="31c22-134">[**microsoft/QuantumKatas**](https://github.com/Microsoft/QuantumKatas): Kuantum bilişimini ve Q# programlama dilini öğrenmeye yönelik, kendi hızınızda ilerleyebileceğiniz programlama alıştırmaları.</span><span class="sxs-lookup"><span data-stu-id="31c22-134">[**microsoft/QuantumKatas**](https://github.com/Microsoft/QuantumKatas): Self-paced programming exercises for learning quantum computing and the Q# programming language.</span></span>
- <span data-ttu-id="31c22-135">[**microsoft/qsharp-compiler**](https://github.com/microsoft/qsharp-compiler): Q# derleyicisi, Visual Studio uzantısı ve Visual Studio Code uzantısı.</span><span class="sxs-lookup"><span data-stu-id="31c22-135">[**microsoft/qsharp-compiler**](https://github.com/microsoft/qsharp-compiler): The Q# compiler, Visual Studio extension, and Visual Studio Code extension.</span></span>
- <span data-ttu-id="31c22-136">[**microsoft/qsharp-runtime**](https://github.com/microsoft/qsharp-runtime): Quantum Development Kit için simülasyon çerçevesi, kod oluşturma ve simülasyon hedef makineleri.</span><span class="sxs-lookup"><span data-stu-id="31c22-136">[**microsoft/qsharp-runtime**](https://github.com/microsoft/qsharp-runtime): Simulation framework, code generation, and simulation target machines for the Quantum Development Kit.</span></span>
- <span data-ttu-id="31c22-137">[**microsoft/iqsharp**](https://github.com/microsoft/iqsharp): Q# için Jupyter çekirdeği ve Python konak işlevinin yanı sıra bulut ortamlarında IQ# kullanmak için Docker görüntüleri.</span><span class="sxs-lookup"><span data-stu-id="31c22-137">[**microsoft/iqsharp**](https://github.com/microsoft/iqsharp): Jupyter kernel and Python host functionality for Q#, as well as Docker images for using IQ# in cloud environments.</span></span>
- <span data-ttu-id="31c22-138">[**MicrosoftDocs/quantum-docs-pr**](https://github.com/MicrosoftDocs/quantum-docs-pr): https://docs.microsoft.com/quantum adresinde yayımlanan belgeler için kaynak kodu.</span><span class="sxs-lookup"><span data-stu-id="31c22-138">[**MicrosoftDocs/quantum-docs-pr**](https://github.com/MicrosoftDocs/quantum-docs-pr): Source code for the documentation published at https://docs.microsoft.com/quantum.</span></span>

> [!NOTE]
> <span data-ttu-id="31c22-139">Şu anda [**microsoft/Quantum-NC**](https://github.com/microsoft/Quantum-NC) deposunda ne yazık ki kod ve belge katkılarını kabul edemiyoruz ancak hata raporlarını hala memnuniyetle karşılıyoruz.</span><span class="sxs-lookup"><span data-stu-id="31c22-139">We unfortunately cannot accept code and documentation contributions on the [**microsoft/Quantum-NC**](https://github.com/microsoft/Quantum-NC) repository at this time, but we still very much appreciate bug reports.</span></span>

<span data-ttu-id="31c22-140">Ayrıca, Quantum geliştirme seti ile ilgili yardımcı işlevlere odaklanan daha ileri düzeyde özelleşmiş birkaç depo daha mevcuttur.</span><span class="sxs-lookup"><span data-stu-id="31c22-140">There are also a few other, more specialized repositories focusing on auxiliary functionality related to the Quantum Development Kit.</span></span>

- <span data-ttu-id="31c22-141">[**msr-quarc/qsharp.sty**](https://github.com/msr-quarc/qsharp.sty): Q# söz dizimi için LaTeX biçimlendirme desteği.</span><span class="sxs-lookup"><span data-stu-id="31c22-141">[**msr-quarc/qsharp.sty**](https://github.com/msr-quarc/qsharp.sty): LaTeX formatting support for Q# syntax.</span></span>

## <a name="next-steps"></a><span data-ttu-id="31c22-142">Sonraki adımlar</span><span class="sxs-lookup"><span data-stu-id="31c22-142">Next steps</span></span>

<span data-ttu-id="31c22-143">Quantum Development Kit topluluğunun bir parçası olduğunuz için teşekkür ederiz. Katkılarınızı heyecanla bekliyoruz!</span><span class="sxs-lookup"><span data-stu-id="31c22-143">Thanks for being a part of the Quantum Development Kit community, we're excited for your contributions!</span></span>
<span data-ttu-id="31c22-144">Katkıda bulunma hakkında daha fazla bilgi edinmek istiyorsanız lütfen aşağıdaki kılavuzlardan biriyle devam edin.</span><span class="sxs-lookup"><span data-stu-id="31c22-144">If you'd like to learn more about contributing, please continue with one of the following guides.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="31c22-145">Hataları nasıl bildireceğinizi öğrenin</span><span class="sxs-lookup"><span data-stu-id="31c22-145">Learn how to report bugs</span></span>](xref:microsoft.quantum.contributing.reporting)

> [!div class="nextstepaction"]
> [<span data-ttu-id="31c22-146">Belgelere nasıl katkıda bulunabileceğinizi öğrenin</span><span class="sxs-lookup"><span data-stu-id="31c22-146">Learn how to contribute documentation</span></span>](xref:microsoft.quantum.contributing.docs)

> [!div class="nextstepaction"]
> [<span data-ttu-id="31c22-147">Çekme isteklerini nasıl açabileceğinizi öğrenin</span><span class="sxs-lookup"><span data-stu-id="31c22-147">Learn how to open pull requests</span></span>](xref:microsoft.quantum.contributing.pulls)
