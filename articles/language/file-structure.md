---
title: Dosya yapısı | Microsoft Docs
description: 'Q # dosya yapısı'
author: QuantumWriter
uid: microsoft.quantum.language.file-structure
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 40b2e7ddf5def6285250dffe130b152429dce1f8
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2019
ms.locfileid: "73185197"
---
# <a name="file-structure"></a><span data-ttu-id="60e7a-103">Dosya Yapısı</span><span class="sxs-lookup"><span data-stu-id="60e7a-103">File Structure</span></span>

<span data-ttu-id="60e7a-104">Bir Q # dosyası, bir dizi ad alanı bildirimi içerir.</span><span class="sxs-lookup"><span data-stu-id="60e7a-104">A Q# file consists of a sequence of namespace declarations.</span></span>
<span data-ttu-id="60e7a-105">Her ad alanı bildirimi, Kullanıcı tanımlı türler, işlemler ve işlevler için bildirimler içerir.</span><span class="sxs-lookup"><span data-stu-id="60e7a-105">Each namespace declaration contains declarations for user-defined types, operations, and functions.</span></span>
<span data-ttu-id="60e7a-106">Bir ad alanı bildirimi her bir tür bildirime ve herhangi bir sıraya sahip olabilir.</span><span class="sxs-lookup"><span data-stu-id="60e7a-106">A namespace declaration may contain any number of each type of declaration, and in any order.</span></span>
<span data-ttu-id="60e7a-107">Bir ad alanı bildiriminin dışında görünebilen tek metin açıklamalardır.</span><span class="sxs-lookup"><span data-stu-id="60e7a-107">The only text that can appear outside of a namespace declaration is comments.</span></span>
<span data-ttu-id="60e7a-108">Özellikle, bir ad alanı için bildirim öncesinde belge açıklamaları.</span><span class="sxs-lookup"><span data-stu-id="60e7a-108">In particular, documentation comments for a namespace precede the declaration.</span></span>

## <a name="namespace-declarations"></a><span data-ttu-id="60e7a-109">Ad alanı bildirimleri</span><span class="sxs-lookup"><span data-stu-id="60e7a-109">Namespace Declarations</span></span>

<span data-ttu-id="60e7a-110">Bir Q # dosyası genellikle tam olarak bir ad alanı bildirimine sahip olur, ancak None (ve boş veya yalnızca açıklama içeremez) olabilir veya birden çok ad alanı içerebilir.</span><span class="sxs-lookup"><span data-stu-id="60e7a-110">A Q# file will typically have exactly one namespace declaration, but may have none (and be empty or just contain comments) or may contain multiple namespaces.</span></span>
<span data-ttu-id="60e7a-111">Ad alanı bildirimleri iç içe olamaz.</span><span class="sxs-lookup"><span data-stu-id="60e7a-111">Namespace declarations may not be nested.</span></span>

<span data-ttu-id="60e7a-112">Aynı ad alanı, aynı ada sahip hiçbir tür, işlem veya işlev bildirimi olmadığı sürece birlikte derlenen birden fazla Q # dosyasında da bildirilemez.</span><span class="sxs-lookup"><span data-stu-id="60e7a-112">The same namespace may be declared in multiple Q# files that are compiled together, as long as there are no type, operation, or function declarations with the same name.</span></span>
<span data-ttu-id="60e7a-113">Özellikle, bildirimler özdeş olsa bile, birden çok dosyada aynı ad alanında aynı türü tanımlamak geçersizdir.</span><span class="sxs-lookup"><span data-stu-id="60e7a-113">In particular, it is invalid to define the same type in the same namespace in multiple files, even if the declarations are identical.</span></span>

<span data-ttu-id="60e7a-114">Bir ad alanı bildirimi, anahtar sözcüğünden `namespace`, ardından ad alanının adı, açık bir küme ayracı `{`, ad alanında yer alan bildirimler ve bir kapalı ayraç `}`oluşur.</span><span class="sxs-lookup"><span data-stu-id="60e7a-114">A namespace declaration consists of the keyword `namespace`, followed by the name of the namespace, an open brace `{`, the declarations contained in the namespace, and a close brace `}`.</span></span>
<span data-ttu-id="60e7a-115">Ad alanı adları, `.`noktalarla ayrılmış bir veya daha fazla yasal sembol dizisinin .NET örüntüsünün izler.</span><span class="sxs-lookup"><span data-stu-id="60e7a-115">Namespace names follow the .NET pattern of a sequence of one or more legal symbols separated by periods `.`.</span></span>
<span data-ttu-id="60e7a-116">Örneğin, `MyQuantumStuff` ve `Microsoft.Quantum.Canon` geçerli ad alanı adlarıdır.</span><span class="sxs-lookup"><span data-stu-id="60e7a-116">For instance, `MyQuantumStuff` and `Microsoft.Quantum.Canon` are valid namespace names.</span></span>
<span data-ttu-id="60e7a-117">Kurala göre, bir ad alanı adındaki semboller büyük harfli olur, ancak bu gerekli değildir.</span><span class="sxs-lookup"><span data-stu-id="60e7a-117">By convention, the symbols in a namespace name are capitalized, but this is not required.</span></span>

<span data-ttu-id="60e7a-118">Bildirimler, bir ad alanı bildiriminde herhangi bir sırada görünebilir.</span><span class="sxs-lookup"><span data-stu-id="60e7a-118">Declarations may appear in any order in a namespace declaration.</span></span>
<span data-ttu-id="60e7a-119">Bir dosyada daha fazla bildirimde bulunan türlerin veya sabit labların başvuruları düzgün şekilde çözümlenir; bir başvurunun önüne geçmek için tür, işlem veya işlev bildirimine gerek yoktur.</span><span class="sxs-lookup"><span data-stu-id="60e7a-119">References to types or callables declared further down in a file are resolved properly; there is no need for the type, operation, or function declaration to precede a reference to it.</span></span>

## <a name="open-directives"></a><span data-ttu-id="60e7a-120">Açık yönergeler</span><span class="sxs-lookup"><span data-stu-id="60e7a-120">Open Directives</span></span>

<span data-ttu-id="60e7a-121">Bir ad alanı bloğunda, belirli bir ad alanında tanımlanan tüm türleri ve callabları içeri aktarmak için `open` yönergesi kullanılabilir ve bunlara nitelenmemiş adlarıyla başvurabilirler.</span><span class="sxs-lookup"><span data-stu-id="60e7a-121">Within a namespace block, the `open` directive may be used to import all types and callables defined in a certain namespace and refer to them by their unqualified name.</span></span> 

<span data-ttu-id="60e7a-122">Böyle bir `open` yönergesi `open` anahtar sözcüğünden, ardından açılacak ad alanı ve bir sonlandırma noktalı virgülünden oluşur.</span><span class="sxs-lookup"><span data-stu-id="60e7a-122">Such an `open` directive consists of the `open` keyword, followed by the namespace to be opened and a terminating semicolon.</span></span>

<span data-ttu-id="60e7a-123">Örneğin,</span><span class="sxs-lookup"><span data-stu-id="60e7a-123">For instance,</span></span>

```qsharp
open Microsoft.Quantum.Canon;
```

<span data-ttu-id="60e7a-124">İsteğe bağlı olarak, açık ad alanı için bir kısa ad, bu ad alanındaki tüm öğelerin tanımlanmış kısa ad ile nitelendirilerek (ve gerek olması) tanımlanabilir.</span><span class="sxs-lookup"><span data-stu-id="60e7a-124">Optionally, a short name for the opened namespace may be defined such that all elements from that namespace can (and need) to be qualified by the defined short name.</span></span> <span data-ttu-id="60e7a-125">Bu tür bir kısa ad, bir `open` yönergesinde noktalı virgülden önce istenen kısa ad anahtar sözcüğü eklenerek `as` tanımlanır:</span><span class="sxs-lookup"><span data-stu-id="60e7a-125">Such a short name is defined by adding the keyword `as` followed by the desired short name before the semicolon in an `open` directive:</span></span>

```qsharp
open Microsoft.Quantum.Math as Math;
```

<span data-ttu-id="60e7a-126">Tüm `open` yönergeleri, ad alanı bloğunda `function`, `operation`veya `newtype` bildirimlerinden önce gelmelidir.</span><span class="sxs-lookup"><span data-stu-id="60e7a-126">All `open` directives must appear before any `function`, `operation`, or `newtype` declarations in the namespace block.</span></span>
<span data-ttu-id="60e7a-127">`open` yönergesi, bir dosya içindeki tüm ad alanı bloğunun tamamına uygulanır.</span><span class="sxs-lookup"><span data-stu-id="60e7a-127">The `open` directive applies to the entire namespace block within a file.</span></span>

## <a name="user-defined-type-declarations"></a><span data-ttu-id="60e7a-128">Kullanıcı tanımlı tür bildirimleri</span><span class="sxs-lookup"><span data-stu-id="60e7a-128">User-Defined Type Declarations</span></span>

<span data-ttu-id="60e7a-129">Q #, kullanıcıların, [Q # tür modeli](xref:microsoft.quantum.language.type-model) bölümünde açıklandığı gibi Kullanıcı tanımlı yeni türler bildirmesi için bir yol sağlar.</span><span class="sxs-lookup"><span data-stu-id="60e7a-129">Q# provides a way for users to declare new user-defined types, as described in the [Q# type model](xref:microsoft.quantum.language.type-model) section.</span></span>
<span data-ttu-id="60e7a-130">Temel türler özdeş olsa bile Kullanıcı tanımlı türler farklıdır.</span><span class="sxs-lookup"><span data-stu-id="60e7a-130">User-defined types are distinct even if the base types are identical.</span></span>
<span data-ttu-id="60e7a-131">Özellikle, temeldeki türler özdeş olsa bile, iki Kullanıcı tanımlı türün değerleri arasında otomatik dönüşüm yoktur.</span><span class="sxs-lookup"><span data-stu-id="60e7a-131">In particular, there is no automatic conversion between values of two user-defined types even if the underlying types are identical.</span></span>

<span data-ttu-id="60e7a-132">Kullanıcı tanımlı tür bildirimi, anahtar sözcüğünden `newtype`, ardından Kullanıcı tanımlı türün adı, bir `=`, geçerli bir tür belirtimi ve sonlandırma noktalı virgülünden oluşur.</span><span class="sxs-lookup"><span data-stu-id="60e7a-132">A user-defined type declaration consists of the keyword `newtype`, followed by the name of the user-defined type, an `=`, a valid type specification, and a terminating semicolon.</span></span>

<span data-ttu-id="60e7a-133">Örnek:</span><span class="sxs-lookup"><span data-stu-id="60e7a-133">For example:</span></span>

```qsharp
newtype PairOfInts = (Int, Int);
```

<span data-ttu-id="60e7a-134">Her Q # kaynak dosyası herhangi bir sayıda kullanıcı tanımlı tür bildirebilir.</span><span class="sxs-lookup"><span data-stu-id="60e7a-134">Each Q# source file may declare any number of user-defined types.</span></span>
<span data-ttu-id="60e7a-135">Tür adları ad alanı içinde benzersiz olmalıdır ve işlem ve işlev adlarıyla çakışmayabilir.</span><span class="sxs-lookup"><span data-stu-id="60e7a-135">Type names must be unique within a namespace and may not conflict with operation and function names.</span></span>

<span data-ttu-id="60e7a-136">Kullanıcı tanımlı türler arasında döngüsel bağımlılıklar tanımlamak mümkün değildir.</span><span class="sxs-lookup"><span data-stu-id="60e7a-136">It is not possible to define circular dependencies between user defined types.</span></span> <span data-ttu-id="60e7a-137">Bu nedenle, özyinelemeli türler Q # içinde mümkün değildir.</span><span class="sxs-lookup"><span data-stu-id="60e7a-137">Recursive types are thus not possible within Q#.</span></span>

## <a name="operation-declarations"></a><span data-ttu-id="60e7a-138">İşlem bildirimleri</span><span class="sxs-lookup"><span data-stu-id="60e7a-138">Operation Declarations</span></span>

<span data-ttu-id="60e7a-139">İşlemler, yaklaşık olarak diğer dillerdeki işlevlere benzeyen Q # ' ın temel sayısıdır.</span><span class="sxs-lookup"><span data-stu-id="60e7a-139">Operations are the core of Q#, roughly analogous to functions in other languages.</span></span>
<span data-ttu-id="60e7a-140">Her Q # kaynak dosyası herhangi bir sayıda işlem tanımlayabilir.</span><span class="sxs-lookup"><span data-stu-id="60e7a-140">Each Q# source file may define any number of operations.</span></span>

<span data-ttu-id="60e7a-141">İşlem adları ad alanı içinde benzersiz olmalıdır ve tür ve işlev adlarıyla çakışmayabilir.</span><span class="sxs-lookup"><span data-stu-id="60e7a-141">Operation names must be unique within a namespace and may not conflict with type and function names.</span></span>

<span data-ttu-id="60e7a-142">İşlem bildirimleri, anahtar `operation`sözcüğünden oluşur, ardından işlem adı olan sembol tarafından, işlem için bağımsız değişkenleri tanımlayan türü belirlenmiş bir tanımlayıcı tanımlama grubu, iki nokta üst üste `:`, işlemin sonuç türünü açıklayan bir tür ek açıklaması, isteğe bağlı olarak, işlem özelliklerine sahip bir ek açıklama, açık bir küme ayracı `{`, işlem bildiriminin gövdesi ve bir son kapanış ayracı `}`.</span><span class="sxs-lookup"><span data-stu-id="60e7a-142">An operation declarations consists of the keyword `operation`, followed by the symbol that is the operation’s name, a typed identifier tuple that defines the arguments to the operation, a colon `:`, a type annotation that describes the operation’s result type, optionally an annotation with the operation characteristics, an open brace `{`, the body of the operation declaration, and a final closing brace `}`.</span></span>

<span data-ttu-id="60e7a-143">İşlem bildiriminin gövdesi, varsayılan uygulamadan ya da bir uzmanlık listesinden oluşur.</span><span class="sxs-lookup"><span data-stu-id="60e7a-143">The body of the operation declaration either consists of the default implementation or of a list of specializations.</span></span>
<span data-ttu-id="60e7a-144">Varsayılan gövde özelleştirmesi yalnızca uygulamanın açıkça belirtilmesi gerekiyorsa, varsayılan uygulama doğrudan bildirim içinde belirtilebilir.</span><span class="sxs-lookup"><span data-stu-id="60e7a-144">The default implementation can be specified directly within the declaration if only the implementation of the default body specialization needs to specified explicitly.</span></span>
<span data-ttu-id="60e7a-145">Bu durumda, bildirimdeki işlem özelliklerine sahip bir ek açıklama derleyicinin varsayılan uygulamayı temel alarak diğer özelleştirilmiş oluşturmaları otomatik olarak oluşturması için yararlıdır.</span><span class="sxs-lookup"><span data-stu-id="60e7a-145">In this case, an annotation with the operation characteristics in the declaration is useful to ensure that the compiler auto-generates other specializations based on the default implementation.</span></span> 

<span data-ttu-id="60e7a-146">Örneğin:</span><span class="sxs-lookup"><span data-stu-id="60e7a-146">For example</span></span> 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit 
is Adj + Ctl { // implies the existence of an adjoint, a controlled, and a controlled adjoint specialization
    H(here);
    CNOT(here, there);
}
```

<span data-ttu-id="60e7a-147">İşlem özellikleri, hangi tür nesnelerin beyan edilen işleme uygulanabileceğini ve sahip oldukları etkiyi tanımlar.</span><span class="sxs-lookup"><span data-stu-id="60e7a-147">Operation characteristics define what kinds of functors can be applied to the declared operation, and what effect they have.</span></span> <span data-ttu-id="60e7a-148">Bir işlem Unitary dönüştürmesi uygularsa, *adjointed* veya *denetimli*olduğunda işlemin nasıl davrandığını tanımlamak mümkündür.</span><span class="sxs-lookup"><span data-stu-id="60e7a-148">If an operation implements a unitary transformation, then it is possible to define how the operation acts when *adjointed* or *controlled*.</span></span>
<span data-ttu-id="60e7a-149">Bu uzmanlıklar, işlem imzasının bir parçası olarak bildirilebilecek.</span><span class="sxs-lookup"><span data-stu-id="60e7a-149">The existence of these specializations can be declared as part of the operation signature.</span></span> <span data-ttu-id="60e7a-150">Bu tür örtülü olarak tanımlanmış her özelleştirme için karşılık gelen uygulama derleyici tarafından oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="60e7a-150">The corresponding implementation for each such implicitly declared specialization is then generated by the compiler.</span></span> <span data-ttu-id="60e7a-151">Yukarıdaki örnekte, derleyici tarafından bir adjoint, denetimli ve denetlenen bir adjoint özelleştirmesi oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="60e7a-151">In the example above, an adjoint, a controlled, and a controlled adjoint specialization are generated by the compiler.</span></span> 

<span data-ttu-id="60e7a-152">Uygulamanın derleyici tarafından üretilebileceği durumda, açıkça belirtilebilir.</span><span class="sxs-lookup"><span data-stu-id="60e7a-152">In the case where the implementation cannot be generated by the compiler, it can be explicitly specified.</span></span> <span data-ttu-id="60e7a-153">Bu tür açık Özelleştirme bildirimleri, belirli bir özelleşmenin nasıl derlenildiği veya Kullanıcı tanımlı bir uygulamanın nasıl oluşturulacağını açıklığa kavuşturacak uygun bir oluşturma yönergesi olabilir.</span><span class="sxs-lookup"><span data-stu-id="60e7a-153">Such explicit specialization declarations can either consist of a suitable generation directive that clarify how a certain specialization is to be built, or a user defined implementation.</span></span> <span data-ttu-id="60e7a-154">Örneğin, yukarıdaki `PrepareEntangledPair` kod, açık özelleştirme bildirimlerini içeren aşağıdaki koda eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="60e7a-154">The code in `PrepareEntangledPair` above for example is equivalent to the code below containing explicit specialization declarations:</span></span> 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    adjoint auto; // auto-generate adjoint specialization
    controlled auto; // auto-generate controlled specialization
    controlled adjoint auto; // auto-generate controlled adjoint specialization
}
```
<span data-ttu-id="60e7a-155">Anahtar sözcüğü `auto`, derleyicinin özelleşme uygulamasının nasıl oluşturulacağını belirlemesi gerektiğini belirtir.</span><span class="sxs-lookup"><span data-stu-id="60e7a-155">The keyword `auto` indicates that the compiler should determine how to generate the specialization implementation.</span></span>
<span data-ttu-id="60e7a-156">Derleyici, daha kesin bir oluşturma yönergesi gibi ek yönergeler olmadan belirli bir özelleşmeye yönelik uygulamayı üretemiyor veya daha verimli bir uygulama verilirse, uygulama da el ile tanımlanabilir.</span><span class="sxs-lookup"><span data-stu-id="60e7a-156">If the compiler cannot generate the implementation for a certain specialization without further instructions - like a more precise generation directive -, or if a more efficient implementation can be given, then the implementation may also be manually defined.</span></span>

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit
is Ctl + Adj {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    controlled (cs, ...) { // user defined implementation for the controlled specialization
        Controlled H(cs, here);
        Controlled X(cs + [here], there);
    }

    adjoint invert; 
    controlled adjoint invert; 
}
```

<span data-ttu-id="60e7a-157">Yukarıdaki örnekte, `adjoint invert;`, adjoint özelleşmesinin, gövde uygulamasını ters çeviren şekilde oluşturulacağını ve `controlled adjoint invert;`, belirtilen ' nin belirtilen uygulamasını tersine getirerek denetlenen adjoint özelleşmesinin oluşturulacağını belirtir. denetlenen özelleşme.</span><span class="sxs-lookup"><span data-stu-id="60e7a-157">In the example above, `adjoint invert;` indicates that the adjoint specialization is to be generated by inverting the body implementation, and `controlled adjoint invert;` indicates that the controlled adjoint specialization is to be generated by inverting the given implementation of the controlled specialization.</span></span>

<span data-ttu-id="60e7a-158">`Adjoint` ve/veya `Controlled` functor uygulamasını desteklemeye yönelik bir işlemin, dönüş türünün `Unit`olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="60e7a-158">For an operation to support application of the `Adjoint` and/or `Controlled` functor, its return type necessarily needs to be `Unit`.</span></span> 


### <a name="explicit-specialization-declarations"></a><span data-ttu-id="60e7a-159">Açık Özelleştirme bildirimleri</span><span class="sxs-lookup"><span data-stu-id="60e7a-159">Explicit Specialization Declarations</span></span>

<span data-ttu-id="60e7a-160">S # işlemleri aşağıdaki açık özelleştirme bildirimlerini içerebilir:</span><span class="sxs-lookup"><span data-stu-id="60e7a-160">Q# operations may contain the following explicit specialization declarations:</span></span>

- <span data-ttu-id="60e7a-161">`body` özelleştirmesi, hiçbir komik uygulanmamış şekilde işlemin uygulanmasını belirtir.</span><span class="sxs-lookup"><span data-stu-id="60e7a-161">The `body` specialization specifies the implementation of the operation with no functors applied.</span></span>
- <span data-ttu-id="60e7a-162">`adjoint` özelleştirmesi, `Adjoint` functor uygulanmış işlemin uygulanmasını belirtir.</span><span class="sxs-lookup"><span data-stu-id="60e7a-162">The `adjoint` specialization specifies the implementation of the operation with the `Adjoint` functor applied.</span></span>
- <span data-ttu-id="60e7a-163">`controlled` özelleştirmesi, `Controlled` functor uygulanmış işlemin uygulanmasını belirtir.</span><span class="sxs-lookup"><span data-stu-id="60e7a-163">The `controlled` specialization specifies the implementation of the operation with the `Controlled` functor applied.</span></span>
- <span data-ttu-id="60e7a-164">`controlled adjoint` özelleştirmesi, her iki `Adjoint` ve `Controlled` funtorları ile işlemin uygulanmasını belirtir.</span><span class="sxs-lookup"><span data-stu-id="60e7a-164">The `controlled adjoint` specialization specifies the implementation of the operation with both the `Adjoint` and `Controlled` functors applied.</span></span>
  <span data-ttu-id="60e7a-165">Bu özelleşme, iki komik bir şekilde `adjoint controlled`de adlandırılmış olabilir.</span><span class="sxs-lookup"><span data-stu-id="60e7a-165">This specialization can also be named `adjoint controlled`, since the two functors commute.</span></span>


<span data-ttu-id="60e7a-166">Bir işlem özelleştirmesi, özelleştirme etiketinden (örn. `body`veya `adjoint`, vb.) sonra aşağıdakilerden birini içerir:</span><span class="sxs-lookup"><span data-stu-id="60e7a-166">An operation specialization consists of the specialization tag (like e.g. `body`, or `adjoint`, etc.) followed by one of:</span></span>

- <span data-ttu-id="60e7a-167">Aşağıda açıklandığı gibi açık bir bildirim.</span><span class="sxs-lookup"><span data-stu-id="60e7a-167">An explicit declaration as described below.</span></span>
- <span data-ttu-id="60e7a-168">Derleyiciye özelleştirmenin nasıl oluşturulacağını belirten bir yönerge, aşağıdakilerden biri:</span><span class="sxs-lookup"><span data-stu-id="60e7a-168">A directive that tells the compiler how to generate the specialization, one of:</span></span>
  - <span data-ttu-id="60e7a-169">`intrinsic`, özelleşmenin hedef makine tarafından sağlandığını gösterir.</span><span class="sxs-lookup"><span data-stu-id="60e7a-169">`intrinsic`, which indicates that the specialization is provided by the target machine.</span></span>
  - <span data-ttu-id="60e7a-170">`distribute`, `controlled` ve `controlled adjoint` uzmanlarıyla birlikte kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="60e7a-170">`distribute`, which may be used with the `controlled` and `controlled adjoint` specializations.</span></span>
    <span data-ttu-id="60e7a-171">`controlled`ile kullanıldığında, derleyicinin, `body`tüm işlemlere `Controlled` uygulayarak özelleştirmeyi hesaplaması gerektiğini belirtir.</span><span class="sxs-lookup"><span data-stu-id="60e7a-171">When used with `controlled`, it indicates that the compiler should compute the specialization by applying `Controlled` to all of the operations in the `body`.</span></span>
    <span data-ttu-id="60e7a-172">`controlled adjoint`ile kullanıldığında, derleyicinin özelleştirmeyi `adjoint` özelleşmesinin tüm işlemlerine `Controlled` uygulayarak hesaplaması gerektiğini belirtir.</span><span class="sxs-lookup"><span data-stu-id="60e7a-172">When used with `controlled adjoint`, it indicates that the compiler should compute the specialization by applying `Controlled` to all of the operations in the `adjoint` specialization.</span></span>
  - <span data-ttu-id="60e7a-173">`invert`, derleyicinin `adjoint` özelleştirmesinin `body`ters çevirerek, örneğin işlem sırasını ters çevirerek ve Adjoint öğesini her birine uygulayarak hesapladığını belirten.</span><span class="sxs-lookup"><span data-stu-id="60e7a-173">`invert`, which indicates that the compiler should compute the `adjoint` specialization by inverting the `body`, i.e. reversing the order of operations and applying the adjoint to each one.</span></span>
    <span data-ttu-id="60e7a-174">`adjoint controlled`ile kullanıldığında, derleyicinin özelleştirmeyi `controlled` özelleştirmeyi tersine getirerek hesaplaması gerektiğini belirtir.</span><span class="sxs-lookup"><span data-stu-id="60e7a-174">When used with `adjoint controlled`, this indicates that the compiler should compute the specialization by inverting the `controlled` specialization.</span></span>
  - <span data-ttu-id="60e7a-175">`self`, adjoint özelleşmenin `body` özelleştirmesi ile aynı olduğunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="60e7a-175">`self`, to indicate that the adjoint specialization is the the same as the `body` specialization.</span></span>
    <span data-ttu-id="60e7a-176">Bu, `adjoint` ve `adjoint controlled` özelleştirmeler için geçerlidir.</span><span class="sxs-lookup"><span data-stu-id="60e7a-176">This is legal for the `adjoint` and `adjoint controlled` specializations.</span></span>
    <span data-ttu-id="60e7a-177">`adjoint controlled`için, `self` `adjoint controlled` özelleşmenin `controlled` özelleştirmesi ile aynı olduğunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="60e7a-177">For `adjoint controlled`, `self` implies that the `adjoint controlled` specialization is the same as the `controlled` specialization.</span></span>
  - <span data-ttu-id="60e7a-178">`auto`, derleyicinin uygulanacak uygun bir yönergeyi seçmesini belirtmek için.</span><span class="sxs-lookup"><span data-stu-id="60e7a-178">`auto`, to indicate that the compiler should select an appropriate directive to apply.</span></span>
    <span data-ttu-id="60e7a-179">`auto` `body` özelleştirmesi için kullanılamayabilir.</span><span class="sxs-lookup"><span data-stu-id="60e7a-179">`auto` may not be used for the `body` specialization.</span></span>

<span data-ttu-id="60e7a-180">Yönergelerin ve `auto` tümünün bir kapanış noktalı virgül `;`gerekir.</span><span class="sxs-lookup"><span data-stu-id="60e7a-180">The directives and `auto` all require a closing semi-colon `;`.</span></span>
<span data-ttu-id="60e7a-181">`auto` yönergesi, `body` açık bildirimi sağlandıysa aşağıdaki nesil yönergesiyle çözümlenir:</span><span class="sxs-lookup"><span data-stu-id="60e7a-181">The `auto` directive resolves to the following generation directive if an explicit declaration of the `body` is provided:</span></span>

- <span data-ttu-id="60e7a-182">`adjoint` özelleştirmesi yönerge `invert`göre oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="60e7a-182">The `adjoint` specialization is generated according to the directive `invert`.</span></span>
- <span data-ttu-id="60e7a-183">`controlled` özelleştirmesi yönerge `distribute`göre oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="60e7a-183">The `controlled` specialization is generated according to the directive `distribute`.</span></span>
- <span data-ttu-id="60e7a-184">`adjoint controlled` özelleştirmesi, bir `controlled` açık bildirimine verilse ancak `adjoint`için yoksa ve `distribute` istemiyorsanız, yönergeye göre oluşturulur `invert`.</span><span class="sxs-lookup"><span data-stu-id="60e7a-184">The `adjoint controlled` specialization is generated according to the directive `invert` if an explicit declaration for `controlled` is given but not one for `adjoint`, and `distribute` otherwise.</span></span>

> [!TIP]   
> <span data-ttu-id="60e7a-185">Bir işlem kendi kendine adekiyiyiyorsa, derleyicinin en iyi duruma getirme amacıyla bu bilgileri kullanmasına izin vermek için, oluşturma `self` yönergesi aracılığıyla adjoint veya denetimli adjoint özelleşmesini açıkça belirtin.</span><span class="sxs-lookup"><span data-stu-id="60e7a-185">If an operation is self-adjoint, explicitly specify either the adjoint or the controlled adjoint specialization via the generation directive `self` to allow the compiler to make use of that information for optimization purposes.</span></span>

<span data-ttu-id="60e7a-186">Kullanıcı tanımlı bir uygulama içeren bir özelleştirme bildirimi, bir bağımsız değişken kayıt kümesinden ve ardından, özelleştirmeyi uygulayan Q # koduna sahip bir ekstre bloğundan oluşur.</span><span class="sxs-lookup"><span data-stu-id="60e7a-186">A specialization declaration containing a user defined implementation consists of an argument tuple followed by a statement block with the Q# code that implements the specialization.</span></span>
<span data-ttu-id="60e7a-187">Bağımsız değişken listesinde, bir bütün olarak işlem için belirtilen bağımsız değişkenleri temsil etmek üzere `...` kullanılır.</span><span class="sxs-lookup"><span data-stu-id="60e7a-187">In the argument list, `...` is used to represent the arguments declared for the operation as a whole.</span></span>
<span data-ttu-id="60e7a-188">`body` ve `adjoint`için bağımsız değişken listesi her zaman `(...)`olmalıdır; `controlled` ve `adjoint controlled`için bağımsız değişken listesi, denetim qubits dizisini temsil eden bir sembol olmalıdır ve sonra parantez içine alınmış `...`. Örneğin, `(controls,...)`.</span><span class="sxs-lookup"><span data-stu-id="60e7a-188">For `body` and `adjoint`, the argument list should always be `(...)`; for `controlled` and `adjoint controlled`, the argument list should be a symbol that represents the array of control qubits, followed by `...`, enclosed in parentheses; for example, `(controls,...)`.</span></span>

<span data-ttu-id="60e7a-189">Varsayılan gövdenin yanı sıra bir veya daha fazla özelleştirilmiş açıkça bildirilmesi gerekiyorsa, varsayılan gövdeye yönelik uygulamanın uygun bir özelleştirme bildirimine de sarmalanması gerekir:</span><span class="sxs-lookup"><span data-stu-id="60e7a-189">If one or more specializations besides the default body need to be explicitly declared, then the implementation for the default body needs to be wrapped into a suitable specialization declaration as well:</span></span>

```qsharp
operation CountOnes(qs: Qubit[]) : Int {

    body (...) // default body specialization
    {
        mutable n = 0;
        for (q in qs) {
            set n += M(q) == One ? 1 | 0;
        }
        return n;
    }

    ...
```

### <a name="adjoint"></a><span data-ttu-id="60e7a-190">Adjoint</span><span class="sxs-lookup"><span data-stu-id="60e7a-190">Adjoint</span></span>

<span data-ttu-id="60e7a-191">Bir işlemin adjoint işlemi, işlemin karmaşık eşlenmesinin nasıl uygulandığını belirtir, yani "ters bir şekilde Çalıştır" durumunda işlem nasıl çalışır.</span><span class="sxs-lookup"><span data-stu-id="60e7a-191">The adjoint of an operation specifies how the complex conjugate transpose of the operation is implemented, i.e. how the operation acts when "run in reverse".</span></span>
<span data-ttu-id="60e7a-192">Adjoint olmadan bir işlem belirtmek geçerlidir; Örneğin, ölçüm işlemlerinde hiçbir adjoint yoktur çünkü bunlar ters çevrilebilir değildir.</span><span class="sxs-lookup"><span data-stu-id="60e7a-192">It is legal to specify an operation with no adjoint; for instance, measurement operations have no adjoint because they are not invertible.</span></span>
<span data-ttu-id="60e7a-193">Bir işlem, bir adjoint özelleştirmesi için örtük veya açık bir bildirim içeriyorsa, functor `Adjoint` destekler.</span><span class="sxs-lookup"><span data-stu-id="60e7a-193">An operation supports the `Adjoint` functor if its declaration contains an implicit or explicit declaration of an adjoint specialization.</span></span>
<span data-ttu-id="60e7a-194">Açıkça tanımlanmış denetimli bir adjoint özelleştirmesi bir adjoint özelleşmenin varlığını gösterir.</span><span class="sxs-lookup"><span data-stu-id="60e7a-194">An explicitly declared controlled adjoint specialization implies the existence of an adjoint specialization.</span></span> 

<span data-ttu-id="60e7a-195">Gövdesi, yineleme-Until-başarılı döngüleri, set deyimlerini, ölçümleri, return deyimlerini veya `Adjoint` functor desteklemeyen diğer işlemlere yapılan çağrıları, `invert` veya @no__ takip eden bir adjoint uzmanlığı otomatik olarak oluşturmayı sağlayan işlem için t_2_ yönergesi mümkün değil.</span><span class="sxs-lookup"><span data-stu-id="60e7a-195">For operation whose body contains repeat-until-success loops, set statements, measurements, return statements, or calls to other operations that do not support the `Adjoint` functor, auto-generating an adjoint specialization following the `invert` or `auto` directive is not possible.</span></span>

### <a name="controlled"></a><span data-ttu-id="60e7a-196">Tarafından</span><span class="sxs-lookup"><span data-stu-id="60e7a-196">Controlled</span></span>

<span data-ttu-id="60e7a-197">Bir işlemin denetlenen sürümü işlemin ücretlendirilenen bir sürümünün nasıl uygulandığını belirtir, yani bir işlem, bir hisse kayıt durumuna göre uygulandıklarında nasıl davranır.</span><span class="sxs-lookup"><span data-stu-id="60e7a-197">The controlled version of an operation specifies how a quantum-controlled version of the operation is implemented, i.e. how an operation acts when applied conditioned on the state of a quantum register.</span></span>
<span data-ttu-id="60e7a-198">[Denetlenen](xref:microsoft.quantum.language.type-model#controlled) bölümde daha kapsamlı bir açıklama verilmiştir.</span><span class="sxs-lookup"><span data-stu-id="60e7a-198">A more complete description is provided in the [Controlled](xref:microsoft.quantum.language.type-model#controlled) section.</span></span>

<span data-ttu-id="60e7a-199">Denetlenen sürüm olmadan bir işlem belirtmek geçerlidir; Örneğin, ölçüm işlemlerinde denetlenebilir olmadığından, denetlenen bir sürüm yoktur.</span><span class="sxs-lookup"><span data-stu-id="60e7a-199">It is legal to specify an operation with no controlled version; for instance, measurement operations have no controlled version because they are not controllable.</span></span>
<span data-ttu-id="60e7a-200">Bir işlem, yalnızca bildirimi denetimli bir özelleşmenin örtük veya açık bir bildirimini içeriyorsa, `Controlled` functor 'ı destekler.</span><span class="sxs-lookup"><span data-stu-id="60e7a-200">An operation supports the `Controlled` functor if and only if its declaration contains an implicit or explicit declaration of a controlled specialization.</span></span>
<span data-ttu-id="60e7a-201">Açıkça tanımlanmış denetlenen bir adjoint özelleştirmesi, denetimli bir özelleştirmenin varlığını gösterir.</span><span class="sxs-lookup"><span data-stu-id="60e7a-201">An explicitly declared controlled adjoint specialization implies the existence of a controlled specialization.</span></span> 

<span data-ttu-id="60e7a-202">Gövdesi `Controlled` functor desteklemeyen diğer işlemlere çağrı içeren bir işlem için, `distribute` veya `auto` yönergesinin ardından denetimli bir özelleşmenin otomatik olarak oluşturulması mümkün değildir.</span><span class="sxs-lookup"><span data-stu-id="60e7a-202">For an operation whose body contains calls to other operations that does not support the `Controlled` functor, auto-generating a controlled specialization following the `distribute` or `auto` directive is not possible.</span></span>

### <a name="controlled-adjoint"></a><span data-ttu-id="60e7a-203">Kontrollü adjoint</span><span class="sxs-lookup"><span data-stu-id="60e7a-203">Controlled Adjoint</span></span>

<span data-ttu-id="60e7a-204">Bir işlemin kontrollü adjoint sürümü, işlemin adjoint öğesinin hisse kontrollü bir sürümünün nasıl uygulandığını belirtir.</span><span class="sxs-lookup"><span data-stu-id="60e7a-204">The controlled adjoint version of an operation specifies how a quantum-controlled version of the adjoint of the operation is implemented.</span></span>
<span data-ttu-id="60e7a-205">Denetlenen adjoint sürümü olmayan bir işlem belirtmek için geçerlidir; Örneğin, ölçüm işlemlerinde denetlenebilir veya ters çevrilebilir olmadıkları için denetimli bir adjoint sürümü yoktur.</span><span class="sxs-lookup"><span data-stu-id="60e7a-205">It is legal to specify an operation with no controlled adjoint version; for instance, measurement operations have no controlled adjoint version because they are neither controllable nor invertible.</span></span>

<span data-ttu-id="60e7a-206">Bir işlem için denetimli bir adjoint özelleştirmesi, ve yalnızca bir adjoint ve denetimli bir özelleştirme varsa var olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="60e7a-206">A controlled adjoint specialization for an operation needs to exist if and only if both an adjoint and a controlled specialization exist.</span></span> <span data-ttu-id="60e7a-207">Bu durumda, denetimli adjoint özelleşmenin varlığı algılanır ve hiçbir uygulama açıkça tanımlanmazsa derleyici tarafından uygun bir özelleştirme oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="60e7a-207">In that case, the existence of the controlled adjoint specialization is inferred and an appropriate specialization is generated by the compiler if no implementation has been defined explicitly.</span></span> 

<span data-ttu-id="60e7a-208">Gövdesi denetimli bir adjoint sürümüne sahip olmayan diğer işlemlere çağrı içeren bir işlem için, `invert`bir adjoint özelleştirmesi otomatik olarak oluşturulur `distribute` veya `auto` yönergesi mümkün değildir.</span><span class="sxs-lookup"><span data-stu-id="60e7a-208">For an operation whose body contains calls to other operations that do not have a controlled adjoint version, auto-generating an adjoint specialization following the `invert`, `distribute` or `auto` directive is not possible.</span></span>


### <a name="examples"></a><span data-ttu-id="60e7a-209">Örnekler</span><span class="sxs-lookup"><span data-stu-id="60e7a-209">Examples</span></span>

<span data-ttu-id="60e7a-210">İşlem bildirimi, temel Pauli X işlemini tanımlayan aşağıdaki kadar basit olabilir:</span><span class="sxs-lookup"><span data-stu-id="60e7a-210">An operation declaration might be as simple as the following, which defines the primitive Pauli X operation:</span></span>

```qsharp
operation X (q : Qubit) : Unit
is Adj + Ctl {
    body intrinsic;
    adjoint self;
}
```

<span data-ttu-id="60e7a-211">Aşağıda teleport işlemi tanımlanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="60e7a-211">The following defines the teleport operation.</span></span>

```qsharp
// Entangle two qubits.
// Assumes that both qubits are in the |0> state.
operation EPR (q1 : Qubit, q2 : Qubit) : Unit 
is Adj + Ctl {
    H(q2);
    CNOT(q2, q1);
}

// Teleport the quantum state of the source to the target.
// Assumes that the target is in the |0> state.
operation Teleport (source : Qubit, target : Qubit) : Unit {

    // Get a temporary for the Bell pair
    using (ancilla = Qubit())
    {
        // Create a Bell pair between the temporary and the target
        EPR(target, ancilla);

        // Do the teleportation
        Adjoint EPR (ancilla, source);

        if (MResetZ(source) == One) {
            X(target);
        }
        if (MResetZ(ancilla) == One) {
            Z(target);
        }
    }
}
```

## <a name="function-declarations"></a><span data-ttu-id="60e7a-212">İşlev bildirimleri</span><span class="sxs-lookup"><span data-stu-id="60e7a-212">Function Declarations</span></span>

<span data-ttu-id="60e7a-213">İşlevler, Q # içinde tamamen klasik yordamlardır.</span><span class="sxs-lookup"><span data-stu-id="60e7a-213">Functions are purely classical routines in Q#.</span></span>
<span data-ttu-id="60e7a-214">Her Q # kaynak dosyası herhangi bir sayıda işlev tanımlayabilir.</span><span class="sxs-lookup"><span data-stu-id="60e7a-214">Each Q# source file may define any number of functions.</span></span>

<span data-ttu-id="60e7a-215">Bir işlev bildirimi, anahtar sözcüğünden `function`, ardından işlevin adı, türü belirlenmiş bir tanımlayıcı tanımlama grubu, işlevin dönüş türünü açıklayan bir tür ek açıklaması ve uygulamanın uygulamasını açıklayan bir ifade bloğu içerir. çalışmayacaktır.</span><span class="sxs-lookup"><span data-stu-id="60e7a-215">A function declaration consists of the keyword `function`, followed by the symbol that is the function’s name, a typed identifier tuple, a type annotation that describes the function's return type, and a statement block that describes the implementation of the function.</span></span>

<span data-ttu-id="60e7a-216">Bir işlevi tanımlayan ifade bloğunun `{` ve diğer tüm ifade blokları gibi `}` alınması gerekir.</span><span class="sxs-lookup"><span data-stu-id="60e7a-216">The statement block defining a function must be enclosed in `{` and `}` like any other statement block.</span></span>

<span data-ttu-id="60e7a-217">İşlev adları bir ad alanı içinde benzersiz olmalıdır ve işlem ve tür adlarıyla çakışmayabilir.</span><span class="sxs-lookup"><span data-stu-id="60e7a-217">Function names must be unique within a namespace and may not conflict with operation and type names.</span></span>
<span data-ttu-id="60e7a-218">İşlevler, qubits veya çağrı işlemleri ayıramayabilir.</span><span class="sxs-lookup"><span data-stu-id="60e7a-218">Functions may not allocate or borrow qubits, or call operations.</span></span> <span data-ttu-id="60e7a-219">İşlemlerin kısmi uygulaması veya işleme ile yazılan değerler arasında geçiş yapmak iyidir.</span><span class="sxs-lookup"><span data-stu-id="60e7a-219">Partial application of operations or passing around operation typed values is fine.</span></span>

<span data-ttu-id="60e7a-220">Örneğin,</span><span class="sxs-lookup"><span data-stu-id="60e7a-220">For example,</span></span>

```qsharp
function DotProduct(a : Double[], b : Double[]) : Double {
    if (Length(a) != Length(b)) {
        fail "Arrays are not compatible";
    }

    mutable accum = 0.0;
    for (i in 0..Length(a)-1) {
        set accum += a[i] * b[i];
    }
    return accum;
}
```
