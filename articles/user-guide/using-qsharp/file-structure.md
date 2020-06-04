---
title: 'Q # dosya yapısı'
description: 'Bir Q # dosyasının yapısını ve sözdizimini açıklar.'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.filestructure
ms.openlocfilehash: b8c24dae6cc8d8f37ad4f1f74017c05cabe3a4b4
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/03/2020
ms.locfileid: "84327467"
---
# <a name="q-file-structure"></a><span data-ttu-id="51dea-103">Q # dosya yapısı</span><span class="sxs-lookup"><span data-stu-id="51dea-103">Q# File Structure</span></span>

<span data-ttu-id="51dea-104">Her Q # işlem, işlev ve Kullanıcı tanımlı tür bir ad alanı içinde tanımlanır.</span><span class="sxs-lookup"><span data-stu-id="51dea-104">Every Q# operation, function, and user-defined type is defined within a namespace.</span></span>

<span data-ttu-id="51dea-105">Bir Q # dosyası, bir dizi *ad alanı bildirimi*içerir.</span><span class="sxs-lookup"><span data-stu-id="51dea-105">A Q# file consists of a sequence of *namespace declarations*.</span></span>
<span data-ttu-id="51dea-106">Her ad alanı bildirimi, Kullanıcı tanımlı türler, işlemler ve işlevler için bildirimler içerir.</span><span class="sxs-lookup"><span data-stu-id="51dea-106">Each namespace declaration contains declarations for user-defined types, operations, and functions.</span></span>
<span data-ttu-id="51dea-107">Bir ad alanı bildirimi her bir tür bildirime ve herhangi bir sıraya sahip olabilir.</span><span class="sxs-lookup"><span data-stu-id="51dea-107">A namespace declaration may contain any number of each type of declaration, and in any order.</span></span>
<span data-ttu-id="51dea-108">Bir ad alanı içindeki [Kullanıcı tanımlı türler](xref:microsoft.quantum.guide.types#user-defined-types), [işlemler](xref:microsoft.quantum.guide.operationsfunctions#defining-new-operations)ve [işlevleri](xref:microsoft.quantum.guide.operationsfunctions#defining-new-functions) bildirme hakkında daha fazla bilgi için bu bağlantıları izleyin.</span><span class="sxs-lookup"><span data-stu-id="51dea-108">Follow these links for more details on declaring [user-defined types](xref:microsoft.quantum.guide.types#user-defined-types), [operations](xref:microsoft.quantum.guide.operationsfunctions#defining-new-operations), and [functions](xref:microsoft.quantum.guide.operationsfunctions#defining-new-functions) within a namespace.</span></span>

<span data-ttu-id="51dea-109">Bir ad alanı bildiriminin dışında görünebilen tek metin açıklamalardır.</span><span class="sxs-lookup"><span data-stu-id="51dea-109">The only text that can appear outside of a namespace declaration is comments.</span></span>
<span data-ttu-id="51dea-110">Özellikle, bildirim öncesinde bir ad alanı için belge açıklamaları (daha fazla ayrıntı).</span><span class="sxs-lookup"><span data-stu-id="51dea-110">In particular, documentation comments (more details below) for a namespace precede the declaration.</span></span>

## <a name="namespace-declarations"></a><span data-ttu-id="51dea-111">Ad alanı bildirimleri</span><span class="sxs-lookup"><span data-stu-id="51dea-111">Namespace Declarations</span></span>

<span data-ttu-id="51dea-112">Bir Q # dosyası genellikle tam olarak bir ad alanı bildirimine sahip olur, ancak None (ve boş veya yalnızca açıklama içeremez) olabilir veya birden çok ad alanı içerebilir.</span><span class="sxs-lookup"><span data-stu-id="51dea-112">A Q# file will typically have exactly one namespace declaration, but may have none (and be empty or just contain comments) or may contain multiple namespaces.</span></span>
<span data-ttu-id="51dea-113">Ad alanı bildirimleri iç içe olamaz.</span><span class="sxs-lookup"><span data-stu-id="51dea-113">Namespace declarations may not be nested.</span></span>

<span data-ttu-id="51dea-114">Aynı ad alanı, aynı ada sahip hiçbir tür, işlem veya işlev bildirimi olmadığı sürece birlikte derlenen birden fazla Q # dosyasında da bildirilemez.</span><span class="sxs-lookup"><span data-stu-id="51dea-114">The same namespace may be declared in multiple Q# files that are compiled together, as long as there are no type, operation, or function declarations with the same name.</span></span>
<span data-ttu-id="51dea-115">Özellikle, bildirimler özdeş olsa bile, birden çok dosyada aynı ad alanında aynı türü tanımlamak geçersizdir.</span><span class="sxs-lookup"><span data-stu-id="51dea-115">In particular, it is invalid to define the same type in the same namespace in multiple files, even if the declarations are identical.</span></span>

<span data-ttu-id="51dea-116">Bir ad alanı bildirimi, anahtar sözcüğünden `namespace` , ardından ad alanının adı, açık bir küme ayracı, `{` ad alanında yer alan bildirimler ve bir kapalı ayraç oluşur `}` .</span><span class="sxs-lookup"><span data-stu-id="51dea-116">A namespace declaration consists of the keyword `namespace`, followed by the name of the namespace, an open brace `{`, the declarations contained in the namespace, and a close brace `}`.</span></span>
<span data-ttu-id="51dea-117">Ad alanı adları, noktalarla ayrılmış bir veya daha fazla yasal sembol dizisinin .NET örüntüsünün izler `.` .</span><span class="sxs-lookup"><span data-stu-id="51dea-117">Namespace names follow the .NET pattern of a sequence of one or more legal symbols separated by periods `.`.</span></span>
<span data-ttu-id="51dea-118">Örneğin, `MyQuantumStuff` ve `Microsoft.Quantum.Intrinsic` geçerli ad alanı adlardır.</span><span class="sxs-lookup"><span data-stu-id="51dea-118">For instance, `MyQuantumStuff` and `Microsoft.Quantum.Intrinsic` are valid namespace names.</span></span>
<span data-ttu-id="51dea-119">Kurala göre, bir ad alanı adındaki semboller büyük harfli olur, ancak bu gerekli değildir.</span><span class="sxs-lookup"><span data-stu-id="51dea-119">By convention, the symbols in a namespace name are capitalized, but this is not required.</span></span>

<span data-ttu-id="51dea-120">Bir dosyada daha fazla bildirimde bulunan türlerin veya sabit labların başvuruları düzgün şekilde çözümlenir; bir başvurunun önüne geçmek için tür, işlem veya işlev bildirimine gerek yoktur.</span><span class="sxs-lookup"><span data-stu-id="51dea-120">References to types or callables declared further down in a file are resolved properly; there is no need for the type, operation, or function declaration to precede a reference to it.</span></span>

## <a name="open-directives"></a><span data-ttu-id="51dea-121">Açık yönergeler</span><span class="sxs-lookup"><span data-stu-id="51dea-121">Open Directives</span></span>

<span data-ttu-id="51dea-122">Bir ad alanı bloğunda, `open` yönerge, belirli bir ad alanında belirtilen tüm türleri ve callabları içeri aktarmak ve bunları nitelenmemiş adlarıyla ifade etmek için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="51dea-122">Within a namespace block, the `open` directive may be used to import all types and callables declared in a certain namespace and refer to them by their unqualified name.</span></span>
<span data-ttu-id="51dea-123">Bu tür bir `open` yönerge, `open` anahtar sözcüğünden, ardından açılacak ad alanı ve bir sona noktalı virgül içerir.</span><span class="sxs-lookup"><span data-stu-id="51dea-123">Such an `open` directive consists of the `open` keyword, followed by the namespace to be opened and a terminating semicolon.</span></span>

> [!NOTE] 
> <span data-ttu-id="51dea-124">Tüm `open` yönergeler `function` `operation` `newtype` ad alanı bloğunda, veya bildirimlerinden önce gelmelidir.</span><span class="sxs-lookup"><span data-stu-id="51dea-124">All `open` directives must appear before any `function`, `operation`, or `newtype` declarations in the namespace block.</span></span>

<span data-ttu-id="51dea-125">İsteğe bağlı olarak, açık ad alanı için bir kısa ad, bu ad alanındaki tüm öğelerin tanımlanmış kısa ad ile nitelendirilerek (ve gerek olması) tanımlanabilir.</span><span class="sxs-lookup"><span data-stu-id="51dea-125">Optionally, a short name for the opened namespace may be defined such that all elements from that namespace can (and need) to be qualified by the defined short name.</span></span> <span data-ttu-id="51dea-126">Örneğin, aşağıdaki ad alanı bildirimi ve açık yönergeler verildiğinde,</span><span class="sxs-lookup"><span data-stu-id="51dea-126">For example, given the following namespace declaration and open directives,</span></span>

```qsharp
namespace NS {
    open Microsoft.Quantum.Intrinsic; // opens the namespace
    open Microsoft.Quantum.Math as Math; // defines a short name for the namespace

    // operation, function, and newtype declarations

}
```

<span data-ttu-id="51dea-127">bildirdiğimiz bir işlem öğesinden bir işlem kullanıyorsa `Op` `Microsoft.Quantum.Intrinsic` , bunu yalnızca kullanarak çağıracağız `Op` .</span><span class="sxs-lookup"><span data-stu-id="51dea-127">if an operation we declare uses an operation `Op` from `Microsoft.Quantum.Intrinsic`, we would call it by simply using `Op`.</span></span>
<span data-ttu-id="51dea-128">Ancak, ' den belirli bir işlevi çağırmayı istiyorduk `Fn` `Microsoft.Quantum.Math` , kullanarak çağırırız `Math.Fn` .</span><span class="sxs-lookup"><span data-stu-id="51dea-128">However, if we wanted a call a certain function `Fn` from `Microsoft.Quantum.Math`, we would need to call it using `Math.Fn`.</span></span>

<span data-ttu-id="51dea-129">`open`Yönerge, bir dosya içindeki tüm ad alanı bloğunun tamamına uygulanır.</span><span class="sxs-lookup"><span data-stu-id="51dea-129">The `open` directive applies to the entire namespace block within a file.</span></span>
<span data-ttu-id="51dea-130">Bu nedenle, yukarıdaki aynı Q # dosyasında ek bir ad alanı tanımlıyoruz `NS` , ikinci ad alanında tanımlanan tüm işlemler/işlevler/türler, `Microsoft.Quantum.Intrinsic` `Microsoft.Quantum.Math` içindeki açık yönergeleri tekrarlamadığı sürece veya ' den herhangi bir şeye erişemez.</span><span class="sxs-lookup"><span data-stu-id="51dea-130">Hence, if we were to define an additional namespace in the same Q# file as `NS` above, then any operations/functions/types defined in the second namespace would not have access to anything from `Microsoft.Quantum.Intrinsic` or `Microsoft.Quantum.Math` unless we repeated the open directives therein.</span></span> 

<span data-ttu-id="51dea-131">Geçerli ad alanında açılmamış başka bir ad alanında tanımlanan bir tür veya *çağrılabilir, tam* nitelikli ad tarafından başvurulmalıdır.</span><span class="sxs-lookup"><span data-stu-id="51dea-131">A type or callable defined in another namespace that is *not* opened in the current namespace must be referenced by its fully-qualified name.</span></span>
<span data-ttu-id="51dea-132">Örneğin, ad alanı `Op` `X.Y` `X.Y.Op` `X.Y` geçerli blokta daha önce açılmamışsa, ad alanından adlı bir işleme tam nitelikli adıyla başvurulmalıdır.</span><span class="sxs-lookup"><span data-stu-id="51dea-132">For example, an operation named `Op` from the `X.Y` namespace must be referenced by its fully-qualified name `X.Y.Op`, unless the `X.Y` namespace has been opened earlier in the current block.</span></span> <span data-ttu-id="51dea-133">Yukarıda belirtildiği gibi, `X` ad alanı açılmış olsa da, işleme olarak başvurmak mümkün değildir `Y.Op` .</span><span class="sxs-lookup"><span data-stu-id="51dea-133">As mentioned above, even if the `X` namespace has been opened, it is not possible to reference the operation as `Y.Op`.</span></span>
<span data-ttu-id="51dea-134">İçin kısa bir ad `Z` `X.Y` , bu ad alanında ve dosyada tanımlanmışsa, `Op` olarak adlandırılmaları gerekir `Z.Op` .</span><span class="sxs-lookup"><span data-stu-id="51dea-134">If a short name `Z` for `X.Y` has been defined in that namespace and file, then `Op` needs to be referred to as `Z.Op`.</span></span> 

<span data-ttu-id="51dea-135">Bir yönergesi kullanarak bir ad alanı eklemek genellikle daha iyidir `open` .</span><span class="sxs-lookup"><span data-stu-id="51dea-135">It is usually better to include a namespace by using an `open` directive.</span></span>
<span data-ttu-id="51dea-136">İki ad alanı aynı ada sahip yapıları tanımladıysa ve geçerli kaynak yapıları her ikisiyle kullanıyorsa, tam nitelikli ad kullanılması gerekir.</span><span class="sxs-lookup"><span data-stu-id="51dea-136">Using a fully-qualified name is required if two namespaces define constructs with the same name, and the current source uses constructs from both.</span></span>

<span data-ttu-id="51dea-137">Q #, diğer .NET dilleri olarak adlandırmayla aynı kuralları izler.</span><span class="sxs-lookup"><span data-stu-id="51dea-137">Q# follows the same rules for naming as other .NET languages.</span></span>
<span data-ttu-id="51dea-138">Ancak, Q # ad alanlarına göreli başvuruları desteklemez.</span><span class="sxs-lookup"><span data-stu-id="51dea-138">However, Q# does not support relative references to namespaces.</span></span>
<span data-ttu-id="51dea-139">Diğer bir deyişle, ad alanı `a.b` açıldıysa, adlı bir işlem için bir başvuru, `c.d` tam ada *not* sahip bir işleme çözümlenmeyecektir `a.b.c.d` .</span><span class="sxs-lookup"><span data-stu-id="51dea-139">That is, if the namespace `a.b` has been opened, a reference to an operation named `c.d` will *not* be resolved to an operation with full name `a.b.c.d`.</span></span>

## <a name="formatting"></a><span data-ttu-id="51dea-140">Biçimlendirme</span><span class="sxs-lookup"><span data-stu-id="51dea-140">Formatting</span></span>

<span data-ttu-id="51dea-141">Çoğu Q # deyimi ve yönergeleri sonlandırma noktalı virgülle biter `;` .</span><span class="sxs-lookup"><span data-stu-id="51dea-141">Most Q# statements and directives end with a terminating semicolon, `;`.</span></span>
<span data-ttu-id="51dea-142">Ve gibi deyimler ve bildirimler `for` `operation` bir deyim bloğu (aşağıya bakın) ile biten bir bitiş noktalı virgül gerektirmez.</span><span class="sxs-lookup"><span data-stu-id="51dea-142">Statements and declarations such as `for` and `operation` that end with a statement block (see below) do not require a terminating semicolon.</span></span>
<span data-ttu-id="51dea-143">Her bir ifade açıklaması, Sonlandırıcı noktalı virgülden gerekli olup olmadığını not edin.</span><span class="sxs-lookup"><span data-stu-id="51dea-143">Each statement description notes whether the terminating semicolon is required.</span></span>

<span data-ttu-id="51dea-144">İfadeler, bildirimler ve yönergeler gibi deyimler birden çok satıra ayrılabilir.</span><span class="sxs-lookup"><span data-stu-id="51dea-144">Statements, like expressions, declarations, and directives, may be broken out across multiple lines.</span></span>
<span data-ttu-id="51dea-145">Tek bir satırda birden çok deyimin olması kaçınılmalıdır.</span><span class="sxs-lookup"><span data-stu-id="51dea-145">Having multiple statements on a single line should be avoided.</span></span>

## <a name="statement-blocks"></a><span data-ttu-id="51dea-146">Ekstre blokları</span><span class="sxs-lookup"><span data-stu-id="51dea-146">Statement Blocks</span></span>

<span data-ttu-id="51dea-147">Q # deyimleri deyim blokları halinde gruplandırılır.</span><span class="sxs-lookup"><span data-stu-id="51dea-147">Q# statements are grouped into statement blocks.</span></span>
<span data-ttu-id="51dea-148">Bir ifade bloğu bir açma ile başlar `{` ve kapanış ile biter `}` .</span><span class="sxs-lookup"><span data-stu-id="51dea-148">A statement block starts with an opening `{` and ends with a closing `}`.</span></span>

<span data-ttu-id="51dea-149">Başka bir blok içinde Sözcüksel olarak bulunan bir ifade bloğu, kapsayan bloğun bir alt bloğu olarak kabul edilir; içerilen ve alt bloklara dış ve iç bloklar de denir.</span><span class="sxs-lookup"><span data-stu-id="51dea-149">A statement block that is lexically enclosed within another block is considered to be a sub-block of the containing block; containing and sub-blocks are also called outer and inner blocks.</span></span>

## <a name="comments"></a><span data-ttu-id="51dea-150">Yorumlar</span><span class="sxs-lookup"><span data-stu-id="51dea-150">Comments</span></span>

<span data-ttu-id="51dea-151">Açıklamalar iki eğik çizgi ile başlar `//` ve satır sonuna kadar devam eder.</span><span class="sxs-lookup"><span data-stu-id="51dea-151">Comments begin with two forward slashes, `//`, and continue until the end of line.</span></span>
<span data-ttu-id="51dea-152">Bir soru, Q # kaynak dosyasında herhangi bir yerde görünebilir.</span><span class="sxs-lookup"><span data-stu-id="51dea-152">A comment may appear anywhere in a Q# source file.</span></span>

## <a name="documentation-comments"></a><span data-ttu-id="51dea-153">Belge Açıklamaları</span><span class="sxs-lookup"><span data-stu-id="51dea-153">Documentation Comments</span></span>

<span data-ttu-id="51dea-154">Üç eğik çizgi ile başlayan yorumlar, `///` bir ad alanı, işlem, özelleştirme, işlev veya tür tanımından hemen önce göründüğü zaman derleyici tarafından özellikle değerlendirilir.</span><span class="sxs-lookup"><span data-stu-id="51dea-154">Comments that begin with three forward slashes, `///`, are treated specially by the compiler when they appear immediately before a namespace, operation, specialization, function, or type definition.</span></span>
<span data-ttu-id="51dea-155">Bu durumda, içeriği diğer .NET dilleri gibi tanımlanmış çağrılabilir veya Kullanıcı tanımlı tür için belgeler olarak alınır.</span><span class="sxs-lookup"><span data-stu-id="51dea-155">In that case, their contents are taken as documentation for the defined callable or user-defined type, as for other .NET languages.</span></span>

<span data-ttu-id="51dea-156">`///`Açıklamalar içinde, API belgelerinin bir parçası olarak görünen metin, özel olarak adlandırılmış üst bilgiler tarafından belirtilen belgelerin farklı bölümleriyle [markaşağı](https://daringfireball.net/projects/markdown/syntax)olarak biçimlendirilir.</span><span class="sxs-lookup"><span data-stu-id="51dea-156">Within `///` comments, text to appear as a part of API documentation is formatted as [Markdown](https://daringfireball.net/projects/markdown/syntax), with different parts of the documentation being indicated by specially-named headers.</span></span>
<span data-ttu-id="51dea-157">Markı 'nin bir uzantısı olarak, Q # içindeki işlemlere, işlevlere ve Kullanıcı tanımlı türlere çapraz başvurular kullanılarak dahil edilebilir, `@"<ref target>"` burada, `<ref target>` başvurulan kod nesnesinin tam adı ile değiştirilmiştir.</span><span class="sxs-lookup"><span data-stu-id="51dea-157">As an extension to Markdown, cross references to operations, functions and user-defined types in Q# can be included using the `@"<ref target>"`, where `<ref target>` is replaced by the fully qualified name of the code object being referenced.</span></span>
<span data-ttu-id="51dea-158">İsteğe bağlı olarak, bir belge altyapısı ek markı uzantılarını da destekleyebilir.</span><span class="sxs-lookup"><span data-stu-id="51dea-158">Optionally, a documentation engine may also support additional Markdown extensions.</span></span>

<span data-ttu-id="51dea-159">Örnek:</span><span class="sxs-lookup"><span data-stu-id="51dea-159">For example:</span></span>

```qsharp
/// # Summary
/// Given an operation and a target for that operation,
/// applies the given operation twice.
///
/// # Input
/// ## op
/// The operation to be applied.
/// ## target
/// The target to which the operation is to be applied.
///
/// # Type Parameters
/// ## 'T
/// The type expected by the given operation as its input.
///
/// # Example
/// ```Q#
/// // Should be equivalent to the identity.
/// ApplyTwice(H, qubit);
/// ```
///
/// # See Also
/// - Microsoft.Quantum.Intrinsic.H
operation ApplyTwice<'T>(op : ('T => Unit), target : 'T) : Unit {
    op(target);
    op(target);
}
```

<span data-ttu-id="51dea-160">Aşağıdaki adlar belge açıklama üstbilgileri olarak tanınır.</span><span class="sxs-lookup"><span data-stu-id="51dea-160">The following names are recognized as documentation comment headers.</span></span>

- <span data-ttu-id="51dea-161">**Özet**: bir işlev veya işlemin davranışının veya bir tür amacının kısa özeti.</span><span class="sxs-lookup"><span data-stu-id="51dea-161">**Summary**: A short summary of the behavior of a function or operation, or of the purpose of a type.</span></span> <span data-ttu-id="51dea-162">Özetin ilk paragrafı, üzerine gelme bilgileri için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="51dea-162">The first paragraph of the summary is used for hover information.</span></span> <span data-ttu-id="51dea-163">Düz metin olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="51dea-163">It should be plain text.</span></span>
- <span data-ttu-id="51dea-164">**Açıklama**: bir işlevin veya işlemin davranışının veya bir türün amacının açıklaması.</span><span class="sxs-lookup"><span data-stu-id="51dea-164">**Description**: A description of the behavior of a function or operation, or of the purpose of a type.</span></span> <span data-ttu-id="51dea-165">Özet ve açıklama, işlev, işlem veya tür için üretilen belge dosyasını oluşturacak şekilde birleştirilir.</span><span class="sxs-lookup"><span data-stu-id="51dea-165">The summary and description are concatenated to form the generated documentation file for the function, operation, or type.</span></span>
  <span data-ttu-id="51dea-166">Açıklama, satır içi LaTeX biçimli sembolleri ve denklemleri içerebilir.</span><span class="sxs-lookup"><span data-stu-id="51dea-166">The description may contain in-line LaTeX-formatted symbols and equations.</span></span>
- <span data-ttu-id="51dea-167">**Giriş**: bir işlemin veya işlevin giriş kayıt düzeninin açıklaması.</span><span class="sxs-lookup"><span data-stu-id="51dea-167">**Input**: A description of the input tuple for an operation or function.</span></span>
  <span data-ttu-id="51dea-168">Giriş kayıt düzeni öğelerinin her birini belirten ek Markup alt bölümleri içerebilir.</span><span class="sxs-lookup"><span data-stu-id="51dea-168">May contain additional Markdown subsections indicating each individual element of the input tuple.</span></span>
- <span data-ttu-id="51dea-169">**Output**: bir işlem veya işlev tarafından döndürülen tanımlama grubunun açıklaması.</span><span class="sxs-lookup"><span data-stu-id="51dea-169">**Output**: A description of the tuple returned by an operation or function.</span></span>
- <span data-ttu-id="51dea-170">**Tür parametreleri**: her genel tür parametresi için bir ek alt bölüm içeren boş bir bölüm.</span><span class="sxs-lookup"><span data-stu-id="51dea-170">**Type Parameters**: An empty section which contains one additional subsection for each generic type parameter.</span></span>
- <span data-ttu-id="51dea-171">**Örnek**: işlemin, işlevin veya tür kullanılan kısa bir örnek.</span><span class="sxs-lookup"><span data-stu-id="51dea-171">**Example**: A short example of the operation, function or type in use.</span></span>
- <span data-ttu-id="51dea-172">**Açıklamalar**: işlemin, işlevin veya türün bazı yönlerini açıklayan çeşitli işlemler.</span><span class="sxs-lookup"><span data-stu-id="51dea-172">**Remarks**: Miscellaneous prose describing some aspect of the operation, function, or type.</span></span>
- <span data-ttu-id="51dea-173">**Ayrıca bkz**: ilgili işlevleri, işlemleri veya Kullanıcı tanımlı türleri gösteren tam nitelikli adların listesi.</span><span class="sxs-lookup"><span data-stu-id="51dea-173">**See Also**: A list of fully qualified names indicating related functions, operations, or user-defined types.</span></span>
- <span data-ttu-id="51dea-174">**Başvurular**: belgelendirilmekte olan öğe için başvuruların ve alıntıların listesi.</span><span class="sxs-lookup"><span data-stu-id="51dea-174">**References**: A list of references and citations for the item being documented.</span></span>

## <a name="next-steps"></a><span data-ttu-id="51dea-175">Sonraki adımlar</span><span class="sxs-lookup"><span data-stu-id="51dea-175">Next steps</span></span>

<span data-ttu-id="51dea-176">Q # içindeki [işlemler ve işlevler](xref:microsoft.quantum.guide.operationsfunctions) hakkında bilgi edinin.</span><span class="sxs-lookup"><span data-stu-id="51dea-176">Learn about [Operations and Functions](xref:microsoft.quantum.guide.operationsfunctions) in Q#.</span></span>