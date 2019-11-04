---
title: 'S # stil kılavuzu | Microsoft Docs'
description: 'S # stil kılavuzu'
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.style
ms.openlocfilehash: 4050e2ee9e516aed7a8ba1398792562926808ee0
ms.sourcegitcommit: c93fea5980d1d46fbda1e7c7153831b9337134bf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73463312"
---
# <a name="q-style-guide"></a><span data-ttu-id="0df1a-103">S # stil kılavuzu</span><span class="sxs-lookup"><span data-stu-id="0df1a-103">Q# Style Guide</span></span> #
## <a name="general-conventions"></a><span data-ttu-id="0df1a-104">Genel kurallar</span><span class="sxs-lookup"><span data-stu-id="0df1a-104">General Conventions</span></span> ##

<span data-ttu-id="0df1a-105">Bu kılavuzda önerilen kurallar, Q # dilinde yazılmış program ve kitaplıkların okunmasını ve anlaşılması daha kolay hale getirmeye yardımcı olmak için tasarlanmıştır.</span><span class="sxs-lookup"><span data-stu-id="0df1a-105">The conventions suggested in this guide are intended to help make programs and libraries written in Q# easier to read and understand.</span></span>

## <a name="guidance"></a><span data-ttu-id="0df1a-106">Kılavuz</span><span class="sxs-lookup"><span data-stu-id="0df1a-106">Guidance</span></span>

<span data-ttu-id="0df1a-107">Şunları öneririz:</span><span class="sxs-lookup"><span data-stu-id="0df1a-107">We suggest:</span></span>

- <span data-ttu-id="0df1a-108">Kullanıcılarınız için daha okunaklı ve anlaşılır kod sağlamak üzere kasıtlı olarak yapmadığınız müddetçe hiçbir şekilde hiçbir kuralı yok saymayın.</span><span class="sxs-lookup"><span data-stu-id="0df1a-108">Never disregard a convention unless you’re doing so intentionally in order to provide more readable and understandable code for your users.</span></span>

## <a name="naming-conventions"></a><span data-ttu-id="0df1a-109">Adlandırma kuralları</span><span class="sxs-lookup"><span data-stu-id="0df1a-109">Naming Conventions</span></span> ##

<span data-ttu-id="0df1a-110">Hisse geliştirme setini sunan bölümünde, hisse geliştiricilerin kolayca okunabilen ve aniden en aza indirecek programlar yazmasına yardımcı olan işlev ve işlem adları için çaba duyuyoruz.</span><span class="sxs-lookup"><span data-stu-id="0df1a-110">In offering the Quantum Development Kit, we strive for function and operation names that help quantum developers write programs that are easy to read and that minimize surprise.</span></span>
<span data-ttu-id="0df1a-111">Bunun önemli bir bölümü, işlevler, işlemler ve türler için ad seçtiğimiz durumlarda, programcıların expressconcepts için kullandığı *sözlüğü* oluşturacağız; seçimlerimiz sayesinde, bunlara açık bir şekilde iletişim kurma çabalarına yardımcı olur veya bu işlemleri de destekliyoruz.</span><span class="sxs-lookup"><span data-stu-id="0df1a-111">An important part of that is that when we choose names for functions, operations, and types, we are establishing the *vocabulary* that programmers use to express quantum concepts; with our choices, we either help or hinder them in their effort to clearly communicate.</span></span>
<span data-ttu-id="0df1a-112">Bu, sunduğumuz adların Saklılığı yerine netlik sağlamalarını sağlamak için bize bir sorumluluk koyar.</span><span class="sxs-lookup"><span data-stu-id="0df1a-112">This places a responsibility on us to make sure that the names we introduce offer clarity rather than obscurity.</span></span>
<span data-ttu-id="0df1a-113">Bu bölümde, Q # geliştirme topluluğu tarafından en iyi şekilde buluşmamıza yardımcı olan açık yönergeler açısından bu yükümlülüğünüzü nasıl karşıladığımızdan ayrıntılıyoruz.</span><span class="sxs-lookup"><span data-stu-id="0df1a-113">In this section, we detail how we meet this obligation in terms of explicit guidance that helps us do the best by the Q# development community.</span></span>

### <a name="operations-and-functions"></a><span data-ttu-id="0df1a-114">İşlemler ve Işlevler</span><span class="sxs-lookup"><span data-stu-id="0df1a-114">Operations and Functions</span></span> ###

<span data-ttu-id="0df1a-115">Bir adın oluşturulması gereken ilk şeylerden biri, belirli bir sembolün bir işlevi veya işlemi temsil ettiğini belirtir.</span><span class="sxs-lookup"><span data-stu-id="0df1a-115">One of the first things that a name should establish is whether a given symbol represents a function or an operation.</span></span>
<span data-ttu-id="0df1a-116">İşlevler ve işlemler arasındaki fark, bir kod bloğunun nasıl davranacağını anlamak açısından önemlidir.</span><span class="sxs-lookup"><span data-stu-id="0df1a-116">The difference between functions and operations is critical to understanding how a block of code behaves.</span></span>
<span data-ttu-id="0df1a-117">İşlevler ve işlemler arasındaki ayrımı kullanıcılara iletmek için, yan etkileri kullanılarak bu Q # model hisse işlemlerine güveniyoruz.</span><span class="sxs-lookup"><span data-stu-id="0df1a-117">To communicate the distinction between functions and operations to users, we rely on that Q# models quantum operations through the use of side effects.</span></span>
<span data-ttu-id="0df1a-118">Diğer bir deyişle, bir işlem bir işlem *yapar* .</span><span class="sxs-lookup"><span data-stu-id="0df1a-118">That is, an operation *does* something.</span></span>

<span data-ttu-id="0df1a-119">Buna karşılık işlevler, veriler arasındaki matematik ilişkilerini tanımlar.</span><span class="sxs-lookup"><span data-stu-id="0df1a-119">By contrast, functions describe the mathematical relationships between data.</span></span>
<span data-ttu-id="0df1a-120">`Sin(PI() / 2.0)` ifadesi `1.0`ve bir programın veya qubits *'in durumu* hakkında hiçbir şey anlamına gelir.</span><span class="sxs-lookup"><span data-stu-id="0df1a-120">The expression `Sin(PI() / 2.0)` *is* `1.0`, and implies nothing about the state of a program or its qubits.</span></span>

<span data-ttu-id="0df1a-121">Özetleme, işlemler, işlevleri işler.</span><span class="sxs-lookup"><span data-stu-id="0df1a-121">Summarizing, operations do things while functions are things.</span></span>
<span data-ttu-id="0df1a-122">Bu ayrım, işlemleri fiiller olarak ve işlevler olarak işlev olarak adı vereceğiz.</span><span class="sxs-lookup"><span data-stu-id="0df1a-122">This distinction suggests that we name operations as verbs and functions as nouns.</span></span>

> [!NOTE]
> <span data-ttu-id="0df1a-123">Kullanıcı tanımlı bir tür bildirildiğinde, bu türün örneklerini oluşturan yeni bir işlev örtülü olarak aynı anda tanımlanır.</span><span class="sxs-lookup"><span data-stu-id="0df1a-123">When a user-defined type is declared, a new function that constructs instances of that type is implicitly defined at the same time.</span></span>
> <span data-ttu-id="0df1a-124">Bu perspektiften, hem türün kendisi hem de Oluşturucu işlevinin tutarlı adlara sahip olması için Kullanıcı tanımlı türlerin adlarla adlandırılması gerekir.</span><span class="sxs-lookup"><span data-stu-id="0df1a-124">From that perspective, user-defined types should be named as nouns so that both the type itself and the constructor function have consistent names.</span></span>

<span data-ttu-id="0df1a-125">Makul yerlerde, işlem adlarının işlem tarafından gerçekleştirilen etkiyi açıkça belirten fiiller ile başlayıp başlamadığından emin olun.</span><span class="sxs-lookup"><span data-stu-id="0df1a-125">Where reasonable, ensure that operation names begin with verbs that clearly indicate the effect taken by the operation.</span></span>
<span data-ttu-id="0df1a-126">Örnek:</span><span class="sxs-lookup"><span data-stu-id="0df1a-126">For example:</span></span>

- `MeasureInteger`
- `EstimateEnergy`
- `SampleInt`

<span data-ttu-id="0df1a-127">Özel bahsetmeye hizmet eden bir durum, bir işlem başka bir işlemi girdi olarak aldığında ve çağırdığında çağırır.</span><span class="sxs-lookup"><span data-stu-id="0df1a-127">One case that deserves special mention is when an operation takes another operation as input and calls it.</span></span>
<span data-ttu-id="0df1a-128">Bu gibi durumlarda, giriş işlemi tarafından gerçekleştirilen eylem, dış işlem tanımlandığında, doğru fiil hemen temizlenmediği için net değildir.</span><span class="sxs-lookup"><span data-stu-id="0df1a-128">In such cases, the action taken by the input operation is not clear when the outer operation is defined, such that the right verb is not immediately clear.</span></span>
<span data-ttu-id="0df1a-129">`ApplyIf`, `ApplyToEach`ve `ApplyToFirst`gibi fiil `Apply`önerilir.</span><span class="sxs-lookup"><span data-stu-id="0df1a-129">We recommend the verb `Apply`, as in `ApplyIf`, `ApplyToEach`, and `ApplyToFirst`.</span></span>
<span data-ttu-id="0df1a-130">Bu örnekte olduğu gibi diğer fiiller da yararlı olabilir `IterateThroughCartesianPower`.</span><span class="sxs-lookup"><span data-stu-id="0df1a-130">Other verbs may be useful in this case as well, as in `IterateThroughCartesianPower`.</span></span>

| <span data-ttu-id="0df1a-131">Ü</span><span class="sxs-lookup"><span data-stu-id="0df1a-131">Verb</span></span> | <span data-ttu-id="0df1a-132">Beklenen efekt</span><span class="sxs-lookup"><span data-stu-id="0df1a-132">Expected Effect</span></span> |
| ---- | ------ |
| <span data-ttu-id="0df1a-133">Başvurun</span><span class="sxs-lookup"><span data-stu-id="0df1a-133">Apply</span></span> | <span data-ttu-id="0df1a-134">Giriş olarak verilen bir işlem çağrılır</span><span class="sxs-lookup"><span data-stu-id="0df1a-134">An operation provided as input is called</span></span> |
| <span data-ttu-id="0df1a-135">Assert</span><span class="sxs-lookup"><span data-stu-id="0df1a-135">Assert</span></span> | <span data-ttu-id="0df1a-136">Olası bir hisse ölçüsünün sonucu hakkında bir varsayım simülatör tarafından denetlenir</span><span class="sxs-lookup"><span data-stu-id="0df1a-136">A hypothesis about the outcome of a possible quantum measurement is checked by a simulator</span></span> |
| <span data-ttu-id="0df1a-137">Tahmin</span><span class="sxs-lookup"><span data-stu-id="0df1a-137">Estimate</span></span> | <span data-ttu-id="0df1a-138">Bir veya daha fazla ölçüden çizilen bir tahmini temsil eden klasik bir değer döndürüldü</span><span class="sxs-lookup"><span data-stu-id="0df1a-138">A classical value is returned, representing an estimate drawn from one or more measurements</span></span> |
| <span data-ttu-id="0df1a-139">Measure</span><span class="sxs-lookup"><span data-stu-id="0df1a-139">Measure</span></span> | <span data-ttu-id="0df1a-140">Bir hisse ölçümü gerçekleştirilir ve sonucu kullanıcıya döndürülür</span><span class="sxs-lookup"><span data-stu-id="0df1a-140">A quantum measurement is performed, and its result is returned to the user</span></span> |
| <span data-ttu-id="0df1a-141">Hazırlanın</span><span class="sxs-lookup"><span data-stu-id="0df1a-141">Prepare</span></span> | <span data-ttu-id="0df1a-142">Belirli bir qubits kaydı belirli bir duruma başlatılır</span><span class="sxs-lookup"><span data-stu-id="0df1a-142">A given register of qubits is initialized into a particular state</span></span> |
| <span data-ttu-id="0df1a-143">Örnek</span><span class="sxs-lookup"><span data-stu-id="0df1a-143">Sample</span></span> | <span data-ttu-id="0df1a-144">Klasik bir değer, bazı dağılılardan rasgele döndürülür</span><span class="sxs-lookup"><span data-stu-id="0df1a-144">A classical value is returned at random from some distribution</span></span> |

<span data-ttu-id="0df1a-145">İşlevler için, fiillerin ortak isimler yerine kullanılmasını önletireceğiz (aşağıdaki doğru isimler üzerinde rehberlik) veya sıfatlar:</span><span class="sxs-lookup"><span data-stu-id="0df1a-145">For functions, we suggest avoiding the use of verbs in favor of common nouns (see guidance on proper nouns below) or adjectives:</span></span>

- `ConstantArray`
- `Head`
- `LookupFunction`

<span data-ttu-id="0df1a-146">Özellikle, neredeyse her durumda, bir işlev adının bir işleme veya bir hisse senedine bağlı olarak bir eyleme bağlı olduğunu göstermek için uygun olan geçmiş participles kullanmayı öneririz.</span><span class="sxs-lookup"><span data-stu-id="0df1a-146">In particular, in almost all cases, we suggest using past participles where appropriate to indicate that a function name is strongly connected to an action or side effect elsewhere in a quantum program.</span></span>
<span data-ttu-id="0df1a-147">Örneğin, `ControlledOnInt` işlevin bağımsız değişkenini değiştirmek üzere sıfatıcı olarak davrandığını göstermek için, "Control" fiilinin bölüm participle formunu kullanır.</span><span class="sxs-lookup"><span data-stu-id="0df1a-147">For example,  `ControlledOnInt` uses the part participle form of the verb "control" to indicate that the function acts as an adjective to modify its argument.</span></span>
<span data-ttu-id="0df1a-148">Bu ad, aşağıda açıklandığı gibi, yerleşik `Controlled` functor semantiğini eşleştirmesinin ek avantajına sahiptir.</span><span class="sxs-lookup"><span data-stu-id="0df1a-148">This name has the additional benefit of matching the semantics of the built-in `Controlled` functor, as discussed further below.</span></span>
<span data-ttu-id="0df1a-149">Benzer şekilde, `Encode`ile ilişkili bir UDT için ad `Encoder` durumda olduğu gibi, işlem adlarından işlev ve UDT adları oluşturmak için _Aracı isimleri_ de kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="0df1a-149">Similarly, _agent nouns_ can be used to construct function and UDT names from operation names, as in the case of the name `Encoder` for a UDT that is strongly associated with `Encode`.</span></span>

# <a name="guidancetabguidance"></a>[<span data-ttu-id="0df1a-150">Rehber</span><span class="sxs-lookup"><span data-stu-id="0df1a-150">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="0df1a-151">Şunları öneririz:</span><span class="sxs-lookup"><span data-stu-id="0df1a-151">We suggest:</span></span>

- <span data-ttu-id="0df1a-152">İşlem adları için fiilleri kullanın.</span><span class="sxs-lookup"><span data-stu-id="0df1a-152">Use verbs for operation names.</span></span>
- <span data-ttu-id="0df1a-153">İşlev adları için isimleri veya sıfatları kullanın.</span><span class="sxs-lookup"><span data-stu-id="0df1a-153">Use nouns or adjectives for function names.</span></span>
- <span data-ttu-id="0df1a-154">Kullanıcı tanımlı türler ve öznitelikler için isimleri kullanın.</span><span class="sxs-lookup"><span data-stu-id="0df1a-154">Use nouns for user-defined types and attributes.</span></span>
- <span data-ttu-id="0df1a-155">Tüm çağrılabilir adlar için, `pascalCase`, `snake_case`veya `ANGRY_CASE`için güçlü bir tercih `CamelCase` kullanın.</span><span class="sxs-lookup"><span data-stu-id="0df1a-155">For all callable names, use `CamelCase` in strong preference to `pascalCase`, `snake_case`, or `ANGRY_CASE`.</span></span> <span data-ttu-id="0df1a-156">Özellikle, çağrılabilir adların büyük harfle başlayıp başlamadiğinden emin olun.</span><span class="sxs-lookup"><span data-stu-id="0df1a-156">In particular, ensure that callable names start with uppercase letters.</span></span>
- <span data-ttu-id="0df1a-157">Tüm yerel değişkenler için, `CamelCase`, `snake_case`veya `ANGRY_CASE`için güçlü bir tercih `pascalCase` kullanın.</span><span class="sxs-lookup"><span data-stu-id="0df1a-157">For all local variables, use `pascalCase` in strong preference to `CamelCase`, `snake_case`, or `ANGRY_CASE`.</span></span> <span data-ttu-id="0df1a-158">Özellikle, yerel değişkenlerin küçük harfle başlayıp başlamadiğinden emin olun.</span><span class="sxs-lookup"><span data-stu-id="0df1a-158">In particular, ensure that local variables start with lowercase letters.</span></span>
- <span data-ttu-id="0df1a-159">İşlev ve işlem adlarında alt çizgi `_` kullanmaktan kaçının; ek hiyerarşi düzeyleri gerekli olduğunda, ad alanları ve ad alanı diğer adları kullanın.</span><span class="sxs-lookup"><span data-stu-id="0df1a-159">Avoid the use of underscores `_` in function and operation names; where additional levels of hierarchy are needed, use namespaces and namespace aliases.</span></span>

# <a name="examplestabexamples"></a>[<span data-ttu-id="0df1a-160">Örnekler</span><span class="sxs-lookup"><span data-stu-id="0df1a-160">Examples</span></span>](#tab/examples)

|   | <span data-ttu-id="0df1a-161">Adı</span><span class="sxs-lookup"><span data-stu-id="0df1a-161">Name</span></span> | <span data-ttu-id="0df1a-162">Açıklama</span><span class="sxs-lookup"><span data-stu-id="0df1a-162">Description</span></span> |
|---|------|-------------|
| <span data-ttu-id="0df1a-163">☑</span><span class="sxs-lookup"><span data-stu-id="0df1a-163">☑</span></span> | `operation ReflectAboutStart` | <span data-ttu-id="0df1a-164">İşlemin etkisini göstermek için bir fiil ("yansıtma") kullanımını temizleyin.</span><span class="sxs-lookup"><span data-stu-id="0df1a-164">Clear use of a verb ("reflect") to indicate the effect of the operation.</span></span> |
| <span data-ttu-id="0df1a-165">☒</span><span class="sxs-lookup"><span data-stu-id="0df1a-165">☒</span></span> | <s>`operation XRotation`</s> | <span data-ttu-id="0df1a-166">İsim ifadesi kullanımı, işlem yerine Function önerisinde bulunur.</span><span class="sxs-lookup"><span data-stu-id="0df1a-166">Use of noun phrase suggests function, rather than operation.</span></span> |
| <span data-ttu-id="0df1a-167">☒</span><span class="sxs-lookup"><span data-stu-id="0df1a-167">☒</span></span> | <s>`operation search_oracle`</s> | <span data-ttu-id="0df1a-168">`snake_case` nvenes Q # gösterimi kullanımı.</span><span class="sxs-lookup"><span data-stu-id="0df1a-168">Use of `snake_case` contravenes Q# notation.</span></span> |
| <span data-ttu-id="0df1a-169">☒</span><span class="sxs-lookup"><span data-stu-id="0df1a-169">☒</span></span> | <s>`operation Search_Oracle`</s> | <span data-ttu-id="0df1a-170">Alt çizgi kullanımı iç işlem adı nvenes Q # gösterimi.</span><span class="sxs-lookup"><span data-stu-id="0df1a-170">Use of underscores internal to operation name contravenes Q# notation.</span></span> |
| <span data-ttu-id="0df1a-171">☑</span><span class="sxs-lookup"><span data-stu-id="0df1a-171">☑</span></span> | `function StatePreparationOracle` | <span data-ttu-id="0df1a-172">İsim ifadesinin kullanılması işlevin bir işlem döndürdüğünü önerir.</span><span class="sxs-lookup"><span data-stu-id="0df1a-172">Use of noun phrase suggests that the function returns an operation.</span></span> |
| <span data-ttu-id="0df1a-173">☑</span><span class="sxs-lookup"><span data-stu-id="0df1a-173">☑</span></span> | `function EqualityFact` | <span data-ttu-id="0df1a-174">Bu işlevin bir işlev olduğunu göstermek için ("olgu"), sıfatı seçimini temizleyin.</span><span class="sxs-lookup"><span data-stu-id="0df1a-174">Clear use of noun ("fact") to indicate that this is a function, while the adjective.</span></span> |
| <span data-ttu-id="0df1a-175">☒</span><span class="sxs-lookup"><span data-stu-id="0df1a-175">☒</span></span> | <s>`function GetRotationAngles`</s> | <span data-ttu-id="0df1a-176">Fiil ("Get") kullanılması bunun bir işlem olduğunu önerir.</span><span class="sxs-lookup"><span data-stu-id="0df1a-176">Use of verb ("get") suggests that this is an operation.</span></span> |
| <span data-ttu-id="0df1a-177">☑</span><span class="sxs-lookup"><span data-stu-id="0df1a-177">☑</span></span> | `newtype GeneratorTerm` | <span data-ttu-id="0df1a-178">Ad ifadesinin kullanımı, UDT oluşturucusunun çağrılması sonucunu açıkça ifade eder.</span><span class="sxs-lookup"><span data-stu-id="0df1a-178">Use of noun phrase clearly refers to the result of calling the UDT constructor.</span></span> |
| <span data-ttu-id="0df1a-179">☒</span><span class="sxs-lookup"><span data-stu-id="0df1a-179">☒</span></span> | <s>`@Attribute() newtype RunOnce()`</s> | <span data-ttu-id="0df1a-180">Fiil ifadesinin kullanımı, UDT oluşturucusunun bir işlem olduğunu önerir.</span><span class="sxs-lookup"><span data-stu-id="0df1a-180">Use of verb phrase suggests that the UDT constructor is an operation.</span></span> |
| <span data-ttu-id="0df1a-181">☑</span><span class="sxs-lookup"><span data-stu-id="0df1a-181">☑</span></span> | `@Attribute() newtype Deprecated(Reason : String)` | <span data-ttu-id="0df1a-182">İsim ifadesinin kullanılması özniteliğin kullanımını iletişim kurar.</span><span class="sxs-lookup"><span data-stu-id="0df1a-182">Use of noun phrase communicates the use of the attribute.</span></span> |

***

### <a name="shorthand-and-abbreviations"></a><span data-ttu-id="0df1a-183">Özet ve kısaltmalar</span><span class="sxs-lookup"><span data-stu-id="0df1a-183">Shorthand and Abbreviations</span></span> ###

<span data-ttu-id="0df1a-184">Yukarıdaki önerinin, hisse yaramakta olan ortak ve kapsamlı kullanımı gösteren çok sayıda kısayol vardır.</span><span class="sxs-lookup"><span data-stu-id="0df1a-184">The above advice notwithstanding, there are many forms of shorthand that see common and pervasive use in quantum computing.</span></span>
<span data-ttu-id="0df1a-185">Özellikle bir hedef makinenin işlemlerine iç işlemler için, var olan ve genel bir toplu işlemin bulunduğu yerde kullanmayı öneririz.</span><span class="sxs-lookup"><span data-stu-id="0df1a-185">We suggest using existing and common shorthand where it exists, especially for operations that are intrinsic to the operation of a target machine.</span></span>
<span data-ttu-id="0df1a-186">Örneğin, `ApplyX`yerine `X` adı ve `RotateAboutZ`yerine `Rz` seçeceğiz.</span><span class="sxs-lookup"><span data-stu-id="0df1a-186">For example, we choose the name `X` instead of `ApplyX`, and `Rz` instead of `RotateAboutZ`.</span></span>
<span data-ttu-id="0df1a-187">Bu tür bir kısayol kullanırken, işlem adları tümü büyük harfle yazılmalıdır (ör.: `MAJ`).</span><span class="sxs-lookup"><span data-stu-id="0df1a-187">When using such shorthand, operation names should be all uppercase (e.g.: `MAJ`).</span></span>

<span data-ttu-id="0df1a-188">Bu kural, yaygın olarak kullanılan kısaltmalar ve başlangıçlar söz konusu olduğunda "hisse Fourier dönüştürmesi" için "QFT" gibi bazı durumlarda gereklidir.</span><span class="sxs-lookup"><span data-stu-id="0df1a-188">Some care is required when applying this convention in the case of commonly used acronyms and initialisms such as "QFT" for "quantum Fourier transform."</span></span>
<span data-ttu-id="0df1a-189">Tam adlarda kısaltmalar ve ınitialisms 'lerin kullanılması için aşağıdaki genel .NET kurallarını öneririz:</span><span class="sxs-lookup"><span data-stu-id="0df1a-189">We suggest following general .NET conventions for the use of acronyms and initialisms in full names, which prescribe that:</span></span>

- <span data-ttu-id="0df1a-190">iki harfli kısaltmalar ve ınitialisms büyük harfle adlandırılır (örneğin, "Big-endian" için `BE`),</span><span class="sxs-lookup"><span data-stu-id="0df1a-190">two-letter acronyms and initialisms are named in upper case (e.g.: `BE` for "big-endian"),</span></span>
- <span data-ttu-id="0df1a-191">daha uzun kısaltmalar ve ınitialisms 'ler `CamelCase` olarak adlandırılır (örn. "hisse Fourier dönüştürmesi" için `Qft`)</span><span class="sxs-lookup"><span data-stu-id="0df1a-191">all longer acronyms and initialisms are named in `CamelCase` (e.g.: `Qft` for "quantum Fourier transform")</span></span>

<span data-ttu-id="0df1a-192">Bu nedenle, QFT 'yi uygulayan bir işlem, kısayol olarak `QFT` çağrılabilir veya `ApplyQft`olarak yazılabilir.</span><span class="sxs-lookup"><span data-stu-id="0df1a-192">Thus, an operation implementing the QFT could either be called `QFT` as shorthand, or written out as `ApplyQft`.</span></span>

<span data-ttu-id="0df1a-193">Özellikle yaygın olarak kullanılan işlemler ve işlevler için daha uzun bir form için bir _diğer_ ad olarak bir kısayol adı sağlanması istenebilir:</span><span class="sxs-lookup"><span data-stu-id="0df1a-193">For particularly commonly used operations and functions, it may be desirable to provide a shorthand name as an _alias_ for a longer form:</span></span>

```qsharp
operation CCNOT(control0 : Qubit, control1 : Qubit, target : Qubit)
is Adj + Ctl {
    Controlled X([control0, control1], target);
}
```

# <a name="guidancetabguidance"></a>[<span data-ttu-id="0df1a-194">Rehber</span><span class="sxs-lookup"><span data-stu-id="0df1a-194">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="0df1a-195">Şunları öneririz:</span><span class="sxs-lookup"><span data-stu-id="0df1a-195">We suggest:</span></span>

- <span data-ttu-id="0df1a-196">Uygun olduğunda genellikle kabul edilen ve yaygın olarak kullanılan toplu adları göz önünde bulundurun.</span><span class="sxs-lookup"><span data-stu-id="0df1a-196">Consider commonly accepted and widely used shorthand names when appropriate.</span></span>
- <span data-ttu-id="0df1a-197">Toplu değer için büyük harf kullanın.</span><span class="sxs-lookup"><span data-stu-id="0df1a-197">Use uppercase for shorthand.</span></span>
- <span data-ttu-id="0df1a-198">Kısa (iki harfli) kısaltmalar ve ınitialisms için büyük harf kullanın.</span><span class="sxs-lookup"><span data-stu-id="0df1a-198">Use uppercase for short (two-letter) acronyms and initialisms.</span></span>
- <span data-ttu-id="0df1a-199">Daha uzun (üç veya daha fazla harf) kısaltmalar ve ınitialisms için `CamelCase` kullanın.</span><span class="sxs-lookup"><span data-stu-id="0df1a-199">Use `CamelCase` for longer (three or more letter) acronyms and initialisms.</span></span>

# <a name="examplestabexamples"></a>[<span data-ttu-id="0df1a-200">Örnekler</span><span class="sxs-lookup"><span data-stu-id="0df1a-200">Examples</span></span>](#tab/examples)

|   | <span data-ttu-id="0df1a-201">Adı</span><span class="sxs-lookup"><span data-stu-id="0df1a-201">Name</span></span> | <span data-ttu-id="0df1a-202">Açıklama</span><span class="sxs-lookup"><span data-stu-id="0df1a-202">Description</span></span> |
|---|------|-------------|
| <span data-ttu-id="0df1a-203">☑</span><span class="sxs-lookup"><span data-stu-id="0df1a-203">☑</span></span> | `X` | <span data-ttu-id="0df1a-204">"Bir $X $ dönüşümü Uygula" için iyi anlaşılan toplu değer</span><span class="sxs-lookup"><span data-stu-id="0df1a-204">Well-understood shorthand for "apply an $X$ transformation"</span></span> |
| <span data-ttu-id="0df1a-205">☑</span><span class="sxs-lookup"><span data-stu-id="0df1a-205">☑</span></span> | `CNOT` | <span data-ttu-id="0df1a-206">"Denetimli-NOT" için iyi anlaşılan toplu değer</span><span class="sxs-lookup"><span data-stu-id="0df1a-206">Well-understood shorthand for "controlled-NOT"</span></span> |
| <span data-ttu-id="0df1a-207">☒</span><span class="sxs-lookup"><span data-stu-id="0df1a-207">☒</span></span> | <s>`Cnot`</s> | <span data-ttu-id="0df1a-208">Kısayol `CamelCase`olmamalıdır.</span><span class="sxs-lookup"><span data-stu-id="0df1a-208">Shorthand should not be in `CamelCase`.</span></span> |
| <span data-ttu-id="0df1a-209">☑</span><span class="sxs-lookup"><span data-stu-id="0df1a-209">☑</span></span> | `ApplyQft` | <span data-ttu-id="0df1a-210">"QFT" ortak ınitialroni uzun biçimli bir adın parçası olarak görünür.</span><span class="sxs-lookup"><span data-stu-id="0df1a-210">Common initialism "QFT" appears as a part of a long-form name.</span></span> |
| <span data-ttu-id="0df1a-211">☑</span><span class="sxs-lookup"><span data-stu-id="0df1a-211">☑</span></span> | `QFT` | <span data-ttu-id="0df1a-212">Genel ınitialısm "QFT", bir kısayol adının parçası olarak görünür.</span><span class="sxs-lookup"><span data-stu-id="0df1a-212">Common initialism "QFT" appears as a part of a shorthand name.</span></span> |



***


### <a name="proper-nouns-in-names"></a><span data-ttu-id="0df1a-213">Adlarda doğru adlar</span><span class="sxs-lookup"><span data-stu-id="0df1a-213">Proper Nouns in Names</span></span> ###

<span data-ttu-id="0df1a-214">Fizik durumunda, bunlar hakkında ilk kişiden sonra yayımlanmayan kişilerin adlarını ve tüm geçmişi öğrenmelerini sağlamak yaygın bir şekilde yapılıyor.</span><span class="sxs-lookup"><span data-stu-id="0df1a-214">While in physics it is common to name things after the first person to publish about them, most non-physicists aren’t familiar with everyone’s names and all of the history.</span></span>
<span data-ttu-id="0df1a-215">Daha fazla bilgi için, diğer arka planlardaki kullanıcıların, genel işlemleri ve kavramları kullanabilmesi için çok sayıda donuk opak ad öğrenmelidir.</span><span class="sxs-lookup"><span data-stu-id="0df1a-215">Relying too heavily on naming conventions from physics can thus put up a substantial barrier to entry, as users from other backgrounds must learn a large number of seemingly opaque names in order to use common operations and concepts.</span></span>
<!-- An important part of the task of reducing confusion is to make code more accessible.
Especially in a field such as quantum computing that is rich with domain expertise, we must at all times be cognizant of the demands we place on that expertise as we design quantum software.
In naming code symbols, one way that this cognizance expresses itself is as an awareness of the convention from physics of adopting as the names of algorithms and operations the names of their original publishers.
While we must maintain the history and intellectual provenance of concepts in quantum computing, demanding that all users be versed in this history to use even the most basic of functions and operations places a barrier to entry that is in most cases severe enough to even present an ethical compromise. -->
<span data-ttu-id="0df1a-216">Bu nedenle, bir kavramı tanımlayan makul, yaygın isimler kavramı, bir kavramın yayın geçmişini tanımlayan doğru isimler için güçlü bir tercih halinde benimsemesi önerilir.</span><span class="sxs-lookup"><span data-stu-id="0df1a-216">Thus, we recommend that wherever reasonable, common nouns that describe a concept be adopted in strong preference to proper nouns that describe the publication history of a concept.</span></span>
<span data-ttu-id="0df1a-217">Belirli bir örnek olarak, listedir kontrollü DEĞIŞTIRME ve buna uygun olmayan işlemler, genellikle akademik belgelerinde "Fredkaş" ve "Toffoli" işlemleri olarak adlandırılır, ancak `CSWAP` ve `CCNOT`olarak Q # içinde tanımlanır.</span><span class="sxs-lookup"><span data-stu-id="0df1a-217">As a particular example, the singly controlled SWAP and doubly controlled NOT operations are often called the "Fredkin" and "Toffoli" operations in academic literature, but are identified in Q# primarily as `CSWAP` and `CCNOT`.</span></span>
<span data-ttu-id="0df1a-218">Her iki durumda da, API belgesi açıklamaları uygun adlara göre eş anlamlı adlar sağlar ve tüm uygun alıntıları birlikte kapsar.</span><span class="sxs-lookup"><span data-stu-id="0df1a-218">In both cases, the API documentation comments provide synonymous names based on proper nouns, along with all appropriate citations.</span></span>

<span data-ttu-id="0df1a-219">Bu tercih, bazı uygun isimler kullanımının her zaman gerekli olacağı bir şekilde önemlidir. Q #, örneğin birçok klasik dile göre gelenek kümesini izler ve daha sonra değer olarak adlandırılan Boolean mantığına başvuru `Bool` türlerine başvurur. George Boole.</span><span class="sxs-lookup"><span data-stu-id="0df1a-219">This preference is especially important given that some usage of proper nouns will always be necessary — Q# follows the tradition set by many classical languages, for instance, and refers to `Bool` types in reference to Boolean logic, which is in turn named in honor of George Boole.</span></span>
<span data-ttu-id="0df1a-220">Benzer şekilde, örneğin, Q # diline yerleşik `Pauli` türü de dahil olmak üzere, benzer bir şekilde adlandırılmış birkaç hisse kavramdır.</span><span class="sxs-lookup"><span data-stu-id="0df1a-220">A few quantum concepts similarly are named in a similar fashion, including the `Pauli` type built-in to the Q# language.</span></span>
<span data-ttu-id="0df1a-221">Bu kullanım açısından gerekli olan doğru isimler kullanımını en aza indirerek, doğru isimleri kabul etmeyeceğinden etkiyi azalttık.</span><span class="sxs-lookup"><span data-stu-id="0df1a-221">By minimizing the usage of proper nouns where such usage is not essential, we reduce the impact where proper nouns cannot be reasonably avoided.</span></span>

# <a name="guidancetabguidance"></a>[<span data-ttu-id="0df1a-222">Rehber</span><span class="sxs-lookup"><span data-stu-id="0df1a-222">Guidance</span></span>](#tab/guidance) 

<span data-ttu-id="0df1a-223">Şunları öneririz:</span><span class="sxs-lookup"><span data-stu-id="0df1a-223">We suggest:</span></span>

- <span data-ttu-id="0df1a-224">Adlarda doğru isimler kullanmaktan kaçının.</span><span class="sxs-lookup"><span data-stu-id="0df1a-224">Avoid the use of proper nouns in names.</span></span>

# <a name="examplestabexamples"></a>[<span data-ttu-id="0df1a-225">Örnekler</span><span class="sxs-lookup"><span data-stu-id="0df1a-225">Examples</span></span>](#tab/examples)

***

### <a name="type-conversions"></a><span data-ttu-id="0df1a-226">Tür dönüştürmeleri</span><span class="sxs-lookup"><span data-stu-id="0df1a-226">Type Conversions</span></span> ###

<span data-ttu-id="0df1a-227">Q #, kesin ve statik olarak yazılmış bir dil olduğundan, bir tür değeri yalnızca bir tür dönüştürme işlevine açık bir çağrı kullanılarak başka bir türün değeri olarak kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="0df1a-227">Since Q# is a strongly and staticly typed language, a value of one type can only be used as a value of another type by using an explicit call to a type conversion function.</span></span>
<span data-ttu-id="0df1a-228">Bu, değerlerin örtük olarak (ör. tür promosyonu) veya atama yoluyla türlerin değiştirilmesini sağlayan dillere karşılık gelir.</span><span class="sxs-lookup"><span data-stu-id="0df1a-228">This is in contrast to languages which allow for values to change types implicitly (e.g.: type promotion), or through casting.</span></span>
<span data-ttu-id="0df1a-229">Sonuç olarak, tür dönüştürme işlevleri Q # kitaplığı geliştirme bölümünde önemli bir rol oynar ve adlandırma hakkında yaygın olarak karşılaşılan kararlardan birini içerir.</span><span class="sxs-lookup"><span data-stu-id="0df1a-229">As a result, type conversion functions play an important role in Q# library development, and comprise one of the more commonly encountered decisions about naming.</span></span>
<span data-ttu-id="0df1a-230">Ancak, tür dönüştürmeleri her zaman _belirleyici_olduğundan, bunlar işlev olarak yazılabilecekleri ve bu nedenle yukarıdaki önerinin altına düşecek.</span><span class="sxs-lookup"><span data-stu-id="0df1a-230">We note, however, that since type conversions are always _deterministic_, they can be written as functions and thus fall under the advice above.</span></span>
<span data-ttu-id="0df1a-231">Özellikle, tür dönüştürme işlevlerinin fiiller (ör.: `ConvertToX`) veya duyurusu b önceden konumsal ifadeler (`ToX`) olarak adlandırılmaması, ancak kaynak ve hedef türlerini belirten sıfatıcı önceden konumsal ifadeler olarak adlandırılması (`XAsY`).</span><span class="sxs-lookup"><span data-stu-id="0df1a-231">In particular, we suggest that type conversion functions should never be named as verbs (e.g.: `ConvertToX`) or adverb prepositional phrases (`ToX`), but should be named as adjective prepositional phrases that indicate the source and destination types (`XAsY`).</span></span>
<span data-ttu-id="0df1a-232">Tür dönüştürme işlevi adlarında dizi türleri listelenirken, toplu `Arr`önerilir.</span><span class="sxs-lookup"><span data-stu-id="0df1a-232">When listing array types in type conversion function names, we recommend the shorthand `Arr`.</span></span>
<span data-ttu-id="0df1a-233">Tüm tür dönüştürme işlevlerinin hızla tanımlanabilmesi için `As` kullanılarak adlandırılması önerilir.</span><span class="sxs-lookup"><span data-stu-id="0df1a-233">Barring exceptional circumstances, we recommend that all type conversion functions be named using `As` so that they can be quickly identified.</span></span>

# <a name="guidancetabguidance"></a>[<span data-ttu-id="0df1a-234">Rehber</span><span class="sxs-lookup"><span data-stu-id="0df1a-234">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="0df1a-235">Şunları öneririz:</span><span class="sxs-lookup"><span data-stu-id="0df1a-235">We suggest:</span></span>

- <span data-ttu-id="0df1a-236">Bir işlev `X` türündeki bir değeri `Y`türünde bir değere dönüştürdüğünde, `AsY` ya da `XAsY`adını kullanın.</span><span class="sxs-lookup"><span data-stu-id="0df1a-236">If a function converts a value of type `X` to a value of type `Y`, use either the name `AsY` or `XAsY`.</span></span>

# <a name="examplestabexamples"></a>[<span data-ttu-id="0df1a-237">Örnekler</span><span class="sxs-lookup"><span data-stu-id="0df1a-237">Examples</span></span>](#tab/examples)

|   | <span data-ttu-id="0df1a-238">Adı</span><span class="sxs-lookup"><span data-stu-id="0df1a-238">Name</span></span> | <span data-ttu-id="0df1a-239">Açıklama</span><span class="sxs-lookup"><span data-stu-id="0df1a-239">Description</span></span> |
|---|------|-------------|
| <span data-ttu-id="0df1a-240">☒</span><span class="sxs-lookup"><span data-stu-id="0df1a-240">☒</span></span> | <s>`ToDouble`</s> | <span data-ttu-id="0df1a-241">"To" ön konumu, bir işlevi değil bir işlem belirten bir fiil ifadesi içinde sonuçlanır.</span><span class="sxs-lookup"><span data-stu-id="0df1a-241">The preposition "to" results in a verb phrase, indicating an operation and not a function.</span></span> |
| <span data-ttu-id="0df1a-242">☒</span><span class="sxs-lookup"><span data-stu-id="0df1a-242">☒</span></span> | <s>`AsDouble`</s> | <span data-ttu-id="0df1a-243">Giriş türü, işlev adından net değildir.</span><span class="sxs-lookup"><span data-stu-id="0df1a-243">The input type is not clear from the function name.</span></span> |
| <span data-ttu-id="0df1a-244">☒</span><span class="sxs-lookup"><span data-stu-id="0df1a-244">☒</span></span> | <s>`PauliArrFromBoolArr`</s> | <span data-ttu-id="0df1a-245">Giriş ve çıkış türleri yanlış sırada görünüyor.</span><span class="sxs-lookup"><span data-stu-id="0df1a-245">The input and output types appear in the wrong order.</span></span> |
| <span data-ttu-id="0df1a-246">☑</span><span class="sxs-lookup"><span data-stu-id="0df1a-246">☑</span></span> | `ResultArrAsBoolArr` | <span data-ttu-id="0df1a-247">Hem giriş türleri hem de çıkış türleri net.</span><span class="sxs-lookup"><span data-stu-id="0df1a-247">Both the input types and output types are clear.</span></span> |

***

### <a name="private-or-internal-names"></a><span data-ttu-id="0df1a-248">Özel veya Iç adlar</span><span class="sxs-lookup"><span data-stu-id="0df1a-248">Private or Internal Names</span></span> ###

<span data-ttu-id="0df1a-249">Çoğu durumda, bir ad bir kitaplık veya proje için dahili olarak kullanılmak üzere veya bir kitaplık tarafından sunulan API 'nin garantili bir parçası değildir.</span><span class="sxs-lookup"><span data-stu-id="0df1a-249">In many cases, a name is intended strictly for use internal to a library or project, and is not a guaranteed part of the API offered by a library.</span></span>
<span data-ttu-id="0df1a-250">Yalnızca iç kodda yanlışlıkla bağımlılıklara açık hale getirilmeleri için işlevleri ve işlemleri adlandırırken bu durumun büyük bir zaman olduğunu açıkça belirtmek faydalı olur.</span><span class="sxs-lookup"><span data-stu-id="0df1a-250">It is helpful to clearly indicate that this is the case when naming functions and operations so that accidental dependencies on internal-only code are made obvious.</span></span>
<span data-ttu-id="0df1a-251">Bir işlem veya işlev doğrudan kullanılmak üzere tasarlanmamıştır, ancak kısmi uygulama tarafından davranan, eşleşen bir çağrılabilir tarafından kullanılması gerekiyorsa, kısmen uygulanmış çağrılabilir için `_` başlayarak bir ad kullanmayı düşünün.</span><span class="sxs-lookup"><span data-stu-id="0df1a-251">If an operation or function is not intended for direct use, but rather should be used by a matching callable which acts by partial application, consider using a name starting with `_` for the callable that is partially applied.</span></span>

# <a name="guidancetabguidance"></a>[<span data-ttu-id="0df1a-252">Rehber</span><span class="sxs-lookup"><span data-stu-id="0df1a-252">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="0df1a-253">Şunları öneririz:</span><span class="sxs-lookup"><span data-stu-id="0df1a-253">We suggest:</span></span>

- <span data-ttu-id="0df1a-254">Bir işlev, işlem veya Kullanıcı tanımlı tür, bir Q # kitaplığı veya programı için ortak API 'nin bir parçası olmadığında, adının öndeki alt çizgiyle (`_`) başladığından emin olun.</span><span class="sxs-lookup"><span data-stu-id="0df1a-254">When a function, operation, or user-defined type is not a part of the public API for a Q# library or program, ensure that its name begins with a leading underscore (`_`).</span></span>

# <a name="examplestabexamples"></a>[<span data-ttu-id="0df1a-255">Örnekler</span><span class="sxs-lookup"><span data-stu-id="0df1a-255">Examples</span></span>](#tab/examples)

|   | <span data-ttu-id="0df1a-256">Adı</span><span class="sxs-lookup"><span data-stu-id="0df1a-256">Name</span></span> | <span data-ttu-id="0df1a-257">Açıklama</span><span class="sxs-lookup"><span data-stu-id="0df1a-257">Description</span></span> |
|---|------|-------------|
| <span data-ttu-id="0df1a-258">☒</span><span class="sxs-lookup"><span data-stu-id="0df1a-258">☒</span></span> | <s>`ApplyDecomposedOperation_`</s> | <span data-ttu-id="0df1a-259">Alt çizgi `_` adın sonunda görünmemelidir.</span><span class="sxs-lookup"><span data-stu-id="0df1a-259">The underscore `_` should not appear at the end of the name.</span></span> |
| <span data-ttu-id="0df1a-260">☑</span><span class="sxs-lookup"><span data-stu-id="0df1a-260">☑</span></span> | `_ApplyDecomposedOperation` | <span data-ttu-id="0df1a-261">Başındaki alt çizgi `_` açıkça bu işlemin yalnızca iç kullanım için olduğunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="0df1a-261">The underscore `_` at the beginning clearly indicates that this operation is for internal use only.</span></span> |

***

### <a name="variants"></a><span data-ttu-id="0df1a-262">Değişken</span><span class="sxs-lookup"><span data-stu-id="0df1a-262">Variants</span></span> ###

<span data-ttu-id="0df1a-263">Bu sınırlama gelecekteki bir soru-cevap sürümünde kalmayabilir, ancak bu durum genellikle, kendilerine ait oldukları veya bağımsız değişkenlerinin somut türleri tarafından kendilerine ait olan ilgili işlem veya işlev grupları olacaktır.</span><span class="sxs-lookup"><span data-stu-id="0df1a-263">Though this limitation may not persist in future versions of Q#, it is presently the case that there will often be groups of related operations or functions that are distinguished by which functors their inputs support, or by the concrete types of their arguments.</span></span>
<span data-ttu-id="0df1a-264">Bu gruplar, kendisini belirten bir veya iki harften sonra aynı kök adı kullanılarak ayırt edilebilir.</span><span class="sxs-lookup"><span data-stu-id="0df1a-264">These groups can be distinguished by using the same root name, followed by one or two letters that indicate its variant.</span></span>

| <span data-ttu-id="0df1a-265">Önekini</span><span class="sxs-lookup"><span data-stu-id="0df1a-265">Suffix</span></span> | <span data-ttu-id="0df1a-266">Anlamı</span><span class="sxs-lookup"><span data-stu-id="0df1a-266">Meaning</span></span> |
|--------|---------|
| `A` | <span data-ttu-id="0df1a-267">`Adjoint` desteklemesi beklenen giriş</span><span class="sxs-lookup"><span data-stu-id="0df1a-267">Input expected to support `Adjoint`</span></span> |
| `C` | <span data-ttu-id="0df1a-268">`Controlled` desteklemesi beklenen giriş</span><span class="sxs-lookup"><span data-stu-id="0df1a-268">Input expected to support `Controlled`</span></span> |
| `CA` | <span data-ttu-id="0df1a-269">`Controlled` ve `Adjoint` desteklemek için giriş bekleniyor</span><span class="sxs-lookup"><span data-stu-id="0df1a-269">Input expected to support `Controlled` and `Adjoint`</span></span> |
| `I` | <span data-ttu-id="0df1a-270">Giriş veya girişler `Int` türündedir</span><span class="sxs-lookup"><span data-stu-id="0df1a-270">Input or inputs are of type `Int`</span></span> |
| `D` | <span data-ttu-id="0df1a-271">Giriş veya girişler `Double` türündedir</span><span class="sxs-lookup"><span data-stu-id="0df1a-271">Input or inputs are of type `Double`</span></span> |
| `L` | <span data-ttu-id="0df1a-272">Giriş veya girişler `BigInt` türündedir</span><span class="sxs-lookup"><span data-stu-id="0df1a-272">Input or inputs are of type `BigInt`</span></span> |

# <a name="guidancetabguidance"></a>[<span data-ttu-id="0df1a-273">Rehber</span><span class="sxs-lookup"><span data-stu-id="0df1a-273">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="0df1a-274">Şunları öneririz:</span><span class="sxs-lookup"><span data-stu-id="0df1a-274">We suggest:</span></span>

- <span data-ttu-id="0df1a-275">Bir işlev veya işlem, girişlerinin türleri ve functor desteğiyle benzer işlevlerle veya işlemlerle ilişkili değilse, bir sonek kullanmayın.</span><span class="sxs-lookup"><span data-stu-id="0df1a-275">If a function or operation is not related to any similar functions or operations by the types and functor support of their inputs, do not use a suffix.</span></span>
- <span data-ttu-id="0df1a-276">Bir işlev veya işlem, girişlerinin türleri ve functor desteğiyle benzer işlevlerle veya işlemlerle ilişkiliyse, sapmaları ayırt etmek için yukarıdaki tabloda olduğu gibi sonekleri kullanın.</span><span class="sxs-lookup"><span data-stu-id="0df1a-276">If a function or operation is related to any similar functions or operations by the types and functor support of their inputs, use suffixes as in the table above to distinguish variants.</span></span>

# <a name="examplestabexamples"></a>[<span data-ttu-id="0df1a-277">Örnekler</span><span class="sxs-lookup"><span data-stu-id="0df1a-277">Examples</span></span>](#tab/examples)

***

### <a name="arguments-and-variables"></a><span data-ttu-id="0df1a-278">Bağımsız değişkenler ve değişkenler</span><span class="sxs-lookup"><span data-stu-id="0df1a-278">Arguments and Variables</span></span> ###

<span data-ttu-id="0df1a-279">Bir işlev veya işlem için Q # kodunun anahtar hedefi kolayca okunabilme ve anlaşılmalıdır.</span><span class="sxs-lookup"><span data-stu-id="0df1a-279">A key goal of the Q# code for a function or operation is for it to be easily read and understood.</span></span>
<span data-ttu-id="0df1a-280">Benzer şekilde, giriş ve tür bağımsız değişkenlerinin adları, bir işlev veya bağımsız değişkenin sağlandığı bir şekilde nasıl kullanılacağını iletmelidir.</span><span class="sxs-lookup"><span data-stu-id="0df1a-280">Similarly, the names of inputs and type arguments should communicate how a function or argument will be used once provided.</span></span>


# <a name="guidancetabguidance"></a>[<span data-ttu-id="0df1a-281">Rehber</span><span class="sxs-lookup"><span data-stu-id="0df1a-281">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="0df1a-282">Şunları öneririz:</span><span class="sxs-lookup"><span data-stu-id="0df1a-282">We suggest:</span></span>

- <span data-ttu-id="0df1a-283">Tüm değişken ve giriş adları için, `CamelCase`, `snake_case`veya `ANGRY_CASE`için güçlü bir tercih `pascalCase` kullanın.</span><span class="sxs-lookup"><span data-stu-id="0df1a-283">For all variable and input names, use `pascalCase` in strong preference to `CamelCase`, `snake_case`, or `ANGRY_CASE`.</span></span>
- <span data-ttu-id="0df1a-284">Giriş adları açıklayıcı olmalıdır; mümkün olduğunda bir veya iki harfli adlardan kaçının.</span><span class="sxs-lookup"><span data-stu-id="0df1a-284">Input names should be descriptive; avoid one or two letter names where possible.</span></span>
- <span data-ttu-id="0df1a-285">Tam olarak bir tür bağımsız değişkeni kabul eden işlemler ve işlevler, rolü belirgin olduğunda `T` tarafından bu tür bağımsız değişkenini göstermelidir.</span><span class="sxs-lookup"><span data-stu-id="0df1a-285">Operations and functions accepting exactly one type argument should denote that type argument by `T` when its role is obvious.</span></span>
- <span data-ttu-id="0df1a-286">Bir işlev veya işlem birden çok tür bağımsız değişkeni alırsa veya tek bir tür bağımsız değişkeninin rolü açık değilse, her tür için `T` (örn.: `TOutput`) kısa harfli bir sözcük kullanmayı düşünün.</span><span class="sxs-lookup"><span data-stu-id="0df1a-286">If a function or operation takes multiple type arguments, or if the role of a single type argument is not obvious, consider using a short capitalized word prefaced by `T` (e.g.: `TOutput`) for each type.</span></span>
- <span data-ttu-id="0df1a-287">Bağımsız değişkene ve değişken adlarına tür adlarını eklemeyin; Bu bilgiler, geliştirme ortamınız tarafından sağlanmış ve sağlanmalıdır.</span><span class="sxs-lookup"><span data-stu-id="0df1a-287">Do not include type names in argument and variable names; this information can and should be provided by your development environment.</span></span>
- <span data-ttu-id="0df1a-288">Skalar türlerini sabit adlarına (`flagQubit`) ve dizi türlerini bir plural (`measResults`) göre gösterir.</span><span class="sxs-lookup"><span data-stu-id="0df1a-288">Denote scalar types by their literal names (`flagQubit`), and array types by a plural (`measResults`).</span></span>
  <span data-ttu-id="0df1a-289">Belirli qubit dizileri için, adın bir şekilde daha yakından ilişkili bir qubit dizisine başvurduğu `Register`, bu tür türleri belirtmeyi göz önünde bulundurun.</span><span class="sxs-lookup"><span data-stu-id="0df1a-289">For arrays of qubits in particular, consider denoting such types by `Register` where the name refers to a sequence of qubits that are closely related in some way.</span></span>
- <span data-ttu-id="0df1a-290">Dizilerde dizin olarak kullanılan değişkenler `idx` ile başlamalı ve tekil olmalıdır (örn.: `things[idxThing]`).</span><span class="sxs-lookup"><span data-stu-id="0df1a-290">Variables used as indices into arrays should begin with `idx` and should be singular (e.g.: `things[idxThing]`).</span></span>
  <span data-ttu-id="0df1a-291">Özellikle, tek harfli değişken adlarını dizin olarak kullanmaktan kesinlikle kaçının; en az `idx` kullanmayı göz önünde bulundurun.</span><span class="sxs-lookup"><span data-stu-id="0df1a-291">In particular, strongly avoid using single-letter variable names as indices; consider using `idx` at a minimum.</span></span>
- <span data-ttu-id="0df1a-292">Dizi uzunluklarını tutmak için kullanılan değişkenler `n` ile başlamalı ve plurar olmalıdır (ör.: `nThings`).</span><span class="sxs-lookup"><span data-stu-id="0df1a-292">Variables used to hold lengths of arrays should begin with `n` and should be pluralized (e.g.: `nThings`).</span></span>

# <a name="examplestabexamples"></a>[<span data-ttu-id="0df1a-293">Örnekler</span><span class="sxs-lookup"><span data-stu-id="0df1a-293">Examples</span></span>](#tab/examples)

***

### <a name="user-defined-type-named-items"></a><span data-ttu-id="0df1a-294">Kullanıcı tanımlı tür öğe adı</span><span class="sxs-lookup"><span data-stu-id="0df1a-294">User Defined Type Named Items</span></span> ###

<span data-ttu-id="0df1a-295">Kullanıcı tanımlı türlerdeki adlandırılmış öğeler, UDT oluşturucularının girişinde bile `CamelCase`olarak adlandırılmalıdır.</span><span class="sxs-lookup"><span data-stu-id="0df1a-295">Named items in user-defined types should be named as `CamelCase`, even in input to UDT constructors.</span></span>
<span data-ttu-id="0df1a-296">Bu, erişimci gösterimini (ör.: `callable::Apply`) veya kopyalama ve güncelleştirme gösterimini (`set arr w/= Data <- newData`) kullanırken, adlandırılmış öğeleri yerel kapsamlı değişkenlere başvuruların açıkça ayrılması için yardımcı olur.</span><span class="sxs-lookup"><span data-stu-id="0df1a-296">This helps in order to clearly separate named items from references to locally scoped variables when using accessor notation (e.g.: `callable::Apply`) or copy-and-update notation (`set arr w/= Data <- newData`).</span></span>

# <a name="guidancetabguidance"></a>[<span data-ttu-id="0df1a-297">Rehber</span><span class="sxs-lookup"><span data-stu-id="0df1a-297">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="0df1a-298">Şunları öneririz:</span><span class="sxs-lookup"><span data-stu-id="0df1a-298">We suggest:</span></span>

- <span data-ttu-id="0df1a-299">UDT oluşturucularında adlandırılmış öğeler `CamelCase`olarak adlandırılmalıdır; diğer bir deyişle, ilk büyük harfle başlamalıdır.</span><span class="sxs-lookup"><span data-stu-id="0df1a-299">Named items in UDT constructors should be named as `CamelCase`; that is, they should begin with an initial uppercase.</span></span>
- <span data-ttu-id="0df1a-300">İşlemlere çözüm veren adlandırılmış öğeler fiil aşamaları olarak adlandırılmalıdır.</span><span class="sxs-lookup"><span data-stu-id="0df1a-300">Named items that resolve to operations should be named as verb phases.</span></span>
- <span data-ttu-id="0df1a-301">İşlemlere çözümlenmez adlandırılmış öğeler, ad ifadeleri olarak adlandırılmalıdır.</span><span class="sxs-lookup"><span data-stu-id="0df1a-301">Named items that do not resolve to operations should be named as noun phrases.</span></span>
- <span data-ttu-id="0df1a-302">Sarmalı işlemler için `Apply` adlı tek bir adlandırılmış öğe tanımlanmalıdır.</span><span class="sxs-lookup"><span data-stu-id="0df1a-302">For UDTs that wrap operations, a single named item called `Apply` should be defined.</span></span>

# <a name="examplestabexamples"></a>[<span data-ttu-id="0df1a-303">Örnekler</span><span class="sxs-lookup"><span data-stu-id="0df1a-303">Examples</span></span>](#tab/examples)

|   | <span data-ttu-id="0df1a-304">Gösterildiği</span><span class="sxs-lookup"><span data-stu-id="0df1a-304">Snippet</span></span> | <span data-ttu-id="0df1a-305">Açıklama</span><span class="sxs-lookup"><span data-stu-id="0df1a-305">Description</span></span> |
|---|---------|-------------|
| <span data-ttu-id="0df1a-306">☑</span><span class="sxs-lookup"><span data-stu-id="0df1a-306">☑</span></span> | `newtype Oracle = (Apply : Qubit[] => Unit is Adj + Ctl)` | <span data-ttu-id="0df1a-307">`Apply` adı, adlandırılmış öğenin bir işlem olmasını öneren `CamelCase`biçimli bir fiil tümceciktir.</span><span class="sxs-lookup"><span data-stu-id="0df1a-307">The name `Apply` is a `CamelCase`-formatted verb phrase, suggesting that the named item is an operation.</span></span> |
| <span data-ttu-id="0df1a-308">☒</span><span class="sxs-lookup"><span data-stu-id="0df1a-308">☒</span></span> | <s>`newtype Oracle = (apply : Qubit[] => Unit is Adj + Ctl) `</s> | <span data-ttu-id="0df1a-309">Adlandırılmış öğeler ilk büyük harfle başlamalıdır.</span><span class="sxs-lookup"><span data-stu-id="0df1a-309">Named items should begin with an initial uppercase letter.</span></span> |
| <span data-ttu-id="0df1a-310">☒</span><span class="sxs-lookup"><span data-stu-id="0df1a-310">☒</span></span> | <s>`newtype Collection = (Length : Int, Get : Int -> (Qubit => Unit)) `</s> | <span data-ttu-id="0df1a-311">İşlevlerine çözüm veren adlandırılmış öğeler, fiil ifadeleri olarak değil, ad ifadeleri olarak adlandırılmalıdır.</span><span class="sxs-lookup"><span data-stu-id="0df1a-311">Named items which resolve to functions should be named as noun phrases, not as verb phrases.</span></span> |

***

## <a name="input-conventions"></a><span data-ttu-id="0df1a-312">Giriş kuralları</span><span class="sxs-lookup"><span data-stu-id="0df1a-312">Input Conventions</span></span> ##

<span data-ttu-id="0df1a-313">Bir geliştirici bir işlem veya işleve çağırdığında, bu işlem veya işleve yönelik çeşitli girişler belirli bir sırada belirtilmelidir, bu da bir geliştiricinin bir kitaplığı kullanabilmesi için bir geliştiricinin yüzlü yükünü artırır.</span><span class="sxs-lookup"><span data-stu-id="0df1a-313">When a developer calls into an operation or function, the various inputs to that operation or function must be specified in a particular order, increasing the cognitive load that a developer faces in order to make use of a library.</span></span>
<span data-ttu-id="0df1a-314">Özellikle, giriş sıralamayı hatırlama görevi genellikle her seferinde bir, bir hisse algoritması uygulamasını programlama.</span><span class="sxs-lookup"><span data-stu-id="0df1a-314">In particular, the task of remembering input orderings is often a distraction from the task at hand: programming an implementation of a quantum algorithm.</span></span>
<span data-ttu-id="0df1a-315">Zengin IDE desteği bunu büyük ölçüde azaltır, yaygın kurallara uygun tasarım ve bağlılığı, bir API tarafından uygulanan bilişsel yükün en aza indirilmesine yardımcı olabilir.</span><span class="sxs-lookup"><span data-stu-id="0df1a-315">Though rich IDE support can mitigate this to a large extent, good design and adherence to common conventions can also help to minimize the cognitive load imposed by an API.</span></span>

<span data-ttu-id="0df1a-316">Mümkün olduğunda, bir işlem veya işlev tarafından beklenen giriş sayısını azaltmak faydalı olabilir, böylece her girdinin rolü hem bu işlem veya işlevi çağıran geliştiriciler için hem de bu kodu daha sonra okuyan geliştiriciler için daha fazla belirgin hale gelir.</span><span class="sxs-lookup"><span data-stu-id="0df1a-316">Where possible, it can be helpful to reduce the number of inputs expected by an operation or function, so that the role of each input is more immediately obvious both to developers calling into that operation or function, and to developers reading that code later.</span></span>
<span data-ttu-id="0df1a-317">Özellikle bir işlem veya işlev için bağımsız değişken sayısını azaltmak mümkün olmadığında veya makul olmadığında, bir kullanıcının giriş sırasını tahmin eden zaman şaşırmasını en aza indiren tutarlı bir sıralama olması önemlidir.</span><span class="sxs-lookup"><span data-stu-id="0df1a-317">Especially when it is not possible or reasonable to reduce the number of arguments to an operation or function, it is important to have a consistent ordering that minimizes the surprise that a user faces when predicting the order of inputs.</span></span>

<span data-ttu-id="0df1a-318">Büyük bir uygulamanın, f (x, y) ≡ f (x) (y) ile bir genelleştirme olarak düşünmekten büyük ölçüde türettiği bir giriş sıralaması kuralları öneririz.</span><span class="sxs-lookup"><span data-stu-id="0df1a-318">We recommend an input ordering conventions that largely derives from thinking of partial application as a generalization of currying 𝑓(𝑥, 𝑦) ≡ 𝑓(𝑥)(𝑦).</span></span>
<span data-ttu-id="0df1a-319">Bu nedenle, ilk bağımsız değişkenlerin kısmen uygulanması, her ne kadar uygun olan her zaman kendi kendine yararlı bir çağrılabilir ile sonuçlanmalıdır.</span><span class="sxs-lookup"><span data-stu-id="0df1a-319">Thus, partially applying the first arguments should result in a callable that is useful in its own right whenever that is reasonable.</span></span>
<span data-ttu-id="0df1a-320">Bu ilkeyi izleyerek aşağıdaki bağımsız değişken sırasını kullanmayı göz önünde bulundurun:</span><span class="sxs-lookup"><span data-stu-id="0df1a-320">Following this principle, consider using the following order of arguments:</span></span>

- <span data-ttu-id="0df1a-321">Açılamayan, açıların vektörleri, üslerdeki vektörler vb. gibi çağrılabilir olmayan bağımsız değişkenler</span><span class="sxs-lookup"><span data-stu-id="0df1a-321">Classical non-callable arguments such as angles, vectors of powers, etc.</span></span>
- <span data-ttu-id="0df1a-322">Çağrılabilir bağımsız değişkenler (işlevler ve bağımsız değişkenler).</span><span class="sxs-lookup"><span data-stu-id="0df1a-322">Callable arguments (functions and arguments).</span></span>
  <span data-ttu-id="0df1a-323">Her iki işlev ve işlem bağımsız değişken olarak götürülüyorsanız, işlemleri işlevlerden sonra yerleştirmeyi göz önünde bulundurun.</span><span class="sxs-lookup"><span data-stu-id="0df1a-323">If both functions and operations are taken as arguments, consider placing operations after functions.</span></span>
- <span data-ttu-id="0df1a-324">`Map`, `Iter`, `Enumerate`ve `Fold`benzer bir şekilde çağrılabilir bağımsız değişkenlerle üzerinde işlem yapan Koleksiyonlar.</span><span class="sxs-lookup"><span data-stu-id="0df1a-324">Collections acted upon by callable arguments in a similar way to `Map`, `Iter`, `Enumerate`, and `Fold`.</span></span>
- <span data-ttu-id="0df1a-325">Denetimler olarak kullanılan qubit bağımsız değişkenleri.</span><span class="sxs-lookup"><span data-stu-id="0df1a-325">Qubit arguments used as controls.</span></span>
- <span data-ttu-id="0df1a-326">Hedef olarak kullanılan qubit bağımsız değişkenleri.</span><span class="sxs-lookup"><span data-stu-id="0df1a-326">Qubit arguments used as targets.</span></span>

<span data-ttu-id="0df1a-327">Bir işlemi, bir açı ve bir Oracle alan bir dizi tahminde kullanmak üzere `ApplyPhaseEstimationIteration` değerlendirin, açısını farklı ölçekleme faktörlerinin bir dizisi tarafından değiştirilen `Rz` geçirir ve sonra Oracle 'ın uygulamalarını denetler.</span><span class="sxs-lookup"><span data-stu-id="0df1a-327">Consider an operation `ApplyPhaseEstimationIteration` for use in phase estimation that takes an angle and an oracle, passes the angle to `Rz` modified by an array of different scaling factors, and then controls applications of the oracle.</span></span>
<span data-ttu-id="0df1a-328">Aşağıdaki şekilde `ApplyPhaseEstimationIteration` girdileri sıralarız:</span><span class="sxs-lookup"><span data-stu-id="0df1a-328">We would order the inputs to `ApplyPhaseEstimationIteration` in the following fashion:</span></span>

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
<span data-ttu-id="0df1a-329">Bazı işlevler ve işlemler aniden en aza indirmeden, bazı işlevler ve işlemler yerleşik komik `Adjoint` ve `Controlled`davranışını taklit ediyor.</span><span class="sxs-lookup"><span data-stu-id="0df1a-329">As a special case of minimizing surprise, some functions and operations mimic the behavior of the built-in functors `Adjoint` and `Controlled`.</span></span>
<span data-ttu-id="0df1a-330">Örneğin, `ControlledOnInt<'T>`, `ControlledOnInt<Qubit[]>(5, _)` `Controlled` functor gibi davranan, ancak denetim kaydının $ \demet{5} = \ayraç{101}$ durumunu temsil ettiği koşulda tür `(Int, ('T => Unit is Adj + Ctl)) => ((Qubit[], 'T) => Unit is Adj + Ctl)`sahiptir.</span><span class="sxs-lookup"><span data-stu-id="0df1a-330">For instance, `ControlledOnInt<'T>` has type `(Int, ('T => Unit is Adj + Ctl)) => ((Qubit[], 'T) => Unit is Adj + Ctl)`, such that `ControlledOnInt<Qubit[]>(5, _)` acts like the `Controlled` functor, but on the condition that the control register represents the state $\ket{5} = \ket{101}$.</span></span>
<span data-ttu-id="0df1a-331">Bu nedenle, bir geliştirici `ControlledOnInt` girişlerinin en son dönüştürdüğünü ve sonuçta elde edilen işlemin, `Controlled` functor çıkışının ardından gelen giriş `(Qubit[], 'T)` olarak---olmasını bekler.</span><span class="sxs-lookup"><span data-stu-id="0df1a-331">Thus, a developer expects that the inputs to `ControlledOnInt` place the callable being transformed last, and that the resulting operation takes as its input `(Qubit[], 'T)` --- the same order as followed by the output of the `Controlled` functor.</span></span>

# <a name="guidancetabguidance"></a>[<span data-ttu-id="0df1a-332">Rehber</span><span class="sxs-lookup"><span data-stu-id="0df1a-332">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="0df1a-333">Şunları öneririz:</span><span class="sxs-lookup"><span data-stu-id="0df1a-333">We suggest:</span></span>

- <span data-ttu-id="0df1a-334">Kısmi uygulama kullanımıyla tutarlı giriş sırası kullanın.</span><span class="sxs-lookup"><span data-stu-id="0df1a-334">Use input orderings consistent with the use of partial application.</span></span>
- <span data-ttu-id="0df1a-335">Yerleşik komik ile tutarlı giriş sırası kullanın.</span><span class="sxs-lookup"><span data-stu-id="0df1a-335">Use input orderings consistent with built-in functors.</span></span>
- <span data-ttu-id="0df1a-336">Tüm klasik girişleri, tüm hisse girişlerinden önce yerleştirin.</span><span class="sxs-lookup"><span data-stu-id="0df1a-336">Place all classical inputs before any quantum inputs.</span></span>

# <a name="examplestabexamples"></a>[<span data-ttu-id="0df1a-337">Örnekler</span><span class="sxs-lookup"><span data-stu-id="0df1a-337">Examples</span></span>](#tab/examples)

***

## <a name="documentation-conventions"></a><span data-ttu-id="0df1a-338">Belge kuralları</span><span class="sxs-lookup"><span data-stu-id="0df1a-338">Documentation Conventions</span></span> ##

<span data-ttu-id="0df1a-339">Q # dili, özel olarak biçimlendirilmiş belge açıklamalarını kullanarak işlemlere, işlevlere ve Kullanıcı tanımlı türlere belge iliştirmeye olanak tanır.</span><span class="sxs-lookup"><span data-stu-id="0df1a-339">The Q# language allows for attaching documentation to operations, functions, and user-defined types through the use of specially formatted documentation comments.</span></span>
<span data-ttu-id="0df1a-340">Üçlü eğik çizgi (`///`) ile belirtilen bu belge açıklamaları, her bir işlemin, işlevin ve Kullanıcı tanımlı türün amacını açıklamak için kullanılabilen küçük [Docfx-flavored markı](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html) belgeleriyle, her birinin hangi girişlerin beklediklerini açıklamak için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="0df1a-340">Denoted by triple-slashes (`///`), these documentation comments are small [DocFX-flavored Markdown](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html) documents that can be used to describing the purpose of each operation, function, and user-defined type, what inputs each expects, and so forth.</span></span>
<span data-ttu-id="0df1a-341">Hisse geliştirme seti ile sağlanan derleyici, bu açıklamaları ayıklar ve bu yorumları, https://docs.microsoft.com/quantum ' de olduğu gibi, karakterlik alan kaplamaları belgelerinin yardım 'ını kullanır.</span><span class="sxs-lookup"><span data-stu-id="0df1a-341">The compiler provided with the Quantum Development Kit extracts these comments and uses them to help typeset documentation similar to that at https://docs.microsoft.com/quantum.</span></span>
<span data-ttu-id="0df1a-342">Benzer şekilde, hisse geliştirme kiti ile birlikte sağlanan dil sunucusu, kullanıcılar için Q # kodundaki sembolleri üzerine getirdiğinde yardım sağlamak üzere bu açıklamaları kullanır.</span><span class="sxs-lookup"><span data-stu-id="0df1a-342">Similarly, the language server provided with the Quantum Development Kit uses these comments to provide help to users when they hover over symbols in their Q# code.</span></span>
<span data-ttu-id="0df1a-343">Belge açıklamalarının kullanımı, bu belgedeki diğer kurallara göre kolayca ifade olmayan Ayrıntılar için yararlı bir başvuru sunarak kullanıcıların kod anlamlı olmasına yardımcı olabilir.</span><span class="sxs-lookup"><span data-stu-id="0df1a-343">Making use of documentation comments can thus help users to make sense of code by providing a useful reference for details that are not easily expressed using the other conventions in this document.</span></span>

<div class="nextstepaction"><span data-ttu-id="0df1a-344">
    [Belge açıklaması sözdizimi başvurusu](xref:microsoft.quantum.language.statements#documentation-comments)
</span><span class="sxs-lookup"><span data-stu-id="0df1a-344">
    [Documentation comment syntax reference](xref:microsoft.quantum.language.statements#documentation-comments)
</span></span></div>

<span data-ttu-id="0df1a-345">Kullanıcılara yardımcı olmak üzere bu işlevselliği etkili bir şekilde kullanabilmek için, belge açıklamalarını yazarken göz önünde bulundurmanız önerilir.</span><span class="sxs-lookup"><span data-stu-id="0df1a-345">In order to effectively use this functionality to help users, we recommend keeping a few things in mind as you write documentation comments.</span></span>

# <a name="guidancetabguidance"></a>[<span data-ttu-id="0df1a-346">Rehber</span><span class="sxs-lookup"><span data-stu-id="0df1a-346">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="0df1a-347">Şunları öneririz:</span><span class="sxs-lookup"><span data-stu-id="0df1a-347">We suggest:</span></span>

- <span data-ttu-id="0df1a-348">Her ortak işlev, işlem ve Kullanıcı tanımlı tür hemen öncesinde bir belge yorumu gelmelidir.</span><span class="sxs-lookup"><span data-stu-id="0df1a-348">Each public function, operation, and user-defined type should be immediately preceded by a documentation comment.</span></span>
- <span data-ttu-id="0df1a-349">En azından, her belge yorumu aşağıdaki bölümleri içermelidir:</span><span class="sxs-lookup"><span data-stu-id="0df1a-349">At a minimum, each documentation comment should include the following sections:</span></span>
    - <span data-ttu-id="0df1a-350">Özet</span><span class="sxs-lookup"><span data-stu-id="0df1a-350">Summary</span></span>
    - <span data-ttu-id="0df1a-351">Girdi</span><span class="sxs-lookup"><span data-stu-id="0df1a-351">Input</span></span>
    - <span data-ttu-id="0df1a-352">Çıkış (varsa)</span><span class="sxs-lookup"><span data-stu-id="0df1a-352">Output (if applicable)</span></span>
- <span data-ttu-id="0df1a-353">Tüm özetlerin iki cümle veya daha az olduğundan emin olun.</span><span class="sxs-lookup"><span data-stu-id="0df1a-353">Ensure that all summaries are two sentences or less.</span></span> <span data-ttu-id="0df1a-354">Daha fazla oda gerekiyorsa, tüm ayrıntıların `# Summary` hemen ardından `# Description` bir bölüm sağlayın.</span><span class="sxs-lookup"><span data-stu-id="0df1a-354">If more room is needed, provide a `# Description` section immediately following `# Summary` with complete details.</span></span>
- <span data-ttu-id="0df1a-355">Her türlü istemci, özetler içinde TeX gösterimini desteklemediği için, her ikisi de, özetler halinde matematik dahil değildir.</span><span class="sxs-lookup"><span data-stu-id="0df1a-355">Where reasonable, do not include math in summaries, as not all clients support TeX notation in summaries.</span></span> <span data-ttu-id="0df1a-356">Prose belgeleri yazarken (örn. TeX veya Markaşağı), daha uzun çizgi uzunluklarının kullanılması tercih edilebilir.</span><span class="sxs-lookup"><span data-stu-id="0df1a-356">Note that when writing prose documents (e.g. TeX or Markdown), it may be preferable to use longer line lengths.</span></span>
- <span data-ttu-id="0df1a-357">`# Description` bölümünde tüm ilgili matematik ifadelerini sağlayın.</span><span class="sxs-lookup"><span data-stu-id="0df1a-357">Provide all relevant mathematical expressions in the `# Description` section.</span></span>
- <span data-ttu-id="0df1a-358">Girişleri açıkladığınızda, derleyici tarafından çıkarsanabilecek ve tutarsızlık doğurabilecek şekilde her girişin türlerini tekrarlamayın.</span><span class="sxs-lookup"><span data-stu-id="0df1a-358">When describing inputs, do not repeat the types of each input as these can be inferred by the compiler and risk introducing inconsistency.</span></span>
- <span data-ttu-id="0df1a-359">Her biri kendi `# Example` bölümünde örnekleri uygun şekilde girin.</span><span class="sxs-lookup"><span data-stu-id="0df1a-359">Provide examples as appropriate, each in their own `# Example` section.</span></span>
- <span data-ttu-id="0df1a-360">Kodu listelemeyi yapmadan önce her bir örneği kısaca açıklama yapın.</span><span class="sxs-lookup"><span data-stu-id="0df1a-360">Briefly describe each example before listing code.</span></span>
- <span data-ttu-id="0df1a-361">`# References` bir bölümdeki tüm ilgili akademik yayınları (örn. incelemeler, uygulama, blog gönderileri ve alternatif uygulamalar) madde işaretli bağlantı listesi olarak belirtin.</span><span class="sxs-lookup"><span data-stu-id="0df1a-361">Cite all relevant academic publications (e.g.: papers, proceedings, blog posts, and alternative implementations) in a `# References` section as a bulleted list of links.</span></span>
- <span data-ttu-id="0df1a-362">Mümkün olduğunda, tüm alıntı bağlantılarının kalıcı ve sabit tanımlayıcılar (Doın veya sürümlenmiş Arxıv numaraları) olduğundan emin olun.</span><span class="sxs-lookup"><span data-stu-id="0df1a-362">Ensure that, where possible, all citation links are to permanent and immutable identifiers (DOIs or versioned arXiv numbers).</span></span>
- <span data-ttu-id="0df1a-363">Bir işlem veya işlev, functor türevlerine göre diğer işlemlerle veya işlevlerle ilişkiliyse, `# See Also` bölümünde diğer çeşitleri madde işaretleri olarak listeleyin.</span><span class="sxs-lookup"><span data-stu-id="0df1a-363">When an operation or function is related to other operations or functions by functor variants, list other variants as bullets in the `# See Also` section.</span></span>
- <span data-ttu-id="0df1a-364">Düzey 1 (`/// #`) bölümleri arasında boş bir yorum çizgisi bırakın, ancak düzey 2 (`/// ##`) bölümleri arasında boş bir satır bırakmayın.</span><span class="sxs-lookup"><span data-stu-id="0df1a-364">Leave a blank comment line between level-1 (`/// #`) sections, but do not leave a blank line between level-2 (`/// ##`) sections.</span></span>

# <a name="examplestabexamples"></a>[<span data-ttu-id="0df1a-365">Örnekler</span><span class="sxs-lookup"><span data-stu-id="0df1a-365">Examples</span></span>](#tab/examples)

#### <a name=""></a><span data-ttu-id="0df1a-366">☑</span><span class="sxs-lookup"><span data-stu-id="0df1a-366">☑</span></span> ####

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

## <a name="formatting-conventions"></a><span data-ttu-id="0df1a-367">Biçimlendirme kuralları</span><span class="sxs-lookup"><span data-stu-id="0df1a-367">Formatting Conventions</span></span> ##

<span data-ttu-id="0df1a-368">Önceki önerilere ek olarak, tutarlı biçimlendirme kuralları kullanmak için kodun mümkün olduğunca okunabilir olmasını sağlamaya yardımcı olmak yararlı olur.</span><span class="sxs-lookup"><span data-stu-id="0df1a-368">In addition to the preceding suggestions, it is helpful to help make code as legible as possible to use consistent formatting rules.</span></span>
<span data-ttu-id="0df1a-369">Doğası gereği bu tür biçimlendirme kuralları, kişisel aesmerkler için biraz rastgele ve kesin bir şekilde çalışır.</span><span class="sxs-lookup"><span data-stu-id="0df1a-369">Such formatting rules by nature tend to be somewhat arbitrary and strongly up to personal aesthetics.</span></span>
<span data-ttu-id="0df1a-370">Nonetheless, bir ortak grup içinde tutarlı bir biçimlendirme kuralları kümesi ve özellikle de hisse geliştirme seti gibi büyük Q # projeleri için bakım yapmanızı öneririz.</span><span class="sxs-lookup"><span data-stu-id="0df1a-370">Nonetheless, we recommend maintaining a consistent set of formatting conventions within a group of collaborators, and especially for large Q# projects such as the Quantum Development Kit itself.</span></span>
<span data-ttu-id="0df1a-371">Bu kurallar, Q # derleyicisi ile tümleştirilmiş biçimlendirme Aracı kullanılarak otomatik olarak uygulanabilir.</span><span class="sxs-lookup"><span data-stu-id="0df1a-371">These rules can be automatically applied by using the formatting tool integrated with the Q# compiler.</span></span>

# <a name="guidancetabguidance"></a>[<span data-ttu-id="0df1a-372">Rehber</span><span class="sxs-lookup"><span data-stu-id="0df1a-372">Guidance</span></span>](#tab/guidance) 

<span data-ttu-id="0df1a-373">Şunları öneririz:</span><span class="sxs-lookup"><span data-stu-id="0df1a-373">We suggest:</span></span>

- <span data-ttu-id="0df1a-374">Taşınabilirlik için sekmeler yerine dört boşluk kullanın.</span><span class="sxs-lookup"><span data-stu-id="0df1a-374">Use four spaces instead of tabs for portability.</span></span>
  <span data-ttu-id="0df1a-375">Örneğin, VS Code:</span><span class="sxs-lookup"><span data-stu-id="0df1a-375">For instance, in VS Code:</span></span>
  ```json
    "editor.insertSpaces": true,
    "editor.tabSize": 4
  ```
- <span data-ttu-id="0df1a-376">Satır kaydırması, makul yerlerde 79 karakterden oluşmalıdır.</span><span class="sxs-lookup"><span data-stu-id="0df1a-376">Line wrap at 79 characters where reasonable.</span></span>
- <span data-ttu-id="0df1a-377">İkili işleçler etrafında boşluklar kullanın.</span><span class="sxs-lookup"><span data-stu-id="0df1a-377">Use spaces around binary operators.</span></span>
- <span data-ttu-id="0df1a-378">Tür ek açıklamaları için kullanılan iki nokta üst kısmında boşluk kullanın.</span><span class="sxs-lookup"><span data-stu-id="0df1a-378">Use spaces on either side of colons used for type annotations.</span></span>
- <span data-ttu-id="0df1a-379">Dizide ve tanımlama değerlerinde kullanılan virgüllerden sonra tek bir boşluk kullanın (örneğin, işlev ve işlemlere yönelik girişler).</span><span class="sxs-lookup"><span data-stu-id="0df1a-379">Use a single space after commas used in array and tuple literals (e.g.: in inputs to functions and operations).</span></span>
- <span data-ttu-id="0df1a-380">İşlev, işlem veya UDT adlarından sonra veya öznitelik bildirimlerinde `@` sonra boşluk kullanmayın.</span><span class="sxs-lookup"><span data-stu-id="0df1a-380">Do not use spaces after function, operation, or UDT names, or after the `@` in attribute declarations.</span></span>
- <span data-ttu-id="0df1a-381">Her öznitelik bildirimi kendi satırında olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="0df1a-381">Each attribute declaration should be on its own line.</span></span>

# <a name="examplestabexamples"></a>[<span data-ttu-id="0df1a-382">Örnekler</span><span class="sxs-lookup"><span data-stu-id="0df1a-382">Examples</span></span>](#tab/examples)

|   | <span data-ttu-id="0df1a-383">Gösterildiği</span><span class="sxs-lookup"><span data-stu-id="0df1a-383">Snippet</span></span> | <span data-ttu-id="0df1a-384">Açıklama</span><span class="sxs-lookup"><span data-stu-id="0df1a-384">Description</span></span> |
|---|---------|-------------|
| <span data-ttu-id="0df1a-385">☒</span><span class="sxs-lookup"><span data-stu-id="0df1a-385">☒</span></span> | <s>`2+3`</s> | <span data-ttu-id="0df1a-386">İkili işleçler etrafında boşluklar kullanın.</span><span class="sxs-lookup"><span data-stu-id="0df1a-386">Use spaces around binary operators.</span></span> |
| <span data-ttu-id="0df1a-387">☒</span><span class="sxs-lookup"><span data-stu-id="0df1a-387">☒</span></span> | <s>`target:Qubit`</s> | <span data-ttu-id="0df1a-388">Tür ek açıklaması etrafında boşluklar kullanın.</span><span class="sxs-lookup"><span data-stu-id="0df1a-388">Use spaces around type annotation colons.</span></span> |
| <span data-ttu-id="0df1a-389">☑</span><span class="sxs-lookup"><span data-stu-id="0df1a-389">☑</span></span> | `Example(a, b, c)` | <span data-ttu-id="0df1a-390">Giriş kayıt girişinde öğeler okunabilirlik için doğru aralıklıdır.</span><span class="sxs-lookup"><span data-stu-id="0df1a-390">Items in input tuple are correctly spaced for readability.</span></span> |
| <span data-ttu-id="0df1a-391">☒</span><span class="sxs-lookup"><span data-stu-id="0df1a-391">☒</span></span> | <s>`Example (a, b, c)`</s> | <span data-ttu-id="0df1a-392">Boşluklar, işlev, işlem veya UDT adlarından sonra bastırılmalıdır.</span><span class="sxs-lookup"><span data-stu-id="0df1a-392">Spaces should be suppressed after function, operation, or UDT names.</span></span> |

***

