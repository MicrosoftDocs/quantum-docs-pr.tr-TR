---
title: Broombridge şema belirtimi
author: guanghaolow
ms.author: gulow@microsoft.com
ms.date: 05/28/2019
ms.topic: article
uid: microsoft.quantum.libraries.chemistry.schema.spec_v_0_2
ms.openlocfilehash: 2f4be96bc6f1e8e6fe21b93bc0d9ab2aa367fd53
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2019
ms.locfileid: "73185316"
---
# <a name="broombridge-specification-v02"></a><span data-ttu-id="2bb03-102">Broombridge belirtimi v 0.2</span><span class="sxs-lookup"><span data-stu-id="2bb03-102">Broombridge Specification v0.2</span></span> #

<span data-ttu-id="2bb03-103">"", "" Gerekli değildir "," gerekli "," Bu "," zorunlu değildir "," durum ",", "ve" Isteğe bağlı "anahtar sözcükleri, [RFC 2119](https://tools.ietf.org/html/rfc2119)' de açıklandığı gibi yorumlanmalıdır.</span><span class="sxs-lookup"><span data-stu-id="2bb03-103">The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED",  "MAY", and "OPTIONAL" in this document are to be interpreted as described in [RFC 2119](https://tools.ietf.org/html/rfc2119).</span></span>

<span data-ttu-id="2bb03-104">"NOTE", "ıNFORMATION" veya "WARNING" başlıklı tüm kenar çubuğu bilgilendirici.</span><span class="sxs-lookup"><span data-stu-id="2bb03-104">Any sidebar with the headings "NOTE," "INFORMATION," or "WARNING" is informative.</span></span>

## <a name="introduction"></a><span data-ttu-id="2bb03-105">Tanıtım</span><span class="sxs-lookup"><span data-stu-id="2bb03-105">Introduction</span></span> ##

<span data-ttu-id="2bb03-106">Bu bölüm bilgilendirme.</span><span class="sxs-lookup"><span data-stu-id="2bb03-106">This section is informative.</span></span>

<span data-ttu-id="2bb03-107">Broombridge belgelerinin, hisse simülasyonu ve programlama araç zincirlerini kullanarak, işleme için hisse deneçlerinde simülasyon sorunlarının örneklerine iletişim kurması amaçlanmıştır.</span><span class="sxs-lookup"><span data-stu-id="2bb03-107">Broombridge documents are intended to communicate instances of simulation problems in quantum chemistry for processing using quantum simulation and programming toolchains.</span></span>

## <a name="serialization"></a><span data-ttu-id="2bb03-108">Getir</span><span class="sxs-lookup"><span data-stu-id="2bb03-108">Serialization</span></span> ##

<span data-ttu-id="2bb03-109">Bu bölüm normatıve 'dir.</span><span class="sxs-lookup"><span data-stu-id="2bb03-109">This section is normative.</span></span>

<span data-ttu-id="2bb03-110">Bir Broombridge belgesi 2,2 [4627](https://tools.ietf.org/html/rfc4627) , bir JSON nesnesini temsil eden bir [YAML 1,2 belgesi](http://yaml.org/spec/) olarak serileştirilmelidir.</span><span class="sxs-lookup"><span data-stu-id="2bb03-110">A Broombridge document MUST be serialized as a [YAML 1.2 document](http://yaml.org/spec/) representing a JSON object as described in [RFC 4627](https://tools.ietf.org/html/rfc4627) section 2.2.</span></span>
<span data-ttu-id="2bb03-111">YAML 'ye seri hale getirilen nesne, değeri `"https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/qchem-0.2.schema.json"`olan bir özellik `"$schema"` sahip OLMALıDıR ve JSON şeması taslağına göre geçerli olmalıdır-06 belirtimleri [[1](https://tools.ietf.org/html/draft-wright-json-schema-01), [2](https://tools.ietf.org/html/draft-wright-json-schema-validation-01)].</span><span class="sxs-lookup"><span data-stu-id="2bb03-111">The object serialized to YAML MUST have a property `"$schema"` whose value is `"https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/qchem-0.2.schema.json"`, and MUST be valid according to the JSON Schema draft-06 specifications [[1](https://tools.ietf.org/html/draft-wright-json-schema-01), [2](https://tools.ietf.org/html/draft-wright-json-schema-validation-01)].</span></span>

<span data-ttu-id="2bb03-112">Bu belirtimin geri kalanı için, "Broombridge nesnesi", bir Brombridge YAML belgesinden Serisi kaldırılan JSON nesnesine başvuracaktır.</span><span class="sxs-lookup"><span data-stu-id="2bb03-112">For the remainder of this specification, "the Broombridge object" will refer to the JSON object deserialized from a Broombridge YAML document.</span></span>

<span data-ttu-id="2bb03-113">Aksi belirtilmedikçe, nesneler bu belgede açıkça belirtilenlerin ötesinde ek özelliklere sahip olmamalıdır.</span><span class="sxs-lookup"><span data-stu-id="2bb03-113">Unless otherwise explicitly noted, objects MUST NOT have additional properties beyond those specified explicitly in this document.</span></span>

## <a name="additional-definitions"></a><span data-ttu-id="2bb03-114">Ek Tanımlar</span><span class="sxs-lookup"><span data-stu-id="2bb03-114">Additional Definitions</span></span> ##

<span data-ttu-id="2bb03-115">Bu bölüm normatıve 'dir.</span><span class="sxs-lookup"><span data-stu-id="2bb03-115">This section is normative.</span></span>

### <a name="quantity-objects"></a><span data-ttu-id="2bb03-116">Miktar nesneleri</span><span class="sxs-lookup"><span data-stu-id="2bb03-116">Quantity Objects</span></span> ###

<span data-ttu-id="2bb03-117">Bu bölüm normatıve 'dir.</span><span class="sxs-lookup"><span data-stu-id="2bb03-117">This section is normative.</span></span>

<span data-ttu-id="2bb03-118">Bir _Quantity_ NESNESI bir JSON nesnesidir ve değeri tablo 1 ' de listelenen izin verilen değerlerden biri olan bir özellik `units` sahip olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="2bb03-118">A _quantity object_ is a JSON object, and MUST have a property `units` whose value is one of the allowed values listed in Table 1.</span></span>

<span data-ttu-id="2bb03-119">Bir Quantity nesnesi, `units` özelliğine ek olarak `value` tek bir özelliğe sahipse _basit bir Quantity nesnesidir_ .</span><span class="sxs-lookup"><span data-stu-id="2bb03-119">A quantity object is a _simple quantity object_ if it has a single property `value` in addition to its `units` property.</span></span>
<span data-ttu-id="2bb03-120">`value` özelliğinin değeri bir sayı olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="2bb03-120">The value of the `value` property MUST be a number.</span></span>

<span data-ttu-id="2bb03-121">Bir Quantity nesnesi, `lower` özellikler varsa ve `units` özelliğine ek olarak `upper` _sınırlanmış bir miktar nesnesidir_ .</span><span class="sxs-lookup"><span data-stu-id="2bb03-121">A quantity object is a _bounded quantity object_ if it has the properties `lower` and `upper` in addition to its `units` property.</span></span>
<span data-ttu-id="2bb03-122">`lower` ve `upper` özelliklerinin değerleri sayı olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="2bb03-122">The values of the `lower` and `upper` properties MUST be numbers.</span></span>
<span data-ttu-id="2bb03-123">Sınırlanmış bir miktar nesnesi değeri sayı olan bir özellik `value` olabılır.</span><span class="sxs-lookup"><span data-stu-id="2bb03-123">A bounded quantity object MAY have a property `value` whose value is a number.</span></span>

<span data-ttu-id="2bb03-124">Bir Quantity nesnesi, özelliğin `format` ve bir özelliğin `units` özelliğine ek olarak `values` varsa _seyrek dizi miktarı nesnesidir_ .</span><span class="sxs-lookup"><span data-stu-id="2bb03-124">A quantity object is a _sparse array quantity object_ if it has the property `format` and a property `values` in addition to its `units` property.</span></span>
<span data-ttu-id="2bb03-125">`format` değeri `sparse`dize OLMALıDıR.</span><span class="sxs-lookup"><span data-stu-id="2bb03-125">The value of `format` MUST be the string `sparse`.</span></span>
<span data-ttu-id="2bb03-126">`values` özelliğinin değeri bir dizi OLMALıDıR.</span><span class="sxs-lookup"><span data-stu-id="2bb03-126">The value of the `values` property MUST be an array.</span></span>
<span data-ttu-id="2bb03-127">Her `values` öğesi, seyrek dizi miktarının indekslerini ve değerini temsil eden bir dizi OLMALıDıR.</span><span class="sxs-lookup"><span data-stu-id="2bb03-127">Each element of `values` MUST be an array representing the indices and value of the sparse array quantity.</span></span>

<span data-ttu-id="2bb03-128">Seyrek dizi miktarı nesnesinin her bir öğesi için dizinler, tüm seyrek dizi miktarı nesnesi genelinde benzersiz OLMALıDıR.</span><span class="sxs-lookup"><span data-stu-id="2bb03-128">The indices for each element of a sparse array quantity object MUST be unique across the entire sparse array quantity object.</span></span>
<span data-ttu-id="2bb03-129">Bir dizin `0`bir değeri varsa, bir Ayrıştırıcı seyrek dizi Quantity nesnesini aynı dizinde yer alan bir seyrek dizi Quantity nesnesi ile aynı şekilde ele ALMALıDıR.</span><span class="sxs-lookup"><span data-stu-id="2bb03-129">If an index is present with a value of `0`, a parser MUST treat the sparse array quantity object identically to a sparse array quantity object in which that index is not present at all.</span></span>


<span data-ttu-id="2bb03-130">Bir Quantity nesnesi olmalıdır</span><span class="sxs-lookup"><span data-stu-id="2bb03-130">A quantity object MUST either be</span></span>

- <span data-ttu-id="2bb03-131">basit bir miktar nesnesi,</span><span class="sxs-lookup"><span data-stu-id="2bb03-131">a simple quantity object,</span></span>
- <span data-ttu-id="2bb03-132">sınırlanmış bir miktar nesnesi veya</span><span class="sxs-lookup"><span data-stu-id="2bb03-132">a bounded quantity object, or</span></span>
- <span data-ttu-id="2bb03-133">seyrek dizi miktarı nesnesi.</span><span class="sxs-lookup"><span data-stu-id="2bb03-133">a sparse array quantity object.</span></span>


### <a name="examples"></a><span data-ttu-id="2bb03-134">Örnekler</span><span class="sxs-lookup"><span data-stu-id="2bb03-134">Examples</span></span> ###

<span data-ttu-id="2bb03-135">Bu bölüm bilgilendirme.</span><span class="sxs-lookup"><span data-stu-id="2bb03-135">This section is informative.</span></span>

<span data-ttu-id="2bb03-136">$1.9844146837\,\mathrm{Ha} $ öğesini temsil eden basit bir miktar:</span><span class="sxs-lookup"><span data-stu-id="2bb03-136">A simple quantity representing $1.9844146837\,\mathrm{Ha}$:</span></span>

```yaml
coulomb_repulsion:
    value: 1.9844146837
    units: hartree
```

<span data-ttu-id="2bb03-137">$ [-7,-6]\,\mathrm{Ha} $ aralığında tek bir dağılımı temsil eden sınırlanmış bir miktar.</span><span class="sxs-lookup"><span data-stu-id="2bb03-137">A bounded quantity representing a uniform distribution over the interval $[-7, -6]\,\mathrm{Ha}$:</span></span>

```yaml
fci_energy:
    upper: -6
    lower: -7
    units: hartree
```

<span data-ttu-id="2bb03-138">Aşağıda, bir öğesi `hello` eşit `[1, 2]` ve bir öğe `world``[3, 4]` eşit olan seyrek dizi miktarı verilmiştir:</span><span class="sxs-lookup"><span data-stu-id="2bb03-138">The following is a sparse array quantity with an element `[1, 2]` equal to `hello` and an element `[3, 4]` equal to `world`:</span></span>

```yaml
sparse_example:
    format: sparse
    units: hartree
    values:
    - [1, 2, "hello"]
    - [3, 4, "world"]
```

## <a name="format-section"></a><span data-ttu-id="2bb03-139">Biçim bölümü</span><span class="sxs-lookup"><span data-stu-id="2bb03-139">Format Section</span></span> ##

<span data-ttu-id="2bb03-140">Bu bölüm normatıve 'dir.</span><span class="sxs-lookup"><span data-stu-id="2bb03-140">This section is normative.</span></span>

<span data-ttu-id="2bb03-141">Broombridge nesnesi, değeri `version`adlı bir özellik olan JSON nesnesi olan bir özellik `format` sahip OLMALıDıR.</span><span class="sxs-lookup"><span data-stu-id="2bb03-141">The Broombridge object MUST have a property `format` whose value is a JSON object with one property called `version`.</span></span>
<span data-ttu-id="2bb03-142">`version` özelliği `"0.2"`değerine sahip OLMALıDıR.</span><span class="sxs-lookup"><span data-stu-id="2bb03-142">The `version` property MUST have the value `"0.2"`.</span></span>

### <a name="example"></a><span data-ttu-id="2bb03-143">Örnek</span><span class="sxs-lookup"><span data-stu-id="2bb03-143">Example</span></span> ###

<span data-ttu-id="2bb03-144">Bu bölüm bilgilendirme.</span><span class="sxs-lookup"><span data-stu-id="2bb03-144">This section is informative.</span></span>

```yaml
format:                        # required
    version: "0.2"             # must match exactly
```

## <a name="problem-description-section"></a><span data-ttu-id="2bb03-145">Sorun açıklaması bölümü</span><span class="sxs-lookup"><span data-stu-id="2bb03-145">Problem Description Section</span></span> ##

<span data-ttu-id="2bb03-146">Bu bölüm normatıve 'dir.</span><span class="sxs-lookup"><span data-stu-id="2bb03-146">This section is normative.</span></span>

<span data-ttu-id="2bb03-147">Broombridge nesnesi değeri bir JSON dizisi olan bir özellik `problem_description` sahip OLMALıDıR.</span><span class="sxs-lookup"><span data-stu-id="2bb03-147">The Broombridge object MUST have a property `problem_description` whose value is a JSON array.</span></span>
<span data-ttu-id="2bb03-148">`problem_description` özelliğinin değerindeki her öğe, bu bölümün geri kalanında açıklandığı gibi bir integralleri kümesini açıklayan bir JSON nesnesi olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="2bb03-148">Each item in the value of the `problem_description` property MUST be a JSON object describing one set of integrals, as described in the remainder of this section.</span></span>
<span data-ttu-id="2bb03-149">Bu bölümün geri kalanında, "sorun açıklaması nesnesi" terimi, Broombridge nesnesinin `problem_description` özelliğinin değerindeki bir öğeye başvuracaktır.</span><span class="sxs-lookup"><span data-stu-id="2bb03-149">In the remainder of this section, the term "problem description object" will refer to an item in the value of the `problem_description` property of the Broombridge object.</span></span>

<span data-ttu-id="2bb03-150">Her sorun açıklaması nesnesinin değeri JSON nesnesi olan bir özellik `metadata` olması gerekır.</span><span class="sxs-lookup"><span data-stu-id="2bb03-150">Each problem description object MUST have a property `metadata` whose value is a JSON object.</span></span>
<span data-ttu-id="2bb03-151">`metadata` değeri boş JSON nesnesi (yani, `{}`) olabilir veya uygulayıcısı tarafından tanımlanan ek özellikleri içerebilir.</span><span class="sxs-lookup"><span data-stu-id="2bb03-151">The value of `metadata` MAY be the empty JSON object (that is, `{}`), or MAY contain additional properties defined by the implementor.</span></span>

### <a name="hamiltonian-section"></a><span data-ttu-id="2bb03-152">Hamiltonian bölümü</span><span class="sxs-lookup"><span data-stu-id="2bb03-152">Hamiltonian Section</span></span> ###

#### <a name="overview"></a><span data-ttu-id="2bb03-153">Genel Bakış</span><span class="sxs-lookup"><span data-stu-id="2bb03-153">Overview</span></span> ####

<span data-ttu-id="2bb03-154">Bu bölüm bilgilendirme.</span><span class="sxs-lookup"><span data-stu-id="2bb03-154">This section is informative.</span></span>

<span data-ttu-id="2bb03-155">Her bir sorun açıklama nesnesinin `hamiltonian` özelliği, belirli bir hisse dili yanılma sorunu için Hamiltonian 'yi, tek ve iki gövdedeki terimleri gerçek sayıların seyrek dizileri olarak listeleyerek açıklar.</span><span class="sxs-lookup"><span data-stu-id="2bb03-155">The `hamiltonian` property of each problem description object describes the Hamiltonian for a particular quantum chemistry problem by listing out its one- and two-body terms as sparse arrays of real numbers.</span></span>
<span data-ttu-id="2bb03-156">Her sorun açıklaması nesnesi tarafından tanımlanan Hamiltonian işleçleri formu alır</span><span class="sxs-lookup"><span data-stu-id="2bb03-156">The Hamiltonian operators described by each problem description object take the form</span></span>

<span data-ttu-id="2bb03-157">$ $ H = \sum\_\{ı, j\}\sum\_{\sigma\in\\{\upok, \downok\\}} H\_\{ij\} a ^\{\dağılım\}\_{ı , \sigma} a\_{j, \sigma} + \frac{1}{2}\sum\_\{i, j, k, l\}\sum\_{\sigma, \rho\in\\{\upok, \downok\\}} h\_{ı , \sigma} a ^ \dağılım\_{k, \rho} a\_{l, \rho} a\_{j, \sigma}, $ $</span><span class="sxs-lookup"><span data-stu-id="2bb03-157">$$ H = \sum\_\{i,j\}\sum\_{\sigma\in\\{\uparrow,\downarrow\\}} h\_\{ij\} a^\{\dagger\}\_{i,\sigma} a\_{j,\sigma} + \frac{1}{2}\sum\_\{i,j,k,l\}\sum\_{\sigma,\rho\in\\{\uparrow,\downarrow\\}} h\_{ijkl} a^\dagger\_{i,\sigma} a^\dagger\_{k,\rho} a\_{l,\rho} a\_{j,\sigma}, $$</span></span>

<span data-ttu-id="2bb03-158">Burada _ {ijkl} = (ij | KL) $ Mullikliksiz kuralına göre $h.</span><span class="sxs-lookup"><span data-stu-id="2bb03-158">here $h_{ijkl}= (ij|kl)$ in Mulliken convention.</span></span>

<span data-ttu-id="2bb03-159">Netlik açısından, tek bir elektron dönemi</span><span class="sxs-lookup"><span data-stu-id="2bb03-159">For clarity, the one-electron term is</span></span>

<span data-ttu-id="2bb03-160">$ $ h_ {ij} = \int {\mathrm d} x \psi ^ \*\_ı (x) \left (\frac{1}{2}\nabla ^ 2 + \ Sum\_{A} \frac{Z\_A} {| x-x\_A |}  \right) \psi\_j (x), $ $</span><span class="sxs-lookup"><span data-stu-id="2bb03-160">$$ h_{ij} = \int {\mathrm d}x \psi^\*\_i(x) \left(\frac{1}{2}\nabla^2 + \sum\_{A}\frac{Z\_A}{|x-x\_A|}  \right) \psi\_j(x), $$</span></span>

<span data-ttu-id="2bb03-161">ve iki elektron terimi</span><span class="sxs-lookup"><span data-stu-id="2bb03-161">and the two-electron term is</span></span>

<span data-ttu-id="2bb03-162">$ $ h\_\{ijkl\} = \iint \{\mathrm d\}x ^ 2 \psı ^\{\*\}\_ı (x\_1) \psi\_j (x\_1) \frac\{1\}\{\|x\_1-x\_2\|\}\psı\_k ^\{\*\}(x\_2) \psı\_l (x\_2).</span><span class="sxs-lookup"><span data-stu-id="2bb03-162">$$ h\_\{ijkl\} = \iint \{\mathrm d\}x^2 \psi^\{\*\}\_i(x\_1)\psi\_j(x\_1) \frac\{1\}\{\|x\_1 -x\_2\|\}\psi\_k^\{\*\}(x\_2) \psi\_l(x\_2).</span></span>
$$

<span data-ttu-id="2bb03-163">`integral_sets` özelliğinin her bir öğesinin [`basis_set` özelliğinin](#basis-set-object) açıklamamız bölümünde belirtildiği gibi, kullanılan temel işlevlerin gerçek değerli olduğunu açıkça varsaydık.</span><span class="sxs-lookup"><span data-stu-id="2bb03-163">As noted in our description of the [`basis_set` property](#basis-set-object) of each element of the `integral_sets` property, we further explicitly assume that the basis functions used are real-valued.</span></span>
<span data-ttu-id="2bb03-164">Bu, Hamiltonian 'ın gösterimini sıkıştırmak için terimler arasında aşağıdaki symmetries kullanmamızı sağlar.</span><span class="sxs-lookup"><span data-stu-id="2bb03-164">This allows us to use the following symmetries between the terms to compress the representation of the Hamiltonian.</span></span>

<span data-ttu-id="2bb03-165">$ $ h_ {ijkl} = h_ {ijlk} = h_ {JIKL} = h_ {jıld} = h_ {klij} = h_ {klji} = h_ {lkij} = h_ {lkji}.</span><span class="sxs-lookup"><span data-stu-id="2bb03-165">$$ h_{ijkl} = h_{ijlk}=h_{jikl}=h_{jilk}=h_{klij}=h_{klji}=h_{lkij}=h_{lkji}.</span></span>
$$


#### <a name="contents"></a><span data-ttu-id="2bb03-166">İçindekiler</span><span class="sxs-lookup"><span data-stu-id="2bb03-166">Contents</span></span> ####

<span data-ttu-id="2bb03-167">Bu bölüm normatıve 'dir.</span><span class="sxs-lookup"><span data-stu-id="2bb03-167">This section is normative.</span></span>

<span data-ttu-id="2bb03-168">Her sorun açıklaması nesnesinin değeri JSON nesnesi olan bir özellik `hamiltonian` olması gerekır.</span><span class="sxs-lookup"><span data-stu-id="2bb03-168">Each problem description object MUST have a property `hamiltonian` whose value is a JSON object.</span></span>
<span data-ttu-id="2bb03-169">`hamiltonian` özelliğinin değeri Hamiltonian nesnesi olarak bilinir ve bu bölümün geri kalanında açıklanan şekilde Özellikler `one_electron_integrals` ve `two_electron_integrals` OLMALıDıR.</span><span class="sxs-lookup"><span data-stu-id="2bb03-169">The value of the `hamiltonian` property is known as a Hamiltonian object, and MUST have the properties `one_electron_integrals` and `two_electron_integrals` as described in the remainder of this section.</span></span>

<span data-ttu-id="2bb03-170">Her sorun açıklaması nesnesinin değeri basit bir miktar nesnesi olan bir özellik `coulomb_repulsion` olması gerekır.</span><span class="sxs-lookup"><span data-stu-id="2bb03-170">Each problem description object MUST have a property `coulomb_repulsion` whose value is a simple quantity object.</span></span>
<span data-ttu-id="2bb03-171">Her sorun açıklaması nesnesinin değeri basit bir miktar nesnesi olan bir özellik `energy_offet` olması gerekır.</span><span class="sxs-lookup"><span data-stu-id="2bb03-171">Each problem description object MUST have a property `energy_offet` whose value is a simple quantity object.</span></span>
> <span data-ttu-id="2bb03-172">NOTUN `coulomb_repulsion` ve `energy_offet` değerleri birlikte eklenen Hamiltonian 'nin kimlik terimini yakalar.</span><span class="sxs-lookup"><span data-stu-id="2bb03-172">[NOTE] The values of `coulomb_repulsion` and `energy_offet` added together capture the identity term of the Hamiltonian.</span></span>

##### <a name="one-electron-integrals-object"></a><span data-ttu-id="2bb03-173">Tek bir elektron Integrals nesnesi</span><span class="sxs-lookup"><span data-stu-id="2bb03-173">One-Electron Integrals Object</span></span> #####

<span data-ttu-id="2bb03-174">Bu bölüm normatıve 'dir.</span><span class="sxs-lookup"><span data-stu-id="2bb03-174">This section is normative.</span></span>

<span data-ttu-id="2bb03-175">Hamiltonian nesnesinin `one_electron_integrals` özelliği, dizinleri iki tamsayı olan ve değerleri sayı olan bir seyrek dizi miktarı olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="2bb03-175">The `one_electron_integrals` property of the Hamiltonian object MUST be a sparse array quantity whose indices are two integers and whose values are numbers.</span></span>
<span data-ttu-id="2bb03-176">Her dönemde `i >= j``[i, j]` dizinler OLMALıDıR.</span><span class="sxs-lookup"><span data-stu-id="2bb03-176">Every term MUST have indices `[i, j]` where `i >= j`.</span></span>

> <span data-ttu-id="2bb03-177">NOTUN Bu, Hamiltonian 'nin hermitian olduğu olgunun bir sonucu olan $h _ {ij} = h_ {Ji} $ olan simetriyi yansıtır.</span><span class="sxs-lookup"><span data-stu-id="2bb03-177">[NOTE] This reflects the symmetry that $h_{ij} = h_{ji}$ which is a consequence of the fact that the Hamiltonian is Hermitian.</span></span>


###### <a name="example"></a><span data-ttu-id="2bb03-178">Örnek</span><span class="sxs-lookup"><span data-stu-id="2bb03-178">Example</span></span> ######

<span data-ttu-id="2bb03-179">Bu bölüm bilgilendirme.</span><span class="sxs-lookup"><span data-stu-id="2bb03-179">This section is informative.</span></span>

<span data-ttu-id="2bb03-180">Şu seyrek dizi miktarı Hamiltonian $ $ H = \left (-5,0 (a ^\{\alger\}\_{1, \upoklu} bir\_{1, \upoklu} + bir ^\{\dağılım\}\_{1, \downok} a\_{1) temsil eder , \downok}) + 0,17 (bir ^\{\dağılım\}\_{2, \upoklu} bir\_{1, \upoklu} + bir ^\{\dağılım\}\_{1, \upoklu} +\_{2, \upoklu} + bir ^\{\dağılım\}\_{2 , \downok} bir\_{1, \downok} + bir ^\{\dağılım\}\_{1, \down\mathrm{ha}.} a\_{2, \downok}) \right)\\,</span><span class="sxs-lookup"><span data-stu-id="2bb03-180">The following sparse array quantity represents the Hamiltonian $$ H = \left(-5.0  (a^\{\dagger\}\_{1,\uparrow} a\_{1,\uparrow}+a^\{\dagger\}\_{1,\downarrow} a\_{1,\downarrow})+ 0.17 (a^\{\dagger\}\_{2,\uparrow} a\_{1,\uparrow}+ a^\{\dagger\}\_{1,\uparrow} a\_{2,\uparrow}+a^\{\dagger\}\_{2,\downarrow} a\_{1,\downarrow}+ a^\{\dagger\}\_{1,\downarrow} a\_{2,\downarrow})\right)\\,\mathrm{Ha}.</span></span>
$$

```yaml
one_electron_integrals:     # required
    units: hartree          # required
    format: sparse          # required
    values:                 # required
        # i j f(i,j)
        - [1, 1, -5.0]
        - [2, 1,  0.17]
```
> [!NOTE]
> <span data-ttu-id="2bb03-181">Broombridge, 1 tabanlı dizin oluşturma kullanır.</span><span class="sxs-lookup"><span data-stu-id="2bb03-181">Broombridge uses 1-based indexing.</span></span>


##### <a name="two-electron-integrals-object"></a><span data-ttu-id="2bb03-182">İki elektron Integrals nesnesi</span><span class="sxs-lookup"><span data-stu-id="2bb03-182">Two-Electron Integrals Object</span></span> #####

<span data-ttu-id="2bb03-183">Bu bölüm normatıve 'dir.</span><span class="sxs-lookup"><span data-stu-id="2bb03-183">This section is normative.</span></span>

<span data-ttu-id="2bb03-184">Hamiltonian nesnesinin `two_electron_integrals` özelliği, `index_convention`adlı bir ek özelliğe sahip bir seyrek dizi miktarı olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="2bb03-184">The `two_electron_integrals` property of the Hamiltonian object MUST be a sparse array quantity with one additional property called `index_convention`.</span></span>
<span data-ttu-id="2bb03-185">`two_electron_integrals` değerinin her bir öğesi dört Dizin IÇERMELIDIR.</span><span class="sxs-lookup"><span data-stu-id="2bb03-185">Each element of the value of `two_electron_integrals` MUST have four indices.</span></span>

<span data-ttu-id="2bb03-186">Her `two_electron_integrals` özelliği bir `index_convention` özelliğine sahip OLMALıDıR.</span><span class="sxs-lookup"><span data-stu-id="2bb03-186">Each `two_electron_integrals` property MUST have a `index_convention` property.</span></span>
<span data-ttu-id="2bb03-187">`index_convention` özelliğinin değeri tablo 1 ' de listelenen izin verilen değerlerden biri OLMALıDıR.</span><span class="sxs-lookup"><span data-stu-id="2bb03-187">The value of the `index_convention` property MUST be one of the allowed values listed in Table 1.</span></span>
<span data-ttu-id="2bb03-188">`index_convention` değeri `mulliken`, sonra da `two_electron_integrals` seyrek dizi miktarının her öğesi için, bir Broombridge belgesi yükleyen bir Ayrıştırıcı, iki elektron işlecine eşit bir Hamiltonian terimi oluşturmalıdır $h _ {i, j, k, l} a ^ \abger_i a ^ \leger_j a_k a_l $ Burada $i $, $j $, $k $ ve $l $ değeri en az 1 tamsayı olmalıdır ve burada $h _ {i, j, k, l} $, seyrek dizi miktarının öğe `[i, j, k, l, h(i, j, k, l)]` öğesidir.</span><span class="sxs-lookup"><span data-stu-id="2bb03-188">If the value of `index_convention` is `mulliken`, then for each element of the `two_electron_integrals` sparse array quantity, a parser loading a Broombridge document MUST instantiate a Hamiltonian term equal to the two-electron operator $h_{i, j, k, l} a^\dagger_i a^\dagger_j a_k a_l$, where $i$, $j$, $k$, and $l$ MUST be integers of value at least 1, and where $h_{i, j, k, l}$ is the element `[i, j, k, l, h(i, j, k, l)]` of the sparse array quantity.</span></span>

###### <a name="symmetries"></a><span data-ttu-id="2bb03-189">Symmetries</span><span class="sxs-lookup"><span data-stu-id="2bb03-189">Symmetries</span></span> ######

<span data-ttu-id="2bb03-190">Bu bölüm normatıve 'dir.</span><span class="sxs-lookup"><span data-stu-id="2bb03-190">This section is normative.</span></span>

<span data-ttu-id="2bb03-191">Bir `two_electron_integrals` nesnesinin `index_convention` özelliği `mulliken`eşitse, dizinler `[i, j, k, l]` olan bir öğe varsa, `[i, j, k, l]`eşit olmadıkları takdirde aşağıdaki dizinler bulunmamalıdır:</span><span class="sxs-lookup"><span data-stu-id="2bb03-191">If the `index_convention` property of a `two_electron_integrals` object is equal to `mulliken`, then if an element with indices `[i, j, k, l]` is present, the following indices MUST NOT be present unless they are equal to `[i, j, k, l]`:</span></span>

- `[i, j, l, k]`
- `[j, i, k, l]`
- `[j, i, l, k]`
- `[k, l, i, j]`
- `[k, l, j, i]`
- `[l, k, j, i]`

> [!NOTE]
> <span data-ttu-id="2bb03-192">`index_convention` özelliği seyrek bir Quantity nesnesi olduğundan, farklı öğelerde hiçbir dizin tekrarlanmayabilir.</span><span class="sxs-lookup"><span data-stu-id="2bb03-192">Because the `index_convention` property is a sparse quantity object, no indices may be repeated on different elements.</span></span>
> <span data-ttu-id="2bb03-193">Özellikle, Dizin `[i, j, k, l]` olan bir öğe varsa, başka bir öğe bu dizinleri içeremez.</span><span class="sxs-lookup"><span data-stu-id="2bb03-193">In particular, if an element with indices `[i, j, k, l]` is present, no other element may have those indices.</span></span>


<!-- h_{ijkl} = h_{ijlk}=h_{jikl}=h_{jilk}=h_{klij}=h_{klji}=h_{lkji}. -->

###### <a name="example"></a><span data-ttu-id="2bb03-194">Örnek</span><span class="sxs-lookup"><span data-stu-id="2bb03-194">Example</span></span> #######

<span data-ttu-id="2bb03-195">Bu bölüm bilgilendirme.</span><span class="sxs-lookup"><span data-stu-id="2bb03-195">This section is informative.</span></span>

<span data-ttu-id="2bb03-196">Aşağıdaki nesne Hamiltonian 'yi belirtir</span><span class="sxs-lookup"><span data-stu-id="2bb03-196">The following object specifies the Hamiltonian</span></span>

<span data-ttu-id="2bb03-197">$ $ H = \frac12 \sum\_{\sigma, \rho\in\\{\upok, \downarrow\\}} \Biggr (1,6 a ^ {\abger}\_{1, \sigma} a ^ {\abger}\_{1, \rho} a\_{1, \rho} a\_{1, \sigma}-0,1 a ^ {\abger}\_{6 , \sigma} a ^ {\hanger}\_{1, \rho} a\_{3, \rho} a\_{2, \sigma}-0,1 a ^ {\abger}\_{6, \sigma} a ^ {\dağılım}\_{1, \rho} a\_{2, \rho} a\_{3 , \sigma}-0,1 a ^ {\hanger}\_{1, \sigma} a ^ {\abger}\_{6, \rho} a\_{3, \rho} a\_{2, \sigma}-0,1 a ^ {\abger}\_{1, \sigma} a ^ {\dağılım ger}\_{6, \rho} a\_{2 , \rho} a\_{3, \sigma} $ $ $ $-0,1 a ^ {\hanger}\_{3, \sigma} a ^ {\abger}\_{2, \rho} a\_{6, \rho} a\_{1, \sigma}-0,1 a ^ {\dağılım}\_{3, \sigma} a ^ {\gesger}\_{2 , \rho} a\_{1, \rho} a\_{6, \sigma}-0,1 a ^ {\abger}\_{2, \sigma} a ^ {\abger}\_{3, \rho} a\_{6, \rho} a\_{1, \sigma}-0,1 a ^ {\hanger}\_{2 , \sigma} a ^ {\hanger}\_{3, \rho} a\_{1, \rho} a\_{6, \sigma}\Biggr)\\, \textrm{Ha}.</span><span class="sxs-lookup"><span data-stu-id="2bb03-197">$$ H = \frac12 \sum\_{\sigma,\rho\in\\{\uparrow,\downarrow\\}}\Biggr( 1.6 a^{\dagger}\_{1,\sigma} a^{\dagger}\_{1,\rho} a\_{1,\rho} a\_{1,\sigma}- 0.1 a^{\dagger}\_{6,\sigma} a^{\dagger}\_{1,\rho} a\_{3,\rho} a\_{2,\sigma}- 0.1 a^{\dagger}\_{6,\sigma} a^{\dagger}\_{1,\rho} a\_{2,\rho} a\_{3,\sigma}- 0.1 a^{\dagger}\_{1,\sigma} a^{\dagger}\_{6,\rho} a\_{3,\rho} a\_{2,\sigma}- 0.1 a^{\dagger}\_{1,\sigma} a^{\dagger}\_{6,\rho} a\_{2,\rho} a\_{3,\sigma} $$ $$- 0.1 a^{\dagger}\_{3,\sigma} a^{\dagger}\_{2,\rho} a\_{6,\rho} a\_{1,\sigma}- 0.1 a^{\dagger}\_{3,\sigma} a^{\dagger}\_{2,\rho} a\_{1,\rho} a\_{6,\sigma}- 0.1 a^{\dagger}\_{2,\sigma} a^{\dagger}\_{3,\rho} a\_{6,\rho} a\_{1,\sigma}- 0.1 a^{\dagger}\_{2,\sigma} a^{\dagger}\_{3,\rho} a\_{1,\rho} a\_{6,\sigma}\Biggr)\\,\textrm{Ha}.</span></span>
$$

```yaml
two_electron_integrals:
    index_convention: mulliken
    units: hartree
    format: sparse
    values:
        - [1, 1, 1, 1,  1.6]
        - [6, 1, 3, 2, -0.1]
```

### <a name="initial-state-section"></a><span data-ttu-id="2bb03-198">İlk durum bölümü</span><span class="sxs-lookup"><span data-stu-id="2bb03-198">Initial State Section</span></span> ###

<span data-ttu-id="2bb03-199">Bu bölüm normatıve 'dir.</span><span class="sxs-lookup"><span data-stu-id="2bb03-199">This section is normative.</span></span>

<span data-ttu-id="2bb03-200">Değeri bir JSON dizisi olan `initial_state_suggestion` nesnesi, belirtilen Hamiltonian ile ilgilenilen ilk hisse kazanç durumlarını belirtir.</span><span class="sxs-lookup"><span data-stu-id="2bb03-200">The `initial_state_suggestion` object whose value is a JSON array specifies initial quantum states of interest to the specified Hamiltonian.</span></span> <span data-ttu-id="2bb03-201">`initial_state_suggestion` özelliğinin değerindeki her öğe, bu bölümün geri kalanında açıklandığı gibi bir hisse miktarını açıklayan bir JSON nesnesi olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="2bb03-201">Each item in the value of the `initial_state_suggestion` property MUST be a JSON object describing one quantum state, as described in the remainder of this section.</span></span>
<span data-ttu-id="2bb03-202">Bu bölümün geri kalanında, "durum nesnesi" terimi, Broombridge nesnesinin `initial_state_suggestion` özelliğinin değerindeki bir öğeye başvuracaktır.</span><span class="sxs-lookup"><span data-stu-id="2bb03-202">In the remainder of this section, the term "state object" will refer to an item in the value of the `initial_state_suggestion` property of the Broombridge object.</span></span>

#### <a name="state-object"></a><span data-ttu-id="2bb03-203">Durum nesnesi</span><span class="sxs-lookup"><span data-stu-id="2bb03-203">State object</span></span> ####

<span data-ttu-id="2bb03-204">Bu bölüm normatıve 'dir.</span><span class="sxs-lookup"><span data-stu-id="2bb03-204">This section is normative.</span></span>

<span data-ttu-id="2bb03-205">Her durum nesnesinin bir dize içeren bir `label` özelliği OLMALıDıR.</span><span class="sxs-lookup"><span data-stu-id="2bb03-205">Each state object MUST have a `label` property containing a string.</span></span> <span data-ttu-id="2bb03-206">Her durum nesnesinin bir `method` özelliği OLMALıDıR.</span><span class="sxs-lookup"><span data-stu-id="2bb03-206">Each state object MUST have a `method` property.</span></span> <span data-ttu-id="2bb03-207">`method` özelliğinin değeri, tablo 3 ' te listelenen izin verilen değerlerden biri OLMALıDıR.</span><span class="sxs-lookup"><span data-stu-id="2bb03-207">The value of the `method` property MUST be one of the allowed values listed in Table 3.</span></span>
<span data-ttu-id="2bb03-208">Her durum nesnesi, değeri bir basit miktar nesnesi olması gereken bir özellik `energy` sahip olabilir.</span><span class="sxs-lookup"><span data-stu-id="2bb03-208">Each state object MAY have a property `energy` whose value MUST be a simple quantity object.</span></span>

<span data-ttu-id="2bb03-209">`method` özelliğinin değeri `sparse_multi_configurational`ise, State nesnesinin bir temel durum dizisi ve bunların Normalleştirilmemiş yükseltilmiş tudes dizisini içeren bir `superposition` özelliğine sahip olması gerekır.</span><span class="sxs-lookup"><span data-stu-id="2bb03-209">If the value of the `method` property is `sparse_multi_configurational`, the state object MUST have a `superposition` property containing an array of basis states and their unnormalized amplitudes.</span></span>

<span data-ttu-id="2bb03-210">Örneğin, ilk durumlar $ $ \ket{G0} = \ket{G1} = \ket{G2} = (a ^ {\gger}\_{1) \upok} a ^ {\abger}\_{2, \upoklu} a ^ {\abger}\_{2, \downok}) \demet{0} $ $ $ $ \ket{E} = \frac{0.exe} (a ^ {\dağılım}\_{1 , \upoklu}a ^ {\hanger}\_{2, \upoklu}\_{2, \downok}) + 0.2 (a ^ {\abger}\_{1, \upoklu} a ^ {\gesger}\_{3, \upoklu} bir ^ {\dağılım}\_{2, \downoklu})} {\sqrt{| 0.1 | ^ 2 + | 0.2 | ^ 2}} \ demet{0}$ $ Burada $ \ket{E} $ enerji $0,987 \textrm{Ha} $, tarafından temsil edilir</span><span class="sxs-lookup"><span data-stu-id="2bb03-210">For example, the initial states $$ \ket{G0}=\ket{G1}=\ket{G2}=(a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{2,\uparrow}a^{\dagger}\_{2,\downarrow})\ket{0} $$ $$ \ket{E}=\frac{0.1 (a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{2,\uparrow}a^{\dagger}\_{2,\downarrow})+0.2 (a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{3,\uparrow}a^{\dagger}\_{2,\downarrow})}{\sqrt{|0.1|^2+|0.2|^2}}\ket{0}, $$ where $\ket{E}$ has energy $0.987 \textrm{Ha}$, are represented by</span></span>
```yaml
initial_state_suggestions: # optional. If not provided, spin-orbitals will be filled to minimize one-body diagonal term energies.
  - label: "|G0>"
    method: sparse_multi_configurational
    superposition:
      - [1.0, "(1a)+","(2a)+","(2b)+","|vacuum>"]
  - label: "|G1>"
    method: sparse_multi_configurational
    superposition:
      - [-1.0, "(2a)+","(1a)+","(2b)+","|vacuum>"]
  - label: "|G2>"
    method: sparse_multi_configurational
    superposition:
      - [1.0, "(3a)","(1a)+","(2a)+","(3a)+","(2b)+","|vacuum>"]
  - label: "|E>"
    energy: {units: hartree, value: 0.987}
    method: sparse_multi_configurational
    superposition:
      - [0.1, "(1a)+","(2a)+","(2b)+","|vacuum>"]
      - [0.2, "(1a)+","(3a)+","(2b)+","|vacuum>"]
```

<span data-ttu-id="2bb03-211">`method` özelliğinin değeri `unitary_coupled_cluster`ise, durum nesnesinin değeri JSON nesnesi olan bir `cluster_operator` özelliğine sahip olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="2bb03-211">If the value of the `method` property is `unitary_coupled_cluster`, the state object MUST have a `cluster_operator` property whose value is a JSON object.</span></span>
<span data-ttu-id="2bb03-212">JSON nesnesi, değeri temel bir durum olan bir `reference_state` özelliğine sahip OLMALıDıR.</span><span class="sxs-lookup"><span data-stu-id="2bb03-212">The JSON object MUST have a `reference_state` property whose value is a basis state.</span></span>
<span data-ttu-id="2bb03-213">JSON nesnesi, değeri bir tek gövde kümesi işleçleri ve bunların yükseltilmiş tudes dizisi olan bir `one_body_amplitudes` özelliğine sahip olabılır.</span><span class="sxs-lookup"><span data-stu-id="2bb03-213">The JSON object MAY have a `one_body_amplitudes` property whose value is an array of one-body cluster operators and their amplitudes.</span></span>
<span data-ttu-id="2bb03-214">JSON nesnesi, değeri iki boyutlu küme işleçleri dizisi olan bir `two_body_amplitudes` özelliğine ve bunların yükseltilmiş tudes 'lerine sahip olabılır.</span><span class="sxs-lookup"><span data-stu-id="2bb03-214">The JSON object MAY have a `two_body_amplitudes` property whose value is an array of two-body cluster operators and their amplitudes.</span></span>
<span data-ttu-id="2bb03-215">temel durumlardan oluşan bir dizi ve bunların Normalleştirilmemiş yükseltilmiş tudes 'i içerir.</span><span class="sxs-lookup"><span data-stu-id="2bb03-215">containing an array of basis states and their unnormalized amplitudes.</span></span>

<span data-ttu-id="2bb03-216">Örneğin, $ $ \ket{\Text{Reference}} = (a ^ {\abger}\_{1, \upoklu}\_{| {\hanger} {2, \upbir ^ {\gesger}\_{2, \downbir}) \ket{0}, $ $</span><span class="sxs-lookup"><span data-stu-id="2bb03-216">For example, the state $$ \ket{\text{reference}}=(a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{2,\uparrow}a^{\dagger}\_{2,\downarrow})\ket{0}, $$</span></span>

<span data-ttu-id="2bb03-217">$ $ \ket{\text{UCCSD}} = e ^ {T-T ^ \dagger}\ket{\Text{Reference}}, $ $</span><span class="sxs-lookup"><span data-stu-id="2bb03-217">$$ \ket{\text{UCCSD}}=e^{T-T^\dagger}\ket{\text{reference}}, $$</span></span>

<span data-ttu-id="2bb03-218">$ $ T = 0,1 a ^ {\hanger}\_{3, \upok} a\_{2, \downok} + 0,2 a ^ {\abger}\_{2, \upok} a\_{2, \downok}-0,3 a ^ {\abger}\_{1, \upoklu} a ^ {\gesger}\_{3, \downoklu} a\_{3 , \upoklu} bir\_{2, \downoklu} $ $ tarafından temsil edilir</span><span class="sxs-lookup"><span data-stu-id="2bb03-218">$$ T = 0.1 a^{\dagger}\_{3,\uparrow}a\_{2,\downarrow} + 0.2 a^{\dagger}\_{2,\uparrow}a\_{2,\downarrow} - 0.3 a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{3,\downarrow}a\_{3,\uparrow}a\_{2,\downarrow} $$ is represented by</span></span>
```yaml
initial_state_suggestions: # optional. If not provided, spin-orbitals will be filled to minimize one-body diagonal term energies.
  - label: "UCCSD"
    method: unitary_coupled_cluster
    cluster_operator: # Initial state that cluster operator is applied to.
        reference_state: 
          [1.0, "(1a)+", "(2a)+", "(2b)+", '|vacuum>']
        one_body_amplitudes: # A one-body cluster term is t^{q}_{p} a^\dag_p a_q   
            - [0.1, "(3a)+", "(2b)"]
            - [-0.2, "(2a)+", "(2b)"]
        two_body_amplitudes: # A two-body unitary cluster term is t^{rs}_{pq} a^\dag_p a^\dag_q a_r a_s
            - [-0.3, "(1a)+", "(3b)+", "(3a)", "(2b)"]
```

#### <a name="basis-set-object"></a><span data-ttu-id="2bb03-219">Taban kümesi nesnesi</span><span class="sxs-lookup"><span data-stu-id="2bb03-219">Basis Set Object</span></span> ####

<span data-ttu-id="2bb03-220">Bu bölüm normatıve 'dir.</span><span class="sxs-lookup"><span data-stu-id="2bb03-220">This section is normative.</span></span>

<span data-ttu-id="2bb03-221">Her sorun açıklaması nesnesinin bir `basis_set` özelliği olabılır.</span><span class="sxs-lookup"><span data-stu-id="2bb03-221">Each problem description object MAY have a `basis_set` property.</span></span>
<span data-ttu-id="2bb03-222">Varsa, `basis_set` özelliğinin değeri, `type` ve `name`iki özelliği olan bir nesne olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="2bb03-222">If present, the value of the `basis_set` property MUST be an object with two properties, `type` and `name`.</span></span>

<span data-ttu-id="2bb03-223">`basis_set` özelliğinin değeri ile tanımlanan temel işlevler gerçek değerli olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="2bb03-223">The basis functions identified by the value of the `basis_set` property MUST be real-valued.</span></span>

> [!NOTE]
> <span data-ttu-id="2bb03-224">Tüm temel işlevlerin gerçek değerli olduğu varsayımını bu belirtimin gelecekteki sürümlerinde gevşek olabilir.</span><span class="sxs-lookup"><span data-stu-id="2bb03-224">The assumption that all basis functions are real-valued may be relaxed in future versions of this specification.</span></span>

## <a name="tables-and-lists"></a><span data-ttu-id="2bb03-225">Tablolar ve listeler</span><span class="sxs-lookup"><span data-stu-id="2bb03-225">Tables and Lists</span></span> ##

### <a name="table-1-allowed-physical-units"></a><span data-ttu-id="2bb03-226">Tablo 1.</span><span class="sxs-lookup"><span data-stu-id="2bb03-226">Table 1.</span></span> <span data-ttu-id="2bb03-227">İzin verilen fiziksel birimler</span><span class="sxs-lookup"><span data-stu-id="2bb03-227">Allowed Physical Units</span></span> ###

<span data-ttu-id="2bb03-228">Bu bölüm normatıve 'dir.</span><span class="sxs-lookup"><span data-stu-id="2bb03-228">This section is normative.</span></span>

<span data-ttu-id="2bb03-229">Bir birimi belirten herhangi bir dize aşağıdakilerden biri OLMALıDıR:</span><span class="sxs-lookup"><span data-stu-id="2bb03-229">Any string specifying a unit MUST be one of the following:</span></span>

- `hartree`
- `ev`

<span data-ttu-id="2bb03-230">Çözümleyiciler ve üreticileri, aşağıdaki basit miktar nesnelerini eşdeğer olarak kabul ETMELIDIR:</span><span class="sxs-lookup"><span data-stu-id="2bb03-230">Parsers and producers MUST treat the following simple quantity objects as equivalent:</span></span>

```yaml
- {"units": "hartree", "value": 1}
- {"units": "ev", "value": 27.2113831301723}
```

### <a name="table-2-allowed-index-conventions"></a><span data-ttu-id="2bb03-231">Tablo 2.</span><span class="sxs-lookup"><span data-stu-id="2bb03-231">Table 2.</span></span> <span data-ttu-id="2bb03-232">İzin verilen dizin kuralları</span><span class="sxs-lookup"><span data-stu-id="2bb03-232">Allowed Index Conventions</span></span> ###

<span data-ttu-id="2bb03-233">Bu bölüm normatıve 'dir.</span><span class="sxs-lookup"><span data-stu-id="2bb03-233">This section is normative.</span></span>

<span data-ttu-id="2bb03-234">Bir dizin kuralını belirten herhangi bir dize aşağıdakilerden biri OLMALıDıR:</span><span class="sxs-lookup"><span data-stu-id="2bb03-234">Any string specifying an index convention MUST be one of the following:</span></span>

- `mulliken`

<span data-ttu-id="2bb03-235">Bu bölüm bilgilendirme.</span><span class="sxs-lookup"><span data-stu-id="2bb03-235">This section is informative.</span></span>

<span data-ttu-id="2bb03-236">Ek dizin kuralları bu belirtimin gelecek sürümlerinde kullanıma sunulacak olabilir.</span><span class="sxs-lookup"><span data-stu-id="2bb03-236">Additional index conventions may be introduced in future versions of this specification.</span></span>

#### <a name="interpretation-of-index-conventions"></a><span data-ttu-id="2bb03-237">Dizin kurallarının yorumu</span><span class="sxs-lookup"><span data-stu-id="2bb03-237">Interpretation of Index Conventions</span></span> ####

<span data-ttu-id="2bb03-238">Bu bölüm bilgilendirme.</span><span class="sxs-lookup"><span data-stu-id="2bb03-238">This section is informative.</span></span>

### <a name="table-3-allowed-state-methods"></a><span data-ttu-id="2bb03-239">Tablo 3.</span><span class="sxs-lookup"><span data-stu-id="2bb03-239">Table 3.</span></span> <span data-ttu-id="2bb03-240">İzin verilen durum metotları</span><span class="sxs-lookup"><span data-stu-id="2bb03-240">Allowed State methods</span></span> ###

<span data-ttu-id="2bb03-241">Bu bölüm normatıve 'dir.</span><span class="sxs-lookup"><span data-stu-id="2bb03-241">This section is normative.</span></span>

<span data-ttu-id="2bb03-242">Bir durum yöntemini belirten herhangi bir dize aşağıdakilerden biri OLMALıDıR:</span><span class="sxs-lookup"><span data-stu-id="2bb03-242">Any string specifying a state method MUST be one of the following:</span></span>

- `sparse_multi_configurational`
- `unitary_coupled_cluster`

<span data-ttu-id="2bb03-243">Bu bölüm bilgilendirme.</span><span class="sxs-lookup"><span data-stu-id="2bb03-243">This section is informative.</span></span>

<span data-ttu-id="2bb03-244">Ek durum yöntemleri bu belirtimin gelecek sürümlerinde bulunabilir.</span><span class="sxs-lookup"><span data-stu-id="2bb03-244">Additional state methods may be introduced in future versions of this specification.</span></span>
