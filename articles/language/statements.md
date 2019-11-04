---
title: 'S # deyimleri | Microsoft Docs'
description: 'Q # deyimleri'
author: QuantumWriter
uid: microsoft.quantum.language.statements
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 5bcbee868c76aaf53d0b7969e6e634da62689aaa
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2019
ms.locfileid: "73184874"
---
# <a name="statements-and-other-constructs"></a><span data-ttu-id="b7fc2-103">Deyimler ve diğer yapılar</span><span class="sxs-lookup"><span data-stu-id="b7fc2-103">Statements and Other Constructs</span></span>

## <a name="comments"></a><span data-ttu-id="b7fc2-104">Yorumlar</span><span class="sxs-lookup"><span data-stu-id="b7fc2-104">Comments</span></span>

<span data-ttu-id="b7fc2-105">Açıklamalar iki eğik çizgi ile başlar, `//`ve satır sonuna kadar devam eder.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-105">Comments begin with two forward slashes, `//`, and continue until the end of line.</span></span>
<span data-ttu-id="b7fc2-106">Bir soru, Q # kaynak dosyasında herhangi bir yerde görünebilir.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-106">A comment may appear anywhere in a Q# source file.</span></span>

### <a name="documentation-comments"></a><span data-ttu-id="b7fc2-107">Belge açıklamaları</span><span class="sxs-lookup"><span data-stu-id="b7fc2-107">Documentation Comments</span></span>

<span data-ttu-id="b7fc2-108">Üç eğik çizgi ile başlayan açıklamalar, `///`, bir ad alanı, işlem, özelleştirme, işlev veya tür tanımından hemen önce görüntülendiklerinde derleyici tarafından özellikle işlenir.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-108">Comments that begin with three forward slashes, `///`, are treated specially by the compiler when they appear immediately before a namespace, operation, specialization, function, or type definition.</span></span>
<span data-ttu-id="b7fc2-109">Bu durumda, içeriği diğer .NET dilleri gibi tanımlanmış çağrılabilir veya Kullanıcı tanımlı tür için belgeler olarak alınır.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-109">In that case, their contents are taken as documentation for the defined callable or user-defined type, as for other .NET languages.</span></span>

<span data-ttu-id="b7fc2-110">`///` açıklamaları içinde, API belgelerinin bir parçası olarak görünen metin, özel olarak adlandırılan üstbilgiler tarafından belirtilen belgelerin farklı bölümleriyle [Markaşağı](https://daringfireball.net/projects/markdown/syntax)olarak biçimlendirilir.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-110">Within `///` comments, text to appear as a part of API documentation is formatted as [Markdown](https://daringfireball.net/projects/markdown/syntax), with different parts of the documentation being indicated by specially-named headers.</span></span>
<span data-ttu-id="b7fc2-111">Markı 'nin bir uzantısı olarak, Q # içindeki işlemlere, işlevlere ve Kullanıcı tanımlı türlere çapraz başvurular `@"<ref target>"`kullanılarak dahil edilebilir. burada `<ref target>`, başvurulan kod nesnesinin tam adı ile değiştirilmiştir.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-111">As an extension to Markdown, cross references to operations, functions and user-defined types in Q# can be included using the `@"<ref target>"`, where `<ref target>` is replaced by the fully qualified name of the code object being referenced.</span></span>
<span data-ttu-id="b7fc2-112">İsteğe bağlı olarak, bir belge altyapısı ek markı uzantılarını da destekleyebilir.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-112">Optionally, a documentation engine may also support additional Markdown extensions.</span></span>

<span data-ttu-id="b7fc2-113">Örnek:</span><span class="sxs-lookup"><span data-stu-id="b7fc2-113">For example:</span></span>

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
operation ApplyTwice<'T>(op : ('T => Unit), target : 'T) : Unit
{
    op(target);
    op(target);
}
```

<span data-ttu-id="b7fc2-114">Aşağıdaki adlar belge açıklama üstbilgileri olarak tanınır.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-114">The following names are recognized as documentation comment headers.</span></span>

- <span data-ttu-id="b7fc2-115">**Özet**: bir işlev veya işlemin davranışının veya bir tür amacının kısa özeti.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-115">**Summary**: A short summary of the behavior of a function or operation, or of the purpose of a type.</span></span> <span data-ttu-id="b7fc2-116">Özetin ilk paragrafı, üzerine gelme bilgileri için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-116">The first paragraph of the summary is used for hover information.</span></span> <span data-ttu-id="b7fc2-117">Düz metin olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-117">It should be plain text.</span></span>
- <span data-ttu-id="b7fc2-118">**Açıklama**: bir işlevin veya işlemin davranışının veya bir türün amacının açıklaması.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-118">**Description**: A description of the behavior of a function or operation, or of the purpose of a type.</span></span> <span data-ttu-id="b7fc2-119">Özet ve açıklama, işlev, işlem veya tür için üretilen belge dosyasını oluşturacak şekilde birleştirilir.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-119">The summary and description are concatenated to form the generated documentation file for the function, operation, or type.</span></span>
  <span data-ttu-id="b7fc2-120">Açıklama, satır içi LaTeX biçimli sembolleri ve denklemleri içerebilir.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-120">The description may contain in-line LaTeX-formatted symbols and equations.</span></span>
- <span data-ttu-id="b7fc2-121">**Giriş**: bir işlemin veya işlevin giriş kayıt düzeninin açıklaması.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-121">**Input**: A description of the input tuple for an operation or function.</span></span>
  <span data-ttu-id="b7fc2-122">Giriş kayıt düzeni öğelerinin her birini belirten ek Markup alt bölümleri içerebilir.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-122">May contain additional Markdown subsections indicating each individual element of the input tuple.</span></span>
- <span data-ttu-id="b7fc2-123">**Output**: bir işlem veya işlev tarafından döndürülen tanımlama grubunun açıklaması.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-123">**Output**: A description of the tuple returned by an operation or function.</span></span>
- <span data-ttu-id="b7fc2-124">**Tür parametreleri**: her genel tür parametresi için bir ek alt bölüm içeren boş bir bölüm.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-124">**Type Parameters**: An empty section which contains one additional subsection for each generic type parameter.</span></span>
- <span data-ttu-id="b7fc2-125">**Örnek**: işlemin, işlevin veya tür kullanılan kısa bir örnek.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-125">**Example**: A short example of the operation, function or type in use.</span></span>
- <span data-ttu-id="b7fc2-126">**Açıklamalar**: işlemin, işlevin veya türün bazı yönlerini açıklayan çeşitli işlemler.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-126">**Remarks**: Miscellaneous prose describing some aspect of the operation, function, or type.</span></span>
- <span data-ttu-id="b7fc2-127">**Ayrıca bkz**: ilgili işlevleri, işlemleri veya Kullanıcı tanımlı türleri gösteren tam nitelikli adların listesi.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-127">**See Also**: A list of fully qualified names indicating related functions, operations, or user-defined types.</span></span>
- <span data-ttu-id="b7fc2-128">**Başvurular**: belgelendirilmekte olan öğe için başvuruların ve alıntıların listesi.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-128">**References**: A list of references and citations for the item being documented.</span></span>

## <a name="namespaces"></a><span data-ttu-id="b7fc2-129">Ad Alanları</span><span class="sxs-lookup"><span data-stu-id="b7fc2-129">Namespaces</span></span>

<span data-ttu-id="b7fc2-130">Her Q # işlem, işlev ve Kullanıcı tanımlı tür bir ad alanı içinde tanımlanır.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-130">Every Q# operation, function, and user-defined type is defined within a namespace.</span></span>
<span data-ttu-id="b7fc2-131">Q #, diğer .NET dilleri olarak adlandırmayla aynı kuralları izler.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-131">Q# follows the same rules for naming as other .NET languages.</span></span>
<span data-ttu-id="b7fc2-132">Ancak, Q # ad alanlarına göreli başvuruları desteklemez.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-132">However, Q# does not support relative references to namespaces.</span></span>
<span data-ttu-id="b7fc2-133">Diğer bir deyişle, ad alanı `a.b` açıldıysa, `c.d` bir işlem adları başvurusu, tam adı `a.b.c.d`olan bir işleme çözümlenmeyecektir.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-133">That is, if the namespace `a.b` has been opened, a reference to an operation names `c.d` will not be resolved to an operation with full name `a.b.c.d`.</span></span>

<span data-ttu-id="b7fc2-134">Bir ad alanı bloğunda, belirli bir ad alanında belirtilen tüm türleri ve callabları içeri aktarmak için `open` yönergesi kullanılabilir ve bunlara nitelenmemiş adlarıyla başvurabilirler.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-134">Within a namespace block, the `open` directive may be used to import all types and callables declared in a certain namespace and refer to them by their unqualified name.</span></span> <span data-ttu-id="b7fc2-135">İsteğe bağlı olarak, açık ad alanı için bir kısa ad, bu ad alanındaki tüm öğelerin tanımlanmış kısa ad ile nitelendirilerek (ve gerek olması) tanımlanabilir.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-135">Optionally, a short name for the opened namespace may be defined such that all elements from that namespace can (and need) to be qualified by the defined short name.</span></span> <span data-ttu-id="b7fc2-136">`open` yönergesi, bir dosya içindeki tüm ad alanı bloğunun tamamına uygulanır.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-136">The `open` directive applies to the entire namespace block within a file.</span></span>

<span data-ttu-id="b7fc2-137">Geçerli ad alanında açılmamış başka bir ad alanında tanımlanan bir tür veya çağrılabilir, tam nitelikli ad tarafından başvurulmalıdır.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-137">A type or callable defined in another namespace that is not opened in the current namespace must be referenced by its fully-qualified name.</span></span>
<span data-ttu-id="b7fc2-138">Örneğin, `X.Y` ad alanındaki `Op` adlı bir işleme, `X.Y` ad alanı geçerli blokta daha önce açılmadığı müddetçe, tam adı `X.Y.Op`tarafından başvurulmalıdır.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-138">For example, an operation named `Op` in the `X.Y` namespace must be referenced by its fully-qualified name `X.Y.Op`, unless the `X.Y` namespace has been opened earlier in the current block.</span></span> <span data-ttu-id="b7fc2-139">Yukarıda belirtildiği gibi, `X` ad alanı açılmış olsa bile, işleme `Y.Op`olarak başvurulmayabilir.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-139">As mentioned above, even if the `X` namespace has been opened, it is not possible to reference the operation as `Y.Op`.</span></span>
<span data-ttu-id="b7fc2-140">`X.Y` için `Z` kısa bir ad, bu ad alanında ve dosyada tanımlanmışsa, `Op` `Z.Op`olarak başvurulduğu gerekir.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-140">If a short name `Z` for `X.Y` has been defined in that namespace and file, then `Op` needs to be referred to as `Z.Op`.</span></span> 

```qsharp
namespace NS {

    open Microsoft.Quantum.Intrinsic; // opens the namespace
    open Microsoft.Quantum.Math as Math; // defines a short name for the namespace
}
```

<span data-ttu-id="b7fc2-141">`open` yönergesini kullanarak bir ad alanı eklemek genellikle daha iyidir.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-141">It is usually better to include a namespace by using an `open` directive.</span></span>
<span data-ttu-id="b7fc2-142">İki ad alanı aynı ada sahip yapıları tanımladıysa ve geçerli kaynak yapıları her ikisiyle kullanıyorsa, tam nitelikli ad kullanılması gerekir.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-142">Using a fully-qualified name is required if two namespaces define constructs with the same name, and the current source uses constructs from both.</span></span>

## <a name="formatting"></a><span data-ttu-id="b7fc2-143">Biçimlendirme</span><span class="sxs-lookup"><span data-stu-id="b7fc2-143">Formatting</span></span>

<span data-ttu-id="b7fc2-144">Çoğu Q # deyimi ve yönergeleri sonlandırma noktalı virgülle biter `;`.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-144">Most Q# statements and directives end with a terminating semicolon, `;`.</span></span>
<span data-ttu-id="b7fc2-145">Bir deyim bloğu ile biten `for` ve `operation` gibi deyimler ve bildirimler sonlandırma noktalı virgül gerektirmez.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-145">Statements and declarations such as `for` and `operation` that end with a statement block do not require a terminating semicolon.</span></span>
<span data-ttu-id="b7fc2-146">Her bir ifade açıklaması, Sonlandırıcı noktalı virgülden gerekli olup olmadığını not edin.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-146">Each statement description notes whether the terminating semicolon is required.</span></span>

<span data-ttu-id="b7fc2-147">İfadeler, bildirimler ve yönergeler gibi deyimler birden çok satıra ayrılabilir.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-147">Statements, like expressions, declarations, and directives, may be broken out across multiple lines.</span></span>
<span data-ttu-id="b7fc2-148">Tek bir satırda birden çok deyimin olması kaçınılmalıdır.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-148">Having multiple statements on a single line should be avoided.</span></span>

## <a name="statement-blocks"></a><span data-ttu-id="b7fc2-149">Ekstre blokları</span><span class="sxs-lookup"><span data-stu-id="b7fc2-149">Statement Blocks</span></span>

<span data-ttu-id="b7fc2-150">Q # deyimleri deyim blokları halinde gruplandırılır.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-150">Q# statements are grouped into statement blocks.</span></span>
<span data-ttu-id="b7fc2-151">Bir ifade bloğu, açma `{` başlar ve bir kapanış `}`ile biter.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-151">A statement block starts with an opening `{` and ends with a closing `}`.</span></span>

<span data-ttu-id="b7fc2-152">Başka bir blok içinde Sözcüksel olarak bulunan bir ifade bloğu, kapsayan bloğun bir alt bloğu olarak kabul edilir; içerilen ve alt bloklara dış ve iç bloklar de denir.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-152">A statement block that is lexically enclosed within another block is considered to be a sub-block of the containing block; containing and sub-blocks are also called outer and inner blocks.</span></span>

## <a name="symbol-binding-and-assignment"></a><span data-ttu-id="b7fc2-153">Sembol bağlama ve atama</span><span class="sxs-lookup"><span data-stu-id="b7fc2-153">Symbol Binding and Assignment</span></span>

<span data-ttu-id="b7fc2-154">S # kesilebilir ve değişmez semboller arasında ayrım yapar.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-154">Q# distinguishes between mutable and immutable symbols.</span></span>
<span data-ttu-id="b7fc2-155">Genellikle, derleyicinin daha iyi iyileştirmeler gerçekleştirmesini sağladığından, değişmez sembollerin kullanılması önerilir.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-155">In general, the use of immutable symbols is encouraged because it allows the compiler to perform more optimizations.</span></span>

<span data-ttu-id="b7fc2-156">Bağlamanın sol tarafı bir sembol tanımlama grubu ve bir ifadenin sağ tarafından oluşur.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-156">The left-hand-side of the binding consists of a symbol tuple, and the right hand side of an expression.</span></span>

<span data-ttu-id="b7fc2-157">Tüm Q # türleri değer türleri olduğundan ve bir özel rol alan qubits ile, bir değer bir simgeye bağlandığında veya bir sembol yeniden bağlandığında bir "kopya" oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-157">Since all Q# types are value types - with the qubits taking a somewhat special role - formally a "copy" is created when a value is bound to a symbol, or when a symbol is rebound.</span></span> <span data-ttu-id="b7fc2-158">Yani, Q # davranışı atamadaki bir kopyanın oluşturulmasıyla aynı olur.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-158">That is to say, the behavior of Q# is the same as if a copy were created on assignment.</span></span> <span data-ttu-id="b7fc2-159">Bu özellikle de diziler içerir.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-159">This in particular also includes arrays.</span></span> <span data-ttu-id="b7fc2-160">Pratikte yalnızca ilgili parçalar gerektiği şekilde yeniden oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-160">Of course in practice only the relevant pieces are actually recreated as needed.</span></span> 

### <a name="tuple-deconstruction"></a><span data-ttu-id="b7fc2-161">Demet oluşturmayı kaldırma</span><span class="sxs-lookup"><span data-stu-id="b7fc2-161">Tuple Deconstruction</span></span>

<span data-ttu-id="b7fc2-162">Bağlamanın sağ tarafı bir tanımlama grubu ise, bu kayıt düzeni atama sonrasında oluşturulabilir.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-162">If the right-hand side of the binding is a tuple, then that tuple may be deconstructed upon assignment.</span></span>
<span data-ttu-id="b7fc2-163">Bu tür ayrıştırmaları iç içe geçmiş tanımlama gruplarını içerebilir ve sağ taraftaki tanımlama grubunun şekli sembol tanımlama grubu şekli ile uyumlu olduğu sürece herhangi bir tam veya kısmi kaldırma geçerli olur.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-163">Such deconstructions may involve nested tuples, and any full or partial deconstruction is valid as long as the shape of the tuple on the right hand side is compatible with the shape of the symbol tuple.</span></span>
<span data-ttu-id="b7fc2-164">Kayıt düzeni, `=` sağ tarafı bir demet değerli ifade olduğunda da kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-164">Tuple deconstruction can in particular also be used when the right-hand side of the `=` is a tuple-valued expression.</span></span>

```qsharp
let (i, f) = (5, 0.1); // i is bound to 5 and f to 0.1
mutable (a, (_, b)) = (1, (2, 3)); // a is bound to 1, b is bound to 3
mutable (x, y) = ((1, 2), [3, 4]); // x is bound to (1,2), y is bound to [3,4]
set (x, _, y) = ((5, 6), 7, [8]);  // x is rebound to (5,6), y is rebound to [8]
let (r1, r2) = MeasureTwice(q1, PauliX, q2, PauliY);
```

### <a name="immutable-symbols"></a><span data-ttu-id="b7fc2-165">Sabit semboller</span><span class="sxs-lookup"><span data-stu-id="b7fc2-165">Immutable Symbols</span></span>

<span data-ttu-id="b7fc2-166">Değişmez semboller `let` ifadesiyle ilişkilidir.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-166">Immutable symbols are bound using the `let` statement.</span></span>
<span data-ttu-id="b7fc2-167">Bu, her ne kadar C#soru-cevap, bu, örneğin, bir kez bağlantılı olan Q # sembolleri değiştirilmedikçe, değişken bildirimine ve başlatmaya eşittir. `let` bağlamaları sabittir.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-167">This is roughly equivalent to variable declaration and initialization in languages such as C#, except that Q# symbols, once bound, may not be changed; `let` bindings are immutable.</span></span>

<span data-ttu-id="b7fc2-168">Değişmez bir bağlama, bir sembol veya sembol kümesi, eşittir işareti `=`, sembolleri bağlamak için bir ifade ve sondaki noktalı virgülden oluşan `let`anahtar sözcükten oluşur.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-168">An immutable binding consists of the keyword `let`, followed by a symbol or symbol tuple, an equals sign `=`, an expression to bind the symbol(s) to, and a terminating semicolon.</span></span>
<span data-ttu-id="b7fc2-169">Bağlı sembol (ler) in türü sağ taraftaki ifadeye göre belirlenir.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-169">The type of the bound symbol(s) is inferred based on the expression on the right hand side.</span></span>

### <a name="mutable-symbols"></a><span data-ttu-id="b7fc2-170">Değişebilir semboller</span><span class="sxs-lookup"><span data-stu-id="b7fc2-170">Mutable Symbols</span></span>

<span data-ttu-id="b7fc2-171">Kesilebilir semboller `mutable` ifadesiyle tanımlanır ve başlatılır.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-171">Mutable symbols are defined and initialized using the `mutable` statement.</span></span>
<span data-ttu-id="b7fc2-172">`mutable` deyimin bir parçası olarak belirtilen ve bağlantılı semboller kodun ilerleyen kısımlarında farklı bir değere yeniden bağlanabilir.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-172">Symbols declared and bound as part of a `mutable` statement may be rebound to a different value later in the code.</span></span> 

<span data-ttu-id="b7fc2-173">Kesilebilir bağlama deyimi, bir sembol veya sembol kümesi, eşittir işareti `=`, sembolleri bağlamak için bir ifade ve sondaki noktalı virgülden oluşan `mutable`anahtar sözcükten oluşur.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-173">A mutable binding statement consists of the keyword `mutable`, followed by a symbol or symbol tuple, an equals sign `=`, an expression to bind the symbol(s) to, and a terminating semicolon.</span></span>
<span data-ttu-id="b7fc2-174">Bağlı sembol (ler) in türü sağ taraftaki ifadeye göre belirlenir.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-174">The type of the bound symbol(s) is inferred based on the expression on the right hand side.</span></span> <span data-ttu-id="b7fc2-175">Bir sembol kodun ilerleyen kısımlarında yeniden bağlanmışsa, türü değişmez ve bağlanan değerin bu türle uyumlu olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-175">If a symbol is rebound later in the code, its type does not change, and the bound value needs to be compatible with that type.</span></span>

### <a name="rebinding-of-mutable-symbols"></a><span data-ttu-id="b7fc2-176">Kesilebilir sembolleri yeniden bağlama</span><span class="sxs-lookup"><span data-stu-id="b7fc2-176">Rebinding of Mutable Symbols</span></span>

<span data-ttu-id="b7fc2-177">Kesilebilir değişken, bir `set` ifadesiyle yeniden bağlanabilir.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-177">A mutable variable may be rebound using a `set` statement.</span></span>
<span data-ttu-id="b7fc2-178">Bu tür bir yeniden bağlama, arkasından bir sembol veya sembol kümesi, eşittir işareti `=`, sembolleri yeniden bağlamak için bir ifade ve bir sonlandırma noktalı virgülle oluşur `set`.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-178">Such a rebinding consists of the keyword `set`, followed by a symbol or symbol tuple, an equals sign `=`, an expression to rebind the symbol(s) to, and a terminating semicolon.</span></span>
<span data-ttu-id="b7fc2-179">Değer, bağlandığı sembolün (ler) türüyle uyumlu olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-179">The value must be compatible with the type(s) of the symbol(s) it is bound to.</span></span>

#### <a name="apply-and-reassign-statement"></a><span data-ttu-id="b7fc2-180">Apply ve-yeniden atama ekstresi</span><span class="sxs-lookup"><span data-stu-id="b7fc2-180">Apply-and-Reassign Statement</span></span>

<span data-ttu-id="b7fc2-181">Bir Apply ve-reassıgn olarak adlandırdığımız belirli bir set-deyimin türü, sağ taraftaki bir ikili işleç uygulamasından oluşuyorsa ve sonuç işlecin sol bağımsız değişkenine yeniden bağlanılacağından, birleştirme işlemi için uygun bir yol sağlar.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-181">A particular kind of set-statement we refer to as an apply-and-reassign statement provides a convenient way of concatenation if the right hand side consists of the application of a binary operator and the result is to be rebound to the left argument to the operator.</span></span> <span data-ttu-id="b7fc2-182">Örneğin,</span><span class="sxs-lookup"><span data-stu-id="b7fc2-182">For example,</span></span>
```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter += 1;
    // ...
}
```
<span data-ttu-id="b7fc2-183">`for` döngüsünün her yinelemesinde sayaç `counter` değerini artırır.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-183">increments the value of the counter `counter` in each iteration of the `for` loop.</span></span> <span data-ttu-id="b7fc2-184">Yukarıdaki kod şu şekilde eşdeğerdir</span><span class="sxs-lookup"><span data-stu-id="b7fc2-184">The code above is equivalent to</span></span> 
```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter = counter + 1;
    // ...
}
```
<span data-ttu-id="b7fc2-185">Benzer deyimler, sol taraftaki türün ifade türüyle eşleştiği tüm ikili işleçler için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-185">Similar statements are available for all binary operators in which the type of the left-hand-side matches the expression type.</span></span> <span data-ttu-id="b7fc2-186">Bu, örneğin değerleri biriktirmek için kullanışlı bir yol sağlar:</span><span class="sxs-lookup"><span data-stu-id="b7fc2-186">This provides for example a convenient way to accumulate values:</span></span>
```qsharp
mutable results = new Result[0];
for (q in qubits) {
    set results += [M(q)];
    // ...
}
```
#### <a name="update-and-reassign-statement"></a><span data-ttu-id="b7fc2-187">Update-ve-yeniden atama ekstresi</span><span class="sxs-lookup"><span data-stu-id="b7fc2-187">Update-and-Reassign Statement</span></span>

<span data-ttu-id="b7fc2-188">Sağ taraftaki kopyalama ve güncelleştirme ifadeleri için benzer bir birleştirme bulunur.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-188">A similar concatenation exists for copy-and-update expressions on the right hand side.</span></span> <span data-ttu-id="b7fc2-189">Kullanıcı tanımlı türlerde ve dizi öğelerinde adlandırılmış öğeler için birlikte, Update-ve-yeniden ata deyimleri mevcuttur.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-189">Correspondingly, update-and-reassign statements exist for named items in user-defined types as well as for array items.</span></span>  

```qsharp
newtype Complex = (Re : Double, Im : Double);

function AddAll (reals : Double[], ims : Double[]) : Complex[] {
    mutable res = Complex(0.,0.);

    for (r in reals) {
        set res w/= Re <- res::Re + r; // update-and-reassign statement
    }
    for (i in ims) {
        set res w/= Im <- res::Im + i; // update-and-reassign statement
    }
    return res;
}
```

<span data-ttu-id="b7fc2-190">Diziler söz konusu olduğunda standart kitaplıklarımız birçok yaygın dizi başlatma ve işleme ihtiyacı için gerekli araçları içerir ve bu nedenle dizi öğelerini ilk yerde güncelleştirmek zorunda kalmamak için yardımcı olur.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-190">In the case of arrays, our standard libraries contain the necessary tools for many common array initialization and manipulation needs, and thus help avoid having to update array items in the first place.</span></span> <span data-ttu-id="b7fc2-191">Update-ve-yeniden ata deyimleri gerekirse bir alternatif sağlar:</span><span class="sxs-lookup"><span data-stu-id="b7fc2-191">Update-and-reassign statements provide an alternative if needed:</span></span>

```qsharp
operation RandomInts(maxInt : Int, nrSamples : Int) : Int[] {

    mutable samples = new Double[0];
    for (i in 1 .. nrSamples) {
        set samples += [RandomInt(maxInt)];
    }
    return samples;
}

operation SampleUniformDistr(nrSamples : Int, prec : Int) : Double[] {

    let normalization = 1. / IntAsDouble(prec);
    mutable samples = RandomInts(prec, nrSamples);
    
    for (i in IndexRange(samples) {
        let value = IntAsDouble(samples[i]);
        set samples w/= i <- normalization * value; // update-and-reassign statement
    }
}

```

> [!TIP]   
> <span data-ttu-id="b7fc2-192"><xref:microsoft.quantum.arrays>' de sunulan araçlardan yararlanarak Update ve-yeniden atama deyimlerinin gereksiz bir şekilde kullanılmasını önleyin.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-192">Avoid unnecessary use of update-and-reassign statements by leveraging the tools provided in <xref:microsoft.quantum.arrays>.</span></span>

<span data-ttu-id="b7fc2-193">İşlevi</span><span class="sxs-lookup"><span data-stu-id="b7fc2-193">The function</span></span>
```qsharp
function EmbedPauli (pauli : Pauli, location : Int, n : Int) : Pauli[]
{
    mutable pauliArray = new Pauli[n];
    for (index in 0 .. n - 1) {
        set pauliArray w/= index <- 
            index == location ? pauli | PauliI;
    }    
    return pauliArray;
}
```
<span data-ttu-id="b7fc2-194">Örneğin, `Microsoft.Quantum.Arrays``ConstantArray` işlevini kullanarak basit bir şekilde basitleştirilebilir ve bir kopya ve güncelleştirme ifadesi getirebilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="b7fc2-194">for example can simply be simplified using the function `ConstantArray` in `Microsoft.Quantum.Arrays`, and returning a copy-and-update expression:</span></span>

```qsharp
function EmbedPauli (pauli : Pauli, i : Int, n : Int) : Pauli[] {
    return ConstantArray(n, PauliI) w/ i <- pauli;
}
```

### <a name="binding-scopes"></a><span data-ttu-id="b7fc2-195">Kapsamları bağlama</span><span class="sxs-lookup"><span data-stu-id="b7fc2-195">Binding Scopes</span></span>

<span data-ttu-id="b7fc2-196">Genel olarak, sembol bağlamaları kapsam dışına çıkar ve içinde oluştuğu deyim bloğunun sonunda çalışır duruma gelir.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-196">In general, symbol bindings go out of scope and become inoperative at the end of the statement block they occur in.</span></span>
<span data-ttu-id="b7fc2-197">Bu kuralın iki özel durumu vardır:</span><span class="sxs-lookup"><span data-stu-id="b7fc2-197">There are two exceptions to this rule:</span></span>

- <span data-ttu-id="b7fc2-198">Bir `for` döngüsünün döngü değişkeninin bağlaması, for döngüsünün gövdesinden, ancak döngünün sonundan sonra değil.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-198">The binding of the loop variable of a `for` loop is in scope for the body of the for loop, but not after the end of the loop.</span></span>
- <span data-ttu-id="b7fc2-199">Bir `repeat`/`until` döngüsünün üç bölümü (gövde, test ve düzeltme) tek bir kapsam olarak değerlendirilir, bu nedenle gövdede bağlanan semboller testte ve düzeltmede kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-199">All three portions of a `repeat`/`until` loop (the body, the test, and the fixup) are treated as a single scope, so symbols that are bound in the body are available in the test and in the fixup.</span></span>

<span data-ttu-id="b7fc2-200">Her iki döngü türü için, döngüden geçen her bir geçiş kendi kapsamında yürütülür, bu nedenle önceki bir geçişte bağlamalar daha sonraki bir geçişte kullanılamaz.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-200">For both types of loops, each pass through the loop executes in its own scope, so bindings from an earlier pass are not available in a later pass.</span></span>

<span data-ttu-id="b7fc2-201">Dış bloklarında sembol bağlamaları iç bloklar tarafından devralınır.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-201">Symbol bindings from outer blocks are inherited by inner blocks.</span></span>
<span data-ttu-id="b7fc2-202">Bir sembol, blok başına yalnızca bir kez bağlanabilir; kapsam içindeki başka bir sembolle aynı ada sahip bir sembol tanımlamak geçersizdir ("gölgeleme" yoktur).</span><span class="sxs-lookup"><span data-stu-id="b7fc2-202">A symbol may only be bound once per block; it is illegal to define a symbol with the same name as another symbol that is within scope (no "shadowing").</span></span>
<span data-ttu-id="b7fc2-203">Aşağıdaki diziler geçerli olacaktır:</span><span class="sxs-lookup"><span data-stu-id="b7fc2-203">The following sequences would be legal:</span></span>

```qsharp
if (a == b) {
    ...
    let n = 5;
    ...             // n is 5
}
let n = 8;
...                 // n is 8
```

<span data-ttu-id="b7fc2-204">'nı ve</span><span class="sxs-lookup"><span data-stu-id="b7fc2-204">and</span></span>

```qsharp
if (a == b) {
    ...
    let n = 5;
    ...             // n is 5
} else {
    ...
    let n = 8;
    ...             // n is 8
}
```

<span data-ttu-id="b7fc2-205">Ancak bu geçersiz olabilir:</span><span class="sxs-lookup"><span data-stu-id="b7fc2-205">But this would be illegal:</span></span>

```qsharp
let n = 5;
...                 // n is 5
let n = 8;          // Error!!
...
```

<span data-ttu-id="b7fc2-206">şöyle olacaktır:</span><span class="sxs-lookup"><span data-stu-id="b7fc2-206">as would:</span></span>

```qsharp
let n = 8;
if (a == b) {
    ...             // n is 8
    let n = 5;      // Error!
    ...
}
...
```

## <a name="control-flow"></a><span data-ttu-id="b7fc2-207">Denetim Akışı</span><span class="sxs-lookup"><span data-stu-id="b7fc2-207">Control Flow</span></span>

### <a name="for-loop"></a><span data-ttu-id="b7fc2-208">For döngüsü</span><span class="sxs-lookup"><span data-stu-id="b7fc2-208">For Loop</span></span>

<span data-ttu-id="b7fc2-209">`for` ifade, bir tamsayı aralığı veya dizi üzerinde yinelemeyi destekler.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-209">The `for` statement supports iteration over an integer range or over an array.</span></span>
<span data-ttu-id="b7fc2-210">Deyimi `for`, bir açık parantez `(`ve ardından bir sembol veya sembol kümesi, anahtar sözcük `in`, `Range` veya dizi türünde bir ifade, bir kapatma parantezi `)`ve bir deyim bloğunu içerir.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-210">The statement consists of the keyword `for`, an open parenthesis `(`, followed by a symbol or symbol tuple, the keyword `in`, an expression of type `Range` or array, a close parenthesis `)`, and a statement block.</span></span>

<span data-ttu-id="b7fc2-211">İfade bloğu (Döngünün gövdesi), her bir değere veya dizideki her bir değere bağlantılı tanımlanmış simgeler (döngü değişkenleri) ile tekrar tekrar yürütülür.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-211">The statement block (the body of the loop) is executed repeatedly, with the defined symbol(s) (the loop variable(s)) bound to each value in the range or array.</span></span>
<span data-ttu-id="b7fc2-212">Aralık ifadesi boş bir aralığa veya diziye değerlendirilirse, gövdenin hiç yürütülmeyeceğini unutmayın.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-212">Note that if the range expression evaluates to an empty range or array, the body will not be executed at all.</span></span>
<span data-ttu-id="b7fc2-213">İfade, döngü girilmeden önce tam olarak değerlendirilir ve döngü yürütülürken değişmeyecektir.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-213">The expression is fully evaluated before entering the loop, and will not change while the loop is executing.</span></span>

<span data-ttu-id="b7fc2-214">Belirtilen sembol (ler) in bağlaması sabittir ve diğer değişken bağlamalarıyla aynı kurallara uyar.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-214">The binding of the declared symbol(s) is immutable and follows the same rules as other variable bindings.</span></span> <span data-ttu-id="b7fc2-215">Özellikle, döngü değişkenlerine atama yapıldığında dizi üzerinde bir yineleme için örneğin dizi öğeleri için bir dizi öğe oluşturulabilir.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-215">In particular, it is possible to destruct e.g. array items for an iteration over an array upon assignment to the loop variable(s).</span></span>

<span data-ttu-id="b7fc2-216">Örneğin,</span><span class="sxs-lookup"><span data-stu-id="b7fc2-216">For example,</span></span>

```qsharp
// ...
for (qb in qubits) { // qubits contains a Qubit[]
    H(qb);
}

mutable results = new (Int, Results)[Length(qubits)];
for (index in 0 .. Length(qubits) - 1) {
    set results w/= index <- (index, M(qubits[index]));
}

mutable accumulated = 0;
for ((index, measured) in results) {
    if (measured == One) {
        set accumulated += 1 <<< index;
    }
}
```

<span data-ttu-id="b7fc2-217">Döngü değişkeni, her giriş gövdesine bağlanır ve gövdenin sonunda ilişkisiz olur.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-217">The loop variable is bound at each entrance to the loop body, and unbound at the end of the body.</span></span>
<span data-ttu-id="b7fc2-218">Özellikle, for döngüsü tamamlandıktan sonra döngü değişkeni bağlantılı değildir.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-218">In particular, the loop variable is not bound after the for loop is completed.</span></span>

### <a name="repeat-until-success-loop"></a><span data-ttu-id="b7fc2-219">Yineleme-Until-başarılı döngüsü</span><span class="sxs-lookup"><span data-stu-id="b7fc2-219">Repeat-Until-Success Loop</span></span>

<span data-ttu-id="b7fc2-220">`repeat` bildiri, hisse "başarılı olana kadar Yinele" deseninin modelini destekler.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-220">The `repeat` statement supports the quantum “repeat until success” pattern.</span></span>
<span data-ttu-id="b7fc2-221">Anahtar sözcüğünden `repeat`, ardından bir deyim bloğu ( _döngü_ gövdesi), anahtar sözcük `until`, bir Boole ifadesi ve bir Sonlandırıcı noktalı virgül veya anahtar sözcüğü `fixup` ve ardından başka bir deyim bloğu ( _Düzeltme_) gelir.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-221">It consists of the keyword `repeat`, followed by a statement block (the _loop_ body), the keyword `until`, a Boolean expression, and either a terminating semicolon or the keyword `fixup` followed by another statement block (the _fixup_).</span></span>
<span data-ttu-id="b7fc2-222">Döngü gövdesi, koşulu ve düzeltme tek bir kapsam olarak kabul edilir, bu nedenle gövdedeki semboller, koşul ve düzeltme içinde kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-222">The loop body, condition, and fixup are all considered to be a single scope, so symbols bound in the body are available in the condition and fixup.</span></span>

```qsharp
mutable iter = 1;
repeat {
    ProbabilisticCircuit(qs);
    let success = ComputeSuccessIndicator(qs);
}
until (success || iter > maxIter)
fixup {
    iter += 1;
    ComputeCorrection(qs);
}
```

<span data-ttu-id="b7fc2-223">Döngü gövdesi yürütülür ve ardından koşul değerlendirilir.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-223">The loop body is executed, and then the condition is evaluated.</span></span>
<span data-ttu-id="b7fc2-224">Koşul doğru ise, ifade tamamlanır; Aksi takdirde, düzeltme yürütülür ve ifade, döngü gövdesiyle başlayarak yeniden yürütülür.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-224">If the condition is true, then the statement is completed; otherwise, the fixup is executed, and the statement is re-executed starting with the loop body.</span></span>
<span data-ttu-id="b7fc2-225">Düzeltme yürütme işlemini tamamlamak deyimin kapsamını sonlandırır, böylece gövde veya Düzeltme sırasında yapılan simge bağlamaları sonraki oturumlarda kullanılamaz.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-225">Note that completing the execution of the fixup ends the scope for the statement, so that symbol bindings made during the body or fixup are not available in subsequent repetitions.</span></span>

<span data-ttu-id="b7fc2-226">Örneğin, aşağıdaki kod, Hadamard ve T kapılarını kullanarak önemli bir dönüş geçidi $V _3 = (\cıvalation+ 2 ı Z)/\sqrt{5}$ uygulayan bir dayalı devresi.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-226">For example, the following code is a probabilistic circuit that implements an important rotation gate $V_3 = (\boldone + 2 i Z) / \sqrt{5}$ using the Hadamard and T gates.</span></span>
<span data-ttu-id="b7fc2-227">Döngü, ortalama 8/5 tekrarda sona erer.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-227">The loop terminates in 8/5 repetitions on average.</span></span>
<span data-ttu-id="b7fc2-228">Ayrıntılar için bkz. [*yineleme-Until-başarılı: tek qubit unityalarının belirleyici olmayan ayrıştırma*](https://arxiv.org/abs/1311.1074) (paetznick ve svore, 2014).</span><span class="sxs-lookup"><span data-stu-id="b7fc2-228">See [*Repeat-Until-Success: Non-deterministic decomposition of single-qubit unitaries*](https://arxiv.org/abs/1311.1074) (Paetznick and Svore, 2014) for details.</span></span>

```qsharp
using (anc = Qubit()) {
    repeat {
        H(anc);
        T(anc);
        CNOT(target,anc);
        H(anc);
        Adjoint T(anc);
        H(anc);
        T(anc);
        H(anc);
        CNOT(target,anc);
        T(anc);
        Z(target);
        H(anc);
        let result = M(anc);
    } until (result == Zero);
}
```

> [!TIP]   
> <span data-ttu-id="b7fc2-229">İşlevler içinde yineleme-başarılı döngüleri kullanmaktan kaçının.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-229">Avoid using repeat-until-success loops inside functions.</span></span> <span data-ttu-id="b7fc2-230">Karşılık gelen işlevler, işlevlerde döngüler sırasında sağlanır.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-230">The corresponding functionality is provided by while loops in functions.</span></span> 

### <a name="while-loop"></a><span data-ttu-id="b7fc2-231">While döngüsü</span><span class="sxs-lookup"><span data-stu-id="b7fc2-231">While Loop</span></span>

<span data-ttu-id="b7fc2-232">Yinele-Success desenlerinin çok hisse özgü bir connotation vardır.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-232">Repeat-until-success patterns have a very quantum-specific connotation.</span></span> <span data-ttu-id="b7fc2-233">Bu diller, belirli hisse algoritmaları sınıflarında yaygın olarak kullanılır. bu nedenle, Q # içinde adanmış dil yapısı.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-233">They are widely used in particular classes of quantum algorithms -- hence the dedicated language construct in Q#.</span></span> <span data-ttu-id="b7fc2-234">Ancak, bir koşula göre kesintiye uğratır ve bu nedenle derleme sırasında yürütme uzunluğunun bilinmediği, bir hisse çalışma zamanında belirli bir ele alınabilmesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-234">However, loops that break based on a condition and whose execution length is thus unknown at compile time need to be handled with particular care in a quantum runtime.</span></span> <span data-ttu-id="b7fc2-235">Diğer yandan işlevleri içindeki kullanımları sorunlu değildir, çünkü bunlar yalnızca geleneksel (hisse olmayan) donanımda yürütülecek kodu içerir.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-235">Their use within functions on the other hand is unproblematic, since these only contain code that will be executed on conventional (non-quantum) hardware.</span></span> 

<span data-ttu-id="b7fc2-236">Q # bu nedenle, yalnızca işlevler içindeki while döngülerinin kullanımını destekler.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-236">Q# therefore supports to use of while loops within functions only.</span></span> <span data-ttu-id="b7fc2-237">`while` deyimi, bir açık parantez `(`, bir koşul (yani Boolean ifadesi), bir kapatma parantezi `)`ve bir deyim bloğunu `while`içerir.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-237">A `while` statement consists of the keyword `while`, an open parenthesis `(`, a condition (i.e. a Boolean expression), a close parenthesis `)`, and a statement block.</span></span>
<span data-ttu-id="b7fc2-238">Koşul bloğu (Döngünün gövdesi) `true`olarak değerlendirilen sürece yürütülür.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-238">The statement block (the body of the loop) is executed as long as the condition evaluates to `true`.</span></span>

```qsharp
// ...
mutable (item, index) = (-1, 0);
while (index < Length(arr) && item < 0) { 
    set item = arr[index];
    set index += 1;
}
```

### <a name="conditional-statement"></a><span data-ttu-id="b7fc2-239">Koşul ekstresi</span><span class="sxs-lookup"><span data-stu-id="b7fc2-239">Conditional Statement</span></span>

<span data-ttu-id="b7fc2-240">`if` deyimleri koşullu yürütmeyi destekler.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-240">The `if` statement supports conditional execution.</span></span>
<span data-ttu-id="b7fc2-241">Anahtar sözcüğünden `if`, açık bir parantez `(`, Boole ifadesi, kapatma parantezi `)`ve deyim bloğu ( _then_ bloğu) oluşur.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-241">It consists of the keyword `if`, an open parenthesis `(`, a Boolean expression, a close parenthesis `)`, and a statement block (the _then_ block).</span></span>
<span data-ttu-id="b7fc2-242">Bu, her biri anahtar sözcük `elif`, bir açık parantez `(`, bir Boole ifadesi, kapatma parantezi `)`ve bir deyim bloğu ( _Else-If_ bloğu) içeren herhangi bir sayıda Else-If yan tümcesi gelebilir.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-242">This may be followed by any number of else-if clauses, each of which consists of the keyword `elif`, an open parenthesis `(`, a Boolean expression, a close parenthesis `)`, and a statement block (the _else-if_ block).</span></span>
<span data-ttu-id="b7fc2-243">Son olarak, deyimi isteğe bağlı olarak bir else yan tümcesi ile bitebileceği gibi, daha sonra başka bir ifade bloğunun ( _Else_ bloğu) tarafından izlenen `else` anahtar sözcükten oluşur.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-243">Finally, the statement may optionally finish with an else clause, which consists of the keyword `else` followed by another statement block (the _else_ block).</span></span>
<span data-ttu-id="b7fc2-244">Koşul değerlendirilir ve true ise blok yürütülür.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-244">The condition is evaluated, and if it is true, the then block is executed.</span></span>
<span data-ttu-id="b7fc2-245">Koşul yanlışsa, ilk else-if koşulu değerlendirilir; true ise, Else-If bloğu yürütülür.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-245">If the condition is false, then the first else-if condition is evaluated; if it is true, that else-if block is executed.</span></span>
<span data-ttu-id="b7fc2-246">Aksi takdirde, ikinci Else-If bloğu test edilir ve ardından üçüncü, vb. doğru bir koşula sahip bir yan tümce ile karşılaşılana ya da başka bir else-if yan tümcesi içermeyecek şekilde devam eder.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-246">Otherwise, the second else-if block is tested, and then the third, and so on until either a clause with a true condition is encountered or there are no more else-if clauses.</span></span>
<span data-ttu-id="b7fc2-247">Özgün If koşulu ve tüm else-if yan tümceleri yanlış olarak değerlendirilmişse, varsa Else bloğu yürütülür.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-247">If the original if condition and all else-if clauses evaluate to false, the else block is executed if one was provided.</span></span>

<span data-ttu-id="b7fc2-248">Hangi bloğun yürütüldüğü, kendi kapsamında yürütüleceğini unutmayın.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-248">Note that whichever block is executed is executed in its own scope.</span></span>
<span data-ttu-id="b7fc2-249">Daha sonra, else-if veya else bloğunun içinde yapılan bağlamalar, IF ifadesinin sonundan sonra görünmez.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-249">Bindings made inside of a then, else-if, or else block are not visible after the end of the if statement.</span></span>

<span data-ttu-id="b7fc2-250">Örneğin,</span><span class="sxs-lookup"><span data-stu-id="b7fc2-250">For example,</span></span>

```qsharp
if (result == One) {
    X(target);
} 
```

<span data-ttu-id="b7fc2-251">or</span><span class="sxs-lookup"><span data-stu-id="b7fc2-251">or</span></span>

```qsharp
if (i == 1) {
    X(target);
} elif (i == 2) {
    Y(target);
} else {
    Z(target);
}
```

### <a name="return"></a><span data-ttu-id="b7fc2-252">döndürülmesini</span><span class="sxs-lookup"><span data-stu-id="b7fc2-252">Return</span></span>

<span data-ttu-id="b7fc2-253">Return deyimleri bir işlemin veya işlevin yürütmesini sonlandırır ve çağırana bir değer döndürür.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-253">The return statement ends execution of an operation or function and returns a value to the caller.</span></span>
<span data-ttu-id="b7fc2-254">Anahtar sözcüğünden `return`, ardından uygun türdeki bir ifade ve sonlandırma noktalı virgülünden oluşur.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-254">It consists of the keyword `return`, followed by an expression of the appropriate type, and a terminating semicolon.</span></span>

<span data-ttu-id="b7fc2-255">Boş bir tanımlama grubu döndüren çağrılabilir, `()`, return ifadesine gerek yoktur.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-255">A callable that returns an empty tuple, `()`, does not require a return statement.</span></span>
<span data-ttu-id="b7fc2-256">Erken çıkış isteniyorsa, bu durumda `return ()` kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-256">If an early exit is desired, `return ()` may be used in this case.</span></span>
<span data-ttu-id="b7fc2-257">Diğer herhangi bir tür döndüren callables, son Return ifadesine gerek duyar.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-257">Callables that return any other type require a final return statement.</span></span>

<span data-ttu-id="b7fc2-258">Bir işlem içinde en fazla dönüş deyimi sayısı yoktur.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-258">There is no maximum number of return statements within an operation.</span></span>
<span data-ttu-id="b7fc2-259">Deyimler bir blok içindeki Return deyimini izif ise derleyici bir uyarı verebilir.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-259">The compiler may emit a warning if statements follow a return statement within a block.</span></span>

<span data-ttu-id="b7fc2-260">Örneğin,</span><span class="sxs-lookup"><span data-stu-id="b7fc2-260">For example,</span></span>

```qsharp
return 1;
```

<span data-ttu-id="b7fc2-261">or</span><span class="sxs-lookup"><span data-stu-id="b7fc2-261">or</span></span>

```qsharp
return ();
```

<span data-ttu-id="b7fc2-262">or</span><span class="sxs-lookup"><span data-stu-id="b7fc2-262">or</span></span>

```qsharp
return (results, qubits);
```

### <a name="fail"></a><span data-ttu-id="b7fc2-263">Neden</span><span class="sxs-lookup"><span data-stu-id="b7fc2-263">Fail</span></span>

<span data-ttu-id="b7fc2-264">Fail deyimleri bir işlemin yürütülmesini sonlandırır ve çağırana bir hata değeri döndürür.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-264">The fail statement ends execution of an operation and returns an error value to the caller.</span></span>
<span data-ttu-id="b7fc2-265">Anahtar sözcüğünden `fail`, ardından bir dize ve Sonlandırıcı noktalı virgülden oluşur.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-265">It consists of the keyword `fail`, followed by a string and a terminating semicolon.</span></span>
<span data-ttu-id="b7fc2-266">Dize, hata iletisi olarak klasik sürücüye döndürülür.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-266">The string is returned to the classical driver as the error message.</span></span>

<span data-ttu-id="b7fc2-267">İşlemdeki başarısızlık deyimlerinin sayısı üzerinde hiçbir kısıtlama yoktur.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-267">There is no restriction on the number of fail statements within an operation.</span></span>
<span data-ttu-id="b7fc2-268">Deyimler bir blok içindeki bir fail deyimini izif ise derleyici bir uyarı verebilir.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-268">The compiler may emit a warning if statements follow a fail statement within a block.</span></span>

<span data-ttu-id="b7fc2-269">Örneğin,</span><span class="sxs-lookup"><span data-stu-id="b7fc2-269">For example,</span></span>

```qsharp
fail $"Impossible state reached";
```

<span data-ttu-id="b7fc2-270">or</span><span class="sxs-lookup"><span data-stu-id="b7fc2-270">or</span></span>

```qsharp
fail $"Syndrome {syn} is incorrect";
```

## <a name="qubit-management"></a><span data-ttu-id="b7fc2-271">Qubit yönetimi</span><span class="sxs-lookup"><span data-stu-id="b7fc2-271">Qubit Management</span></span>

<span data-ttu-id="b7fc2-272">Bir işlevin gövdesinde bu deyimlerden hiçbirine izin verilmediğini unutmayın.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-272">Note that none of these statements are allowed within the body of a function.</span></span>
<span data-ttu-id="b7fc2-273">Bunlar yalnızca işlemler içinde geçerlidir.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-273">They are only valid within operations.</span></span>

### <a name="clean-qubits"></a><span data-ttu-id="b7fc2-274">Qubit Temizleme</span><span class="sxs-lookup"><span data-stu-id="b7fc2-274">Clean Qubits</span></span>

<span data-ttu-id="b7fc2-275">`using` deyimleri, bir bildirim bloğu sırasında kullanılmak üzere yeni qubit almak için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-275">The `using` statement is used to acquire new qubits for use during a statement block.</span></span>
<span data-ttu-id="b7fc2-276">Qubits 'in hesaplama `Zero` durumuna başlatılması garanti edilir.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-276">The qubits are guaranteed to be initialized to the computational `Zero` state.</span></span>
<span data-ttu-id="b7fc2-277">Qubits, bildiri bloğunun sonundaki hesaplama `Zero` durumunda olmalıdır; simülatörleri bunu zorunlu tutmaları önerilir.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-277">The qubits should be in the computational `Zero` state at the end of the statement block; simulators are encouraged to enforce this.</span></span>

<span data-ttu-id="b7fc2-278">İfade, anahtar sözcüğünden `using`, ardından bir açık parantez `(`, bir bağlama, bir kapatma parantezi `)`ve qubits 'in kullanılabileceği bildiri bloğunu içerir.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-278">The statement consists of the keyword `using`, followed by an open parenthesis `(`, a binding, a close parenthesis `)`, and the statement block within which the qubits will be available.</span></span>
<span data-ttu-id="b7fc2-279">Bağlama `let` deyimleriyle aynı düzeni izler: tek bir sembol veya sembol tanımlama grubu, ardından eşittir işareti `=`ve tek bir değer ya da eşleşen bir başlatıcı grubu.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-279">The binding follows the same pattern as `let` statements: either a single symbol or a tuple of symbols, followed by an equals sign `=`, and either a single value or a matching tuple of initializers.</span></span>
<span data-ttu-id="b7fc2-280">Başlatıcılar, `Qubit()`olarak belirtilen tek bir qubit için veya `Qubit[`, `Int` ifadesi ve `]`belirtilen bir qubit dizisi için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-280">Initializers are available either for a single qubit, indicated as `Qubit()`, or an array of qubits, indicated by `Qubit[`, an `Int` expression, and `]`.</span></span>

<span data-ttu-id="b7fc2-281">Örneğin,</span><span class="sxs-lookup"><span data-stu-id="b7fc2-281">For example,</span></span>

```qsharp
using (q = Qubit()) {
    // ...
}
using ((ancilla, qubits) = (Qubit(), Qubit[bits * 2 + 3])) {
    // ...
}
```

### <a name="dirty-qubits"></a><span data-ttu-id="b7fc2-282">Kirli qubits</span><span class="sxs-lookup"><span data-stu-id="b7fc2-282">Dirty Qubits</span></span>

<span data-ttu-id="b7fc2-283">`borrowing` deyimleri, geçici kullanım için qubits almak için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-283">The `borrowing` statement is used to obtain qubits for temporary use.</span></span> <span data-ttu-id="b7fc2-284">İfade, anahtar sözcüğünden `borrowing`, ardından bir açık parantez `(`, bir bağlama, bir kapatma parantezi `)`ve qubits 'in kullanılabileceği bildiri bloğunu içerir.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-284">The statement consists of the keyword `borrowing`, followed by an open parenthesis `(`, a binding, a close parenthesis `)`, and the statement block within which the qubits will be available.</span></span>
<span data-ttu-id="b7fc2-285">Bağlama, bir `using` bildirimiyle aynı model ve kurallara uyar.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-285">The binding follows the same pattern and rules as the one in a `using` statement.</span></span>

<span data-ttu-id="b7fc2-286">Örneğin,</span><span class="sxs-lookup"><span data-stu-id="b7fc2-286">For example,</span></span>

```qsharp
borrowing (q = Qubit()) {
    // ...
}
borrowing ((ancilla, qubits) = (Qubit(), Qubit[bits * 2 + 3])) {
    // ...
}
```

<span data-ttu-id="b7fc2-287">Ödünç alınan qubits, bilinmeyen bir durumda ve bildiri bloğunun sonundaki kapsam dışına çıkar.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-287">The borrowed qubits are in an unknown state and go out of scope at the end of the statement block.</span></span>
<span data-ttu-id="b7fc2-288">Ödünç alma, qubits 'i ödünç aldıkları aynı durumda bırakır, yani deyimin başındaki ve sonundaki durumları aynı olmalıdır. bu durum, ifade bloğunun başındaki ve sonundaki durumunun aynı olması beklenir.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-288">The borrower commits to leaving the qubits in the same state they were in when they were borrowed, i.e. their state at the beginning and at the end of the statement block is expected to be the same.</span></span>
<span data-ttu-id="b7fc2-289">Özellikle bu durum klasik bir durum değildir; çoğu durumda, ödünç alınan kapsamlar ölçüm içermemelidir.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-289">This state in particular is not necessarily a classical state, such that in most cases, borrowing scopes should not contain measurements.</span></span> 

<span data-ttu-id="b7fc2-290">Bu tür qugeler genellikle "kirli anyenla" olarak bilinir.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-290">Such qubits are often known as “dirty ancilla”.</span></span>
<span data-ttu-id="b7fc2-291">Düzenleme, bir kirli kullanımı örneği için Toffoli tabanlı modüler çarpma (haner, Roetteler ve Svore 2017) [*ile 2n + 2 qubit kullanarak*](https://arxiv.org/abs/1611.07995) bkz.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-291">See [*Factoring using 2n+2 qubits with Toffoli based modular multiplication*](https://arxiv.org/abs/1611.07995) (Haner, Roetteler, and Svore 2017) for an example of dirty ancilla use.</span></span>

<span data-ttu-id="b7fc2-292">Qubits 'i ödünç alırken, sistem önce kullanımda olan ancak `borrowing` ifadesinin gövdesi sırasında erişilemeyen qubits 'ten gelen isteği doldurmaya çalışacaktır.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-292">When borrowing qubits, the system will first try to fill the request from qubits that are in use but that are not accessed during the body of the `borrowing` statement.</span></span>
<span data-ttu-id="b7fc2-293">Bu tür qubit yoksa, isteği tamamlayacak yeni qubit ayırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-293">If there aren't enough such qubits, then it will allocate new qubits to complete the request.</span></span>

## <a name="conjugations"></a><span data-ttu-id="b7fc2-294">Conjugations</span><span class="sxs-lookup"><span data-stu-id="b7fc2-294">Conjugations</span></span>

<span data-ttu-id="b7fc2-295">Klasik bitlerin aksine, qubits 'in hala bir daha açık olması durumunda qubits 'in kalan hesaplamada istenmeyen etkileri olabildiğinden, hisse bitlerinin serbest bırakılması biraz daha karmaşıktır.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-295">In contrast to classical bits, releasing quantum memory is slightly more involved since blindly resetting qubits can have undesired effects on the remaining computation if the qubits are still entangled.</span></span> <span data-ttu-id="b7fc2-296">Bu, belleğin serbest bırakılmasından önce düzgün bir şekilde "geri alma" sırasında gerçekleştirilen hesaplamaları önlenebilir.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-296">This can be avoided by properly "undoing" performed computations prior to releasing the memory.</span></span> <span data-ttu-id="b7fc2-297">Bu nedenle, hisse kullanımı için genel bir model aşağıda verilmiştir:</span><span class="sxs-lookup"><span data-stu-id="b7fc2-297">A common pattern in quantum computing is hence the following:</span></span> 

```qsharp
operation ApplyWith<'T>(
    outerOperation : ('T => Unit is Adj), 
    innerOperation : ('T => Unit), 
    target : 'T) 
: Unit {

    outerOperation(target);
    innerOperation(target);
    Adjoint outerOperation(target);
}
```

<span data-ttu-id="b7fc2-298">: yeni: 0,9 sürümümüzden başlayarak, yukarıdaki dönüşümü uygulayan bir Birleşik bildirim bildirisini destekliyoruz.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-298">:new: Starting with our 0.9 release, we support a conjugation statement that implements the transformation above.</span></span> <span data-ttu-id="b7fc2-299">Bu ifadeyi kullanarak, işlem `ApplyWith` aşağıdaki şekilde uygulanabilir:</span><span class="sxs-lookup"><span data-stu-id="b7fc2-299">Using that statement, the operation `ApplyWith` can be implemented in the following way:</span></span>

```qsharp
operation ApplyWith<'T>(
    outerOperation : ('T => Unit is Adj), 
    innerOperation : ('T => Unit), 
    target : 'T) 
: Unit {

    within{ 
        outerOperation(target);
    }
    apply {
        innerOperation(target);
    }
}
```
<span data-ttu-id="b7fc2-300">Bu tür bir birleşim deyimi, dış ve iç dönüşüm işlem olarak hazır değilse ancak birkaç deyimden oluşan bir blok tarafından tanımlanmakla daha kullanışlı hale gelirse çok daha yararlıdır.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-300">Such a conjugation statement obviously becomes far more useful if the outer and inner transformation are not readily available as operations but are instead more convenient to describe by a block consisting of several statements.</span></span> 

<span data-ttu-id="b7fc2-301">İçindeki blok içinde tanımlanan deyimler için ters dönüşüm, derleyici tarafından otomatik olarak oluşturulur ve Apply-Block tamamlandıktan sonra yürütülür.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-301">The inverse transformation for the statements defined in the within-block is automatically generated by the compiler and executed after the apply-block completes.</span></span> <span data-ttu-id="b7fc2-302">İçindeki blok içinde kullanılan herhangi bir değişebilir değişken, Apply-Block içinde yeniden bağlanamaz, oluşturulan dönüşümün, hesaplamanın içindeki adeklik olduğu garanti edilir.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-302">Since any mutable variables used as part of the within-block cannot be rebound in the apply-block, the generated transformation is guaranteed to be the adjoint of the computation in the within-block.</span></span> 

## <a name="expression-evaluation-statements"></a><span data-ttu-id="b7fc2-303">İfade değerlendirme deyimleri</span><span class="sxs-lookup"><span data-stu-id="b7fc2-303">Expression Evaluation Statements</span></span>

<span data-ttu-id="b7fc2-304">`Unit` türündeki herhangi bir çağrı ifadesi bir deyim olarak kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-304">Any call expression of type `Unit` may be used as a statement.</span></span>
<span data-ttu-id="b7fc2-305">Bu, deyimin amacı örtülü hisse durumu ' nu değiştirecek olduğundan, bu, öncelikle `Unit` döndüren qubits üzerinde işlemler çağrılırken kullanılır.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-305">This is primarily of use when calling operations on qubits that return `Unit` because the purpose of the statement is to modify the implicit quantum state.</span></span>
<span data-ttu-id="b7fc2-306">İfade değerlendirme deyimleri, sonlandırma noktalı virgül gerektirir.</span><span class="sxs-lookup"><span data-stu-id="b7fc2-306">Expression evaluation statements require a terminating semicolon.</span></span>

<span data-ttu-id="b7fc2-307">Örneğin,</span><span class="sxs-lookup"><span data-stu-id="b7fc2-307">For example,</span></span>

```qsharp
X(q);
CNOT(control, target);
Adjoint T(q);
```
