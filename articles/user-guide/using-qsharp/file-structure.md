---
title: Q# Dosya yapısı
description: Bir dosyanın yapısını ve sözdizimini açıklar Q# .
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.filestructure
no-loc:
- Q#
- $$v
ms.openlocfilehash: 98b3a2e35186989b8191cc566a5d5310bc26eafc
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/21/2020
ms.locfileid: "90833304"
---
# <a name="no-locq-file-structure"></a><span data-ttu-id="127b1-103">Q# Dosya yapısı</span><span class="sxs-lookup"><span data-stu-id="127b1-103">Q# File Structure</span></span>

<span data-ttu-id="127b1-104">Bir Q# Dosya, bir dizi *ad alanı bildirimi*içerir.</span><span class="sxs-lookup"><span data-stu-id="127b1-104">A Q# file consists of a sequence of *namespace declarations*.</span></span>
<span data-ttu-id="127b1-105">Her ad alanı bildirimi, Kullanıcı tanımlı türler, işlemler ve işlevler için bildirimler içerir ve her bir tür bildirime ve herhangi bir sıraya sahip olabilir.</span><span class="sxs-lookup"><span data-stu-id="127b1-105">Each namespace declaration contains declarations for user-defined types, operations, and functions, and can contain any number of each type of declaration and in any order.</span></span>
<span data-ttu-id="127b1-106">Bir ad alanı içindeki bildirimler hakkında daha fazla bilgi için bkz. [Kullanıcı tanımlı türler](xref:microsoft.quantum.guide.types#user-defined-types), [işlemler](xref:microsoft.quantum.guide.operationsfunctions#defining-new-operations)ve [işlevler](xref:microsoft.quantum.guide.operationsfunctions#defining-new-functions).</span><span class="sxs-lookup"><span data-stu-id="127b1-106">For more information on declarations within a namespace, see [user-defined types](xref:microsoft.quantum.guide.types#user-defined-types), [operations](xref:microsoft.quantum.guide.operationsfunctions#defining-new-operations), and [functions](xref:microsoft.quantum.guide.operationsfunctions#defining-new-functions).</span></span>

<span data-ttu-id="127b1-107">Bir ad alanı bildiriminin dışında görünebilen tek metin açıklamalardır.</span><span class="sxs-lookup"><span data-stu-id="127b1-107">The only text that can appear outside of a namespace declaration is comments.</span></span>
<span data-ttu-id="127b1-108">Özellikle, bir ad alanı için bildirim öncesinde belge açıklamaları.</span><span class="sxs-lookup"><span data-stu-id="127b1-108">In particular, documentation comments for a namespace precede the declaration.</span></span> <span data-ttu-id="127b1-109">Daha fazla bilgi için bu makaledeki [belge açıklamaları](#documentation-comments) bölümüne bakın.</span><span class="sxs-lookup"><span data-stu-id="127b1-109">For more information, see [Documentation comments](#documentation-comments) in this article.</span></span> 

## <a name="namespace-declarations"></a><span data-ttu-id="127b1-110">Ad alanı bildirimleri</span><span class="sxs-lookup"><span data-stu-id="127b1-110">Namespace Declarations</span></span>

<span data-ttu-id="127b1-111">Bir Q# dosya genellikle yalnızca bir ad alanı bildirimine sahiptir, ancak None (ve boş olabilir veya yalnızca açıklama içeremez) veya birden çok ad alanı içerebilir.</span><span class="sxs-lookup"><span data-stu-id="127b1-111">A Q# file typically has just one namespace declaration, but could have none (and be empty or just contain comments) or could contain multiple namespaces.</span></span>
<span data-ttu-id="127b1-112">Ad alanı bildirimleri iç içe olamaz.</span><span class="sxs-lookup"><span data-stu-id="127b1-112">Namespace declarations can not be nested.</span></span>

<span data-ttu-id="127b1-113">Aynı Q# ada sahip hiçbir tür, işlem veya işlev bildirimi olmadığı sürece, birlikte derlenen birden çok dosyada aynı ad alanını bildirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="127b1-113">You can declare the same namespace in multiple Q# files that are compiled together, as long as there are no type, operation, or function declarations with the same name.</span></span>
<span data-ttu-id="127b1-114">Özellikle, bildirimler özdeş olsa bile, birden çok dosyada aynı ad alanında aynı türü tanımlamak geçersizdir.</span><span class="sxs-lookup"><span data-stu-id="127b1-114">In particular, it is invalid to define the same type in the same namespace in multiple files, even if the declarations are identical.</span></span>

<span data-ttu-id="127b1-115">Bir ad alanı bildirimi, anahtar sözcüğünden `namespace` ve ardından ad alanının adı ve küme ayraçları içine alınmış ad alanında yer alan bildirimlerin oluşur `{ }` .</span><span class="sxs-lookup"><span data-stu-id="127b1-115">A namespace declaration consists of the keyword `namespace`, followed by the name of the namespace, and the declarations contained in the namespace enclosed in braces `{ }`.</span></span>
<span data-ttu-id="127b1-116">Ad alanı adları, noktalarla ayrılmış bir veya daha fazla yasal sembol dizisinin .NET örüntüsünün izler `.` .</span><span class="sxs-lookup"><span data-stu-id="127b1-116">Namespace names follow the .NET pattern of a sequence of one or more legal symbols separated by periods `.`.</span></span>
<span data-ttu-id="127b1-117">Örneğin, `MyQuantumStuff` ve `Microsoft.Quantum.Intrinsic` geçerli ad alanı adlardır.</span><span class="sxs-lookup"><span data-stu-id="127b1-117">For example, `MyQuantumStuff` and `Microsoft.Quantum.Intrinsic` are valid namespace names.</span></span>
<span data-ttu-id="127b1-118">Kurala göre, bir ad alanı adında sembolleri büyük harfle yapın, ancak bu gerekli değildir.</span><span class="sxs-lookup"><span data-stu-id="127b1-118">By convention, capitalize the symbols in a namespace name, however, this is not required.</span></span>

<span data-ttu-id="127b1-119">Bir dosyada düzgün şekilde tanımlanan türlerin veya callabların başvuruları doğru bir şekilde çözümlenir; bir başvurunun önüne geçmek için tür, işlem veya işlev bildirimine gerek yoktur.</span><span class="sxs-lookup"><span data-stu-id="127b1-119">References to types or callables declared further down in a file resolve properly; there is no need for the type, operation, or function declaration to precede a reference to it.</span></span>

## <a name="open-directives"></a><span data-ttu-id="127b1-120">Açık yönergeler</span><span class="sxs-lookup"><span data-stu-id="127b1-120">Open Directives</span></span>

<span data-ttu-id="127b1-121">Bir ad alanı bloğunda, `open` belirli bir ad alanında belirtilen tüm türleri ve callabları içeri aktarmak için yönergesini kullanın ve bunları nitelenmemiş adlarıyla inceleyin.</span><span class="sxs-lookup"><span data-stu-id="127b1-121">Within a namespace block, use the `open` directive to import all types and callables declared in a certain namespace and refer to them by their unqualified name.</span></span>
<span data-ttu-id="127b1-122">Bu tür bir `open` yönerge, `open` anahtar sözcüğünden, ardından açılacak ad alanı ve bir sona noktalı virgül içerir.</span><span class="sxs-lookup"><span data-stu-id="127b1-122">Such an `open` directive consists of the `open` keyword, followed by the namespace to be opened and a terminating semicolon.</span></span>

> [!NOTE] 
> <span data-ttu-id="127b1-123">Tüm `open` yönergeler `function` `operation` `newtype` ad alanı bloğunda, veya bildirimlerinden önce gelmelidir.</span><span class="sxs-lookup"><span data-stu-id="127b1-123">All `open` directives must appear before any `function`, `operation`, or `newtype` declarations in the namespace block.</span></span>

<span data-ttu-id="127b1-124">İsteğe bağlı olarak, açılan ad alanı için kısa bir ad tanımlayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="127b1-124">Optionally, you can define a short name for the opened namespace.</span></span> <span data-ttu-id="127b1-125">Kısa bir ad tanımlanmışsa, bu ad alanındaki tüm öğeleri tanımlanmış kısa ad ile nitelemeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="127b1-125">If a short name is defined, you must qualify all elements from that namespace by the defined short name.</span></span> <span data-ttu-id="127b1-126">Örneğin, aşağıdaki ad alanı bildirimi ve açık yönergeler verildiğinde,</span><span class="sxs-lookup"><span data-stu-id="127b1-126">For example, given the following namespace declaration and open directives,</span></span>

```qsharp
namespace NS {
    open Microsoft.Quantum.Intrinsic; // opens the namespace
    open Microsoft.Quantum.Math as Math; // defines a short name for the namespace

    // operation, function, and newtype declarations

}
```

<span data-ttu-id="127b1-127">tanımlı bir işlem öğesinden bir işlem kullanıyorsa `Op` `Microsoft.Quantum.Intrinsic` , bunu kullanarak çağırın `Op` .</span><span class="sxs-lookup"><span data-stu-id="127b1-127">if a declared operation uses an operation `Op` from `Microsoft.Quantum.Intrinsic`, you call it by simply using `Op`.</span></span>
<span data-ttu-id="127b1-128">Ancak, ' den belirli bir işlevi çağırmak için `Fn` `Microsoft.Quantum.Math` öğesini kullanarak çağırmanız gerekir `Math.Fn` .</span><span class="sxs-lookup"><span data-stu-id="127b1-128">However, to call a certain function `Fn` from `Microsoft.Quantum.Math`, you must call it using `Math.Fn`.</span></span>

<span data-ttu-id="127b1-129">`open`Yönerge, bir dosya içindeki tüm ad alanı bloğunun tamamına uygulanır.</span><span class="sxs-lookup"><span data-stu-id="127b1-129">The `open` directive applies to the entire namespace block within a file.</span></span>
<span data-ttu-id="127b1-130">Bu nedenle, daha önce aynı dosyada ek bir ad alanı tanımlarsanız, bu durumda, Q# `NS` ikinci ad alanında tanımlanan tüm işlemler/işlevler/türler, `Microsoft.Quantum.Intrinsic` `Microsoft.Quantum.Math` içindeki açık yönergeleri tekrarlamazsanız veya hiçbir şeye erişemez.</span><span class="sxs-lookup"><span data-stu-id="127b1-130">Hence, if you define an additional namespace in the same Q# file as `NS` earlier, then any operations/functions/types defined in the second namespace would not have access to anything from `Microsoft.Quantum.Intrinsic` or `Microsoft.Quantum.Math` unless you repeated the open directives therein.</span></span> 

<span data-ttu-id="127b1-131">Geçerli ad alanında *açılmayan* başka bir ad alanında tanımlanan bir türe veya çağrılabilir öğesine başvurmak için, tam adı ile ona başvurmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="127b1-131">To reference a type or callable defined in another namespace that is *not* opened in the current namespace, you must reference it by its fully-qualified name.</span></span>
<span data-ttu-id="127b1-132">Örneğin, ad alanından adlı bir işlem verilince `Op` `X.Y` :</span><span class="sxs-lookup"><span data-stu-id="127b1-132">For example, given an operation named `Op` from the `X.Y` namespace:</span></span>

* <span data-ttu-id="127b1-133">`X.Y.Op` `X.Y` Ad alanı geçerli blokta daha önce açılmamışsa, bu ada tam adı ile başvurmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="127b1-133">You must reference it by its fully-qualified name `X.Y.Op`, unless the `X.Y` namespace has been opened earlier in the current block.</span></span> 
* <span data-ttu-id="127b1-134">`X`Ad alanı açılmış olsa da, işleme olarak başvurmak mümkün değildir `Y.Op` .</span><span class="sxs-lookup"><span data-stu-id="127b1-134">Even if the `X` namespace is opened, it is not possible to reference the operation as `Y.Op`.</span></span>
* <span data-ttu-id="127b1-135">`Z` `X.Y` Bu ad alanında ve dosyada için kısa ad tanımladıysanız, olarak başvurmanız gerekir `Op` `Z.Op` .</span><span class="sxs-lookup"><span data-stu-id="127b1-135">If you defined the short name `Z` for `X.Y` in that namespace and file, you must reference `Op` as `Z.Op`.</span></span> 

<span data-ttu-id="127b1-136">Bir yönergesi kullanarak bir ad alanı eklemek genellikle daha iyidir `open` .</span><span class="sxs-lookup"><span data-stu-id="127b1-136">It is usually better to include a namespace by using an `open` directive.</span></span>
<span data-ttu-id="127b1-137">İki ad alanı aynı ada sahip yapıları tanımladıysa ve geçerli kaynak yapıları her ikisiyle kullanıyorsa, tam nitelikli ad kullanılması gerekir.</span><span class="sxs-lookup"><span data-stu-id="127b1-137">Using a fully-qualified name is required if two namespaces define constructs with the same name, and the current source uses constructs from both.</span></span>

<span data-ttu-id="127b1-138">Q# diğer .NET dilleri olarak adlandırmayla aynı kurallara uyar.</span><span class="sxs-lookup"><span data-stu-id="127b1-138">Q# follows the same rules for naming as other .NET languages.</span></span>
<span data-ttu-id="127b1-139">Ancak, Q# ad alanlarına göreli başvuruları desteklemez.</span><span class="sxs-lookup"><span data-stu-id="127b1-139">However, Q# does not support relative references to namespaces.</span></span>
<span data-ttu-id="127b1-140">Örneğin, ad alanı `a.b` açıksa adlı bir işleme başvuru, `c.d` tam ada sahip bir işleme *çözümlenmez* `a.b.c.d` .</span><span class="sxs-lookup"><span data-stu-id="127b1-140">For example, if the namespace `a.b` is open, a reference to an operation named `c.d` does *not* resolve to an operation with full name `a.b.c.d`.</span></span>

## <a name="formatting"></a><span data-ttu-id="127b1-141">Biçimlendirme</span><span class="sxs-lookup"><span data-stu-id="127b1-141">Formatting</span></span>

<span data-ttu-id="127b1-142">Çoğu Q# deyim ve yönergeler sonlandırma noktalı virgülle biter `;` .</span><span class="sxs-lookup"><span data-stu-id="127b1-142">Most Q# statements and directives end with a terminating semicolon, `;`.</span></span>
<span data-ttu-id="127b1-143">Ve gibi deyimler ve bildirimler `for` `operation` bir deyim bloğu ile biter (aşağıdaki bölüme bakın) sonlandırma noktalı virgül gerektirmez.</span><span class="sxs-lookup"><span data-stu-id="127b1-143">Statements and declarations such as `for` and `operation` that end with a statement block (see the following section) do not require a terminating semicolon.</span></span>
<span data-ttu-id="127b1-144">Her bir ifade açıklaması, Sonlandırıcı noktalı virgülden gerekli olup olmadığını not edin.</span><span class="sxs-lookup"><span data-stu-id="127b1-144">Each statement description notes whether the terminating semicolon is required.</span></span>

<span data-ttu-id="127b1-145">İfadeler, bildirimler ve yönergeler gibi deyimler birden çok satıra ayrılabilir.</span><span class="sxs-lookup"><span data-stu-id="127b1-145">Statements, like expressions, declarations, and directives, can be broken out across multiple lines.</span></span>
<span data-ttu-id="127b1-146">Birden çok deyimi tek bir satıra yerleştirmekten kaçının.</span><span class="sxs-lookup"><span data-stu-id="127b1-146">Avoid putting multiple statements on a single line.</span></span>

## <a name="statement-blocks"></a><span data-ttu-id="127b1-147">Ekstre blokları</span><span class="sxs-lookup"><span data-stu-id="127b1-147">Statement Blocks</span></span>

<span data-ttu-id="127b1-148">Q# deyimler, küme ayraçları ile birlikte bulunan deyim blokları halinde gruplandırılır `{ }` .</span><span class="sxs-lookup"><span data-stu-id="127b1-148">Q# statements are grouped into statement blocks, which are contained with braces `{ }`.</span></span> <span data-ttu-id="127b1-149">Bir ifade bloğu bir açma ile başlar `{` ve kapanış ile biter `}` .</span><span class="sxs-lookup"><span data-stu-id="127b1-149">A statement block starts with an opening `{` and ends with a closing `}`.</span></span>

<span data-ttu-id="127b1-150">Başka bir blok içinde Sözcüksel olarak bulunan bir ifade bloğu, kapsayan bloğun bir alt bloğu olarak kabul edilir; içerilen ve alt bloklara dış ve iç bloklar de denir.</span><span class="sxs-lookup"><span data-stu-id="127b1-150">A statement block that is lexically enclosed within another block is considered to be a sub-block of the containing block; containing and sub-blocks are also called outer and inner blocks.</span></span>

## <a name="comments"></a><span data-ttu-id="127b1-151">Yorumlar</span><span class="sxs-lookup"><span data-stu-id="127b1-151">Comments</span></span>

<span data-ttu-id="127b1-152">Açıklamalar iki eğik çizgi ile başlar `//` ve satırın sonuna kadar devam eder.</span><span class="sxs-lookup"><span data-stu-id="127b1-152">Comments begin with two forward slashes, `//`, and continue until the end of the line.</span></span>
<span data-ttu-id="127b1-153">Bir yorum, kaynak dosyasında herhangi bir yerde görünebilir Q# .</span><span class="sxs-lookup"><span data-stu-id="127b1-153">A comment can appear anywhere in a Q# source file.</span></span>

## <a name="documentation-comments"></a><span data-ttu-id="127b1-154">Belge Açıklamaları</span><span class="sxs-lookup"><span data-stu-id="127b1-154">Documentation Comments</span></span>

<span data-ttu-id="127b1-155">Üç eğik çizgi ile başlayan yorumlar, `///` bir ad alanı, işlem, özelleştirme, işlev veya tür tanımından hemen önce göründüğü zaman derleyici tarafından özellikle değerlendirilir.</span><span class="sxs-lookup"><span data-stu-id="127b1-155">Comments that begin with three forward slashes, `///`, are treated specially by the compiler when they appear immediately before a namespace, operation, specialization, function, or type definition.</span></span>
<span data-ttu-id="127b1-156">Bu durumda, derleyici, tanımlı çağrılabilir veya Kullanıcı tanımlı tür için diğer .NET dilleri ile aynı şekilde bir belge olarak davranır.</span><span class="sxs-lookup"><span data-stu-id="127b1-156">In that case, the compiler treats them as documentation for the defined callable or user-defined type, the same as other .NET languages.</span></span>

<span data-ttu-id="127b1-157">`///`Açıklamalar içinde, API belgelerinin bir parçası olarak görünen metin, özel olarak adlandırılan üstbilgiler tarafından belirtilen farklı kısımlarla [markaşağı](https://daringfireball.net/projects/markdown/syntax)olarak biçimlendirilir.</span><span class="sxs-lookup"><span data-stu-id="127b1-157">Within `///` comments, text to appear as a part of API documentation is formatted as [Markdown](https://daringfireball.net/projects/markdown/syntax), with different parts of the documentation indicated by specially-named headers.</span></span>
<span data-ttu-id="127b1-158">Markaşağı içinde, `@"<ref target>"` içindeki çapraz başvuru işlemleri, işlevler ve Kullanıcı tanımlı türler için uzantıyı kullanın Q# .</span><span class="sxs-lookup"><span data-stu-id="127b1-158">In Markdown, use the `@"<ref target>"` extension to cross-reference operations, functions, and user-defined types in Q#.</span></span> <span data-ttu-id="127b1-159">`<ref target>`Başvurulan kod nesnesinin tam adı ile değiştirin.</span><span class="sxs-lookup"><span data-stu-id="127b1-159">Replace `<ref target>` with the fully qualified name of the referenced code object.</span></span>
<span data-ttu-id="127b1-160">Farklı belge motorları, ek Marki uzantılarını da destekleyebilir.</span><span class="sxs-lookup"><span data-stu-id="127b1-160">Different documentation engines may also support additional Markdown extensions.</span></span>

<span data-ttu-id="127b1-161">Örnek:</span><span class="sxs-lookup"><span data-stu-id="127b1-161">For example:</span></span>

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

<span data-ttu-id="127b1-162">Aşağıdaki adlar belge açıklaması üst bilgileri olarak geçerlidir.</span><span class="sxs-lookup"><span data-stu-id="127b1-162">The following names are valid as documentation comment headers.</span></span>

- <span data-ttu-id="127b1-163">**Özet**: bir işlev veya işlemin davranışının kısa bir özeti veya bir türün amacı.</span><span class="sxs-lookup"><span data-stu-id="127b1-163">**Summary**: A short summary of the behavior of a function or operation, or the purpose of a type.</span></span> <span data-ttu-id="127b1-164">Özetin ilk paragrafı, üzerine gelme bilgileri için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="127b1-164">The first paragraph of the summary is used for hover information.</span></span> <span data-ttu-id="127b1-165">Düz metin olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="127b1-165">It should be plain text.</span></span>
- <span data-ttu-id="127b1-166">**Açıklama**: bir işlev veya işlemin davranışının açıklaması veya bir türün amacı.</span><span class="sxs-lookup"><span data-stu-id="127b1-166">**Description**: A description of the behavior of a function or operation, or the purpose of a type.</span></span> <span data-ttu-id="127b1-167">Birlikte, Özet ve açıklama işlev, işlem veya tür için üretilen belge dosyasını oluşturur.</span><span class="sxs-lookup"><span data-stu-id="127b1-167">Together, the summary and description form the generated documentation file for the function, operation, or type.</span></span>
  <span data-ttu-id="127b1-168">Açıklama, satır içi LaTeX biçimli sembolleri ve denklemleri destekler.</span><span class="sxs-lookup"><span data-stu-id="127b1-168">The description supports in-line LaTeX-formatted symbols and equations.</span></span>
- <span data-ttu-id="127b1-169">**Giriş**: bir işlemin veya işlevin giriş kayıt düzeninin açıklaması.</span><span class="sxs-lookup"><span data-stu-id="127b1-169">**Input**: A description of the input tuple for an operation or function.</span></span>
  <span data-ttu-id="127b1-170">Giriş kayıt düzeninin her bir öğesini gösteren ek Markup alt bölümleri içerebilir.</span><span class="sxs-lookup"><span data-stu-id="127b1-170">Can contain additional Markdown subsections indicating each element of the input tuple.</span></span>
- <span data-ttu-id="127b1-171">**Output**: bir işlem veya işlev tarafından döndürülen tanımlama grubunun açıklaması.</span><span class="sxs-lookup"><span data-stu-id="127b1-171">**Output**: A description of the tuple returned by an operation or function.</span></span>
- <span data-ttu-id="127b1-172">**Tür parametreleri**: her genel tür parametresi için bir ek alt bölüm içeren boş bir bölüm.</span><span class="sxs-lookup"><span data-stu-id="127b1-172">**Type Parameters**: An empty section that contains one additional subsection for each generic type parameter.</span></span>
- <span data-ttu-id="127b1-173">**Örnek**: işlem, işlev veya kullanılan tür için kısa bir örnek.</span><span class="sxs-lookup"><span data-stu-id="127b1-173">**Example**: A short example of the operation, function, or type in use.</span></span>
- <span data-ttu-id="127b1-174">**Açıklamalar**: işlemin, işlevin veya türün bazı yönlerini açıklayan çeşitli işlemler.</span><span class="sxs-lookup"><span data-stu-id="127b1-174">**Remarks**: Miscellaneous prose describing some aspect of the operation, function, or type.</span></span>
- <span data-ttu-id="127b1-175">**Ayrıca bkz**: ilgili işlevleri, işlemleri veya Kullanıcı tanımlı türleri gösteren tam nitelikli adların listesi.</span><span class="sxs-lookup"><span data-stu-id="127b1-175">**See Also**: A list of fully qualified names indicating related functions, operations, or user-defined types.</span></span>
- <span data-ttu-id="127b1-176">**Başvurular**: belgelenen öğe için başvuruların ve alıntıların listesi.</span><span class="sxs-lookup"><span data-stu-id="127b1-176">**References**: A list of references and citations for the documented item.</span></span>

## <a name="next-steps"></a><span data-ttu-id="127b1-177">Sonraki adımlar</span><span class="sxs-lookup"><span data-stu-id="127b1-177">Next steps</span></span>

<span data-ttu-id="127b1-178">İçindeki [işlemler ve işlevler](xref:microsoft.quantum.guide.operationsfunctions) hakkında bilgi edinin Q# .</span><span class="sxs-lookup"><span data-stu-id="127b1-178">Learn about [Operations and Functions](xref:microsoft.quantum.guide.operationsfunctions) in Q#.</span></span>