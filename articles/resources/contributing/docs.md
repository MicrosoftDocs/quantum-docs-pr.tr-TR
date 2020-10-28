---
title: Microsoft QDK 'ye katkıda bulunan belgeler
description: Kavramsal veya API içeriğinin Microsoft hisse belgesi kümesine nasıl katkıda bulunabileceğinizi öğrenin.
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.docs
no-loc:
- ':::no-loc(Q#):::'
- ':::no-loc($$v):::'
ms.openlocfilehash: 2debef858c38b9a8f11264858130ed7cb41543ae
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691789"
---
# <a name="improving-documentation"></a><span data-ttu-id="16da1-103">İyileştirme Belgeleri</span><span class="sxs-lookup"><span data-stu-id="16da1-103">Improving Documentation</span></span>

<span data-ttu-id="16da1-104">Hisse geliştirme kiti için belgeler birçok farklı biçimde sürer. Bu bilgiler, bilgi almak için daha kolay kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="16da1-104">The documentation for the Quantum Development Kit takes on several different forms, such that information is readily available to quantum developers.</span></span>

<span data-ttu-id="16da1-105">[Belgeler kodu olarak, kod olarak](https://www.writethedocs.org/guide/docs-as-code/), tüm hisse Geliştirme Seti belgeleri kod olarak biçimlendirilir ve GIT kullanarak, hisse geliştirme setini oluşturmak için kullanılan kaynak kodla aynı şekilde yönetilir.</span><span class="sxs-lookup"><span data-stu-id="16da1-105">Following the principles of [Docs as Code](https://www.writethedocs.org/guide/docs-as-code/), all Quantum Development Kit documentation is formatted as code and is managed using Git in the same way as the source code that is used to build the Quantum Development Kit.</span></span>
<span data-ttu-id="16da1-106">Çoğu durumda, kod yedekleme belgelerinin çeşitli [markı](https://daringfireball.net/projects/markdown/)biçimlerinden biri, zengin biçimli bir metnin, komut satırında, Ides 'te ve kaynak denetimiyle birlikte kullanılması kolay bir düz metin biçiminde yazılmasına yönelik bir dildir.</span><span class="sxs-lookup"><span data-stu-id="16da1-106">For the most part, the code backing documentation consists of various forms of [Markdown](https://daringfireball.net/projects/markdown/), a language for writing out richly formatted text in a plain text format that's easy to use at the command line, in IDEs, and with source control.</span></span>
<span data-ttu-id="16da1-107">Benzer şekilde, aşağıda açıklandığı gibi LaTeX dilini kullanarak belgelerde matematik olarak biçimlendirmeye izin vermek için [MathJax](https://www.mathjax.org/) kitaplığını benimseyin.</span><span class="sxs-lookup"><span data-stu-id="16da1-107">We similarly adopt the [MathJax](https://www.mathjax.org/) library to allow for formatting mathematics in documentation using the LaTeX language, as detailed further below.</span></span>


<span data-ttu-id="16da1-108">Bu şekilde, her belge formu ayrıntılarda biraz farklılık gösterir:</span><span class="sxs-lookup"><span data-stu-id="16da1-108">That said, each form of documentation does vary somewhat in the details:</span></span>

- <span data-ttu-id="16da1-109">**Kavramsal belgeler** , ' de yayımlanan bir makale https://docs.microsoft.com/quantum grubundan oluşur ve hisse kullanımı temellerini, değişim biçimleri için teknik belirtimlere göre anlatmaktadır.</span><span class="sxs-lookup"><span data-stu-id="16da1-109">The **conceptual documentation** consists of a set of articles that are published to https://docs.microsoft.com/quantum, and that describe everything from the basics of quantum computing to the technical specifications for interchange formats.</span></span> <span data-ttu-id="16da1-110">Bu makaleler, zengin belge kümeleri oluşturmak için kullanılan bir Markaşağı varyantı olan [Docfx-flavored markaşağı (DFM)](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html)dilinde yazılmıştır.</span><span class="sxs-lookup"><span data-stu-id="16da1-110">These articles are written in [DocFX-Flavored Markdown (DFM)](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html), a Markdown variant used for creating rich documentation sets.</span></span>
- <span data-ttu-id="16da1-111">**API başvurusu** , üzerinde yayınlanan her bir :::no-loc(Q#)::: işlev, işlem ve Kullanıcı tanımlı tür için bir sayfa kümesidir https://docs.microsoft.com/qsharp/api/ .</span><span class="sxs-lookup"><span data-stu-id="16da1-111">The **API reference** is a set of pages for each :::no-loc(Q#)::: function, operation, and user-defined type, published to https://docs.microsoft.com/qsharp/api/.</span></span> <span data-ttu-id="16da1-112">Bu sayfalar, her çağrılabilir girdi ve işlemi örneklerle birlikte ve daha fazla bilgi için bağlantıları belgeleyin.</span><span class="sxs-lookup"><span data-stu-id="16da1-112">These pages document the inputs and operations to each callable, along with examples and links to more information.</span></span> <span data-ttu-id="16da1-113">API başvurusu, :::no-loc(Q#)::: her sürümün parçası olarak kaynak kodundaki küçük DFM belgelerinden otomatik olarak ayıklanır.</span><span class="sxs-lookup"><span data-stu-id="16da1-113">The API reference is automatically extracted from small DFM documents in :::no-loc(Q#)::: source code as a part of each release.</span></span>
- <span data-ttu-id="16da1-114">Her örnekle birlikte bulunan **README <!----> . MD** dosyaları ve küta, bu örnek veya Kütin nasıl kullanıldığını, ne kapsadığını ve hisse geliştirme setinin geri kalanı ile ilişkisini açıklamaktadır.</span><span class="sxs-lookup"><span data-stu-id="16da1-114">The **README<!---->.md** files included with each sample and kata describe how to use that sample or kata is used, what it covers, and how it relates to the rest of the Quantum Development Kit.</span></span> <span data-ttu-id="16da1-115">Bu dosyalar [GitHub flavored Markaşağı (GFM)](https://github.github.com/gfm/)kullanılarak yazılır. Bu, DFM 'in doğrudan kod depolarına belge iliştirmek için popüler bir alternatiftir.</span><span class="sxs-lookup"><span data-stu-id="16da1-115">These files are written using [GitHub Flavored Markdown (GFM)](https://github.github.com/gfm/), a more lightweight alternative to DFM that's popular for attaching documentation directly to code repositories.</span></span>

## <a name="contributing-to-the-conceptual-documentation"></a><span data-ttu-id="16da1-116">Kavramsal belgelere katkıda bulunma</span><span class="sxs-lookup"><span data-stu-id="16da1-116">Contributing to the Conceptual Documentation</span></span>

<span data-ttu-id="16da1-117">Kavramsal veya BENIOKU belgelerine bir iyileştirmeden katkıda bulunmak için, uygun olduğu gibi, Microsoft [**docs/hisse-docs-PR**](https://github.com/MicrosoftDocs/quantum-docs-pr/
), [**Microsoft/hisse**](https://github.com/Microsoft/Quantum)ya da [**Microsoft/niceleykatas**](https://github.com/Microsoft/QuantumKatas)üzerinde bir çekme isteğiyle başlar.</span><span class="sxs-lookup"><span data-stu-id="16da1-117">To contribute an improvement to the conceptual or README documentation, then, starts with a pull request onto either [**MicrosoftDocs/quantum-docs-pr**](https://github.com/MicrosoftDocs/quantum-docs-pr/
), [**Microsoft/Quantum**](https://github.com/Microsoft/Quantum), or [**Microsoft/QuantumKatas**](https://github.com/Microsoft/QuantumKatas), as is appropriate.</span></span>
<span data-ttu-id="16da1-118">Aşağıdaki çekme istekleri hakkında daha fazla bilgi edineceksiniz, ancak şimdilik belgeleri geliştirmekte olduğu gibi göz önünde bulundurmanız gereken birkaç nokta vardır:</span><span class="sxs-lookup"><span data-stu-id="16da1-118">We'll describe more about pull requests below, but for now there's a few things that are good to keep in mind as you improve documentation:</span></span>

- <span data-ttu-id="16da1-119">Okuyucular, çok geniş bir arka plan yelpazızdaki hisse geliştirme seti belgelerine gelir.</span><span class="sxs-lookup"><span data-stu-id="16da1-119">Readers come to the Quantum Development Kit documentation from a very wide range of backgrounds.</span></span> <span data-ttu-id="16da1-120">Yüksek okul öğrencilerine ait herkes, geçirmiş fakülte yeni ve heyecan verici bir şey öğrenmek isteyen herkesin, belgeleri okumaktan bir şeyi alabilmesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="16da1-120">Everyone from high school students looking to learn something new and exciting through to tenured faculty performing quantum computing research should be able to get something out of reading the documentation.</span></span> <span data-ttu-id="16da1-121">Mümkün olduğunca fazla bilgi sahibi olmak için lütfen okuyucularınızın parçası hakkında kapsamlı bilgiler kullanmayın. Daha fazla bilgi için, açık ve erişilebilir açıklamalar sağlayabilmeniz veya diğer kaynakların bağlantılarını sağlayabilmeniz çok yararlı olur.</span><span class="sxs-lookup"><span data-stu-id="16da1-121">To the extent that's possible, please don't assume extensive knowledge on the part of your readers, as they may just be starting out. It's most helpful if you can provide clear and accessible descriptions, or can provide links to other resources for more information.</span></span>
- <span data-ttu-id="16da1-122">Belge kümeleri kitap veya kağıtlar gibi düzenlenmez, bu da okuyucular "Orta" gibi görünse de ulaşacaktır.</span><span class="sxs-lookup"><span data-stu-id="16da1-122">Documentation sets aren't laid out like books or papers, in that readers will arrive in what might seem like the "middle."</span></span> <span data-ttu-id="16da1-123">Örneğin, arama motorları Dizin önermeyebilir veya yardım almaya çalışan bir arkadaşınız tarafından bir bağlantı göndermiş olabilirler. Uygun yerlerde olan bağlantılarla birlikte her zaman açık bir bağlam sunarak okuyucunuzun yardımına yardımcı olmaya çalışın.</span><span class="sxs-lookup"><span data-stu-id="16da1-123">For example, search engines might not suggest the index, or they might have been sent a link by a friend trying to help them out. Try to help your reader by always providing a clear context, along with links where appropriate.</span></span>
- <span data-ttu-id="16da1-124">Bazı okuyucular Özet deyimler ve tanımları en yararlı bulurken, diğer okuyucular somut örneklerden yararlanarak en iyi şekilde çalışır.</span><span class="sxs-lookup"><span data-stu-id="16da1-124">Some readers will find abstract statements and definitions most helpful, while other readers work best by extrapolating from concrete examples.</span></span> <span data-ttu-id="16da1-125">Hem genel durumun hem de belirli örneklerin sağlanması, her iki okuyucunun de en fazla hisse programlamayla programlama sağlanmasına yardımcı olabilir.</span><span class="sxs-lookup"><span data-stu-id="16da1-125">Providing both the general case and specific examples can help both readers get the most out of quantum programming.</span></span>
- <span data-ttu-id="16da1-126">Özellikle de belgelenmekte olan kodu de yazmış olmanız durumunda, okuyucunuz için hiç açık olmayan bir şey sizin için açık olabilir.</span><span class="sxs-lookup"><span data-stu-id="16da1-126">Especially if you also wrote the code being documented, things may be obvious to you that are not at all obvious to your reader.</span></span> <span data-ttu-id="16da1-127">Programınızın en iyi bir en iyi yolu yoktur; bu nedenle, bir okuyucunun ne kadar süden olduğunu veya öğrendiğine bakılmaksızın, fikirlerinizi kodda ifade etmek için en yararlı bulduğunuz tasarım modellerini tahmin edemeyebilir.</span><span class="sxs-lookup"><span data-stu-id="16da1-127">There's no one unique best way to program, so no matter how clever or experienced a reader might be, they can't guess at what design patterns you found the most helpful to express your ideas in code.</span></span> <span data-ttu-id="16da1-128">Bir okuyucunun kodunuzun kullanımını nasıl beklediğini öğrenmek, bu bağlamın sağlanmasına yardımcı olabilir.</span><span class="sxs-lookup"><span data-stu-id="16da1-128">Being clear about how a reader can expect to make use of your code can help provide that context.</span></span>
- <span data-ttu-id="16da1-129">Hisse programlama topluluğunun birçok üyesi akademik araştırmacılar ve temel olarak topluluk katkılarına yönelik alıntılar aracılığıyla tanınır.</span><span class="sxs-lookup"><span data-stu-id="16da1-129">Many members of the quantum programming community are academic researchers, and are recognized mainly through citations for their contributions to the community.</span></span> <span data-ttu-id="16da1-130">Okuyucuların ek malzemeler bulmasına yardımcı olmaya ek olarak, incelemeler, Talks, blog gönderileri ve yazılım araçları gibi akademik çıkışları doğru bir şekilde ayırarak, akademik katkıların topluluğu geliştirmek için en iyi işleri yapmasına yardımcı olabilir.</span><span class="sxs-lookup"><span data-stu-id="16da1-130">In addition to helping readers find additional materials, making sure to properly cite academic outputs such as papers, talks, blog posts, and software tools can help academic contributors to keep doing their best work to improve the community.</span></span>
- <span data-ttu-id="16da1-131">Hisse programlama topluluğu, geniş ve wonderfully farklı bir topluluktur.</span><span class="sxs-lookup"><span data-stu-id="16da1-131">The quantum programming community is a broad and wonderfully diverse community.</span></span> <span data-ttu-id="16da1-132">Üçüncü kişi örneklerinde genimli zamirler kullanımı (örn...................................</span><span class="sxs-lookup"><span data-stu-id="16da1-132">The use of gendered pronouns in third-person examples (e.g.: "if a user ..., he will ...") can work to exclude rather than include.</span></span> <span data-ttu-id="16da1-133">Kişilerin alıntılar ve bağlantılarla ilgili adlarını bilmekte ve ASCII olmayan karakterlerin doğru eklenmesi, üyelerinin üyelerine göre, topluluk çeşitliliğine hizmet verebilir.</span><span class="sxs-lookup"><span data-stu-id="16da1-133">Being cognizant of people's names in citations and links, and of the correct inclusion of non-ASCII characters can serve the diversity of the community by showing respect to its members.</span></span> <span data-ttu-id="16da1-134">Benzer şekilde, Ingilizce dilde pek çok sözcük genellikle bir şekilde kullanılır. bu şekilde, teknik belgelerde kullanımları hem bireysel okuyucular hem de topluluk için büyük ölçekli bir zarar oluşmasına neden olabilir.</span><span class="sxs-lookup"><span data-stu-id="16da1-134">Similarly, many words in the English language are often used in a hateful manner, such that their use in technical documentation can cause harm both to individual readers and to the community at large.</span></span>

### <a name="referencing-sample-code-from-conceptual-articles"></a><span data-ttu-id="16da1-135">Kavramsal makalelerden örnek koda başvurma</span><span class="sxs-lookup"><span data-stu-id="16da1-135">Referencing Sample Code from Conceptual Articles</span></span>

<span data-ttu-id="16da1-136">[Örnek deposundan](https://github.com/Microsoft/Quantum)kod eklemek istiyorsanız, özel bir DocFX-Flavored Marku komutu kullanarak bunu yapabilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="16da1-136">If you want to include code from the [samples repository](https://github.com/Microsoft/Quantum), you can do so using a special DocFX-Flavored Markdown command:</span></span>

```markdown
:::code language="qsharp" source="~/quantum/samples/algorithms/chsh-game/Game.qs" range="4-8":::
```

<span data-ttu-id="16da1-137">Bu komut, [ `Game.qs` dosyadaki `chsh-game` ](https://github.com/microsoft/Quantum/blob/main/samples/algorithms/chsh-game/Game.qs)4 ' e kadar olan satırları, :::no-loc(Q#)::: söz dizimi vurgulamanın amacı için kod olarak işaretleyerek, örnekten içeri aktarır.</span><span class="sxs-lookup"><span data-stu-id="16da1-137">This command will import lines 4 to 8 of the [`Game.qs` file from the `chsh-game` sample](https://github.com/microsoft/Quantum/blob/main/samples/algorithms/chsh-game/Game.qs), marking them as :::no-loc(Q#)::: code for the purpose of syntax highlighting.</span></span>
<span data-ttu-id="16da1-138">Bu komutu kullanarak, kavramsal makaleler ve örnekler deposu arasında kodu çoğaltmaktan kaçınabilirsiniz. böylece, belgelerde örnek kod her zaman mümkün olduğunca güncel olur.</span><span class="sxs-lookup"><span data-stu-id="16da1-138">Using this command, you can avoid duplicating code between conceptual articles and the samples repository, so that sample code in documentation is always as up to date as possible.</span></span>

## <a name="contributing-to-the-api-references"></a><span data-ttu-id="16da1-139">API başvurularına katkıda bulunma</span><span class="sxs-lookup"><span data-stu-id="16da1-139">Contributing to the API References</span></span>

<span data-ttu-id="16da1-140">API başvurularına bir iyileştirmeden katkıda bulunmak için, bir çekme isteğini doğrudan belgelenmiş kodda açmak çok faydalı olur.</span><span class="sxs-lookup"><span data-stu-id="16da1-140">To contribute an improvement to the API references, it's most helpful to open a pull request directly on the code being documented.</span></span>
<span data-ttu-id="16da1-141">Her işlev, işlem veya Kullanıcı tanımlı tür bir belge açıklamasını destekler (yerine ile gösterilir `///` `//` ).</span><span class="sxs-lookup"><span data-stu-id="16da1-141">Each function, operation, or user-defined type supports a documentation comment (denoted with `///` instead of `//`).</span></span>
<span data-ttu-id="16da1-142">Hisse geliştirme setinin her bir sürümünü derliyoruz. bu yorumlar, https://docs.microsoft.com/qsharp/api/ her çağrılabilir giriş ve çıkışları, her çağrılabilir şekilde yaptığı varsayımlar ve bunların nasıl kullanılacağına ilişkin ayrıntılar dahil olmak üzere ' de API başvurusunu oluşturmak için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="16da1-142">When we compile each release of the Quantum Development Kit, these comments are used to generate the API reference at https://docs.microsoft.com/qsharp/api/, including details about the inputs to and outputs from each callable, the assumptions each callable makes, and examples of how to use them.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="16da1-143">Lütfen oluşturulan API belgelerini el ile düzenlemediğinizden emin olun. Bu dosyalar her yeni sürümde üzerine yazılır.</span><span class="sxs-lookup"><span data-stu-id="16da1-143">Please make sure to not manually edit the generated API documentation, as these files are overwritten with each new release.</span></span>
> <span data-ttu-id="16da1-144">Topluluğa katkılarınız için değer veriyoruz ve kullanıcıların sürümden sonra serbest olmasına yardımcı olmaya devam etmesini sağlamak istiyorsunuz.</span><span class="sxs-lookup"><span data-stu-id="16da1-144">We value your contribution to the community, and want to make sure that your changes continue to help users release after release.</span></span>

<span data-ttu-id="16da1-145">Örneğin, işlevini düşünün `ControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="16da1-145">For example, consider the function `ControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="16da1-146">Bir belge yorumu, bir kullanıcının nasıl yorumlayacağını `bits` ve işlevin ne olduğunu öğreni konusunda bilgi edinmelidir `oracle` .</span><span class="sxs-lookup"><span data-stu-id="16da1-146">A documentation comment should help a user learn how to interpret `bits` and `oracle` and what the function is for.</span></span>
<span data-ttu-id="16da1-147">Bu farklı bilgi parçalarının her biri, :::no-loc(Q#)::: belge açıklamasında özel olarak adlandırılmış bir Markaşağı bölümü tarafından derleyiciye alınabilir.</span><span class="sxs-lookup"><span data-stu-id="16da1-147">Each of these different pieces of information can be provided to the :::no-loc(Q#)::: compiler by a specially named Markdown section in the documentation comment.</span></span>
<span data-ttu-id="16da1-148">Örneği için aşağıdakine `ControlledOnBitString` benzer bir şey yazabiliriz:</span><span class="sxs-lookup"><span data-stu-id="16da1-148">For the example of `ControlledOnBitString`, we might write something like the following:</span></span>

```qsharp
 /// # Summary
 /// Returns a unitary operation that applies an oracle on the target register if the 
 /// control register state corresponds to a specified bit mask.
 ///
 /// # Description
 /// The output of this function is an operation that can be represented by a
 /// unitary transformation $U$ such that
 /// \begin{align}
 ///     U \ket{b_0 b_1 \cdots b_{n - 1}} \ket{\psi} = \ket{b_0 b_1 \cdots b_{n-1}} \otimes
 ///     \begin{cases}
 ///         V \ket{\psi} & \textrm{if} (b_0 b_1 \cdots b_{n - 1}) = \texttt{bits} \\\\
 ///         \ket{\psi} & \textrm{otherwise}
 ///     \end{cases},
 /// \end{align}
 /// where $V$ is a unitary transformation that represents the action of the
 /// `oracle` operation.
 ///
 /// # Input
 /// ## bits
 /// The bit string to control the given unitary operation on.
 /// ## oracle
 /// The unitary operation to be applied on the target register.
 ///
 /// # Output
 /// A unitary operation that applies `oracle` on the target register if the control 
 /// register state corresponds to the bit mask `bits`.
 ///
 /// # Remarks
 /// The length of `bits` and `controlRegister` must be equal.
 ///
 /// Given a Boolean array `bits` and a unitary operation `oracle`, the output of this function
 /// is an operation that performs the following steps:
 /// * apply an `X` operation to each qubit of the control register that corresponds to `false` 
 /// element of the `bits`;
 /// * apply `Controlled oracle` to the control and target registers;
 /// * apply an `X` operation to each qubit of the control register that corresponds to `false` 
 /// element of the `bits` again to return the control register to the original state.
 ///
 /// The output of the `Controlled` functor is a special case of `ControlledOnBitString` where `bits` is equal to `[true, ..., true]`.
 ///
 /// # Example
 /// The following code snippets are equivalent:
 /// ```qsharp
 /// (ControlledOnBitString(bits, oracle))(controlRegister, targetRegister);
 /// ```
 /// and
 /// ```qsharp
 /// within {
 ///     ApplyPauliFromBitString(PauliX, false, bits, controlRegister);
 /// } apply {
 ///     Controlled oracle(controlRegister, targetRegister);
 /// }
 /// ```
 ///
 /// The following code prepares a state $\frac{1}{2}(\ket{00} - \ket{01} + \ket{10} + \ket{11})$:
 /// ```qsharp
 /// using (register = Qubit[2]) {
 ///     ApplyToEach(H, register);
 ///     (ControlledOnBitString([false], Z))(register[0..0], register[1]);
 /// }
 /// ```
 function ControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)
 {
     return ControlledOnBitStringImpl(bits, oracle, _, _);
 }
```

<span data-ttu-id="16da1-149">Yukarıdaki kodun işlenmiş sürümünü, [ `ControlledOnBitString` işlevin API belgelerinde](xref:Microsoft.Quantum.Canon.ControlledOnBitString)görebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="16da1-149">You can see the rendered version of the code above in the [API documentation for the `ControlledOnBitString` function](xref:Microsoft.Quantum.Canon.ControlledOnBitString).</span></span>

<span data-ttu-id="16da1-150">Belge yazma hakkında genel olarak, API belge açıklamalarını yazma bölümünde birkaç şeyi aklınızda tutmaya yardımcı olur:</span><span class="sxs-lookup"><span data-stu-id="16da1-150">In addition to the general practice of documentation writing, in writing API documentation comments it helps to keep a few things in mind:</span></span>

- <span data-ttu-id="16da1-151">Her belge açıklamasının biçimi, :::no-loc(Q#)::: derleyicinin belgelerinize doğru görünmesini beklediklerini eşleştirmek için sahiptir.</span><span class="sxs-lookup"><span data-stu-id="16da1-151">The format of each documentation comment has to match what the :::no-loc(Q#)::: compiler expects for your documentation to appear correctly.</span></span> <span data-ttu-id="16da1-152">`/// # Remarks`Bölüm gibi bölümler daha kısıtlayıcı olsa da, serbest biçimli içeriğe izin ver gibi bazı bölümler `/// # See Also` .</span><span class="sxs-lookup"><span data-stu-id="16da1-152">Some sections, such as `/// # Remarks` allow for freeform content, while sections such as `/// # See Also` section are more restrictive.</span></span>
- <span data-ttu-id="16da1-153">Bir okuyucu, API belgelerinizi ana API başvuru sitesinde, her bir ad alanının özetinde veya hatta, üzerine gelme bilgilerini kullanarak IDE içinden okuyabilir.</span><span class="sxs-lookup"><span data-stu-id="16da1-153">A reader may read your API documentation on the main API reference site, on the summary for each namespace, or even from within their IDE through the use of hover information.</span></span> <span data-ttu-id="16da1-154">`/// # Summary`Bunun yaklaşık bir cümle olduğundan emin olmak, okuyucunun daha fazla okuma yapmak veya başka bir yere bakmak gerekip gerekmediğini hızlı bir şekilde izlemesine yardımcı olur ve ad alanı özetleri aracılığıyla hızla tarama yapmaya yardımcı olabilir.</span><span class="sxs-lookup"><span data-stu-id="16da1-154">Making sure that `/// # Summary` isn't longer than about a sentence helps your reader quickly sort out whether they need to read further or look elsewhere, and can help in quickly scanning through namespace summaries.</span></span>
- <span data-ttu-id="16da1-155">Belgeleriniz kodun kendisinden çok daha uzun bir süre daha fazla olabilir, ancak bu tamam!</span><span class="sxs-lookup"><span data-stu-id="16da1-155">Your documentation may well wind up being much longer than the code itself, but that's OK!</span></span> <span data-ttu-id="16da1-156">Küçük bir kod parçası bile, bu kodun bulunduğu bağlamı bilmiyor olan kullanıcılar için beklenmeyen etkileri olabilir.</span><span class="sxs-lookup"><span data-stu-id="16da1-156">Even a small piece of code can have unexpected effects to users that don't know the context in which that code exists.</span></span> <span data-ttu-id="16da1-157">Somut örnekler ve açık açıklamalar sunarak kullanıcıların, kendileri için kullanılabilir olan kodun en iyi şekilde kullanılmasını sağlayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="16da1-157">By providing concrete examples and clear explanations, you can help users make the best use of the code that's available to them.</span></span>

<!-- ## LaTeX Formatting ##

**TODO** -->
