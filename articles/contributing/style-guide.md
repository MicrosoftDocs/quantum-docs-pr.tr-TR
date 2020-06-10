---
title: 'Microsoft Q # Stil Kılavuzu'
description: 'Q # programları ve kitaplıkları için adlandırma, giriş, belge ve biçimlendirme kurallarını öğrenin.'
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.style
ms.openlocfilehash: 948b385948f0b362e7c12500662132883959a798
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630222"
---
# <a name="q-style-guide"></a><span data-ttu-id="16acc-103">S # stil kılavuzu</span><span class="sxs-lookup"><span data-stu-id="16acc-103">Q# Style Guide</span></span> #
## <a name="general-conventions"></a><span data-ttu-id="16acc-104">Genel kurallar</span><span class="sxs-lookup"><span data-stu-id="16acc-104">General Conventions</span></span> ##

<span data-ttu-id="16acc-105">Bu kılavuzda önerilen kurallar, Q # dilinde yazılmış program ve kitaplıkların okunmasını ve anlaşılması daha kolay hale getirmeye yardımcı olmak için tasarlanmıştır.</span><span class="sxs-lookup"><span data-stu-id="16acc-105">The conventions suggested in this guide are intended to help make programs and libraries written in Q# easier to read and understand.</span></span>

## <a name="guidance"></a><span data-ttu-id="16acc-106">Rehber</span><span class="sxs-lookup"><span data-stu-id="16acc-106">Guidance</span></span>

<span data-ttu-id="16acc-107">Şunları öneririz:</span><span class="sxs-lookup"><span data-stu-id="16acc-107">We suggest:</span></span>

- <span data-ttu-id="16acc-108">Kullanıcılarınız için daha okunaklı ve anlaşılır kod sağlamak üzere kasıtlı olarak yapmadığınız müddetçe hiçbir şekilde hiçbir kuralı yok saymayın.</span><span class="sxs-lookup"><span data-stu-id="16acc-108">Never disregard a convention unless you’re doing so intentionally in order to provide more readable and understandable code for your users.</span></span>

## <a name="naming-conventions"></a><span data-ttu-id="16acc-109">Adlandırma Kuralları</span><span class="sxs-lookup"><span data-stu-id="16acc-109">Naming Conventions</span></span> ##

<span data-ttu-id="16acc-110">Hisse geliştirme setini sunan bölümünde, hisse geliştiricilerin kolayca okunabilen ve aniden en aza indirecek programlar yazmasına yardımcı olan işlev ve işlem adları için çaba duyuyoruz.</span><span class="sxs-lookup"><span data-stu-id="16acc-110">In offering the Quantum Development Kit, we strive for function and operation names that help quantum developers write programs that are easy to read and that minimize surprise.</span></span>
<span data-ttu-id="16acc-111">Bunun önemli bir bölümü, işlevler, işlemler ve türler için ad seçtiğimiz durumlarda, programcıların expressconcepts için kullandığı *sözlüğü* oluşturacağız; seçimlerimiz sayesinde, bunlara açık bir şekilde iletişim kurma çabalarına yardımcı olur veya bu işlemleri de destekliyoruz.</span><span class="sxs-lookup"><span data-stu-id="16acc-111">An important part of that is that when we choose names for functions, operations, and types, we are establishing the *vocabulary* that programmers use to express quantum concepts; with our choices, we either help or hinder them in their effort to clearly communicate.</span></span>
<span data-ttu-id="16acc-112">Bu, sunduğumuz adların Saklılığı yerine netlik sağlamalarını sağlamak için bize bir sorumluluk koyar.</span><span class="sxs-lookup"><span data-stu-id="16acc-112">This places a responsibility on us to make sure that the names we introduce offer clarity rather than obscurity.</span></span>
<span data-ttu-id="16acc-113">Bu bölümde, Q # geliştirme topluluğu tarafından en iyi şekilde buluşmamıza yardımcı olan açık yönergeler açısından bu yükümlülüğünüzü nasıl karşıladığımızdan ayrıntılıyoruz.</span><span class="sxs-lookup"><span data-stu-id="16acc-113">In this section, we detail how we meet this obligation in terms of explicit guidance that helps us do the best by the Q# development community.</span></span>

### <a name="operations-and-functions"></a><span data-ttu-id="16acc-114">İşlemler ve Işlevler</span><span class="sxs-lookup"><span data-stu-id="16acc-114">Operations and Functions</span></span> ###

<span data-ttu-id="16acc-115">Bir adın oluşturulması gereken ilk şeylerden biri, belirli bir sembolün bir işlevi veya işlemi temsil ettiğini belirtir.</span><span class="sxs-lookup"><span data-stu-id="16acc-115">One of the first things that a name should establish is whether a given symbol represents a function or an operation.</span></span>
<span data-ttu-id="16acc-116">İşlevler ve işlemler arasındaki fark, bir kod bloğunun nasıl davranacağını anlamak açısından önemlidir.</span><span class="sxs-lookup"><span data-stu-id="16acc-116">The difference between functions and operations is critical to understanding how a block of code behaves.</span></span>
<span data-ttu-id="16acc-117">İşlevler ve işlemler arasındaki ayrımı kullanıcılara iletmek için, yan etkileri kullanılarak bu Q # model hisse işlemlerine güveniyoruz.</span><span class="sxs-lookup"><span data-stu-id="16acc-117">To communicate the distinction between functions and operations to users, we rely on that Q# models quantum operations through the use of side effects.</span></span>
<span data-ttu-id="16acc-118">Diğer bir deyişle, bir işlem bir işlem *yapar* .</span><span class="sxs-lookup"><span data-stu-id="16acc-118">That is, an operation *does* something.</span></span>

<span data-ttu-id="16acc-119">Buna karşılık işlevler, veriler arasındaki matematik ilişkilerini tanımlar.</span><span class="sxs-lookup"><span data-stu-id="16acc-119">By contrast, functions describe the mathematical relationships between data.</span></span>
<span data-ttu-id="16acc-120">İfade `Sin(PI() / 2.0)` *olur* `1.0` ve bir programın veya qubits 'in durumu hakkında hiçbir şey anlamına gelir.</span><span class="sxs-lookup"><span data-stu-id="16acc-120">The expression `Sin(PI() / 2.0)` *is* `1.0`, and implies nothing about the state of a program or its qubits.</span></span>

<span data-ttu-id="16acc-121">Özetleme, işlemler, işlevleri işler.</span><span class="sxs-lookup"><span data-stu-id="16acc-121">Summarizing, operations do things while functions are things.</span></span>
<span data-ttu-id="16acc-122">Bu ayrım, işlemleri fiiller olarak ve işlevler olarak işlev olarak adı vereceğiz.</span><span class="sxs-lookup"><span data-stu-id="16acc-122">This distinction suggests that we name operations as verbs and functions as nouns.</span></span>

> [!NOTE]
> <span data-ttu-id="16acc-123">Kullanıcı tanımlı bir tür bildirildiğinde, bu türün örneklerini oluşturan yeni bir işlev örtülü olarak aynı anda tanımlanır.</span><span class="sxs-lookup"><span data-stu-id="16acc-123">When a user-defined type is declared, a new function that constructs instances of that type is implicitly defined at the same time.</span></span>
> <span data-ttu-id="16acc-124">Bu perspektiften, hem türün kendisi hem de Oluşturucu işlevinin tutarlı adlara sahip olması için Kullanıcı tanımlı türlerin adlarla adlandırılması gerekir.</span><span class="sxs-lookup"><span data-stu-id="16acc-124">From that perspective, user-defined types should be named as nouns so that both the type itself and the constructor function have consistent names.</span></span>

<span data-ttu-id="16acc-125">Makul yerlerde, işlem adlarının işlem tarafından gerçekleştirilen etkiyi açıkça belirten fiiller ile başlayıp başlamadığından emin olun.</span><span class="sxs-lookup"><span data-stu-id="16acc-125">Where reasonable, ensure that operation names begin with verbs that clearly indicate the effect taken by the operation.</span></span>
<span data-ttu-id="16acc-126">Örnek:</span><span class="sxs-lookup"><span data-stu-id="16acc-126">For example:</span></span>

- `MeasureInteger`
- `EstimateEnergy`
- `SampleInt`

<span data-ttu-id="16acc-127">Özel bahsetmeye hizmet eden bir durum, bir işlem başka bir işlemi girdi olarak aldığında ve çağırdığında çağırır.</span><span class="sxs-lookup"><span data-stu-id="16acc-127">One case that deserves special mention is when an operation takes another operation as input and calls it.</span></span>
<span data-ttu-id="16acc-128">Bu gibi durumlarda, giriş işlemi tarafından gerçekleştirilen eylem, dış işlem tanımlandığında, doğru fiil hemen temizlenmediği için net değildir.</span><span class="sxs-lookup"><span data-stu-id="16acc-128">In such cases, the action taken by the input operation is not clear when the outer operation is defined, such that the right verb is not immediately clear.</span></span>
<span data-ttu-id="16acc-129">, `Apply` Ve ' de olduğu gibi fiili `ApplyIf` önerilir `ApplyToEach` `ApplyToFirst` .</span><span class="sxs-lookup"><span data-stu-id="16acc-129">We recommend the verb `Apply`, as in `ApplyIf`, `ApplyToEach`, and `ApplyToFirst`.</span></span>
<span data-ttu-id="16acc-130">Diğer fiiller, içinde olduğu gibi, bu durumda da yararlı olabilir `IterateThroughCartesianPower` .</span><span class="sxs-lookup"><span data-stu-id="16acc-130">Other verbs may be useful in this case as well, as in `IterateThroughCartesianPower`.</span></span>

| <span data-ttu-id="16acc-131">Fiil</span><span class="sxs-lookup"><span data-stu-id="16acc-131">Verb</span></span> | <span data-ttu-id="16acc-132">Beklenen efekt</span><span class="sxs-lookup"><span data-stu-id="16acc-132">Expected Effect</span></span> |
| ---- | ------ |
| <span data-ttu-id="16acc-133">Uygula</span><span class="sxs-lookup"><span data-stu-id="16acc-133">Apply</span></span> | <span data-ttu-id="16acc-134">Giriş olarak verilen bir işlem çağrılır</span><span class="sxs-lookup"><span data-stu-id="16acc-134">An operation provided as input is called</span></span> |
| <span data-ttu-id="16acc-135">Assert</span><span class="sxs-lookup"><span data-stu-id="16acc-135">Assert</span></span> | <span data-ttu-id="16acc-136">Olası bir hisse ölçüsünün sonucu hakkında bir varsayım simülatör tarafından denetlenir</span><span class="sxs-lookup"><span data-stu-id="16acc-136">A hypothesis about the outcome of a possible quantum measurement is checked by a simulator</span></span> |
| <span data-ttu-id="16acc-137">Tahmin</span><span class="sxs-lookup"><span data-stu-id="16acc-137">Estimate</span></span> | <span data-ttu-id="16acc-138">Bir veya daha fazla ölçüden çizilen bir tahmini temsil eden klasik bir değer döndürüldü</span><span class="sxs-lookup"><span data-stu-id="16acc-138">A classical value is returned, representing an estimate drawn from one or more measurements</span></span> |
| <span data-ttu-id="16acc-139">Measure</span><span class="sxs-lookup"><span data-stu-id="16acc-139">Measure</span></span> | <span data-ttu-id="16acc-140">Bir hisse ölçümü gerçekleştirilir ve sonucu kullanıcıya döndürülür</span><span class="sxs-lookup"><span data-stu-id="16acc-140">A quantum measurement is performed, and its result is returned to the user</span></span> |
| <span data-ttu-id="16acc-141">Hazırlama</span><span class="sxs-lookup"><span data-stu-id="16acc-141">Prepare</span></span> | <span data-ttu-id="16acc-142">Belirli bir qubits kaydı belirli bir duruma başlatılır</span><span class="sxs-lookup"><span data-stu-id="16acc-142">A given register of qubits is initialized into a particular state</span></span> |
| <span data-ttu-id="16acc-143">Örnek</span><span class="sxs-lookup"><span data-stu-id="16acc-143">Sample</span></span> | <span data-ttu-id="16acc-144">Klasik bir değer, bazı dağılılardan rasgele döndürülür</span><span class="sxs-lookup"><span data-stu-id="16acc-144">A classical value is returned at random from some distribution</span></span> |

<span data-ttu-id="16acc-145">İşlevler için, fiillerin ortak isimler yerine kullanılmasını önletireceğiz (aşağıdaki doğru isimler üzerinde rehberlik) veya sıfatlar:</span><span class="sxs-lookup"><span data-stu-id="16acc-145">For functions, we suggest avoiding the use of verbs in favor of common nouns (see guidance on proper nouns below) or adjectives:</span></span>

- `ConstantArray`
- `Head`
- `LookupFunction`

<span data-ttu-id="16acc-146">Özellikle, neredeyse her durumda, bir işlev adının bir işleme veya bir hisse senedine bağlı olarak bir eyleme bağlı olduğunu göstermek için uygun olan geçmiş participles kullanmayı öneririz.</span><span class="sxs-lookup"><span data-stu-id="16acc-146">In particular, in almost all cases, we suggest using past participles where appropriate to indicate that a function name is strongly connected to an action or side effect elsewhere in a quantum program.</span></span>
<span data-ttu-id="16acc-147">Örneğin, `ControlledOnInt` işlevin bağımsız değişkenini değiştirmek için bir sıfatlar olarak davrandığını göstermek için, "Control" fiilinin bölüm participle formunu kullanır.</span><span class="sxs-lookup"><span data-stu-id="16acc-147">For example,  `ControlledOnInt` uses the part participle form of the verb "control" to indicate that the function acts as an adjective to modify its argument.</span></span>
<span data-ttu-id="16acc-148">Bu ad, `Controlled` aşağıda açıklandığı gibi yerleşik funın semantiğini eşleştirmesinin ek avantajına sahiptir.</span><span class="sxs-lookup"><span data-stu-id="16acc-148">This name has the additional benefit of matching the semantics of the built-in `Controlled` functor, as discussed further below.</span></span>
<span data-ttu-id="16acc-149">Benzer şekilde, _Aracı isimleri_ , işlem adlarından Işlev ve udt adlarını oluşturmak için, `Encoder` kesin olarak ilişkili bir udt 'nin adı durumunda olduğu gibi kullanılabilir `Encode` .</span><span class="sxs-lookup"><span data-stu-id="16acc-149">Similarly, _agent nouns_ can be used to construct function and UDT names from operation names, as in the case of the name `Encoder` for a UDT that is strongly associated with `Encode`.</span></span>

# <a name="guidance"></a>[<span data-ttu-id="16acc-150">Rehber</span><span class="sxs-lookup"><span data-stu-id="16acc-150">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="16acc-151">Şunları öneririz:</span><span class="sxs-lookup"><span data-stu-id="16acc-151">We suggest:</span></span>

- <span data-ttu-id="16acc-152">İşlem adları için fiilleri kullanın.</span><span class="sxs-lookup"><span data-stu-id="16acc-152">Use verbs for operation names.</span></span>
- <span data-ttu-id="16acc-153">İşlev adları için isimleri veya sıfatları kullanın.</span><span class="sxs-lookup"><span data-stu-id="16acc-153">Use nouns or adjectives for function names.</span></span>
- <span data-ttu-id="16acc-154">Kullanıcı tanımlı türler ve öznitelikler için isimleri kullanın.</span><span class="sxs-lookup"><span data-stu-id="16acc-154">Use nouns for user-defined types and attributes.</span></span>
- <span data-ttu-id="16acc-155">Çağrılabilir tüm adlar için, `CamelCase` veya için güçlü bir tercih `pascalCase` kullanın `snake_case` `ANGRY_CASE` .</span><span class="sxs-lookup"><span data-stu-id="16acc-155">For all callable names, use `CamelCase` in strong preference to `pascalCase`, `snake_case`, or `ANGRY_CASE`.</span></span> <span data-ttu-id="16acc-156">Özellikle, çağrılabilir adların büyük harfle başlayıp başlamadiğinden emin olun.</span><span class="sxs-lookup"><span data-stu-id="16acc-156">In particular, ensure that callable names start with uppercase letters.</span></span>
- <span data-ttu-id="16acc-157">Tüm yerel değişkenler için, `pascalCase` veya için güçlü bir tercih `CamelCase` kullanın `snake_case` `ANGRY_CASE` .</span><span class="sxs-lookup"><span data-stu-id="16acc-157">For all local variables, use `pascalCase` in strong preference to `CamelCase`, `snake_case`, or `ANGRY_CASE`.</span></span> <span data-ttu-id="16acc-158">Özellikle, yerel değişkenlerin küçük harfle başlayıp başlamadiğinden emin olun.</span><span class="sxs-lookup"><span data-stu-id="16acc-158">In particular, ensure that local variables start with lowercase letters.</span></span>
- <span data-ttu-id="16acc-159">`_`İşlev ve işlem adlarında alt çizgi kullanmaktan kaçının; burada ek hiyerarşi düzeyleri gerekir, ad alanları ve ad alanı diğer adları kullanın.</span><span class="sxs-lookup"><span data-stu-id="16acc-159">Avoid the use of underscores `_` in function and operation names; where additional levels of hierarchy are needed, use namespaces and namespace aliases.</span></span>

# <a name="examples"></a>[<span data-ttu-id="16acc-160">Örnekler</span><span class="sxs-lookup"><span data-stu-id="16acc-160">Examples</span></span>](#tab/examples)

|   | <span data-ttu-id="16acc-161">Name</span><span class="sxs-lookup"><span data-stu-id="16acc-161">Name</span></span> | <span data-ttu-id="16acc-162">Description</span><span class="sxs-lookup"><span data-stu-id="16acc-162">Description</span></span> |
|---|------|-------------|
| <span data-ttu-id="16acc-163">☑</span><span class="sxs-lookup"><span data-stu-id="16acc-163">☑</span></span> | `operation ReflectAboutStart` | <span data-ttu-id="16acc-164">İşlemin etkisini göstermek için bir fiil ("yansıtma") kullanımını temizleyin.</span><span class="sxs-lookup"><span data-stu-id="16acc-164">Clear use of a verb ("reflect") to indicate the effect of the operation.</span></span> |
| <span data-ttu-id="16acc-165">☒</span><span class="sxs-lookup"><span data-stu-id="16acc-165">☒</span></span> | <s>`operation XRotation`</s> | <span data-ttu-id="16acc-166">İsim ifadesi kullanımı, işlem yerine Function önerisinde bulunur.</span><span class="sxs-lookup"><span data-stu-id="16acc-166">Use of noun phrase suggests function, rather than operation.</span></span> |
| <span data-ttu-id="16acc-167">☒</span><span class="sxs-lookup"><span data-stu-id="16acc-167">☒</span></span> | <s>`operation search_oracle`</s> | <span data-ttu-id="16acc-168">`snake_case`Değişken venes Q # gösterimi kullanımı.</span><span class="sxs-lookup"><span data-stu-id="16acc-168">Use of `snake_case` contravenes Q# notation.</span></span> |
| <span data-ttu-id="16acc-169">☒</span><span class="sxs-lookup"><span data-stu-id="16acc-169">☒</span></span> | <s>`operation Search_Oracle`</s> | <span data-ttu-id="16acc-170">Alt çizgi kullanımı iç işlem adı nvenes Q # gösterimi.</span><span class="sxs-lookup"><span data-stu-id="16acc-170">Use of underscores internal to operation name contravenes Q# notation.</span></span> |
| <span data-ttu-id="16acc-171">☑</span><span class="sxs-lookup"><span data-stu-id="16acc-171">☑</span></span> | `function StatePreparationOracle` | <span data-ttu-id="16acc-172">İsim ifadesinin kullanılması işlevin bir işlem döndürdüğünü önerir.</span><span class="sxs-lookup"><span data-stu-id="16acc-172">Use of noun phrase suggests that the function returns an operation.</span></span> |
| <span data-ttu-id="16acc-173">☑</span><span class="sxs-lookup"><span data-stu-id="16acc-173">☑</span></span> | `function EqualityFact` | <span data-ttu-id="16acc-174">Bu işlevin bir işlev olduğunu göstermek için ("olgu"), sıfatı seçimini temizleyin.</span><span class="sxs-lookup"><span data-stu-id="16acc-174">Clear use of noun ("fact") to indicate that this is a function, while the adjective.</span></span> |
| <span data-ttu-id="16acc-175">☒</span><span class="sxs-lookup"><span data-stu-id="16acc-175">☒</span></span> | <s>`function GetRotationAngles`</s> | <span data-ttu-id="16acc-176">Fiil ("Get") kullanılması bunun bir işlem olduğunu önerir.</span><span class="sxs-lookup"><span data-stu-id="16acc-176">Use of verb ("get") suggests that this is an operation.</span></span> |
| <span data-ttu-id="16acc-177">☑</span><span class="sxs-lookup"><span data-stu-id="16acc-177">☑</span></span> | `newtype GeneratorTerm` | <span data-ttu-id="16acc-178">Ad ifadesinin kullanımı, UDT oluşturucusunun çağrılması sonucunu açıkça ifade eder.</span><span class="sxs-lookup"><span data-stu-id="16acc-178">Use of noun phrase clearly refers to the result of calling the UDT constructor.</span></span> |
| <span data-ttu-id="16acc-179">☒</span><span class="sxs-lookup"><span data-stu-id="16acc-179">☒</span></span> | <s>`@Attribute() newtype RunOnce()`</s> | <span data-ttu-id="16acc-180">Fiil ifadesinin kullanımı, UDT oluşturucusunun bir işlem olduğunu önerir.</span><span class="sxs-lookup"><span data-stu-id="16acc-180">Use of verb phrase suggests that the UDT constructor is an operation.</span></span> |
| <span data-ttu-id="16acc-181">☑</span><span class="sxs-lookup"><span data-stu-id="16acc-181">☑</span></span> | `@Attribute() newtype Deprecated(Reason : String)` | <span data-ttu-id="16acc-182">İsim ifadesinin kullanılması özniteliğin kullanımını iletişim kurar.</span><span class="sxs-lookup"><span data-stu-id="16acc-182">Use of noun phrase communicates the use of the attribute.</span></span> |

***

### <a name="shorthand-and-abbreviations"></a><span data-ttu-id="16acc-183">Özet ve kısaltmalar</span><span class="sxs-lookup"><span data-stu-id="16acc-183">Shorthand and Abbreviations</span></span> ###

<span data-ttu-id="16acc-184">Yukarıdaki önerinin, hisse yaramakta olan ortak ve kapsamlı kullanımı gösteren çok sayıda kısayol vardır.</span><span class="sxs-lookup"><span data-stu-id="16acc-184">The above advice notwithstanding, there are many forms of shorthand that see common and pervasive use in quantum computing.</span></span>
<span data-ttu-id="16acc-185">Özellikle bir hedef makinenin işlemlerine iç işlemler için, var olan ve genel bir toplu işlemin bulunduğu yerde kullanmayı öneririz.</span><span class="sxs-lookup"><span data-stu-id="16acc-185">We suggest using existing and common shorthand where it exists, especially for operations that are intrinsic to the operation of a target machine.</span></span>
<span data-ttu-id="16acc-186">Örneğin, yerine ve yerine adını seçtik `X` `ApplyX` `Rz` `RotateAboutZ` .</span><span class="sxs-lookup"><span data-stu-id="16acc-186">For example, we choose the name `X` instead of `ApplyX`, and `Rz` instead of `RotateAboutZ`.</span></span>
<span data-ttu-id="16acc-187">Bu tür bir kısayol kullanırken, işlem adları tümü büyük harfle yazılmalıdır (ör.: `MAJ` ).</span><span class="sxs-lookup"><span data-stu-id="16acc-187">When using such shorthand, operation names should be all uppercase (e.g.: `MAJ`).</span></span>

<span data-ttu-id="16acc-188">Bu kural, yaygın olarak kullanılan kısaltmalar ve başlangıçlar söz konusu olduğunda "hisse Fourier dönüştürmesi" için "QFT" gibi bazı durumlarda gereklidir.</span><span class="sxs-lookup"><span data-stu-id="16acc-188">Some care is required when applying this convention in the case of commonly used acronyms and initialisms such as "QFT" for "quantum Fourier transform."</span></span>
<span data-ttu-id="16acc-189">Tam adlarda kısaltmalar ve ınitialisms 'lerin kullanılması için aşağıdaki genel .NET kurallarını öneririz:</span><span class="sxs-lookup"><span data-stu-id="16acc-189">We suggest following general .NET conventions for the use of acronyms and initialisms in full names, which prescribe that:</span></span>

- <span data-ttu-id="16acc-190">iki harfli kısaltmalar ve ınitialisms büyük harfle adlandırılır (örn. `BE` "Big-endian" için),</span><span class="sxs-lookup"><span data-stu-id="16acc-190">two-letter acronyms and initialisms are named in upper case (e.g.: `BE` for "big-endian"),</span></span>
- <span data-ttu-id="16acc-191">daha uzun kısaltmalar ve ınitialisms 'ler içinde adlandırılır `CamelCase` (örn. `Qft` "hisse Fourier dönüştürmesi" için)</span><span class="sxs-lookup"><span data-stu-id="16acc-191">all longer acronyms and initialisms are named in `CamelCase` (e.g.: `Qft` for "quantum Fourier transform")</span></span>

<span data-ttu-id="16acc-192">Bu nedenle, QFT 'yi uygulayan bir işlem `QFT` , toplu olarak çağrılabilir ya da olarak yazılabilir `ApplyQft` .</span><span class="sxs-lookup"><span data-stu-id="16acc-192">Thus, an operation implementing the QFT could either be called `QFT` as shorthand, or written out as `ApplyQft`.</span></span>

<span data-ttu-id="16acc-193">Özellikle yaygın olarak kullanılan işlemler ve işlevler için daha uzun bir form için bir _diğer_ ad olarak bir kısayol adı sağlanması istenebilir:</span><span class="sxs-lookup"><span data-stu-id="16acc-193">For particularly commonly used operations and functions, it may be desirable to provide a shorthand name as an _alias_ for a longer form:</span></span>

```qsharp
operation CCNOT(control0 : Qubit, control1 : Qubit, target : Qubit)
is Adj + Ctl {
    Controlled X([control0, control1], target);
}
```

# <a name="guidance"></a>[<span data-ttu-id="16acc-194">Rehber</span><span class="sxs-lookup"><span data-stu-id="16acc-194">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="16acc-195">Şunları öneririz:</span><span class="sxs-lookup"><span data-stu-id="16acc-195">We suggest:</span></span>

- <span data-ttu-id="16acc-196">Uygun olduğunda genellikle kabul edilen ve yaygın olarak kullanılan toplu adları göz önünde bulundurun.</span><span class="sxs-lookup"><span data-stu-id="16acc-196">Consider commonly accepted and widely used shorthand names when appropriate.</span></span>
- <span data-ttu-id="16acc-197">Toplu değer için büyük harf kullanın.</span><span class="sxs-lookup"><span data-stu-id="16acc-197">Use uppercase for shorthand.</span></span>
- <span data-ttu-id="16acc-198">Kısa (iki harfli) kısaltmalar ve ınitialisms için büyük harf kullanın.</span><span class="sxs-lookup"><span data-stu-id="16acc-198">Use uppercase for short (two-letter) acronyms and initialisms.</span></span>
- <span data-ttu-id="16acc-199">Daha `CamelCase` uzun (üç veya daha fazla harf) kısaltmalar ve ınitialisms için kullanın.</span><span class="sxs-lookup"><span data-stu-id="16acc-199">Use `CamelCase` for longer (three or more letter) acronyms and initialisms.</span></span>

# <a name="examples"></a>[<span data-ttu-id="16acc-200">Örnekler</span><span class="sxs-lookup"><span data-stu-id="16acc-200">Examples</span></span>](#tab/examples)

|   | <span data-ttu-id="16acc-201">Name</span><span class="sxs-lookup"><span data-stu-id="16acc-201">Name</span></span> | <span data-ttu-id="16acc-202">Description</span><span class="sxs-lookup"><span data-stu-id="16acc-202">Description</span></span> |
|---|------|-------------|
| <span data-ttu-id="16acc-203">☑</span><span class="sxs-lookup"><span data-stu-id="16acc-203">☑</span></span> | `X` | <span data-ttu-id="16acc-204">"Bir $X $ dönüşümü Uygula" için iyi anlaşılan toplu değer</span><span class="sxs-lookup"><span data-stu-id="16acc-204">Well-understood shorthand for "apply an $X$ transformation"</span></span> |
| <span data-ttu-id="16acc-205">☑</span><span class="sxs-lookup"><span data-stu-id="16acc-205">☑</span></span> | `CNOT` | <span data-ttu-id="16acc-206">"Denetimli-NOT" için iyi anlaşılan toplu değer</span><span class="sxs-lookup"><span data-stu-id="16acc-206">Well-understood shorthand for "controlled-NOT"</span></span> |
| <span data-ttu-id="16acc-207">☒</span><span class="sxs-lookup"><span data-stu-id="16acc-207">☒</span></span> | <s>`Cnot`</s> | <span data-ttu-id="16acc-208">Kısayol içinde olmamalıdır `CamelCase` .</span><span class="sxs-lookup"><span data-stu-id="16acc-208">Shorthand should not be in `CamelCase`.</span></span> |
| <span data-ttu-id="16acc-209">☑</span><span class="sxs-lookup"><span data-stu-id="16acc-209">☑</span></span> | `ApplyQft` | <span data-ttu-id="16acc-210">"QFT" ortak ınitialroni uzun biçimli bir adın parçası olarak görünür.</span><span class="sxs-lookup"><span data-stu-id="16acc-210">Common initialism "QFT" appears as a part of a long-form name.</span></span> |
| <span data-ttu-id="16acc-211">☑</span><span class="sxs-lookup"><span data-stu-id="16acc-211">☑</span></span> | `QFT` | <span data-ttu-id="16acc-212">Genel ınitialısm "QFT", bir kısayol adının parçası olarak görünür.</span><span class="sxs-lookup"><span data-stu-id="16acc-212">Common initialism "QFT" appears as a part of a shorthand name.</span></span> |



***


### <a name="proper-nouns-in-names"></a><span data-ttu-id="16acc-213">Adlarda doğru adlar</span><span class="sxs-lookup"><span data-stu-id="16acc-213">Proper Nouns in Names</span></span> ###

<span data-ttu-id="16acc-214">Fizik durumunda, bunlar hakkında ilk kişiden sonra yayımlanmayan kişilerin adlarını ve tüm geçmişi öğrenmelerini sağlamak yaygın bir şekilde yapılıyor.</span><span class="sxs-lookup"><span data-stu-id="16acc-214">While in physics it is common to name things after the first person to publish about them, most non-physicists aren’t familiar with everyone’s names and all of the history.</span></span>
<span data-ttu-id="16acc-215">Daha fazla bilgi için, diğer arka planlardaki kullanıcıların, genel işlemleri ve kavramları kullanabilmesi için çok sayıda donuk opak ad öğrenmelidir.</span><span class="sxs-lookup"><span data-stu-id="16acc-215">Relying too heavily on naming conventions from physics can thus put up a substantial barrier to entry, as users from other backgrounds must learn a large number of seemingly opaque names in order to use common operations and concepts.</span></span>
<!-- An important part of the task of reducing confusion is to make code more accessible.
Especially in a field such as quantum computing that is rich with domain expertise, we must at all times be cognizant of the demands we place on that expertise as we design quantum software.
In naming code symbols, one way that this cognizance expresses itself is as an awareness of the convention from physics of adopting as the names of algorithms and operations the names of their original publishers.
While we must maintain the history and intellectual provenance of concepts in quantum computing, demanding that all users be versed in this history to use even the most basic of functions and operations places a barrier to entry that is in most cases severe enough to even present an ethical compromise. -->
<span data-ttu-id="16acc-216">Bu nedenle, bir kavramı tanımlayan makul, yaygın isimler kavramı, bir kavramın yayın geçmişini tanımlayan doğru isimler için güçlü bir tercih halinde benimsemesi önerilir.</span><span class="sxs-lookup"><span data-stu-id="16acc-216">Thus, we recommend that wherever reasonable, common nouns that describe a concept be adopted in strong preference to proper nouns that describe the publication history of a concept.</span></span>
<span data-ttu-id="16acc-217">Belirli bir örnek olarak, listedir kontrollü DEĞIŞTIRME ve buna uygun olmayan işlemler, genellikle akademik belgelerinde "Fredkaş" ve "Toffoli" işlemleri olarak adlandırılır, ancak bu, birincil olarak `CSWAP` ve ile olarak tanımlanmıştır `CCNOT` .</span><span class="sxs-lookup"><span data-stu-id="16acc-217">As a particular example, the singly controlled SWAP and doubly controlled NOT operations are often called the "Fredkin" and "Toffoli" operations in academic literature, but are identified in Q# primarily as `CSWAP` and `CCNOT`.</span></span>
<span data-ttu-id="16acc-218">Her iki durumda da, API belgesi açıklamaları uygun adlara göre eş anlamlı adlar sağlar ve tüm uygun alıntıları birlikte kapsar.</span><span class="sxs-lookup"><span data-stu-id="16acc-218">In both cases, the API documentation comments provide synonymous names based on proper nouns, along with all appropriate citations.</span></span>

<span data-ttu-id="16acc-219">Bu tercih, bazı uygun isimler kullanımının her zaman gerekli olacağı bir şekilde önemlidir. Q #, örneğin birçok klasik dil tarafından ayarlanan gelenek kümesini izler ve daha sonra `Bool` George Boole 'in içinde adı verilen Boolean mantığına başvuru türleri anlamına gelir.</span><span class="sxs-lookup"><span data-stu-id="16acc-219">This preference is especially important given that some usage of proper nouns will always be necessary — Q# follows the tradition set by many classical languages, for instance, and refers to `Bool` types in reference to Boolean logic, which is in turn named in honor of George Boole.</span></span>
<span data-ttu-id="16acc-220">Benzer şekilde, örneğin, `Pauli` Q # dilinde yerleşik olan türü de dahil olmak üzere, benzer bir şekilde adlandırılmış birkaç hisse kavramdır.</span><span class="sxs-lookup"><span data-stu-id="16acc-220">A few quantum concepts similarly are named in a similar fashion, including the `Pauli` type built-in to the Q# language.</span></span>
<span data-ttu-id="16acc-221">Bu kullanım açısından gerekli olan doğru isimler kullanımını en aza indirerek, doğru isimleri kabul etmeyeceğinden etkiyi azalttık.</span><span class="sxs-lookup"><span data-stu-id="16acc-221">By minimizing the usage of proper nouns where such usage is not essential, we reduce the impact where proper nouns cannot be reasonably avoided.</span></span>

# <a name="guidance"></a>[<span data-ttu-id="16acc-222">Rehber</span><span class="sxs-lookup"><span data-stu-id="16acc-222">Guidance</span></span>](#tab/guidance) 

<span data-ttu-id="16acc-223">Şunları öneririz:</span><span class="sxs-lookup"><span data-stu-id="16acc-223">We suggest:</span></span>

- <span data-ttu-id="16acc-224">Adlarda doğru isimler kullanmaktan kaçının.</span><span class="sxs-lookup"><span data-stu-id="16acc-224">Avoid the use of proper nouns in names.</span></span>

# <a name="examples"></a>[<span data-ttu-id="16acc-225">Örnekler</span><span class="sxs-lookup"><span data-stu-id="16acc-225">Examples</span></span>](#tab/examples)

***

### <a name="type-conversions"></a><span data-ttu-id="16acc-226">Tür Dönüştürmeleri</span><span class="sxs-lookup"><span data-stu-id="16acc-226">Type Conversions</span></span> ###

<span data-ttu-id="16acc-227">Q #, kesin ve statik olarak yazılmış bir dil olduğundan, bir tür değeri yalnızca bir tür dönüştürme işlevine açık bir çağrı kullanılarak başka bir türün değeri olarak kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="16acc-227">Since Q# is a strongly and staticly typed language, a value of one type can only be used as a value of another type by using an explicit call to a type conversion function.</span></span>
<span data-ttu-id="16acc-228">Bu, değerlerin örtük olarak (ör. tür promosyonu) veya atama yoluyla türlerin değiştirilmesini sağlayan dillere karşılık gelir.</span><span class="sxs-lookup"><span data-stu-id="16acc-228">This is in contrast to languages which allow for values to change types implicitly (e.g.: type promotion), or through casting.</span></span>
<span data-ttu-id="16acc-229">Sonuç olarak, tür dönüştürme işlevleri Q # kitaplığı geliştirme bölümünde önemli bir rol oynar ve adlandırma hakkında yaygın olarak karşılaşılan kararlardan birini içerir.</span><span class="sxs-lookup"><span data-stu-id="16acc-229">As a result, type conversion functions play an important role in Q# library development, and comprise one of the more commonly encountered decisions about naming.</span></span>
<span data-ttu-id="16acc-230">Ancak, tür dönüştürmeleri her zaman _belirleyici_olduğundan, bunlar işlev olarak yazılabilecekleri ve bu nedenle yukarıdaki önerinin altına düşecek.</span><span class="sxs-lookup"><span data-stu-id="16acc-230">We note, however, that since type conversions are always _deterministic_, they can be written as functions and thus fall under the advice above.</span></span>
<span data-ttu-id="16acc-231">Özellikle, tür dönüştürme işlevlerinin hiçbir şekilde fiiller (ör.: `ConvertToX` ) veya duyurusu b önceden konumsal tümceleri () olarak adlandırılmaması önerilir `ToX` , ancak kaynak ve hedef türlerini belirten sıfatıcı önceden konumsal ifadeler olarak adlandırılmalıdır ( `XAsY` ).</span><span class="sxs-lookup"><span data-stu-id="16acc-231">In particular, we suggest that type conversion functions should never be named as verbs (e.g.: `ConvertToX`) or adverb prepositional phrases (`ToX`), but should be named as adjective prepositional phrases that indicate the source and destination types (`XAsY`).</span></span>
<span data-ttu-id="16acc-232">Tür dönüştürme işlevi adlarında dizi türleri listelenirken, Stenk önerilir `Arr` .</span><span class="sxs-lookup"><span data-stu-id="16acc-232">When listing array types in type conversion function names, we recommend the shorthand `Arr`.</span></span>
<span data-ttu-id="16acc-233">Tüm tür dönüştürme işlevlerinin, `As` hızlı bir şekilde tanımlanabilmesi için kullanılarak adlandırılması önerilir.</span><span class="sxs-lookup"><span data-stu-id="16acc-233">Barring exceptional circumstances, we recommend that all type conversion functions be named using `As` so that they can be quickly identified.</span></span>

# <a name="guidance"></a>[<span data-ttu-id="16acc-234">Rehber</span><span class="sxs-lookup"><span data-stu-id="16acc-234">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="16acc-235">Şunları öneririz:</span><span class="sxs-lookup"><span data-stu-id="16acc-235">We suggest:</span></span>

- <span data-ttu-id="16acc-236">Bir işlev, türünde bir değeri `X` türünde bir değere dönüştürdüğünde `Y` , adını `AsY` veya kullanın `XAsY` .</span><span class="sxs-lookup"><span data-stu-id="16acc-236">If a function converts a value of type `X` to a value of type `Y`, use either the name `AsY` or `XAsY`.</span></span>

# <a name="examples"></a>[<span data-ttu-id="16acc-237">Örnekler</span><span class="sxs-lookup"><span data-stu-id="16acc-237">Examples</span></span>](#tab/examples)

|   | <span data-ttu-id="16acc-238">Name</span><span class="sxs-lookup"><span data-stu-id="16acc-238">Name</span></span> | <span data-ttu-id="16acc-239">Description</span><span class="sxs-lookup"><span data-stu-id="16acc-239">Description</span></span> |
|---|------|-------------|
| <span data-ttu-id="16acc-240">☒</span><span class="sxs-lookup"><span data-stu-id="16acc-240">☒</span></span> | <s>`ToDouble`</s> | <span data-ttu-id="16acc-241">"To" ön konumu, bir işlevi değil bir işlem belirten bir fiil ifadesi içinde sonuçlanır.</span><span class="sxs-lookup"><span data-stu-id="16acc-241">The preposition "to" results in a verb phrase, indicating an operation and not a function.</span></span> |
| <span data-ttu-id="16acc-242">☒</span><span class="sxs-lookup"><span data-stu-id="16acc-242">☒</span></span> | <s>`AsDouble`</s> | <span data-ttu-id="16acc-243">Giriş türü, işlev adından net değildir.</span><span class="sxs-lookup"><span data-stu-id="16acc-243">The input type is not clear from the function name.</span></span> |
| <span data-ttu-id="16acc-244">☒</span><span class="sxs-lookup"><span data-stu-id="16acc-244">☒</span></span> | <s>`PauliArrFromBoolArr`</s> | <span data-ttu-id="16acc-245">Giriş ve çıkış türleri yanlış sırada görünüyor.</span><span class="sxs-lookup"><span data-stu-id="16acc-245">The input and output types appear in the wrong order.</span></span> |
| <span data-ttu-id="16acc-246">☑</span><span class="sxs-lookup"><span data-stu-id="16acc-246">☑</span></span> | `ResultArrAsBoolArr` | <span data-ttu-id="16acc-247">Hem giriş türleri hem de çıkış türleri net.</span><span class="sxs-lookup"><span data-stu-id="16acc-247">Both the input types and output types are clear.</span></span> |

***

### <a name="private-or-internal-names"></a><span data-ttu-id="16acc-248">Özel veya Iç adlar</span><span class="sxs-lookup"><span data-stu-id="16acc-248">Private or Internal Names</span></span> ###

<span data-ttu-id="16acc-249">Çoğu durumda, bir ad bir kitaplık veya proje için dahili olarak kullanılmak üzere veya bir kitaplık tarafından sunulan API 'nin garantili bir parçası değildir.</span><span class="sxs-lookup"><span data-stu-id="16acc-249">In many cases, a name is intended strictly for use internal to a library or project, and is not a guaranteed part of the API offered by a library.</span></span>
<span data-ttu-id="16acc-250">Yalnızca iç kodda yanlışlıkla bağımlılıklara açık hale getirilmeleri için işlevleri ve işlemleri adlandırırken bu durumun büyük bir zaman olduğunu açıkça belirtmek faydalı olur.</span><span class="sxs-lookup"><span data-stu-id="16acc-250">It is helpful to clearly indicate that this is the case when naming functions and operations so that accidental dependencies on internal-only code are made obvious.</span></span>
<span data-ttu-id="16acc-251">Bir işlem veya işlev doğrudan kullanım için tasarlanmamıştır, ancak kısmi uygulama tarafından davranan eşleşen bir çağrılabilir tarafından kullanılması gerekiyorsa, `_` kısmen uygulanan çağrılabilir için ile başlayan bir ad kullanmayı düşünün.</span><span class="sxs-lookup"><span data-stu-id="16acc-251">If an operation or function is not intended for direct use, but rather should be used by a matching callable which acts by partial application, consider using a name starting with `_` for the callable that is partially applied.</span></span>

# <a name="guidance"></a>[<span data-ttu-id="16acc-252">Rehber</span><span class="sxs-lookup"><span data-stu-id="16acc-252">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="16acc-253">Şunları öneririz:</span><span class="sxs-lookup"><span data-stu-id="16acc-253">We suggest:</span></span>

- <span data-ttu-id="16acc-254">Bir işlev, işlem veya Kullanıcı tanımlı tür, bir Q # kitaplığı veya programı için ortak API 'nin bir parçası olmadığında, adının öndeki alt çizgi () ile başladığından emin olun `_` .</span><span class="sxs-lookup"><span data-stu-id="16acc-254">When a function, operation, or user-defined type is not a part of the public API for a Q# library or program, ensure that its name begins with a leading underscore (`_`).</span></span>

# <a name="examples"></a>[<span data-ttu-id="16acc-255">Örnekler</span><span class="sxs-lookup"><span data-stu-id="16acc-255">Examples</span></span>](#tab/examples)

|   | <span data-ttu-id="16acc-256">Name</span><span class="sxs-lookup"><span data-stu-id="16acc-256">Name</span></span> | <span data-ttu-id="16acc-257">Description</span><span class="sxs-lookup"><span data-stu-id="16acc-257">Description</span></span> |
|---|------|-------------|
| <span data-ttu-id="16acc-258">☒</span><span class="sxs-lookup"><span data-stu-id="16acc-258">☒</span></span> | <s>`ApplyDecomposedOperation_`</s> | <span data-ttu-id="16acc-259">Alt çizgi, `_` adın sonunda görünmemelidir.</span><span class="sxs-lookup"><span data-stu-id="16acc-259">The underscore `_` should not appear at the end of the name.</span></span> |
| <span data-ttu-id="16acc-260">☑</span><span class="sxs-lookup"><span data-stu-id="16acc-260">☑</span></span> | `_ApplyDecomposedOperation` | <span data-ttu-id="16acc-261">Başındaki alt çizgi `_` açık bir şekilde bu işlemin yalnızca iç kullanım için olduğunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="16acc-261">The underscore `_` at the beginning clearly indicates that this operation is for internal use only.</span></span> |

***

### <a name="variants"></a><span data-ttu-id="16acc-262">Değişkenler</span><span class="sxs-lookup"><span data-stu-id="16acc-262">Variants</span></span> ###

<span data-ttu-id="16acc-263">Bu sınırlama gelecekteki bir soru-cevap sürümünde kalmayabilir, ancak bu durum genellikle, kendilerine ait oldukları veya bağımsız değişkenlerinin somut türleri tarafından kendilerine ait olan ilgili işlem veya işlev grupları olacaktır.</span><span class="sxs-lookup"><span data-stu-id="16acc-263">Though this limitation may not persist in future versions of Q#, it is presently the case that there will often be groups of related operations or functions that are distinguished by which functors their inputs support, or by the concrete types of their arguments.</span></span>
<span data-ttu-id="16acc-264">Bu gruplar, kendisini belirten bir veya iki harften sonra aynı kök adı kullanılarak ayırt edilebilir.</span><span class="sxs-lookup"><span data-stu-id="16acc-264">These groups can be distinguished by using the same root name, followed by one or two letters that indicate its variant.</span></span>

| <span data-ttu-id="16acc-265">Önekini</span><span class="sxs-lookup"><span data-stu-id="16acc-265">Suffix</span></span> | <span data-ttu-id="16acc-266">Anlamı</span><span class="sxs-lookup"><span data-stu-id="16acc-266">Meaning</span></span> |
|--------|---------|
| `A` | <span data-ttu-id="16acc-267">Destek için giriş bekleniyor`Adjoint`</span><span class="sxs-lookup"><span data-stu-id="16acc-267">Input expected to support `Adjoint`</span></span> |
| `C` | <span data-ttu-id="16acc-268">Destek için giriş bekleniyor`Controlled`</span><span class="sxs-lookup"><span data-stu-id="16acc-268">Input expected to support `Controlled`</span></span> |
| `CA` | <span data-ttu-id="16acc-269">Destek için giriş bekleniyordu `Controlled` ve`Adjoint`</span><span class="sxs-lookup"><span data-stu-id="16acc-269">Input expected to support `Controlled` and `Adjoint`</span></span> |
| `I` | <span data-ttu-id="16acc-270">Giriş veya girişler tür`Int`</span><span class="sxs-lookup"><span data-stu-id="16acc-270">Input or inputs are of type `Int`</span></span> |
| `D` | <span data-ttu-id="16acc-271">Giriş veya girişler tür`Double`</span><span class="sxs-lookup"><span data-stu-id="16acc-271">Input or inputs are of type `Double`</span></span> |
| `L` | <span data-ttu-id="16acc-272">Giriş veya girişler tür`BigInt`</span><span class="sxs-lookup"><span data-stu-id="16acc-272">Input or inputs are of type `BigInt`</span></span> |

# <a name="guidance"></a>[<span data-ttu-id="16acc-273">Rehber</span><span class="sxs-lookup"><span data-stu-id="16acc-273">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="16acc-274">Şunları öneririz:</span><span class="sxs-lookup"><span data-stu-id="16acc-274">We suggest:</span></span>

- <span data-ttu-id="16acc-275">Bir işlev veya işlem, girişlerinin türleri ve functor desteğiyle benzer işlevlerle veya işlemlerle ilişkili değilse, bir sonek kullanmayın.</span><span class="sxs-lookup"><span data-stu-id="16acc-275">If a function or operation is not related to any similar functions or operations by the types and functor support of their inputs, do not use a suffix.</span></span>
- <span data-ttu-id="16acc-276">Bir işlev veya işlem, girişlerinin türleri ve functor desteğiyle benzer işlevlerle veya işlemlerle ilişkiliyse, sapmaları ayırt etmek için yukarıdaki tabloda olduğu gibi sonekleri kullanın.</span><span class="sxs-lookup"><span data-stu-id="16acc-276">If a function or operation is related to any similar functions or operations by the types and functor support of their inputs, use suffixes as in the table above to distinguish variants.</span></span>

# <a name="examples"></a>[<span data-ttu-id="16acc-277">Örnekler</span><span class="sxs-lookup"><span data-stu-id="16acc-277">Examples</span></span>](#tab/examples)

***

### <a name="arguments-and-variables"></a><span data-ttu-id="16acc-278">Bağımsız değişkenler ve değişkenler</span><span class="sxs-lookup"><span data-stu-id="16acc-278">Arguments and Variables</span></span> ###

<span data-ttu-id="16acc-279">Bir işlev veya işlem için Q # kodunun anahtar hedefi kolayca okunabilme ve anlaşılmalıdır.</span><span class="sxs-lookup"><span data-stu-id="16acc-279">A key goal of the Q# code for a function or operation is for it to be easily read and understood.</span></span>
<span data-ttu-id="16acc-280">Benzer şekilde, giriş ve tür bağımsız değişkenlerinin adları, bir işlev veya bağımsız değişkenin sağlandığı bir şekilde nasıl kullanılacağını iletmelidir.</span><span class="sxs-lookup"><span data-stu-id="16acc-280">Similarly, the names of inputs and type arguments should communicate how a function or argument will be used once provided.</span></span>


# <a name="guidance"></a>[<span data-ttu-id="16acc-281">Rehber</span><span class="sxs-lookup"><span data-stu-id="16acc-281">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="16acc-282">Şunları öneririz:</span><span class="sxs-lookup"><span data-stu-id="16acc-282">We suggest:</span></span>

- <span data-ttu-id="16acc-283">Tüm değişken ve giriş adları için, `pascalCase` veya için güçlü bir tercih içinde kullanın `CamelCase` `snake_case` `ANGRY_CASE` .</span><span class="sxs-lookup"><span data-stu-id="16acc-283">For all variable and input names, use `pascalCase` in strong preference to `CamelCase`, `snake_case`, or `ANGRY_CASE`.</span></span>
- <span data-ttu-id="16acc-284">Giriş adları açıklayıcı olmalıdır; mümkün olduğunda bir veya iki harfli adlardan kaçının.</span><span class="sxs-lookup"><span data-stu-id="16acc-284">Input names should be descriptive; avoid one or two letter names where possible.</span></span>
- <span data-ttu-id="16acc-285">Tam olarak bir tür bağımsız değişkeni kabul eden işlemler ve işlevler, rolü belirgin olduğunda bu tür bağımsız değişkenini göstermelidir `T` .</span><span class="sxs-lookup"><span data-stu-id="16acc-285">Operations and functions accepting exactly one type argument should denote that type argument by `T` when its role is obvious.</span></span>
- <span data-ttu-id="16acc-286">Bir işlev veya işlem birden çok tür bağımsız değişkeni alırsa veya tek bir tür bağımsız değişkeninin rolü açık değilse, `T` her tür için (ör.:) kısa harfli bir sözcük kullanmayı düşünün `TOutput` .</span><span class="sxs-lookup"><span data-stu-id="16acc-286">If a function or operation takes multiple type arguments, or if the role of a single type argument is not obvious, consider using a short capitalized word prefaced by `T` (e.g.: `TOutput`) for each type.</span></span>
- <span data-ttu-id="16acc-287">Bağımsız değişkene ve değişken adlarına tür adlarını eklemeyin; Bu bilgiler, geliştirme ortamınız tarafından sağlanmış ve sağlanmalıdır.</span><span class="sxs-lookup"><span data-stu-id="16acc-287">Do not include type names in argument and variable names; this information can and should be provided by your development environment.</span></span>
- <span data-ttu-id="16acc-288">Skalar türlerini, sabit adlarına ( `flagQubit` ) ve dizi türlerini bir plural () ile gösterir `measResults` .</span><span class="sxs-lookup"><span data-stu-id="16acc-288">Denote scalar types by their literal names (`flagQubit`), and array types by a plural (`measResults`).</span></span>
  <span data-ttu-id="16acc-289">Belirli qubit dizileri için, bu tür türleri `Register` , adın bir şekilde daha yakından ilişkili bir qubit dizisine başvurduğu şekilde belirtmeyi düşünün.</span><span class="sxs-lookup"><span data-stu-id="16acc-289">For arrays of qubits in particular, consider denoting such types by `Register` where the name refers to a sequence of qubits that are closely related in some way.</span></span>
- <span data-ttu-id="16acc-290">Dizilerde dizin olarak kullanılan değişkenler, ile başlamalı `idx` ve tekil olmalıdır (ör.: `things[idxThing]` ).</span><span class="sxs-lookup"><span data-stu-id="16acc-290">Variables used as indices into arrays should begin with `idx` and should be singular (e.g.: `things[idxThing]`).</span></span>
  <span data-ttu-id="16acc-291">Özellikle, tek harfli değişken adlarını dizin olarak kullanmaktan kesinlikle kaçının; En azından kullanmayı göz önünde bulundurun `idx` .</span><span class="sxs-lookup"><span data-stu-id="16acc-291">In particular, strongly avoid using single-letter variable names as indices; consider using `idx` at a minimum.</span></span>
- <span data-ttu-id="16acc-292">Dizi uzunluklarını tutmak için kullanılan değişkenler, ile başlamalı `n` ve plurar (ör.: `nThings` ) olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="16acc-292">Variables used to hold lengths of arrays should begin with `n` and should be pluralized (e.g.: `nThings`).</span></span>

# <a name="examples"></a>[<span data-ttu-id="16acc-293">Örnekler</span><span class="sxs-lookup"><span data-stu-id="16acc-293">Examples</span></span>](#tab/examples)

***

### <a name="user-defined-type-named-items"></a><span data-ttu-id="16acc-294">Kullanıcı tanımlı tür öğeleri</span><span class="sxs-lookup"><span data-stu-id="16acc-294">User-Defined Type Named Items</span></span> ###

<span data-ttu-id="16acc-295">Kullanıcı tanımlı türlerdeki adlandırılmış öğeler `CamelCase` , udt oluşturucularının girişinde bile olarak adlandırılmalıdır.</span><span class="sxs-lookup"><span data-stu-id="16acc-295">Named items in user-defined types should be named as `CamelCase`, even in input to UDT constructors.</span></span>
<span data-ttu-id="16acc-296">Bu, erişimci gösterimini (ör.: `callable::Apply` ) veya kopyalama ve güncelleştirme gösterimini () kullanırken, adlandırılmış öğeleri yerel kapsamlı değişkenlere göre açıkça ayırmak için yardımcı olur `set arr w/= Data <- newData` .</span><span class="sxs-lookup"><span data-stu-id="16acc-296">This helps in order to clearly separate named items from references to locally scoped variables when using accessor notation (e.g.: `callable::Apply`) or copy-and-update notation (`set arr w/= Data <- newData`).</span></span>

# <a name="guidance"></a>[<span data-ttu-id="16acc-297">Rehber</span><span class="sxs-lookup"><span data-stu-id="16acc-297">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="16acc-298">Şunları öneririz:</span><span class="sxs-lookup"><span data-stu-id="16acc-298">We suggest:</span></span>

- <span data-ttu-id="16acc-299">UDT oluşturucularında adlandırılmış öğeler olarak adlandırılmalıdır `CamelCase` ; diğer bir deyişle, ilk büyük harfle başlamalıdır.</span><span class="sxs-lookup"><span data-stu-id="16acc-299">Named items in UDT constructors should be named as `CamelCase`; that is, they should begin with an initial uppercase.</span></span>
- <span data-ttu-id="16acc-300">İşlemlere çözüm veren adlandırılmış öğeler fiil aşamaları olarak adlandırılmalıdır.</span><span class="sxs-lookup"><span data-stu-id="16acc-300">Named items that resolve to operations should be named as verb phases.</span></span>
- <span data-ttu-id="16acc-301">İşlemlere çözümlenmez adlandırılmış öğeler, ad ifadeleri olarak adlandırılmalıdır.</span><span class="sxs-lookup"><span data-stu-id="16acc-301">Named items that do not resolve to operations should be named as noun phrases.</span></span>
- <span data-ttu-id="16acc-302">Sarmalı işlemler için, adlı tek bir adlandırılmış öğe `Apply` tanımlanmalıdır.</span><span class="sxs-lookup"><span data-stu-id="16acc-302">For UDTs that wrap operations, a single named item called `Apply` should be defined.</span></span>

# <a name="examples"></a>[<span data-ttu-id="16acc-303">Örnekler</span><span class="sxs-lookup"><span data-stu-id="16acc-303">Examples</span></span>](#tab/examples)

|   | <span data-ttu-id="16acc-304">Kod Parçacığı</span><span class="sxs-lookup"><span data-stu-id="16acc-304">Snippet</span></span> | <span data-ttu-id="16acc-305">Description</span><span class="sxs-lookup"><span data-stu-id="16acc-305">Description</span></span> |
|---|---------|-------------|
| <span data-ttu-id="16acc-306">☑</span><span class="sxs-lookup"><span data-stu-id="16acc-306">☑</span></span> | `newtype Oracle = (Apply : Qubit[] => Unit is Adj + Ctl)` | <span data-ttu-id="16acc-307">Ad, `Apply` `CamelCase` adlandırılmış öğenin bir işlem olmasını öneren, biçimli bir fiil tümceciktir.</span><span class="sxs-lookup"><span data-stu-id="16acc-307">The name `Apply` is a `CamelCase`-formatted verb phrase, suggesting that the named item is an operation.</span></span> |
| <span data-ttu-id="16acc-308">☒</span><span class="sxs-lookup"><span data-stu-id="16acc-308">☒</span></span> | <s>`newtype Oracle = (apply : Qubit[] => Unit is Adj + Ctl) `</s> | <span data-ttu-id="16acc-309">Adlandırılmış öğeler ilk büyük harfle başlamalıdır.</span><span class="sxs-lookup"><span data-stu-id="16acc-309">Named items should begin with an initial uppercase letter.</span></span> |
| <span data-ttu-id="16acc-310">☒</span><span class="sxs-lookup"><span data-stu-id="16acc-310">☒</span></span> | <s>`newtype Collection = (Length : Int, Get : Int -> (Qubit => Unit)) `</s> | <span data-ttu-id="16acc-311">İşlevlerine çözüm veren adlandırılmış öğeler, fiil ifadeleri olarak değil, ad ifadeleri olarak adlandırılmalıdır.</span><span class="sxs-lookup"><span data-stu-id="16acc-311">Named items which resolve to functions should be named as noun phrases, not as verb phrases.</span></span> |

***

## <a name="input-conventions"></a><span data-ttu-id="16acc-312">Giriş kuralları</span><span class="sxs-lookup"><span data-stu-id="16acc-312">Input Conventions</span></span> ##

<span data-ttu-id="16acc-313">Bir geliştirici bir işlem veya işleve çağırdığında, bu işlem veya işleve yönelik çeşitli girişler belirli bir sırada belirtilmelidir, bu da bir geliştiricinin bir kitaplığı kullanabilmesi için bir geliştiricinin yüzlü yükünü artırır.</span><span class="sxs-lookup"><span data-stu-id="16acc-313">When a developer calls into an operation or function, the various inputs to that operation or function must be specified in a particular order, increasing the cognitive load that a developer faces in order to make use of a library.</span></span>
<span data-ttu-id="16acc-314">Özellikle, giriş sıralamayı hatırlama görevi genellikle her seferinde bir, bir hisse algoritması uygulamasını programlama.</span><span class="sxs-lookup"><span data-stu-id="16acc-314">In particular, the task of remembering input orderings is often a distraction from the task at hand: programming an implementation of a quantum algorithm.</span></span>
<span data-ttu-id="16acc-315">Zengin IDE desteği bunu büyük ölçüde azaltır, yaygın kurallara uygun tasarım ve bağlılığı, bir API tarafından uygulanan bilişsel yükün en aza indirilmesine yardımcı olabilir.</span><span class="sxs-lookup"><span data-stu-id="16acc-315">Though rich IDE support can mitigate this to a large extent, good design and adherence to common conventions can also help to minimize the cognitive load imposed by an API.</span></span>

<span data-ttu-id="16acc-316">Mümkün olduğunda, bir işlem veya işlev tarafından beklenen giriş sayısını azaltmak faydalı olabilir, böylece her girdinin rolü hem bu işlem veya işlevi çağıran geliştiriciler için hem de bu kodu daha sonra okuyan geliştiriciler için daha fazla belirgin hale gelir.</span><span class="sxs-lookup"><span data-stu-id="16acc-316">Where possible, it can be helpful to reduce the number of inputs expected by an operation or function, so that the role of each input is more immediately obvious both to developers calling into that operation or function, and to developers reading that code later.</span></span>
<span data-ttu-id="16acc-317">Özellikle bir işlem veya işlev için bağımsız değişken sayısını azaltmak mümkün olmadığında veya makul olmadığında, bir kullanıcının giriş sırasını tahmin eden zaman şaşırmasını en aza indiren tutarlı bir sıralama olması önemlidir.</span><span class="sxs-lookup"><span data-stu-id="16acc-317">Especially when it is not possible or reasonable to reduce the number of arguments to an operation or function, it is important to have a consistent ordering that minimizes the surprise that a user faces when predicting the order of inputs.</span></span>

<span data-ttu-id="16acc-318">Büyük bir uygulamanın, f (x, y) ≡ f (x) (y) ile bir genelleştirme olarak düşünmekten büyük ölçüde türettiği bir giriş sıralaması kuralları öneririz.</span><span class="sxs-lookup"><span data-stu-id="16acc-318">We recommend an input ordering conventions that largely derives from thinking of partial application as a generalization of currying 𝑓(𝑥, 𝑦) ≡ 𝑓(𝑥)(𝑦).</span></span>
<span data-ttu-id="16acc-319">Bu nedenle, ilk bağımsız değişkenlerin kısmen uygulanması, her ne kadar uygun olan her zaman kendi kendine yararlı bir çağrılabilir ile sonuçlanmalıdır.</span><span class="sxs-lookup"><span data-stu-id="16acc-319">Thus, partially applying the first arguments should result in a callable that is useful in its own right whenever that is reasonable.</span></span>
<span data-ttu-id="16acc-320">Bu ilkeyi izleyerek aşağıdaki bağımsız değişken sırasını kullanmayı göz önünde bulundurun:</span><span class="sxs-lookup"><span data-stu-id="16acc-320">Following this principle, consider using the following order of arguments:</span></span>

- <span data-ttu-id="16acc-321">Açılamayan, açıların vektörleri, üslerdeki vektörler vb. gibi çağrılabilir olmayan bağımsız değişkenler</span><span class="sxs-lookup"><span data-stu-id="16acc-321">Classical non-callable arguments such as angles, vectors of powers, etc.</span></span>
- <span data-ttu-id="16acc-322">Çağrılabilir bağımsız değişkenler (işlevler ve bağımsız değişkenler).</span><span class="sxs-lookup"><span data-stu-id="16acc-322">Callable arguments (functions and arguments).</span></span>
  <span data-ttu-id="16acc-323">Her iki işlev ve işlem bağımsız değişken olarak götürülüyorsanız, işlemleri işlevlerden sonra yerleştirmeyi göz önünde bulundurun.</span><span class="sxs-lookup"><span data-stu-id="16acc-323">If both functions and operations are taken as arguments, consider placing operations after functions.</span></span>
- <span data-ttu-id="16acc-324">,, Ve için benzer bir şekilde çağrılabilir bağımsız değişkenlerle üzerinde işlem yapan koleksiyonlar `Map` `Iter` `Enumerate` `Fold` .</span><span class="sxs-lookup"><span data-stu-id="16acc-324">Collections acted upon by callable arguments in a similar way to `Map`, `Iter`, `Enumerate`, and `Fold`.</span></span>
- <span data-ttu-id="16acc-325">Denetimler olarak kullanılan qubit bağımsız değişkenleri.</span><span class="sxs-lookup"><span data-stu-id="16acc-325">Qubit arguments used as controls.</span></span>
- <span data-ttu-id="16acc-326">Hedef olarak kullanılan qubit bağımsız değişkenleri.</span><span class="sxs-lookup"><span data-stu-id="16acc-326">Qubit arguments used as targets.</span></span>

<span data-ttu-id="16acc-327">Bir `ApplyPhaseEstimationIteration` açıyı, bir açı ve Oracle alan bir işlem tahminlerinde kullanmak için bir işlem düşünün, açıyı `Rz` farklı ölçekleme faktörleri dizisiyle geçirir ve sonra Oracle 'ın uygulamalarını denetler.</span><span class="sxs-lookup"><span data-stu-id="16acc-327">Consider an operation `ApplyPhaseEstimationIteration` for use in phase estimation that takes an angle and an oracle, passes the angle to `Rz` modified by an array of different scaling factors, and then controls applications of the oracle.</span></span>
<span data-ttu-id="16acc-328">Girişleri `ApplyPhaseEstimationIteration` aşağıdaki biçimde sıraya ekleyeceğiz:</span><span class="sxs-lookup"><span data-stu-id="16acc-328">We would order the inputs to `ApplyPhaseEstimationIteration` in the following fashion:</span></span>

```qsharp
operation ApplyPhaseEstimationIteration(
    angle : Double,
    callable : (Qubit => () is Ctl),
    scaleFactors : Double[],
    controlQubit : Qubit,
    targetQubits : Qubit[]
)
: Unit
...
```
<span data-ttu-id="16acc-329">Bazı işlevler ve işlemler beklenmedik bir şekilde en aza indirildiği için, bazı işlevler ve işlemler yerleşik komik ve ' ın davranışını taklit ediyor `Adjoint` `Controlled` .</span><span class="sxs-lookup"><span data-stu-id="16acc-329">As a special case of minimizing surprise, some functions and operations mimic the behavior of the built-in functors `Adjoint` and `Controlled`.</span></span>
<span data-ttu-id="16acc-330">Örneğin, `ControlledOnInt<'T>` `(Int, ('T => Unit is Adj + Ctl)) => ((Qubit[], 'T) => Unit is Adj + Ctl)` `ControlledOnInt<Qubit[]>(5, _)` functor gibi davranan, `Controlled` ancak denetim kaydının $ \ket {5} = \ket $ durumunu temsil ettiği koşulda, türü vardır {101} .</span><span class="sxs-lookup"><span data-stu-id="16acc-330">For instance, `ControlledOnInt<'T>` has type `(Int, ('T => Unit is Adj + Ctl)) => ((Qubit[], 'T) => Unit is Adj + Ctl)`, such that `ControlledOnInt<Qubit[]>(5, _)` acts like the `Controlled` functor, but on the condition that the control register represents the state $\ket{5} = \ket{101}$.</span></span>
<span data-ttu-id="16acc-331">Bu nedenle, bir geliştirici, `ControlledOnInt` çağrılabilir 'in, en son dönüştürülmüş değerini yerleştirmesini ve sonuçta elde edilen işlemin giriş---, diğer bir deyişle, `(Qubit[], 'T)` functor çıkışı tarafından aynı sırada sürdüğünü bekler `Controlled` .</span><span class="sxs-lookup"><span data-stu-id="16acc-331">Thus, a developer expects that the inputs to `ControlledOnInt` place the callable being transformed last, and that the resulting operation takes as its input `(Qubit[], 'T)` --- the same order as followed by the output of the `Controlled` functor.</span></span>

# <a name="guidance"></a>[<span data-ttu-id="16acc-332">Rehber</span><span class="sxs-lookup"><span data-stu-id="16acc-332">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="16acc-333">Şunları öneririz:</span><span class="sxs-lookup"><span data-stu-id="16acc-333">We suggest:</span></span>

- <span data-ttu-id="16acc-334">Kısmi uygulama kullanımıyla tutarlı giriş sırası kullanın.</span><span class="sxs-lookup"><span data-stu-id="16acc-334">Use input orderings consistent with the use of partial application.</span></span>
- <span data-ttu-id="16acc-335">Yerleşik komik ile tutarlı giriş sırası kullanın.</span><span class="sxs-lookup"><span data-stu-id="16acc-335">Use input orderings consistent with built-in functors.</span></span>
- <span data-ttu-id="16acc-336">Tüm klasik girişleri, tüm hisse girişlerinden önce yerleştirin.</span><span class="sxs-lookup"><span data-stu-id="16acc-336">Place all classical inputs before any quantum inputs.</span></span>

# <a name="examples"></a>[<span data-ttu-id="16acc-337">Örnekler</span><span class="sxs-lookup"><span data-stu-id="16acc-337">Examples</span></span>](#tab/examples)

***

## <a name="documentation-conventions"></a><span data-ttu-id="16acc-338">Belge kuralları</span><span class="sxs-lookup"><span data-stu-id="16acc-338">Documentation Conventions</span></span> ##

<span data-ttu-id="16acc-339">Q # dili, özel olarak biçimlendirilmiş belge açıklamalarını kullanarak işlemlere, işlevlere ve Kullanıcı tanımlı türlere belge iliştirmeye olanak tanır.</span><span class="sxs-lookup"><span data-stu-id="16acc-339">The Q# language allows for attaching documentation to operations, functions, and user-defined types through the use of specially formatted documentation comments.</span></span>
<span data-ttu-id="16acc-340">Üçlü eğik çizgi () tarafından belirtilen `///` Bu belge Yorumları, her bir işlemin, işlevin ve Kullanıcı tanımlı türün amacını açıklamak için kullanılabilen küçük [docfx-flavored](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html) , her beklediği girişi, vb..</span><span class="sxs-lookup"><span data-stu-id="16acc-340">Denoted by triple-slashes (`///`), these documentation comments are small [DocFX-flavored Markdown](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html) documents that can be used to describing the purpose of each operation, function, and user-defined type, what inputs each expects, and so forth.</span></span>
<span data-ttu-id="16acc-341">Hisse geliştirme seti ile sağlanan derleyici, bu açıklamaları ayıklar ve bu yorumları, ' deki şuna benzer şekilde karakterlik alan kaplamaları belgelerine yardımcı olmak için kullanır https://docs.microsoft.com/quantum .</span><span class="sxs-lookup"><span data-stu-id="16acc-341">The compiler provided with the Quantum Development Kit extracts these comments and uses them to help typeset documentation similar to that at https://docs.microsoft.com/quantum.</span></span>
<span data-ttu-id="16acc-342">Benzer şekilde, hisse geliştirme kiti ile birlikte sağlanan dil sunucusu, kullanıcılar için Q # kodundaki sembolleri üzerine getirdiğinde yardım sağlamak üzere bu açıklamaları kullanır.</span><span class="sxs-lookup"><span data-stu-id="16acc-342">Similarly, the language server provided with the Quantum Development Kit uses these comments to provide help to users when they hover over symbols in their Q# code.</span></span>
<span data-ttu-id="16acc-343">Belge açıklamalarının kullanımı, bu belgedeki diğer kurallara göre kolayca ifade olmayan Ayrıntılar için yararlı bir başvuru sunarak kullanıcıların kod anlamlı olmasına yardımcı olabilir.</span><span class="sxs-lookup"><span data-stu-id="16acc-343">Making use of documentation comments can thus help users to make sense of code by providing a useful reference for details that are not easily expressed using the other conventions in this document.</span></span>

<div class="nextstepaction"><span data-ttu-id="16acc-344">
    [Belge açıklaması sözdizimi başvurusu](xref:microsoft.quantum.guide.filestructure#documentation-comments)
</span><span class="sxs-lookup"><span data-stu-id="16acc-344">
    [Documentation comment syntax reference](xref:microsoft.quantum.guide.filestructure#documentation-comments)
</span></span></div>

<span data-ttu-id="16acc-345">Kullanıcılara yardımcı olmak üzere bu işlevselliği etkili bir şekilde kullanabilmek için, belge açıklamalarını yazarken göz önünde bulundurmanız önerilir.</span><span class="sxs-lookup"><span data-stu-id="16acc-345">In order to effectively use this functionality to help users, we recommend keeping a few things in mind as you write documentation comments.</span></span>

# <a name="guidance"></a>[<span data-ttu-id="16acc-346">Rehber</span><span class="sxs-lookup"><span data-stu-id="16acc-346">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="16acc-347">Şunları öneririz:</span><span class="sxs-lookup"><span data-stu-id="16acc-347">We suggest:</span></span>

- <span data-ttu-id="16acc-348">Her ortak işlev, işlem ve Kullanıcı tanımlı tür hemen öncesinde bir belge yorumu gelmelidir.</span><span class="sxs-lookup"><span data-stu-id="16acc-348">Each public function, operation, and user-defined type should be immediately preceded by a documentation comment.</span></span>
- <span data-ttu-id="16acc-349">En azından, her belge yorumu aşağıdaki bölümleri içermelidir:</span><span class="sxs-lookup"><span data-stu-id="16acc-349">At a minimum, each documentation comment should include the following sections:</span></span>
    - <span data-ttu-id="16acc-350">Özet</span><span class="sxs-lookup"><span data-stu-id="16acc-350">Summary</span></span>
    - <span data-ttu-id="16acc-351">Giriş</span><span class="sxs-lookup"><span data-stu-id="16acc-351">Input</span></span>
    - <span data-ttu-id="16acc-352">Çıkış (varsa)</span><span class="sxs-lookup"><span data-stu-id="16acc-352">Output (if applicable)</span></span>
- <span data-ttu-id="16acc-353">Tüm özetlerin iki cümle veya daha az olduğundan emin olun.</span><span class="sxs-lookup"><span data-stu-id="16acc-353">Ensure that all summaries are two sentences or less.</span></span> <span data-ttu-id="16acc-354">Daha fazla oda gerekiyorsa, `# Description` tüm ayrıntılarla hemen takip eden bir bölüm sağlayın `# Summary` .</span><span class="sxs-lookup"><span data-stu-id="16acc-354">If more room is needed, provide a `# Description` section immediately following `# Summary` with complete details.</span></span>
- <span data-ttu-id="16acc-355">Her türlü istemci, özetler içinde TeX gösterimini desteklemediği için, her ikisi de, özetler halinde matematik dahil değildir.</span><span class="sxs-lookup"><span data-stu-id="16acc-355">Where reasonable, do not include math in summaries, as not all clients support TeX notation in summaries.</span></span> <span data-ttu-id="16acc-356">Prose belgeleri yazarken (örn. TeX veya Markaşağı), daha uzun çizgi uzunluklarının kullanılması tercih edilebilir.</span><span class="sxs-lookup"><span data-stu-id="16acc-356">Note that when writing prose documents (e.g. TeX or Markdown), it may be preferable to use longer line lengths.</span></span>
- <span data-ttu-id="16acc-357">Bölümündeki tüm ilgili matematik ifadelerini belirtin `# Description` .</span><span class="sxs-lookup"><span data-stu-id="16acc-357">Provide all relevant mathematical expressions in the `# Description` section.</span></span>
- <span data-ttu-id="16acc-358">Girişleri açıkladığınızda, derleyici tarafından çıkarsanabilecek ve tutarsızlık doğurabilecek şekilde her girişin türlerini tekrarlamayın.</span><span class="sxs-lookup"><span data-stu-id="16acc-358">When describing inputs, do not repeat the types of each input as these can be inferred by the compiler and risk introducing inconsistency.</span></span>
- <span data-ttu-id="16acc-359">Her biri kendi bölümünde uygun şekilde örnekler sağlayın `# Example` .</span><span class="sxs-lookup"><span data-stu-id="16acc-359">Provide examples as appropriate, each in their own `# Example` section.</span></span>
- <span data-ttu-id="16acc-360">Kodu listelemeyi yapmadan önce her bir örneği kısaca açıklama yapın.</span><span class="sxs-lookup"><span data-stu-id="16acc-360">Briefly describe each example before listing code.</span></span>
- <span data-ttu-id="16acc-361">Bir bölümdeki tüm ilgili akademik yayınları (örn. incelemeler, devam edimler, blog gönderileri ve alternatif uygulamalar) `# References` madde işaretli bağlantı listesi olarak belirtin.</span><span class="sxs-lookup"><span data-stu-id="16acc-361">Cite all relevant academic publications (e.g.: papers, proceedings, blog posts, and alternative implementations) in a `# References` section as a bulleted list of links.</span></span>
- <span data-ttu-id="16acc-362">Mümkün olduğunda, tüm alıntı bağlantılarının kalıcı ve sabit tanımlayıcılar (Doın veya sürümlenmiş Arxıv numaraları) olduğundan emin olun.</span><span class="sxs-lookup"><span data-stu-id="16acc-362">Ensure that, where possible, all citation links are to permanent and immutable identifiers (DOIs or versioned arXiv numbers).</span></span>
- <span data-ttu-id="16acc-363">Bir işlem veya işlev, functor türevlerine göre diğer işlemlerle veya işlevlerle ilişkiliyse, diğer çeşitleri bölümünde madde işaretleri olarak listeleyin `# See Also` .</span><span class="sxs-lookup"><span data-stu-id="16acc-363">When an operation or function is related to other operations or functions by functor variants, list other variants as bullets in the `# See Also` section.</span></span>
- <span data-ttu-id="16acc-364">Level-1 () bölümleri arasında boş bir yorum çizgisi bırakın `/// #` , ancak Level-2 () bölümleri arasında boş bir satır bırakmayın `/// ##` .</span><span class="sxs-lookup"><span data-stu-id="16acc-364">Leave a blank comment line between level-1 (`/// #`) sections, but do not leave a blank line between level-2 (`/// ##`) sections.</span></span>

# <a name="examples"></a>[<span data-ttu-id="16acc-365">Örnekler</span><span class="sxs-lookup"><span data-stu-id="16acc-365">Examples</span></span>](#tab/examples)

#### <a name=""></a><span data-ttu-id="16acc-366">☑</span><span class="sxs-lookup"><span data-stu-id="16acc-366">☑</span></span> ####

```
/// # Summary
/// Applies a rotation about the X-axis by a given angle.
///
///
/// # Description
/// This operation rotates a single qubit by the unitary operation
/// \begin{align}
///     R_x(\theta) \mathrel{:=} e^{-i \theta \sigma_x / 2}.
/// \end{align}
///
/// # Input
/// ## theta
/// Angle about which the qubit is to be rotated.
/// ## qubit
/// Qubit to which the gate should be applied.
///
/// # Remarks
/// Equivalent to:
/// ```qsharp
/// R(PauliX, theta, qubit);
/// ```
///
/// # See Also
/// - Ry
/// - Rz
operation Rx(theta : Double, qubit : Qubit) : Unit
is Adj + Ctl {
    body (...) { R(PauliX, theta, qubit); }
    adjoint (...) { R(PauliX, -theta, qubit); }
}
```

***

## <a name="formatting-conventions"></a><span data-ttu-id="16acc-367">Biçimlendirme kuralları</span><span class="sxs-lookup"><span data-stu-id="16acc-367">Formatting Conventions</span></span> ##

<span data-ttu-id="16acc-368">Önceki önerilere ek olarak, tutarlı biçimlendirme kuralları kullanmak için kodun mümkün olduğunca okunabilir olmasını sağlamaya yardımcı olmak yararlı olur.</span><span class="sxs-lookup"><span data-stu-id="16acc-368">In addition to the preceding suggestions, it is helpful to help make code as legible as possible to use consistent formatting rules.</span></span>
<span data-ttu-id="16acc-369">Doğası gereği bu tür biçimlendirme kuralları, kişisel aesmerkler için biraz rastgele ve kesin bir şekilde çalışır.</span><span class="sxs-lookup"><span data-stu-id="16acc-369">Such formatting rules by nature tend to be somewhat arbitrary and strongly up to personal aesthetics.</span></span>
<span data-ttu-id="16acc-370">Nonetheless, bir ortak grup içinde tutarlı bir biçimlendirme kuralları kümesi ve özellikle de hisse geliştirme seti gibi büyük Q # projeleri için bakım yapmanızı öneririz.</span><span class="sxs-lookup"><span data-stu-id="16acc-370">Nonetheless, we recommend maintaining a consistent set of formatting conventions within a group of collaborators, and especially for large Q# projects such as the Quantum Development Kit itself.</span></span>
<span data-ttu-id="16acc-371">Bu kurallar, Q # derleyicisi ile tümleştirilmiş biçimlendirme Aracı kullanılarak otomatik olarak uygulanabilir.</span><span class="sxs-lookup"><span data-stu-id="16acc-371">These rules can be automatically applied by using the formatting tool integrated with the Q# compiler.</span></span>

# <a name="guidance"></a>[<span data-ttu-id="16acc-372">Rehber</span><span class="sxs-lookup"><span data-stu-id="16acc-372">Guidance</span></span>](#tab/guidance) 

<span data-ttu-id="16acc-373">Şunları öneririz:</span><span class="sxs-lookup"><span data-stu-id="16acc-373">We suggest:</span></span>

- <span data-ttu-id="16acc-374">Taşınabilirlik için sekmeler yerine dört boşluk kullanın.</span><span class="sxs-lookup"><span data-stu-id="16acc-374">Use four spaces instead of tabs for portability.</span></span>
  <span data-ttu-id="16acc-375">Örneğin, VS Code:</span><span class="sxs-lookup"><span data-stu-id="16acc-375">For instance, in VS Code:</span></span>
  ```json
    "editor.insertSpaces": true,
    "editor.tabSize": 4
  ```
- <span data-ttu-id="16acc-376">Satır kaydırması, makul yerlerde 79 karakterden oluşmalıdır.</span><span class="sxs-lookup"><span data-stu-id="16acc-376">Line wrap at 79 characters where reasonable.</span></span>
- <span data-ttu-id="16acc-377">İkili işleçler etrafında boşluklar kullanın.</span><span class="sxs-lookup"><span data-stu-id="16acc-377">Use spaces around binary operators.</span></span>
- <span data-ttu-id="16acc-378">Tür ek açıklamaları için kullanılan iki nokta üst kısmında boşluk kullanın.</span><span class="sxs-lookup"><span data-stu-id="16acc-378">Use spaces on either side of colons used for type annotations.</span></span>
- <span data-ttu-id="16acc-379">Dizide ve tanımlama değerlerinde kullanılan virgüllerden sonra tek bir boşluk kullanın (örneğin, işlev ve işlemlere yönelik girişler).</span><span class="sxs-lookup"><span data-stu-id="16acc-379">Use a single space after commas used in array and tuple literals (e.g.: in inputs to functions and operations).</span></span>
- <span data-ttu-id="16acc-380">İşlev, işlem veya UDT adlarından sonra veya `@` öznitelik bildirimlerinden sonra boşluk kullanmayın.</span><span class="sxs-lookup"><span data-stu-id="16acc-380">Do not use spaces after function, operation, or UDT names, or after the `@` in attribute declarations.</span></span>
- <span data-ttu-id="16acc-381">Her öznitelik bildirimi kendi satırında olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="16acc-381">Each attribute declaration should be on its own line.</span></span>

# <a name="examples"></a>[<span data-ttu-id="16acc-382">Örnekler</span><span class="sxs-lookup"><span data-stu-id="16acc-382">Examples</span></span>](#tab/examples)

|   | <span data-ttu-id="16acc-383">Kod Parçacığı</span><span class="sxs-lookup"><span data-stu-id="16acc-383">Snippet</span></span> | <span data-ttu-id="16acc-384">Description</span><span class="sxs-lookup"><span data-stu-id="16acc-384">Description</span></span> |
|---|---------|-------------|
| <span data-ttu-id="16acc-385">☒</span><span class="sxs-lookup"><span data-stu-id="16acc-385">☒</span></span> | <s>`2+3`</s> | <span data-ttu-id="16acc-386">İkili işleçler etrafında boşluklar kullanın.</span><span class="sxs-lookup"><span data-stu-id="16acc-386">Use spaces around binary operators.</span></span> |
| <span data-ttu-id="16acc-387">☒</span><span class="sxs-lookup"><span data-stu-id="16acc-387">☒</span></span> | <s>`target:Qubit`</s> | <span data-ttu-id="16acc-388">Tür ek açıklaması etrafında boşluklar kullanın.</span><span class="sxs-lookup"><span data-stu-id="16acc-388">Use spaces around type annotation colons.</span></span> |
| <span data-ttu-id="16acc-389">☑</span><span class="sxs-lookup"><span data-stu-id="16acc-389">☑</span></span> | `Example(a, b, c)` | <span data-ttu-id="16acc-390">Giriş kayıt girişinde öğeler okunabilirlik için doğru aralıklıdır.</span><span class="sxs-lookup"><span data-stu-id="16acc-390">Items in input tuple are correctly spaced for readability.</span></span> |
| <span data-ttu-id="16acc-391">☒</span><span class="sxs-lookup"><span data-stu-id="16acc-391">☒</span></span> | <s>`Example (a, b, c)`</s> | <span data-ttu-id="16acc-392">Boşluklar, işlev, işlem veya UDT adlarından sonra bastırılmalıdır.</span><span class="sxs-lookup"><span data-stu-id="16acc-392">Spaces should be suppressed after function, operation, or UDT names.</span></span> |

***

