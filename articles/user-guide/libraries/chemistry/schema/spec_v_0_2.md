---
title: Broombridge şema belirtimi (ver 0,2)
description: Microsoft hisse dili Mistry kitaplığı için broombridge hisse Kimya şeması v
author: guanghaolow
ms.author: gulow@microsoft.com
ms.date: 05/28/2019
ms.topic: article
uid: microsoft.quantum.libraries.chemistry.schema.spec_v_0_2
ms.openlocfilehash: df7e651b7d32e672c6e83346ff603132bd55c1a2
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275861"
---
# <a name="broombridge-specification-v02"></a><span data-ttu-id="1bc73-103">Broombridge belirtimi v 0.2</span><span class="sxs-lookup"><span data-stu-id="1bc73-103">Broombridge Specification v0.2</span></span> #

<span data-ttu-id="1bc73-104">"", "" Gerekli değildir "," gerekli "," Bu "," zorunlu değildir "," durum ",", "ve" Isteğe bağlı "anahtar sözcükleri, [RFC 2119](https://tools.ietf.org/html/rfc2119)' de açıklandığı gibi yorumlanmalıdır.</span><span class="sxs-lookup"><span data-stu-id="1bc73-104">The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED",  "MAY", and "OPTIONAL" in this document are to be interpreted as described in [RFC 2119](https://tools.ietf.org/html/rfc2119).</span></span>

<span data-ttu-id="1bc73-105">"NOTE", "ıNFORMATION" veya "WARNING" başlıklı tüm kenar çubuğu bilgilendirici.</span><span class="sxs-lookup"><span data-stu-id="1bc73-105">Any sidebar with the headings "NOTE," "INFORMATION," or "WARNING" is informative.</span></span>

## <a name="introduction"></a><span data-ttu-id="1bc73-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="1bc73-106">Introduction</span></span> ##

<span data-ttu-id="1bc73-107">Bu bölüm bilgilendirme.</span><span class="sxs-lookup"><span data-stu-id="1bc73-107">This section is informative.</span></span>

<span data-ttu-id="1bc73-108">Broombridge belgelerinin, hisse simülasyonu ve programlama araç zincirlerini kullanarak, işleme için hisse deneçlerinde simülasyon sorunlarının örneklerine iletişim kurması amaçlanmıştır.</span><span class="sxs-lookup"><span data-stu-id="1bc73-108">Broombridge documents are intended to communicate instances of simulation problems in quantum chemistry for processing using quantum simulation and programming toolchains.</span></span>

## <a name="serialization"></a><span data-ttu-id="1bc73-109">Serileştirme</span><span class="sxs-lookup"><span data-stu-id="1bc73-109">Serialization</span></span> ##

<span data-ttu-id="1bc73-110">Bu bölüm normatıve 'dir.</span><span class="sxs-lookup"><span data-stu-id="1bc73-110">This section is normative.</span></span>

<span data-ttu-id="1bc73-111">Bir Broombridge belgesi 2,2 [4627](https://tools.ietf.org/html/rfc4627) , bir JSON nesnesini temsil eden bir [YAML 1,2 belgesi](http://yaml.org/spec/) olarak serileştirilmelidir.</span><span class="sxs-lookup"><span data-stu-id="1bc73-111">A Broombridge document MUST be serialized as a [YAML 1.2 document](http://yaml.org/spec/) representing a JSON object as described in [RFC 4627](https://tools.ietf.org/html/rfc4627) section 2.2.</span></span>
<span data-ttu-id="1bc73-112">YAML 'ye seri hale getirilen nesnenin değeri olan bir özelliği OLMALıDıR `"$schema"` `"https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/qchem-0.2.schema.json"` ve JSON şeması taslağına göre geçerli olmalıdır-06 belirtimleri [[1](https://tools.ietf.org/html/draft-wright-json-schema-01), [2](https://tools.ietf.org/html/draft-wright-json-schema-validation-01)].</span><span class="sxs-lookup"><span data-stu-id="1bc73-112">The object serialized to YAML MUST have a property `"$schema"` whose value is `"https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/qchem-0.2.schema.json"`, and MUST be valid according to the JSON Schema draft-06 specifications [[1](https://tools.ietf.org/html/draft-wright-json-schema-01), [2](https://tools.ietf.org/html/draft-wright-json-schema-validation-01)].</span></span>

<span data-ttu-id="1bc73-113">Bu belirtimin geri kalanı için, "Broombridge nesnesi", bir Brombridge YAML belgesinden Serisi kaldırılan JSON nesnesine başvuracaktır.</span><span class="sxs-lookup"><span data-stu-id="1bc73-113">For the remainder of this specification, "the Broombridge object" will refer to the JSON object deserialized from a Broombridge YAML document.</span></span>

<span data-ttu-id="1bc73-114">Aksi belirtilmedikçe, nesneler bu belgede açıkça belirtilenlerin ötesinde ek özelliklere sahip olmamalıdır.</span><span class="sxs-lookup"><span data-stu-id="1bc73-114">Unless otherwise explicitly noted, objects MUST NOT have additional properties beyond those specified explicitly in this document.</span></span>

## <a name="additional-definitions"></a><span data-ttu-id="1bc73-115">Ek tanımlar</span><span class="sxs-lookup"><span data-stu-id="1bc73-115">Additional Definitions</span></span> ##

<span data-ttu-id="1bc73-116">Bu bölüm normatıve 'dir.</span><span class="sxs-lookup"><span data-stu-id="1bc73-116">This section is normative.</span></span>

### <a name="quantity-objects"></a><span data-ttu-id="1bc73-117">Miktar nesneleri</span><span class="sxs-lookup"><span data-stu-id="1bc73-117">Quantity Objects</span></span> ###

<span data-ttu-id="1bc73-118">Bu bölüm normatıve 'dir.</span><span class="sxs-lookup"><span data-stu-id="1bc73-118">This section is normative.</span></span>

<span data-ttu-id="1bc73-119">Bir _Quantity_ NESNESI bir JSON nesnesidir ve `units` değeri tablo 1 ' de listelenen izin verilen değerlerden biri olan BIR özelliğine sahip olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="1bc73-119">A _quantity object_ is a JSON object, and MUST have a property `units` whose value is one of the allowed values listed in Table 1.</span></span>

<span data-ttu-id="1bc73-120">Bir Quantity nesnesi, özelliğine ek olarak tek bir özelliği varsa _basit bir Quantity nesnesidir_ `value` `units` .</span><span class="sxs-lookup"><span data-stu-id="1bc73-120">A quantity object is a _simple quantity object_ if it has a single property `value` in addition to its `units` property.</span></span>
<span data-ttu-id="1bc73-121">`value`Özelliğin değeri bir sayı olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="1bc73-121">The value of the `value` property MUST be a number.</span></span>

<span data-ttu-id="1bc73-122">Bir Quantity nesnesi, özelliklerine ve özelliğine ek olarak, _sınırlanmış bir Quantity nesnesidir_ `lower` `upper` `units` .</span><span class="sxs-lookup"><span data-stu-id="1bc73-122">A quantity object is a _bounded quantity object_ if it has the properties `lower` and `upper` in addition to its `units` property.</span></span>
<span data-ttu-id="1bc73-123">`lower`Ve özelliklerinin değerleri sayı olmalıdır `upper` .</span><span class="sxs-lookup"><span data-stu-id="1bc73-123">The values of the `lower` and `upper` properties MUST be numbers.</span></span>
<span data-ttu-id="1bc73-124">Sınırlanmış bir miktar nesnesi değeri sayı olan bir özelliğe sahip olabılır `value` .</span><span class="sxs-lookup"><span data-stu-id="1bc73-124">A bounded quantity object MAY have a property `value` whose value is a number.</span></span>

<span data-ttu-id="1bc73-125">Bir Quantity nesnesi, özelliği ve özelliğine ek olarak özelliği varsa _seyrek dizi miktar nesnesidir_ `format` `values` `units` .</span><span class="sxs-lookup"><span data-stu-id="1bc73-125">A quantity object is a _sparse array quantity object_ if it has the property `format` and a property `values` in addition to its `units` property.</span></span>
<span data-ttu-id="1bc73-126">Değeri dize olmalıdır `format` `sparse` .</span><span class="sxs-lookup"><span data-stu-id="1bc73-126">The value of `format` MUST be the string `sparse`.</span></span>
<span data-ttu-id="1bc73-127">`values`Özelliğin değeri bir dızı olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="1bc73-127">The value of the `values` property MUST be an array.</span></span>
<span data-ttu-id="1bc73-128">Her öğesi, `values` seyrek dizi miktarının dizinlerini ve değerini temsil eden bir dizi olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="1bc73-128">Each element of `values` MUST be an array representing the indices and value of the sparse array quantity.</span></span>

<span data-ttu-id="1bc73-129">Seyrek dizi miktarı nesnesinin her bir öğesi için dizinler, tüm seyrek dizi miktarı nesnesi genelinde benzersiz OLMALıDıR.</span><span class="sxs-lookup"><span data-stu-id="1bc73-129">The indices for each element of a sparse array quantity object MUST be unique across the entire sparse array quantity object.</span></span>
<span data-ttu-id="1bc73-130">Bir dizin bir değeri ile mevcutsa `0` , bir Ayrıştırıcı seyrek dizi Quantity nesnesini aynı dizinde bulunmayan bir seyrek dizi Quantity nesnesine aynı şekilde işlemelidir.</span><span class="sxs-lookup"><span data-stu-id="1bc73-130">If an index is present with a value of `0`, a parser MUST treat the sparse array quantity object identically to a sparse array quantity object in which that index is not present at all.</span></span>


<span data-ttu-id="1bc73-131">Bir Quantity nesnesi olmalıdır</span><span class="sxs-lookup"><span data-stu-id="1bc73-131">A quantity object MUST either be</span></span>

- <span data-ttu-id="1bc73-132">basit bir miktar nesnesi,</span><span class="sxs-lookup"><span data-stu-id="1bc73-132">a simple quantity object,</span></span>
- <span data-ttu-id="1bc73-133">sınırlanmış bir miktar nesnesi veya</span><span class="sxs-lookup"><span data-stu-id="1bc73-133">a bounded quantity object, or</span></span>
- <span data-ttu-id="1bc73-134">seyrek dizi miktarı nesnesi.</span><span class="sxs-lookup"><span data-stu-id="1bc73-134">a sparse array quantity object.</span></span>


### <a name="examples"></a><span data-ttu-id="1bc73-135">Örnekler</span><span class="sxs-lookup"><span data-stu-id="1bc73-135">Examples</span></span> ###

<span data-ttu-id="1bc73-136">Bu bölüm bilgilendirme.</span><span class="sxs-lookup"><span data-stu-id="1bc73-136">This section is informative.</span></span>

<span data-ttu-id="1bc73-137">$1.9844146837 \Mathrm{ha} $ öğesini temsil eden basit bir miktar \, :</span><span class="sxs-lookup"><span data-stu-id="1bc73-137">A simple quantity representing $1.9844146837\,\mathrm{Ha}$:</span></span>

```yaml
coulomb_repulsion:
    value: 1.9844146837
    units: hartree
```

<span data-ttu-id="1bc73-138">$ [-7,-6] \Mathrm{ha} $ aralığında tek bir dağılımı temsil eden sınırlanmış bir miktar \, .</span><span class="sxs-lookup"><span data-stu-id="1bc73-138">A bounded quantity representing a uniform distribution over the interval $[-7, -6]\,\mathrm{Ha}$:</span></span>

```yaml
fci_energy:
    upper: -6
    lower: -7
    units: hartree
```

<span data-ttu-id="1bc73-139">Aşağıda öğesine `[1, 2]` eşit öğe `hello` ve `[3, 4]` Şuna eşit bir öğe olan seyrek dizi miktarı verilmiştir `world` :</span><span class="sxs-lookup"><span data-stu-id="1bc73-139">The following is a sparse array quantity with an element `[1, 2]` equal to `hello` and an element `[3, 4]` equal to `world`:</span></span>

```yaml
sparse_example:
    format: sparse
    units: hartree
    values:
    - [1, 2, "hello"]
    - [3, 4, "world"]
```

## <a name="format-section"></a><span data-ttu-id="1bc73-140">Biçim bölümü</span><span class="sxs-lookup"><span data-stu-id="1bc73-140">Format Section</span></span> ##

<span data-ttu-id="1bc73-141">Bu bölüm normatıve 'dir.</span><span class="sxs-lookup"><span data-stu-id="1bc73-141">This section is normative.</span></span>

<span data-ttu-id="1bc73-142">Broombridge nesnesi, `format` değeri bir bir özelliği olan JSON nesnesi olan bir özelliğe sahıp olmalıdır `version` .</span><span class="sxs-lookup"><span data-stu-id="1bc73-142">The Broombridge object MUST have a property `format` whose value is a JSON object with one property called `version`.</span></span>
<span data-ttu-id="1bc73-143">`version`Özelliğin değeri olmalıdır `"0.2"` .</span><span class="sxs-lookup"><span data-stu-id="1bc73-143">The `version` property MUST have the value `"0.2"`.</span></span>

### <a name="example"></a><span data-ttu-id="1bc73-144">Örnek</span><span class="sxs-lookup"><span data-stu-id="1bc73-144">Example</span></span> ###

<span data-ttu-id="1bc73-145">Bu bölüm bilgilendirme.</span><span class="sxs-lookup"><span data-stu-id="1bc73-145">This section is informative.</span></span>

```yaml
format:                        # required
    version: "0.2"             # must match exactly
```

## <a name="problem-description-section"></a><span data-ttu-id="1bc73-146">Sorun açıklaması bölümü</span><span class="sxs-lookup"><span data-stu-id="1bc73-146">Problem Description Section</span></span> ##

<span data-ttu-id="1bc73-147">Bu bölüm normatıve 'dir.</span><span class="sxs-lookup"><span data-stu-id="1bc73-147">This section is normative.</span></span>

<span data-ttu-id="1bc73-148">Broombridge nesnesi, `problem_description` değeri BIR JSON dizisi olan bir özelliğe sahıp olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="1bc73-148">The Broombridge object MUST have a property `problem_description` whose value is a JSON array.</span></span>
<span data-ttu-id="1bc73-149">Özelliğin değerindeki her öğe, `problem_description` Bu bölümün geri kalanında açıklandığı gibi bir integralleri kümesini açıklayan BIR JSON nesnesi olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="1bc73-149">Each item in the value of the `problem_description` property MUST be a JSON object describing one set of integrals, as described in the remainder of this section.</span></span>
<span data-ttu-id="1bc73-150">Bu bölümün geri kalanında, "sorun açıklaması nesnesi" terimi, `problem_description` Broombridge nesnesinin özelliğinin değerindeki bir öğeye başvuracaktır.</span><span class="sxs-lookup"><span data-stu-id="1bc73-150">In the remainder of this section, the term "problem description object" will refer to an item in the value of the `problem_description` property of the Broombridge object.</span></span>

<span data-ttu-id="1bc73-151">Her sorun açıklaması nesnesinin `metadata` değeri BIR JSON nesnesi olan bir ÖZELLIĞI olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="1bc73-151">Each problem description object MUST have a property `metadata` whose value is a JSON object.</span></span>
<span data-ttu-id="1bc73-152">Değeri `metadata` boş JSON nesnesi (yani `{}` ) olabilir veya uygulayıcısı tarafından tanımlanan ek özellikleri içerebilir.</span><span class="sxs-lookup"><span data-stu-id="1bc73-152">The value of `metadata` MAY be the empty JSON object (that is, `{}`), or MAY contain additional properties defined by the implementor.</span></span>

### <a name="hamiltonian-section"></a><span data-ttu-id="1bc73-153">Hamiltonian bölümü</span><span class="sxs-lookup"><span data-stu-id="1bc73-153">Hamiltonian Section</span></span> ###

#### <a name="overview"></a><span data-ttu-id="1bc73-154">Genel Bakış</span><span class="sxs-lookup"><span data-stu-id="1bc73-154">Overview</span></span> ####

<span data-ttu-id="1bc73-155">Bu bölüm bilgilendirme.</span><span class="sxs-lookup"><span data-stu-id="1bc73-155">This section is informative.</span></span>

<span data-ttu-id="1bc73-156">`hamiltonian`Her bir sorun açıklama nesnesinin özelliği, belirli bir hisse dili yanılma sorunu Için Hamiltonian 'yi, tek ve iki gövdedeki terimleri gerçek sayıların seyrek dizileri olarak listeleyerek açıklar.</span><span class="sxs-lookup"><span data-stu-id="1bc73-156">The `hamiltonian` property of each problem description object describes the Hamiltonian for a particular quantum chemistry problem by listing out its one- and two-body terms as sparse arrays of real numbers.</span></span>
<span data-ttu-id="1bc73-157">Her sorun açıklaması nesnesi tarafından tanımlanan Hamiltonian işleçleri formu alır</span><span class="sxs-lookup"><span data-stu-id="1bc73-157">The Hamiltonian operators described by each problem description object take the form</span></span>

<span data-ttu-id="1bc73-158">$ $ H = \sum \_ \{ i, j \} \ Sum \_ {\sigma\in \\ {\upok, \downok \\ }} H \_ \{ ij \} a ^ \{ \gesger \} \_ {i, \sigma} a \_ {j, \sigma} + \frac {1} {2} \sum \_ \{ i, j, k, l \} \ Sum \_ {\sigma, \rho\in \\ {\upok, \downok \\ }} H \_ {ijkl} a ^ \gesger \_ {i, \sigma} a ^ \dağılım \_ {k, \rho} a \_ {l, \rho} a \_ {j, \sigma}, $ $</span><span class="sxs-lookup"><span data-stu-id="1bc73-158">$$ H = \sum\_\{i,j\}\sum\_{\sigma\in\\{\uparrow,\downarrow\\}} h\_\{ij\} a^\{\dagger\}\_{i,\sigma} a\_{j,\sigma} + \frac{1}{2}\sum\_\{i,j,k,l\}\sum\_{\sigma,\rho\in\\{\uparrow,\downarrow\\}} h\_{ijkl} a^\dagger\_{i,\sigma} a^\dagger\_{k,\rho} a\_{l,\rho} a\_{j,\sigma}, $$</span></span>

<span data-ttu-id="1bc73-159">Burada _ {ijkl} = (ij | KL) $ Mullikliksiz kuralına göre $h.</span><span class="sxs-lookup"><span data-stu-id="1bc73-159">here $h_{ijkl}= (ij|kl)$ in Mulliken convention.</span></span>

<span data-ttu-id="1bc73-160">Netlik açısından, tek bir elektron dönemi</span><span class="sxs-lookup"><span data-stu-id="1bc73-160">For clarity, the one-electron term is</span></span>

<span data-ttu-id="1bc73-161">$ $ h_ {ij} = \int {\mathrm d} x \psi ^ \* \_ ı (x) \left (\frac {1} {2} \nabla ^ 2 + \ Sum \_ {A} \frac{Z \_ A} {| x-x \_ A |}  \ sağ) \psı \_ j (x), $ $</span><span class="sxs-lookup"><span data-stu-id="1bc73-161">$$ h_{ij} = \int {\mathrm d}x \psi^\*\_i(x) \left(\frac{1}{2}\nabla^2 + \sum\_{A}\frac{Z\_A}{|x-x\_A|}  \right) \psi\_j(x), $$</span></span>

<span data-ttu-id="1bc73-162">ve iki elektron terimi</span><span class="sxs-lookup"><span data-stu-id="1bc73-162">and the two-electron term is</span></span>

<span data-ttu-id="1bc73-163">$ $ h \_ \{ ijkl \} = \iınt \{ \mathrm d \} x ^ 2 \psi ^ \{ \* \} \_ i (x \_ 1) \psı \_ j (x \_ 1) \frac \{ 1 \} \{ \| x \_ 1-x \_ 2 \| \} \ PSI \_ k ^ \{ \* \} (x \_ 2) \psı \_ l (x \_ 2).</span><span class="sxs-lookup"><span data-stu-id="1bc73-163">$$ h\_\{ijkl\} = \iint \{\mathrm d\}x^2 \psi^\{\*\}\_i(x\_1)\psi\_j(x\_1) \frac\{1\}\{\|x\_1 -x\_2\|\}\psi\_k^\{\*\}(x\_2) \psi\_l(x\_2).</span></span>
$$

<span data-ttu-id="1bc73-164">Özelliğin her bir öğesinin [ `basis_set` özelliğinin](#basis-set-object) açıklamamız bölümünde belirtildiği gibi `integral_sets` , kullanılan temel işlevlerin gerçek değerli olduğunu açıkça varsaydık.</span><span class="sxs-lookup"><span data-stu-id="1bc73-164">As noted in our description of the [`basis_set` property](#basis-set-object) of each element of the `integral_sets` property, we further explicitly assume that the basis functions used are real-valued.</span></span>
<span data-ttu-id="1bc73-165">Bu, Hamiltonian 'ın gösterimini sıkıştırmak için terimler arasında aşağıdaki symmetries kullanmamızı sağlar.</span><span class="sxs-lookup"><span data-stu-id="1bc73-165">This allows us to use the following symmetries between the terms to compress the representation of the Hamiltonian.</span></span>

<span data-ttu-id="1bc73-166">$ $ h_ {ijkl} = h_ {ijlk} = h_ {JIKL} = h_ {jılb} = h_ {klij} = h_ {klji} = h_ {lkij} = h_ {lkji}.</span><span class="sxs-lookup"><span data-stu-id="1bc73-166">$$ h_{ijkl} = h_{ijlk}=h_{jikl}=h_{jilk}=h_{klij}=h_{klji}=h_{lkij}=h_{lkji}.</span></span>
$$


#### <a name="contents"></a><span data-ttu-id="1bc73-167">İçindekiler</span><span class="sxs-lookup"><span data-stu-id="1bc73-167">Contents</span></span> ####

<span data-ttu-id="1bc73-168">Bu bölüm normatıve 'dir.</span><span class="sxs-lookup"><span data-stu-id="1bc73-168">This section is normative.</span></span>

<span data-ttu-id="1bc73-169">Her sorun açıklaması nesnesinin `hamiltonian` değeri BIR JSON nesnesi olan bir ÖZELLIĞI olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="1bc73-169">Each problem description object MUST have a property `hamiltonian` whose value is a JSON object.</span></span>
<span data-ttu-id="1bc73-170">`hamiltonian`Özelliğin değeri Hamiltonian nesnesi olarak bilinir ve `one_electron_integrals` `two_electron_integrals` Bu bölümün geri kalanında açıklanan özelliklere ve özelliklerine sahip olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="1bc73-170">The value of the `hamiltonian` property is known as a Hamiltonian object, and MUST have the properties `one_electron_integrals` and `two_electron_integrals` as described in the remainder of this section.</span></span>

<span data-ttu-id="1bc73-171">Her sorun açıklaması nesnesinin `coulomb_repulsion` değeri bir basit Quantity nesnesi olan bir ÖZELLIĞI olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="1bc73-171">Each problem description object MUST have a property `coulomb_repulsion` whose value is a simple quantity object.</span></span>
<span data-ttu-id="1bc73-172">Her sorun açıklaması nesnesinin `energy_offet` değeri bir basit Quantity nesnesi olan bir ÖZELLIĞI olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="1bc73-172">Each problem description object MUST have a property `energy_offet` whose value is a simple quantity object.</span></span>
> <span data-ttu-id="1bc73-173">NOTUN `coulomb_repulsion`Ve `energy_offet` birlikte eklenen değerler, Hamiltonian 'nin kimlik terimini yakalar.</span><span class="sxs-lookup"><span data-stu-id="1bc73-173">[NOTE] The values of `coulomb_repulsion` and `energy_offet` added together capture the identity term of the Hamiltonian.</span></span>

##### <a name="one-electron-integrals-object"></a><span data-ttu-id="1bc73-174">Tek bir elektron Integrals nesnesi</span><span class="sxs-lookup"><span data-stu-id="1bc73-174">One-Electron Integrals Object</span></span> #####

<span data-ttu-id="1bc73-175">Bu bölüm normatıve 'dir.</span><span class="sxs-lookup"><span data-stu-id="1bc73-175">This section is normative.</span></span>

<span data-ttu-id="1bc73-176">`one_electron_integrals`Hamiltonian nesnesinin özelliği, dizinleri iki tamsayı olan ve değerleri sayı olan bir seyrek dizi miktarı olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="1bc73-176">The `one_electron_integrals` property of the Hamiltonian object MUST be a sparse array quantity whose indices are two integers and whose values are numbers.</span></span>
<span data-ttu-id="1bc73-177">Her dönemde dizinler bulunmalıdır `[i, j]` `i >= j` .</span><span class="sxs-lookup"><span data-stu-id="1bc73-177">Every term MUST have indices `[i, j]` where `i >= j`.</span></span>

> <span data-ttu-id="1bc73-178">NOTUN Bu, Hamiltonian 'ın hermitian olduğu olgunun bir sonucu olan $h _ {ij} = h_ {Ji} $ olan simetriyi yansıtır.</span><span class="sxs-lookup"><span data-stu-id="1bc73-178">[NOTE] This reflects the symmetry that $h_{ij} = h_{ji}$ which is a consequence of the fact that the Hamiltonian is Hermitian.</span></span>


###### <a name="example"></a><span data-ttu-id="1bc73-179">Örnek</span><span class="sxs-lookup"><span data-stu-id="1bc73-179">Example</span></span> ######

<span data-ttu-id="1bc73-180">Bu bölüm bilgilendirme.</span><span class="sxs-lookup"><span data-stu-id="1bc73-180">This section is informative.</span></span>

<span data-ttu-id="1bc73-181">Şu seyrek dizi miktarı Hamiltonian $ $ H = \left (-5,0 (a ^ \{ \dağılım {1) temsil eder. \} \_ \upoklu} a \_ {1, \upoklu} + bir ^ \{ \dağılım \} \_ {1, \downok} a \_ {1, \downoklu}) + 0,17 (bir ^ \{ \dağılım \} \_ {2, \upoklu} a \_ {1, \upoklu} + bir ^ \{ \dağılım \} \_ {1, \upoklu} a \_ {2, \upoklu} + bir ^ \{ \dağılım \} \_ {2, \downok} a \_ {1, \downok} + bir ^ \{ \dağılım \} \_ {1, \downok} a \_ {2, \downok}) \right) \\ , \mathrm{ha}.</span><span class="sxs-lookup"><span data-stu-id="1bc73-181">The following sparse array quantity represents the Hamiltonian $$ H = \left(-5.0  (a^\{\dagger\}\_{1,\uparrow} a\_{1,\uparrow}+a^\{\dagger\}\_{1,\downarrow} a\_{1,\downarrow})+ 0.17 (a^\{\dagger\}\_{2,\uparrow} a\_{1,\uparrow}+ a^\{\dagger\}\_{1,\uparrow} a\_{2,\uparrow}+a^\{\dagger\}\_{2,\downarrow} a\_{1,\downarrow}+ a^\{\dagger\}\_{1,\downarrow} a\_{2,\downarrow})\right)\\,\mathrm{Ha}.</span></span>
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
> <span data-ttu-id="1bc73-182">Broombridge, 1 tabanlı dizin oluşturma kullanır.</span><span class="sxs-lookup"><span data-stu-id="1bc73-182">Broombridge uses 1-based indexing.</span></span>


##### <a name="two-electron-integrals-object"></a><span data-ttu-id="1bc73-183">İki elektron Integrals nesnesi</span><span class="sxs-lookup"><span data-stu-id="1bc73-183">Two-Electron Integrals Object</span></span> #####

<span data-ttu-id="1bc73-184">Bu bölüm normatıve 'dir.</span><span class="sxs-lookup"><span data-stu-id="1bc73-184">This section is normative.</span></span>

<span data-ttu-id="1bc73-185">`two_electron_integrals`Hamiltonian nesnesinin özelliği, adlı bir ek özelliğe sahip bir seyrek dizi miktarı olmalıdır `index_convention` .</span><span class="sxs-lookup"><span data-stu-id="1bc73-185">The `two_electron_integrals` property of the Hamiltonian object MUST be a sparse array quantity with one additional property called `index_convention`.</span></span>
<span data-ttu-id="1bc73-186">Değerinin her öğesinin `two_electron_integrals` dört dizini olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="1bc73-186">Each element of the value of `two_electron_integrals` MUST have four indices.</span></span>

<span data-ttu-id="1bc73-187">Her `two_electron_integrals` özelliğin bir ÖZELLIĞI olmalıdır `index_convention` .</span><span class="sxs-lookup"><span data-stu-id="1bc73-187">Each `two_electron_integrals` property MUST have a `index_convention` property.</span></span>
<span data-ttu-id="1bc73-188">Özelliğin değeri, `index_convention` Tablo 1 ' de listelenen izin verilen değerlerden bırı olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="1bc73-188">The value of the `index_convention` property MUST be one of the allowed values listed in Table 1.</span></span>
<span data-ttu-id="1bc73-189">Değeri `index_convention` ise `mulliken` , seyrek dizi miktarının her bir öğesi için, `two_electron_integrals` bir Broombridge belgesi yükleyen bir Ayrıştırıcı, iki elektron Işleci olan bir Hamiltonian terimi oluşturmalıdır $h _ {i, j, k, l} a ^ \ dagger_i bir ^ \ dagger_j a_k a_l $, burada $i $, $j $, $k $ ve $l $ değeri en az 1 tamsayı olmalıdır ve $h _ {i, j, k, l} $, `[i, j, k, l, h(i, j, k, l)]` seyrek dizi miktarının öğesidir.</span><span class="sxs-lookup"><span data-stu-id="1bc73-189">If the value of `index_convention` is `mulliken`, then for each element of the `two_electron_integrals` sparse array quantity, a parser loading a Broombridge document MUST instantiate a Hamiltonian term equal to the two-electron operator $h_{i, j, k, l} a^\dagger_i a^\dagger_j a_k a_l$, where $i$, $j$, $k$, and $l$ MUST be integers of value at least 1, and where $h_{i, j, k, l}$ is the element `[i, j, k, l, h(i, j, k, l)]` of the sparse array quantity.</span></span>

###### <a name="symmetries"></a><span data-ttu-id="1bc73-190">Symmetries</span><span class="sxs-lookup"><span data-stu-id="1bc73-190">Symmetries</span></span> ######

<span data-ttu-id="1bc73-191">Bu bölüm normatıve 'dir.</span><span class="sxs-lookup"><span data-stu-id="1bc73-191">This section is normative.</span></span>

<span data-ttu-id="1bc73-192">`index_convention`Bir `two_electron_integrals` nesnenin özelliği öğesine eşitse `mulliken` , dizinler içeren bir öğe varsa, `[i, j, k, l]` Şuna eşit olmadıkları takdirde aşağıdaki dizinler mevcut olmamalıdır `[i, j, k, l]` :</span><span class="sxs-lookup"><span data-stu-id="1bc73-192">If the `index_convention` property of a `two_electron_integrals` object is equal to `mulliken`, then if an element with indices `[i, j, k, l]` is present, the following indices MUST NOT be present unless they are equal to `[i, j, k, l]`:</span></span>

- `[i, j, l, k]`
- `[j, i, k, l]`
- `[j, i, l, k]`
- `[k, l, i, j]`
- `[k, l, j, i]`
- `[l, k, j, i]`

> [!NOTE]
> <span data-ttu-id="1bc73-193">`index_convention`Özelliği seyrek bir Quantity nesnesi olduğundan, farklı öğelerde hiçbir dizin tekrarlanmayabilir.</span><span class="sxs-lookup"><span data-stu-id="1bc73-193">Because the `index_convention` property is a sparse quantity object, no indices may be repeated on different elements.</span></span>
> <span data-ttu-id="1bc73-194">Özellikle, dizinler içeren bir öğe varsa `[i, j, k, l]` , başka bir öğe bu dizinleri içeremez.</span><span class="sxs-lookup"><span data-stu-id="1bc73-194">In particular, if an element with indices `[i, j, k, l]` is present, no other element may have those indices.</span></span>


<!-- h_{ijkl} = h_{ijlk}=h_{jikl}=h_{jilk}=h_{klij}=h_{klji}=h_{lkji}. -->

###### <a name="example"></a><span data-ttu-id="1bc73-195">Örnek</span><span class="sxs-lookup"><span data-stu-id="1bc73-195">Example</span></span> #######

<span data-ttu-id="1bc73-196">Bu bölüm bilgilendirme.</span><span class="sxs-lookup"><span data-stu-id="1bc73-196">This section is informative.</span></span>

<span data-ttu-id="1bc73-197">Aşağıdaki nesne Hamiltonian 'yi belirtir</span><span class="sxs-lookup"><span data-stu-id="1bc73-197">The following object specifies the Hamiltonian</span></span>

<span data-ttu-id="1bc73-198">$$ H = \frac12 \sum \_ {\sigma,\rho\in \\ {\uparrow,\downarrow \\ }}\Biggr( 1.6 a^{\dagger} \_ {1,\sigma} a^{\dagger} \_ {1,\rho} a \_ {1,\rho} a \_ {1,\sigma}- 0.1 a^{\dagger} \_ {6,\sigma} a^{\dagger} \_ {1,\rho} a \_ {3,\rho} a \_ {2,\sigma}- 0.1 a^{\dagger} \_ {6,\sigma} a^{\dagger} \_ {1,\rho} a \_ {2,\rho} a \_ {3,\sigma}- 0.1 a^{\dagger} \_ {1,\sigma} a^{\dagger} \_ {6,\rho} a \_ {3,\rho} a \_ {2,\sigma}- 0.1 a^{\dagger} \_ {1,\sigma} a^{\dagger} \_ {6,\rho} a \_ {2,\rho} a \_ {3,\sigma} $$ $$- 0.1 a^{\dagger} \_ {3,\sigma} a^{\dagger} \_ {2,\rho} a \_ {6,\rho} a \_ {1,\sigma}- 0.1 a^{\dagger} \_ {3,\sigma} a^{\dagger} \_ {2,\rho} a \_ {1,\rho} a \_ {6,\sigma}- 0.1 a^{\dagger} \_ {2,\sigma} a^{\dagger} \_ {3 , \rho} a \_ {6, \rho} a \_ {1, \sigma}-0,1 a ^ {\abger} \_ {2, \sigma} a ^ {\dağılım} \_ {3, \rho} a \_ {1, \Rho} a \_ {6, \Sigma}\Biggr) \\ , \Textrm{ha}.</span><span class="sxs-lookup"><span data-stu-id="1bc73-198">$$ H = \frac12 \sum\_{\sigma,\rho\in\\{\uparrow,\downarrow\\}}\Biggr( 1.6 a^{\dagger}\_{1,\sigma} a^{\dagger}\_{1,\rho} a\_{1,\rho} a\_{1,\sigma}- 0.1 a^{\dagger}\_{6,\sigma} a^{\dagger}\_{1,\rho} a\_{3,\rho} a\_{2,\sigma}- 0.1 a^{\dagger}\_{6,\sigma} a^{\dagger}\_{1,\rho} a\_{2,\rho} a\_{3,\sigma}- 0.1 a^{\dagger}\_{1,\sigma} a^{\dagger}\_{6,\rho} a\_{3,\rho} a\_{2,\sigma}- 0.1 a^{\dagger}\_{1,\sigma} a^{\dagger}\_{6,\rho} a\_{2,\rho} a\_{3,\sigma} $$ $$- 0.1 a^{\dagger}\_{3,\sigma} a^{\dagger}\_{2,\rho} a\_{6,\rho} a\_{1,\sigma}- 0.1 a^{\dagger}\_{3,\sigma} a^{\dagger}\_{2,\rho} a\_{1,\rho} a\_{6,\sigma}- 0.1 a^{\dagger}\_{2,\sigma} a^{\dagger}\_{3,\rho} a\_{6,\rho} a\_{1,\sigma}- 0.1 a^{\dagger}\_{2,\sigma} a^{\dagger}\_{3,\rho} a\_{1,\rho} a\_{6,\sigma}\Biggr)\\,\textrm{Ha}.</span></span>
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

### <a name="initial-state-section"></a><span data-ttu-id="1bc73-199">İlk durum bölümü</span><span class="sxs-lookup"><span data-stu-id="1bc73-199">Initial State Section</span></span> ###

<span data-ttu-id="1bc73-200">Bu bölüm normatıve 'dir.</span><span class="sxs-lookup"><span data-stu-id="1bc73-200">This section is normative.</span></span>

<span data-ttu-id="1bc73-201">`initial_state_suggestion`Değeri BIR JSON dizisi olan nesne, belirtilen Hamiltonian ile ilgilenilen ilk hisse kazanç durumlarını belirtir.</span><span class="sxs-lookup"><span data-stu-id="1bc73-201">The `initial_state_suggestion` object whose value is a JSON array specifies initial quantum states of interest to the specified Hamiltonian.</span></span> <span data-ttu-id="1bc73-202">Özelliğin değerindeki her öğe, `initial_state_suggestion` Bu bölümün geri kalanında açıklandığı gibi, tek bir hisse durumu tanımlayan BIR JSON nesnesi olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="1bc73-202">Each item in the value of the `initial_state_suggestion` property MUST be a JSON object describing one quantum state, as described in the remainder of this section.</span></span>
<span data-ttu-id="1bc73-203">Bu bölümün geri kalanında, "durum nesnesi" terimi, `initial_state_suggestion` Broombridge nesnesinin özelliğinin değerindeki bir öğeye başvuracaktır.</span><span class="sxs-lookup"><span data-stu-id="1bc73-203">In the remainder of this section, the term "state object" will refer to an item in the value of the `initial_state_suggestion` property of the Broombridge object.</span></span>

#### <a name="state-object"></a><span data-ttu-id="1bc73-204">Durum nesnesi</span><span class="sxs-lookup"><span data-stu-id="1bc73-204">State object</span></span> ####

<span data-ttu-id="1bc73-205">Bu bölüm normatıve 'dir.</span><span class="sxs-lookup"><span data-stu-id="1bc73-205">This section is normative.</span></span>

<span data-ttu-id="1bc73-206">Her durum nesnesinin bir `label` dize içeren bir ÖZELLIĞI olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="1bc73-206">Each state object MUST have a `label` property containing a string.</span></span> <span data-ttu-id="1bc73-207">Her durum nesnesinin bir özelliği OLMALıDıR `method` .</span><span class="sxs-lookup"><span data-stu-id="1bc73-207">Each state object MUST have a `method` property.</span></span> <span data-ttu-id="1bc73-208">Özelliğin değeri, `method` Tablo 3 ' te listelenen izin verilen değerlerden bırı olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="1bc73-208">The value of the `method` property MUST be one of the allowed values listed in Table 3.</span></span>
<span data-ttu-id="1bc73-209">Her durum nesnesinin `energy` değeri bir basit miktar nesnesi olması gereken bir ÖZELLIĞI olabilir.</span><span class="sxs-lookup"><span data-stu-id="1bc73-209">Each state object MAY have a property `energy` whose value MUST be a simple quantity object.</span></span>

<span data-ttu-id="1bc73-210">`method`Özelliğin değeri ise `sparse_multi_configurational` , durum nesnesinin bir `superposition` temel durumlar dizisi ve Normalleştirilmemiş yükseltilmiş Tular içeren BIR özelliği olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="1bc73-210">If the value of the `method` property is `sparse_multi_configurational`, the state object MUST have a `superposition` property containing an array of basis states and their unnormalized amplitudes.</span></span>

<span data-ttu-id="1bc73-211">Örneğin, ilk durumlar $ $ \ket{G0} = \ket{G1} = \ket{G2} = (a ^ {\gger} \_ {1, \upoklu} a ^ {\gger} \_ {2, \uphh} a ^ {\abger} \_ {2, \downok}) \ket {0} $ $ $ $ \Ket{e} = \frac{0.exe 1 (a ^ {\dağılım} { \_ 1, \upnı}a ^ {\gesger} { \_ 2, \upoklu}a ^ {\abger} {2, \_ \downok}) + 0.2 (a ^ {\gesger} \_ {1, \upoklu} a ^ {\dağılım} { \_ 3, \upoklu} a ^ {\dağılım} \_ {2, \downoklu})} {\sqrt{| 0.1 | ^ 2 + | 0.2 | ^ 2}} \Ayraç {0} , $ $ burada $ \Ket{e} $ enerji $0,987 \textrm{ha} $ tarafından temsil edilir</span><span class="sxs-lookup"><span data-stu-id="1bc73-211">For example, the initial states $$ \ket{G0}=\ket{G1}=\ket{G2}=(a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{2,\uparrow}a^{\dagger}\_{2,\downarrow})\ket{0} $$ $$ \ket{E}=\frac{0.1 (a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{2,\uparrow}a^{\dagger}\_{2,\downarrow})+0.2 (a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{3,\uparrow}a^{\dagger}\_{2,\downarrow})}{\sqrt{|0.1|^2+|0.2|^2}}\ket{0}, $$ where $\ket{E}$ has energy $0.987 \textrm{Ha}$, are represented by</span></span>
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

<span data-ttu-id="1bc73-212">`method`Özelliğin değeri ise `unitary_coupled_cluster` , durum NESNESININ `cluster_operator` değeri JSON nesnesi olan bir özelliğine sahip olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="1bc73-212">If the value of the `method` property is `unitary_coupled_cluster`, the state object MUST have a `cluster_operator` property whose value is a JSON object.</span></span>
<span data-ttu-id="1bc73-213">JSON nesnesi `reference_state` değeri temel bir durum olan bir özelliğe sahıp olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="1bc73-213">The JSON object MUST have a `reference_state` property whose value is a basis state.</span></span>
<span data-ttu-id="1bc73-214">JSON nesnesi, `one_body_amplitudes` değeri bir tek gövde kümesi işleçleri ve bunların yükseltilmiş tudes dizisi olan bir özelliğe sahıp olabilir.</span><span class="sxs-lookup"><span data-stu-id="1bc73-214">The JSON object MAY have a `one_body_amplitudes` property whose value is an array of one-body cluster operators and their amplitudes.</span></span>
<span data-ttu-id="1bc73-215">JSON nesnesi, `two_body_amplitudes` değeri iki boyutlu küme işleçleri dizisi olan bir özelliğe ve bunların yükseltilmiş tudes 'lerine sahıp olabilir.</span><span class="sxs-lookup"><span data-stu-id="1bc73-215">The JSON object MAY have a `two_body_amplitudes` property whose value is an array of two-body cluster operators and their amplitudes.</span></span>
<span data-ttu-id="1bc73-216">temel durumlardan oluşan bir dizi ve bunların Normalleştirilmemiş yükseltilmiş tudes 'i içerir.</span><span class="sxs-lookup"><span data-stu-id="1bc73-216">containing an array of basis states and their unnormalized amplitudes.</span></span>

<span data-ttu-id="1bc73-217">Örneğin, $ $ \ket{\Text{Reference}} = (a ^ {\dağılım} \_ {1, \upoklu} a ^ {\gesger} { \_ 2, \upoklu} bir ^ {\dağılım} \_ {2, \downok}) \tus, {0} $ $</span><span class="sxs-lookup"><span data-stu-id="1bc73-217">For example, the state $$ \ket{\text{reference}}=(a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{2,\uparrow}a^{\dagger}\_{2,\downarrow})\ket{0}, $$</span></span>

<span data-ttu-id="1bc73-218">$ $ \ket{\text{UCCSD}} = e ^ {T-T ^ \dagger}\ket{\Text{Reference}}, $ $</span><span class="sxs-lookup"><span data-stu-id="1bc73-218">$$ \ket{\text{UCCSD}}=e^{T-T^\dagger}\ket{\text{reference}}, $$</span></span>

<span data-ttu-id="1bc73-219">$ $ T = 0,1 a ^ {\gesger} \_ {3, \upoklu}a \_ {2, \downoklu} + 0,2 a ^ {\gesger} \_ {2, \upoklu}a \_ {2, \downok}-0,3 a ^ {\abger} \_ {1, \upoklu}a ^ {\gesger} \_ {3, \downoklu}a \_ {3, \upoklu \_ } $ $ tarafından temsil edilir</span><span class="sxs-lookup"><span data-stu-id="1bc73-219">$$ T = 0.1 a^{\dagger}\_{3,\uparrow}a\_{2,\downarrow} + 0.2 a^{\dagger}\_{2,\uparrow}a\_{2,\downarrow} - 0.3 a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{3,\downarrow}a\_{3,\uparrow}a\_{2,\downarrow} $$ is represented by</span></span>
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

#### <a name="basis-set-object"></a><span data-ttu-id="1bc73-220">Taban kümesi nesnesi</span><span class="sxs-lookup"><span data-stu-id="1bc73-220">Basis Set Object</span></span> ####

<span data-ttu-id="1bc73-221">Bu bölüm normatıve 'dir.</span><span class="sxs-lookup"><span data-stu-id="1bc73-221">This section is normative.</span></span>

<span data-ttu-id="1bc73-222">Her sorun açıklaması nesnesinin bir özelliği olabılır `basis_set` .</span><span class="sxs-lookup"><span data-stu-id="1bc73-222">Each problem description object MAY have a `basis_set` property.</span></span>
<span data-ttu-id="1bc73-223">Varsa, `basis_set` özelliğinin değeri iki özelliklerine sahip bir nesne olmalıdır `type` ve `name` .</span><span class="sxs-lookup"><span data-stu-id="1bc73-223">If present, the value of the `basis_set` property MUST be an object with two properties, `type` and `name`.</span></span>

<span data-ttu-id="1bc73-224">Özelliğin değeri ile tanımlanan temel işlevler `basis_set` gerçek değerli olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="1bc73-224">The basis functions identified by the value of the `basis_set` property MUST be real-valued.</span></span>

> [!NOTE]
> <span data-ttu-id="1bc73-225">Tüm temel işlevlerin gerçek değerli olduğu varsayımını bu belirtimin gelecekteki sürümlerinde gevşek olabilir.</span><span class="sxs-lookup"><span data-stu-id="1bc73-225">The assumption that all basis functions are real-valued may be relaxed in future versions of this specification.</span></span>

## <a name="tables-and-lists"></a><span data-ttu-id="1bc73-226">Tablolar ve listeler</span><span class="sxs-lookup"><span data-stu-id="1bc73-226">Tables and Lists</span></span> ##

### <a name="table-1-allowed-physical-units"></a><span data-ttu-id="1bc73-227">Tablo 1.</span><span class="sxs-lookup"><span data-stu-id="1bc73-227">Table 1.</span></span> <span data-ttu-id="1bc73-228">İzin verilen fiziksel birimler</span><span class="sxs-lookup"><span data-stu-id="1bc73-228">Allowed Physical Units</span></span> ###

<span data-ttu-id="1bc73-229">Bu bölüm normatıve 'dir.</span><span class="sxs-lookup"><span data-stu-id="1bc73-229">This section is normative.</span></span>

<span data-ttu-id="1bc73-230">Bir birimi belirten herhangi bir dize aşağıdakilerden biri OLMALıDıR:</span><span class="sxs-lookup"><span data-stu-id="1bc73-230">Any string specifying a unit MUST be one of the following:</span></span>

- `hartree`
- `ev`

<span data-ttu-id="1bc73-231">Çözümleyiciler ve üreticileri, aşağıdaki basit miktar nesnelerini eşdeğer olarak kabul ETMELIDIR:</span><span class="sxs-lookup"><span data-stu-id="1bc73-231">Parsers and producers MUST treat the following simple quantity objects as equivalent:</span></span>

```yaml
- {"units": "hartree", "value": 1}
- {"units": "ev", "value": 27.2113831301723}
```

### <a name="table-2-allowed-index-conventions"></a><span data-ttu-id="1bc73-232">Tablo 2.</span><span class="sxs-lookup"><span data-stu-id="1bc73-232">Table 2.</span></span> <span data-ttu-id="1bc73-233">İzin verilen dizin kuralları</span><span class="sxs-lookup"><span data-stu-id="1bc73-233">Allowed Index Conventions</span></span> ###

<span data-ttu-id="1bc73-234">Bu bölüm normatıve 'dir.</span><span class="sxs-lookup"><span data-stu-id="1bc73-234">This section is normative.</span></span>

<span data-ttu-id="1bc73-235">Bir dizin kuralını belirten herhangi bir dize aşağıdakilerden biri OLMALıDıR:</span><span class="sxs-lookup"><span data-stu-id="1bc73-235">Any string specifying an index convention MUST be one of the following:</span></span>

- `mulliken`

<span data-ttu-id="1bc73-236">Bu bölüm bilgilendirme.</span><span class="sxs-lookup"><span data-stu-id="1bc73-236">This section is informative.</span></span>

<span data-ttu-id="1bc73-237">Ek dizin kuralları bu belirtimin gelecek sürümlerinde kullanıma sunulacak olabilir.</span><span class="sxs-lookup"><span data-stu-id="1bc73-237">Additional index conventions may be introduced in future versions of this specification.</span></span>

#### <a name="interpretation-of-index-conventions"></a><span data-ttu-id="1bc73-238">Dizin kurallarının yorumu</span><span class="sxs-lookup"><span data-stu-id="1bc73-238">Interpretation of Index Conventions</span></span> ####

<span data-ttu-id="1bc73-239">Bu bölüm bilgilendirme.</span><span class="sxs-lookup"><span data-stu-id="1bc73-239">This section is informative.</span></span>

### <a name="table-3-allowed-state-methods"></a><span data-ttu-id="1bc73-240">Tablo 3.</span><span class="sxs-lookup"><span data-stu-id="1bc73-240">Table 3.</span></span> <span data-ttu-id="1bc73-241">İzin verilen durum metotları</span><span class="sxs-lookup"><span data-stu-id="1bc73-241">Allowed State methods</span></span> ###

<span data-ttu-id="1bc73-242">Bu bölüm normatıve 'dir.</span><span class="sxs-lookup"><span data-stu-id="1bc73-242">This section is normative.</span></span>

<span data-ttu-id="1bc73-243">Bir durum yöntemini belirten herhangi bir dize aşağıdakilerden biri OLMALıDıR:</span><span class="sxs-lookup"><span data-stu-id="1bc73-243">Any string specifying a state method MUST be one of the following:</span></span>

- `sparse_multi_configurational`
- `unitary_coupled_cluster`

<span data-ttu-id="1bc73-244">Bu bölüm bilgilendirme.</span><span class="sxs-lookup"><span data-stu-id="1bc73-244">This section is informative.</span></span>

<span data-ttu-id="1bc73-245">Ek durum yöntemleri bu belirtimin gelecek sürümlerinde bulunabilir.</span><span class="sxs-lookup"><span data-stu-id="1bc73-245">Additional state methods may be introduced in future versions of this specification.</span></span>
