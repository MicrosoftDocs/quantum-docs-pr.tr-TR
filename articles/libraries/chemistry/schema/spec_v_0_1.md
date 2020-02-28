---
title: Broombridge şema belirtimi (ver 0,1)
description: Microsoft hisse dili Mistry kitaplığı için Broombridge hisse
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/17/2018
ms.topic: article
uid: microsoft.quantum.libraries.chemistry.schema.spec_v_0_1
ms.openlocfilehash: 618892b6cb01855d17522b06e47f72f68595ab38
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/28/2020
ms.locfileid: "77906432"
---
# <a name="broombridge-specification-v01"></a><span data-ttu-id="91470-103">Broombridge belirtimi v 0.1</span><span class="sxs-lookup"><span data-stu-id="91470-103">Broombridge Specification v0.1</span></span> #

<span data-ttu-id="91470-104">"", "" Gerekli değildir "," gerekli "," Bu "," zorunlu değildir "," durum ",", "ve" Isteğe bağlı "anahtar sözcükleri, [RFC 2119](https://tools.ietf.org/html/rfc2119)' de açıklandığı gibi yorumlanmalıdır.</span><span class="sxs-lookup"><span data-stu-id="91470-104">The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED",  "MAY", and "OPTIONAL" in this document are to be interpreted as described in [RFC 2119](https://tools.ietf.org/html/rfc2119).</span></span>

<span data-ttu-id="91470-105">"NOTE", "ıNFORMATION" veya "WARNING" başlıklı tüm kenar çubuğu bilgilendirici.</span><span class="sxs-lookup"><span data-stu-id="91470-105">Any sidebar with the headings "NOTE," "INFORMATION," or "WARNING" is informative.</span></span>

## <a name="introduction"></a><span data-ttu-id="91470-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="91470-106">Introduction</span></span> ##

<span data-ttu-id="91470-107">Bu bölüm bilgilendirme.</span><span class="sxs-lookup"><span data-stu-id="91470-107">This section is informative.</span></span>

<span data-ttu-id="91470-108">Broombridge belgelerinin, hisse simülasyonu ve programlama araç zincirlerini kullanarak, işleme için hisse deneçlerinde simülasyon sorunlarının örneklerine iletişim kurması amaçlanmıştır.</span><span class="sxs-lookup"><span data-stu-id="91470-108">Broombridge documents are intended to communicate instances of simulation problems in quantum chemistry for processing using quantum simulation and programming toolchains.</span></span>

## <a name="serialization"></a><span data-ttu-id="91470-109">Getir</span><span class="sxs-lookup"><span data-stu-id="91470-109">Serialization</span></span> ##

<span data-ttu-id="91470-110">Bu bölüm normatıve 'dir.</span><span class="sxs-lookup"><span data-stu-id="91470-110">This section is normative.</span></span>

<span data-ttu-id="91470-111">Bir Broombridge belgesi 2,2 [4627](https://tools.ietf.org/html/rfc4627) , bir JSON nesnesini temsil eden bir [YAML 1,2 belgesi](http://yaml.org/spec/) olarak serileştirilmelidir.</span><span class="sxs-lookup"><span data-stu-id="91470-111">A Broombridge document MUST be serialized as a [YAML 1.2 document](http://yaml.org/spec/) representing a JSON object as described in [RFC 4627](https://tools.ietf.org/html/rfc4627) section 2.2.</span></span>
<span data-ttu-id="91470-112">YAML 'ye seri hale getirilen nesne, değeri `"https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/qchem-0.1.schema.json"`olan bir özellik `"$schema"` sahip OLMALıDıR ve JSON şeması taslağına göre geçerli olmalıdır-06 belirtimleri [[1](https://tools.ietf.org/html/draft-wright-json-schema-01), [2](https://tools.ietf.org/html/draft-wright-json-schema-validation-01)].</span><span class="sxs-lookup"><span data-stu-id="91470-112">The object serialized to YAML MUST have a property `"$schema"` whose value is `"https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/qchem-0.1.schema.json"`, and MUST be valid according to the JSON Schema draft-06 specifications [[1](https://tools.ietf.org/html/draft-wright-json-schema-01), [2](https://tools.ietf.org/html/draft-wright-json-schema-validation-01)].</span></span>

<span data-ttu-id="91470-113">Bu belirtimin geri kalanı için, "Broombridge nesnesi", bir Brombridge YAML belgesinden Serisi kaldırılan JSON nesnesine başvuracaktır.</span><span class="sxs-lookup"><span data-stu-id="91470-113">For the remainder of this specification, "the Broombridge object" will refer to the JSON object deserialized from a Broombridge YAML document.</span></span>

<span data-ttu-id="91470-114">Aksi belirtilmedikçe, nesneler bu belgede açıkça belirtilenlerin ötesinde ek özelliklere sahip olmamalıdır.</span><span class="sxs-lookup"><span data-stu-id="91470-114">Unless otherwise explicitly noted, objects MUST NOT have additional properties beyond those specified explicitly in this document.</span></span>

## <a name="additional-definitions"></a><span data-ttu-id="91470-115">Ek tanımlar</span><span class="sxs-lookup"><span data-stu-id="91470-115">Additional Definitions</span></span> ##

<span data-ttu-id="91470-116">Bu bölüm normatıve 'dir.</span><span class="sxs-lookup"><span data-stu-id="91470-116">This section is normative.</span></span>

### <a name="quantity-objects"></a><span data-ttu-id="91470-117">Miktar nesneleri</span><span class="sxs-lookup"><span data-stu-id="91470-117">Quantity Objects</span></span> ###

<span data-ttu-id="91470-118">Bu bölüm normatıve 'dir.</span><span class="sxs-lookup"><span data-stu-id="91470-118">This section is normative.</span></span>

<span data-ttu-id="91470-119">Bir _Quantity_ NESNESI bir JSON nesnesidir ve değeri tablo 1 ' de listelenen izin verilen değerlerden biri olan bir özellik `units` sahip olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="91470-119">A _quantity object_ is a JSON object, and MUST have a property `units` whose value is one of the allowed values listed in Table 1.</span></span>

<span data-ttu-id="91470-120">Bir Quantity nesnesi, `units` özelliğine ek olarak `value` tek bir özelliğe sahipse _basit bir Quantity nesnesidir_ .</span><span class="sxs-lookup"><span data-stu-id="91470-120">A quantity object is a _simple quantity object_ if it has a single property `value` in addition to its `units` property.</span></span>
<span data-ttu-id="91470-121">`value` özelliğinin değeri bir sayı olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="91470-121">The value of the `value` property MUST be a number.</span></span>

<span data-ttu-id="91470-122">Bir Quantity nesnesi, `lower` özellikler varsa ve `units` özelliğine ek olarak `upper` _sınırlanmış bir miktar nesnesidir_ .</span><span class="sxs-lookup"><span data-stu-id="91470-122">A quantity object is a _bounded quantity object_ if it has the properties `lower` and `upper` in addition to its `units` property.</span></span>
<span data-ttu-id="91470-123">`lower` ve `upper` özelliklerinin değerleri sayı olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="91470-123">The values of the `lower` and `upper` properties MUST be numbers.</span></span>
<span data-ttu-id="91470-124">Sınırlanmış bir miktar nesnesi değeri sayı olan bir özellik `value` olabılır.</span><span class="sxs-lookup"><span data-stu-id="91470-124">A bounded quantity object MAY have a property `value` whose value is a number.</span></span>

<span data-ttu-id="91470-125">Bir Quantity nesnesi, özelliğin `format` ve bir özelliğin `units` özelliğine ek olarak `values` varsa _seyrek dizi miktarı nesnesidir_ .</span><span class="sxs-lookup"><span data-stu-id="91470-125">A quantity object is a _sparse array quantity object_ if it has the property `format` and a property `values` in addition to its `units` property.</span></span>
<span data-ttu-id="91470-126">`format` değeri `sparse`dize OLMALıDıR.</span><span class="sxs-lookup"><span data-stu-id="91470-126">The value of `format` MUST be the string `sparse`.</span></span>
<span data-ttu-id="91470-127">`values` özelliğinin değeri bir dizi OLMALıDıR.</span><span class="sxs-lookup"><span data-stu-id="91470-127">The value of the `values` property MUST be an array.</span></span>
<span data-ttu-id="91470-128">Her `values` öğesi, seyrek dizi miktarının indekslerini ve değerini temsil eden bir dizi OLMALıDıR.</span><span class="sxs-lookup"><span data-stu-id="91470-128">Each element of `values` MUST be an array representing the indices and value of the sparse array quantity.</span></span>

<span data-ttu-id="91470-129">Seyrek dizi miktarı nesnesinin her bir öğesi için dizinler, tüm seyrek dizi miktarı nesnesi genelinde benzersiz OLMALıDıR.</span><span class="sxs-lookup"><span data-stu-id="91470-129">The indices for each element of a sparse array quantity object MUST be unique across the entire sparse array quantity object.</span></span>
<span data-ttu-id="91470-130">Bir dizin `0`bir değeri varsa, bir Ayrıştırıcı seyrek dizi Quantity nesnesini aynı dizinde yer alan bir seyrek dizi Quantity nesnesi ile aynı şekilde ele ALMALıDıR.</span><span class="sxs-lookup"><span data-stu-id="91470-130">If an index is present with a value of `0`, a parser MUST treat the sparse array quantity object identically to a sparse array quantity object in which that index is not present at all.</span></span>


<span data-ttu-id="91470-131">Bir Quantity nesnesi olmalıdır</span><span class="sxs-lookup"><span data-stu-id="91470-131">A quantity object MUST either be</span></span>

- <span data-ttu-id="91470-132">basit bir miktar nesnesi,</span><span class="sxs-lookup"><span data-stu-id="91470-132">a simple quantity object,</span></span>
- <span data-ttu-id="91470-133">sınırlanmış bir miktar nesnesi veya</span><span class="sxs-lookup"><span data-stu-id="91470-133">a bounded quantity object, or</span></span>
- <span data-ttu-id="91470-134">seyrek dizi miktarı nesnesi.</span><span class="sxs-lookup"><span data-stu-id="91470-134">a sparse array quantity object.</span></span>


### <a name="examples"></a><span data-ttu-id="91470-135">Örnekler</span><span class="sxs-lookup"><span data-stu-id="91470-135">Examples</span></span> ###

<span data-ttu-id="91470-136">Bu bölüm bilgilendirme.</span><span class="sxs-lookup"><span data-stu-id="91470-136">This section is informative.</span></span>

<span data-ttu-id="91470-137">$1.9844146837\,\mathrm{Ha} $ öğesini temsil eden basit bir miktar:</span><span class="sxs-lookup"><span data-stu-id="91470-137">A simple quantity representing $1.9844146837\,\mathrm{Ha}$:</span></span>

```yaml
coulomb_repulsion:
    value: 1.9844146837
    units: hartree
```

<span data-ttu-id="91470-138">$ [-7,-6]\,\mathrm{Ha} $ aralığında tek bir dağılımı temsil eden sınırlanmış bir miktar.</span><span class="sxs-lookup"><span data-stu-id="91470-138">A bounded quantity representing a uniform distribution over the interval $[-7, -6]\,\mathrm{Ha}$:</span></span>

```yaml
fci_energy:
    upper: -6
    lower: -7
    units: hartree
```

<span data-ttu-id="91470-139">Aşağıda, bir öğesi `hello` eşit `[1, 2]` ve bir öğe `world``[3, 4]` eşit olan seyrek dizi miktarı verilmiştir:</span><span class="sxs-lookup"><span data-stu-id="91470-139">The following is a sparse array quantity with an element `[1, 2]` equal to `hello` and an element `[3, 4]` equal to `world`:</span></span>

```yaml
sparse_example:
    format: sparse
    units: hartree
    values:
    - [1, 2, "hello"]
    - [3, 4, "world"]
```

## <a name="format-section"></a><span data-ttu-id="91470-140">Biçim bölümü</span><span class="sxs-lookup"><span data-stu-id="91470-140">Format Section</span></span> ##

<span data-ttu-id="91470-141">Bu bölüm normatıve 'dir.</span><span class="sxs-lookup"><span data-stu-id="91470-141">This section is normative.</span></span>

<span data-ttu-id="91470-142">Broombridge nesnesi, değeri `version`adlı bir özellik olan JSON nesnesi olan bir özellik `format` sahip OLMALıDıR.</span><span class="sxs-lookup"><span data-stu-id="91470-142">The Broombridge object MUST have a property `format` whose value is a JSON object with one property called `version`.</span></span>
<span data-ttu-id="91470-143">`version` özelliği `"0.1"`değerine sahip OLMALıDıR.</span><span class="sxs-lookup"><span data-stu-id="91470-143">The `version` property MUST have the value `"0.1"`.</span></span>

### <a name="example"></a><span data-ttu-id="91470-144">Örnek</span><span class="sxs-lookup"><span data-stu-id="91470-144">Example</span></span> ###

<span data-ttu-id="91470-145">Bu bölüm bilgilendirme.</span><span class="sxs-lookup"><span data-stu-id="91470-145">This section is informative.</span></span>

```yaml
format:                        # required
    version: "0.1"             # must match exactly
```

## <a name="integral-sets-section"></a><span data-ttu-id="91470-146">Integral kümeleri bölümü</span><span class="sxs-lookup"><span data-stu-id="91470-146">Integral Sets Section</span></span> ##

<span data-ttu-id="91470-147">Bu bölüm normatıve 'dir.</span><span class="sxs-lookup"><span data-stu-id="91470-147">This section is normative.</span></span>

<span data-ttu-id="91470-148">Broombridge nesnesi değeri bir JSON dizisi olan bir özellik `integral_sets` sahip OLMALıDıR.</span><span class="sxs-lookup"><span data-stu-id="91470-148">The Broombridge object MUST have a property `integral_sets` whose value is a JSON array.</span></span>
<span data-ttu-id="91470-149">`integral_sets` özelliğinin değerindeki her öğe, bu bölümün geri kalanında açıklandığı gibi bir integralleri kümesini açıklayan bir JSON nesnesi olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="91470-149">Each item in the value of the `integral_sets` property MUST be a JSON object describing one set of integrals, as described in the remainder of this section.</span></span>
<span data-ttu-id="91470-150">Bu bölümün geri kalanında, "integral kümesi nesnesi" terimi, Broombridge nesnesinin `integral_sets` özelliğinin değerindeki bir öğeye başvuracaktır.</span><span class="sxs-lookup"><span data-stu-id="91470-150">In the remainder of this section, the term "integral set object" will refer to an item in the value of the `integral_sets` property of the Broombridge object.</span></span>

<span data-ttu-id="91470-151">Her integral kümesi nesnesi değeri JSON nesnesi olan bir özellik `metadata` sahip OLMALıDıR.</span><span class="sxs-lookup"><span data-stu-id="91470-151">Each integral set object MUST have a property `metadata` whose value is a JSON object.</span></span>
<span data-ttu-id="91470-152">`metadata` değeri boş JSON nesnesi (yani, `{}`) olabilir veya uygulayıcısı tarafından tanımlanan ek özellikleri içerebilir.</span><span class="sxs-lookup"><span data-stu-id="91470-152">The value of `metadata` MAY be the empty JSON object (that is, `{}`), or MAY contain additional properties defined by the implementor.</span></span>

### <a name="hamiltonian-section"></a><span data-ttu-id="91470-153">Hamiltonian bölümü</span><span class="sxs-lookup"><span data-stu-id="91470-153">Hamiltonian Section</span></span> ###

#### <a name="overview"></a><span data-ttu-id="91470-154">Genel Bakış</span><span class="sxs-lookup"><span data-stu-id="91470-154">Overview</span></span> ####

<span data-ttu-id="91470-155">Bu bölüm bilgilendirme.</span><span class="sxs-lookup"><span data-stu-id="91470-155">This section is informative.</span></span>

<span data-ttu-id="91470-156">Her bir integral kümesi nesnesinin `hamiltonian` özelliği, belirli bir hisse dili hatası için Hamiltonian 'yi, tek ve iki gövdedeki terimleri gerçek sayıların seyrek dizileri olarak listeleyerek tanımlar.</span><span class="sxs-lookup"><span data-stu-id="91470-156">The `hamiltonian` property of each integral set object describes the Hamiltonian for a particular quantum chemistry problem by listing out its one- and two-body terms as sparse arrays of real numbers.</span></span>
<span data-ttu-id="91470-157">Her bir integral kümesi nesnesi tarafından tanımlanan Hamiltonian işleçleri formu alır</span><span class="sxs-lookup"><span data-stu-id="91470-157">The Hamiltonian operators described by each integral set object take the form</span></span>

<span data-ttu-id="91470-158">$ $ H = \sum\_\{ı, j\}\sum\_{\sigma\in\\{\upok, \downok\\}} H\_\{ij\} a ^\{\dağılım\}\_{i, \sigma} a\_{j, \sigma} + \frac{1}{2}\sum\_\{i, j, k, l\}\sum\_{\sigma, \rho\in\\{\upok, \downok\\}} H\_{ı , \sigma} a ^ \dağılım\_{k, \rho} a\_{l, \rho} a\_{j, \sigma}, $ $\_</span><span class="sxs-lookup"><span data-stu-id="91470-158">$$ H = \sum\_\{i,j\}\sum\_{\sigma\in\\{\uparrow,\downarrow\\}} h\_\{ij\} a^\{\dagger\}\_{i,\sigma} a\_{j,\sigma} + \frac{1}{2}\sum\_\{i,j,k,l\}\sum\_{\sigma,\rho\in\\{\uparrow,\downarrow\\}} h\_{ijkl} a^\dagger\_{i,\sigma} a^\dagger\_{k,\rho} a\_{l,\rho} a\_{j,\sigma}, $$</span></span>

<span data-ttu-id="91470-159">Burada _ {ijkl} = (ij | KL) $ Mullikliksiz kuralına göre $h.</span><span class="sxs-lookup"><span data-stu-id="91470-159">here $h_{ijkl}= (ij|kl)$ in Mulliken convention.</span></span>

<span data-ttu-id="91470-160">Netlik açısından, tek bir elektron dönemi</span><span class="sxs-lookup"><span data-stu-id="91470-160">For clarity, the one-electron term is</span></span>

<span data-ttu-id="91470-161">$ $ h_ {ij} = \int {\mathrm d} x \psi ^ \*\_ı (x) \left (\frac{1}{2}\nabla ^ 2 + \ Sum\_{A} \frac{Z\_A} {| x-x\_A |}  \right) \psi\_j (x), $ $</span><span class="sxs-lookup"><span data-stu-id="91470-161">$$ h_{ij} = \int {\mathrm d}x \psi^\*\_i(x) \left(\frac{1}{2}\nabla^2 + \sum\_{A}\frac{Z\_A}{|x-x\_A|}  \right) \psi\_j(x), $$</span></span>

<span data-ttu-id="91470-162">ve iki elektron terimi</span><span class="sxs-lookup"><span data-stu-id="91470-162">and the two-electron term is</span></span>

<span data-ttu-id="91470-163">$ $ h\_\{ijkl\} = \iint \{\mathrm d\}x ^ 2 \psı ^\{\*\}\_ı (x\_1) \psi\_j (x\_1) \frac\{1\}\{\|x\_1-x\_2\|\}\psi\_k ^\{\*\}(x\_2) \psı\_l (x\_2).</span><span class="sxs-lookup"><span data-stu-id="91470-163">$$ h\_\{ijkl\} = \iint \{\mathrm d\}x^2 \psi^\{\*\}\_i(x\_1)\psi\_j(x\_1) \frac\{1\}\{\|x\_1 -x\_2\|\}\psi\_k^\{\*\}(x\_2) \psi\_l(x\_2).</span></span>
$$

<span data-ttu-id="91470-164">`integral_sets` özelliğinin her bir öğesinin [`basis_set` özelliğinin](#basis-set-object) açıklamamız bölümünde belirtildiği gibi, kullanılan temel işlevlerin gerçek değerli olduğunu açıkça varsaydık.</span><span class="sxs-lookup"><span data-stu-id="91470-164">As noted in our description of the [`basis_set` property](#basis-set-object) of each element of the `integral_sets` property, we further explicitly assume that the basis functions used are real-valued.</span></span>
<span data-ttu-id="91470-165">Bu, Hamiltonian 'ın gösterimini sıkıştırmak için terimler arasında aşağıdaki symmetries kullanmamızı sağlar.</span><span class="sxs-lookup"><span data-stu-id="91470-165">This allows us to use the following symmetries between the terms to compress the representation of the Hamiltonian.</span></span>

<span data-ttu-id="91470-166">$ $ h_ {ijkl} = h_ {ijlk} = h_ {JIKL} = h_ {jılb} = h_ {klij} = h_ {klji} = h_ {lkij} = h_ {lkji}.</span><span class="sxs-lookup"><span data-stu-id="91470-166">$$ h_{ijkl} = h_{ijlk}=h_{jikl}=h_{jilk}=h_{klij}=h_{klji}=h_{lkij}=h_{lkji}.</span></span>
$$


#### <a name="contents"></a><span data-ttu-id="91470-167">İçindekiler</span><span class="sxs-lookup"><span data-stu-id="91470-167">Contents</span></span> ####

<span data-ttu-id="91470-168">Bu bölüm normatıve 'dir.</span><span class="sxs-lookup"><span data-stu-id="91470-168">This section is normative.</span></span>

<span data-ttu-id="91470-169">Her integral kümesi değeri bir JSON nesnesi olan bir özellik `hamiltonian` sahip OLMALıDıR.</span><span class="sxs-lookup"><span data-stu-id="91470-169">Each integral set MUST have a property `hamiltonian` whose value is a JSON object.</span></span>
<span data-ttu-id="91470-170">`hamiltonian` özelliğinin değeri Hamiltonian nesnesi olarak bilinir ve bu bölümün geri kalanında açıklanan şekilde Özellikler `one_electron_integrals` ve `two_electron_integrals` OLMALıDıR.</span><span class="sxs-lookup"><span data-stu-id="91470-170">The value of the `hamiltonian` property is known as a Hamiltonian object, and MUST have the properties `one_electron_integrals` and `two_electron_integrals` as described in the remainder of this section.</span></span>
<span data-ttu-id="91470-171">Hamiltonian nesnesinin Ayrıca bir özelliği `particle_hole_representation`olabılır.</span><span class="sxs-lookup"><span data-stu-id="91470-171">A Hamiltonian object MAY also have a property `particle_hole_representation`.</span></span>
<span data-ttu-id="91470-172">Varsa, `particle_hole_representation` değeri bu bölümün geri kalanında açıklanan biçimi izlemelidir.</span><span class="sxs-lookup"><span data-stu-id="91470-172">If present, the value of `particle_hole_representation` MUST follow the format described in the remainder of this section.</span></span>

##### <a name="one-electron-integrals-object"></a><span data-ttu-id="91470-173">Tek bir elektron Integrals nesnesi</span><span class="sxs-lookup"><span data-stu-id="91470-173">One-Electron Integrals Object</span></span> #####

<span data-ttu-id="91470-174">Bu bölüm normatıve 'dir.</span><span class="sxs-lookup"><span data-stu-id="91470-174">This section is normative.</span></span>

<span data-ttu-id="91470-175">Hamiltonian nesnesinin `one_electron_integrals` özelliği, dizinleri iki tamsayı olan ve değerleri sayı olan bir seyrek dizi miktarı olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="91470-175">The `one_electron_integrals` property of the Hamiltonian object MUST be a sparse array quantity whose indices are two integers and whose values are numbers.</span></span>
<span data-ttu-id="91470-176">Her dönemde `i >= j``[i, j]` dizinler OLMALıDıR.</span><span class="sxs-lookup"><span data-stu-id="91470-176">Every term MUST have indices `[i, j]` where `i >= j`.</span></span>

> <span data-ttu-id="91470-177">NOTUN Bu, Hamiltonian 'ın hermitian olduğu olgunun bir sonucu olan $h _ {ij} = h_ {Ji} $ olan simetriyi yansıtır.</span><span class="sxs-lookup"><span data-stu-id="91470-177">[NOTE] This reflects the symmetry that $h_{ij} = h_{ji}$ which is a consequence of the fact that the Hamiltonian is Hermitian.</span></span>


###### <a name="example"></a><span data-ttu-id="91470-178">Örnek</span><span class="sxs-lookup"><span data-stu-id="91470-178">Example</span></span> ######

<span data-ttu-id="91470-179">Bu bölüm bilgilendirme.</span><span class="sxs-lookup"><span data-stu-id="91470-179">This section is informative.</span></span>

<span data-ttu-id="91470-180">Şu seyrek dizi miktarı Hamiltonian $ $ H = \left (-5,0 (bir ^\{\dağılım\}\_{1, \upoklu} bir\_{1, \upoklu} + bir ^\{\dağılım\}\_{1, \downok} a\_{1, \downok}) + 0,17 (bir ^\{\hanger\}\_{2, \upoklu} +\_{1, \upoklu} + bir ^\{\dağılım\}\_{1, \upoklu} +\_{2, \upoklu} + a ^\{\dağılım\}\_{2 , \downok} bir\_{1, \downok} + bir ^\{\dağılım\}\_{1, \down\mathrm{ha}.} a\_{2, \downok}) \right)\\,</span><span class="sxs-lookup"><span data-stu-id="91470-180">The following sparse array quantity represents the Hamiltonian $$ H = \left(-5.0  (a^\{\dagger\}\_{1,\uparrow} a\_{1,\uparrow}+a^\{\dagger\}\_{1,\downarrow} a\_{1,\downarrow})+ 0.17 (a^\{\dagger\}\_{2,\uparrow} a\_{1,\uparrow}+ a^\{\dagger\}\_{1,\uparrow} a\_{2,\uparrow}+a^\{\dagger\}\_{2,\downarrow} a\_{1,\downarrow}+ a^\{\dagger\}\_{1,\downarrow} a\_{2,\downarrow})\right)\\,\mathrm{Ha}.</span></span>
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
> <span data-ttu-id="91470-181">Broombridge, 1 tabanlı dizin oluşturma kullanır.</span><span class="sxs-lookup"><span data-stu-id="91470-181">Broombridge uses 1-based indexing.</span></span>


##### <a name="two-electron-integrals-object"></a><span data-ttu-id="91470-182">İki elektron Integrals nesnesi</span><span class="sxs-lookup"><span data-stu-id="91470-182">Two-Electron Integrals Object</span></span> #####

<span data-ttu-id="91470-183">Bu bölüm normatıve 'dir.</span><span class="sxs-lookup"><span data-stu-id="91470-183">This section is normative.</span></span>

<span data-ttu-id="91470-184">Hamiltonian nesnesinin `two_electron_integrals` özelliği, `index_convention`adlı bir ek özelliğe sahip bir seyrek dizi miktarı olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="91470-184">The `two_electron_integrals` property of the Hamiltonian object MUST be a sparse array quantity with one additional property called `index_convention`.</span></span>
<span data-ttu-id="91470-185">`two_electron_integrals` değerinin her bir öğesi dört Dizin IÇERMELIDIR.</span><span class="sxs-lookup"><span data-stu-id="91470-185">Each element of the value of `two_electron_integrals` MUST have four indices.</span></span>

<span data-ttu-id="91470-186">Her `two_electron_integrals` özelliği bir `index_convention` özelliğine sahip OLMALıDıR.</span><span class="sxs-lookup"><span data-stu-id="91470-186">Each `two_electron_integrals` property MUST have a `index_convention` property.</span></span>
<span data-ttu-id="91470-187">`index_convention` özelliğinin değeri tablo 1 ' de listelenen izin verilen değerlerden biri OLMALıDıR.</span><span class="sxs-lookup"><span data-stu-id="91470-187">The value of the `index_convention` property MUST be one of the allowed values listed in Table 1.</span></span>
<span data-ttu-id="91470-188">`index_convention` değeri `mulliken`, sonra da `two_electron_integrals` seyrek dizi miktarının her bir öğesi için, bir Broombridge belgesi yükleyen bir ayrıştırıcıda bir Hamiltonian teriminin iki elektron işlecine eşit olması gerekir $h _ {i, j, k, l} a ^ \ dagger_i bir ^ \ dagger_j a_k a_l $, burada $i $, $j $, $k $ ve $l $, 1 ' den kapsamlı olarak tamsayı kümesi nesnesinin `n_electrons` özelliği tarafından belirtilen elektriklerin sayısına ve $h _ {i, j , k, l} $, seyrek dizi miktarının `[i, j, k, l, h(i, j, k, l)]` öğesidir.</span><span class="sxs-lookup"><span data-stu-id="91470-188">If the value of `index_convention` is `mulliken`, then for each element of the `two_electron_integrals` sparse array quantity, a parser loading a Broombridge document MUST instantiate a Hamiltonian term equal to the two-electron operator $h_{i, j, k, l} a^\dagger_i a^\dagger_j a_k a_l$, where $i$, $j$, $k$, and $l$ MUST be integers in the inclusive range from 1 to the number of electrons specified by the `n_electrons` property of the integral set object, and where $h_{i, j, k, l}$ is the element `[i, j, k, l, h(i, j, k, l)]` of the sparse array quantity.</span></span>

###### <a name="symmetries"></a><span data-ttu-id="91470-189">Symmetries</span><span class="sxs-lookup"><span data-stu-id="91470-189">Symmetries</span></span> ######

<span data-ttu-id="91470-190">Bu bölüm normatıve 'dir.</span><span class="sxs-lookup"><span data-stu-id="91470-190">This section is normative.</span></span>

<span data-ttu-id="91470-191">Bir `two_electron_integrals` nesnesinin `index_convention` özelliği `mulliken`eşitse, dizinler `[i, j, k, l]` olan bir öğe varsa, `[i, j, k, l]`eşit olmadıkları takdirde aşağıdaki dizinler bulunmamalıdır:</span><span class="sxs-lookup"><span data-stu-id="91470-191">If the `index_convention` property of a `two_electron_integrals` object is equal to `mulliken`, then if an element with indices `[i, j, k, l]` is present, the following indices MUST NOT be present unless they are equal to `[i, j, k, l]`:</span></span>

- `[i, j, l, k]`
- `[j, i, k, l]`
- `[j, i, l, k]`
- `[k, l, i, j]`
- `[k, l, j, i]`
- `[l, k, j, i]`

> [!NOTE]
> <span data-ttu-id="91470-192">`index_convention` özelliği seyrek bir Quantity nesnesi olduğundan, farklı öğelerde hiçbir dizin tekrarlanmayabilir.</span><span class="sxs-lookup"><span data-stu-id="91470-192">Because the `index_convention` property is a sparse quantity object, no indices may be repeated on different elements.</span></span>
> <span data-ttu-id="91470-193">Özellikle, Dizin `[i, j, k, l]` olan bir öğe varsa, başka bir öğe bu dizinleri içeremez.</span><span class="sxs-lookup"><span data-stu-id="91470-193">In particular, if an element with indices `[i, j, k, l]` is present, no other element may have those indices.</span></span>


<!-- h_{ijkl} = h_{ijlk}=h_{jikl}=h_{jilk}=h_{klij}=h_{klji}=h_{lkji}. -->

###### <a name="example"></a><span data-ttu-id="91470-194">Örnek</span><span class="sxs-lookup"><span data-stu-id="91470-194">Example</span></span> #######

<span data-ttu-id="91470-195">Bu bölüm bilgilendirme.</span><span class="sxs-lookup"><span data-stu-id="91470-195">This section is informative.</span></span>

<span data-ttu-id="91470-196">Aşağıdaki nesne Hamiltonian 'yi belirtir</span><span class="sxs-lookup"><span data-stu-id="91470-196">The following object specifies the Hamiltonian</span></span>

<span data-ttu-id="91470-197">$ $ H = \frac12 \sum\_{\sigma, \rho\in\\{\upok, \downarrow\\}} \Biggr (1,6 a ^ {\abger}\_{1, \sigma} a ^ {\abger}\_{1, \rho} a\_{1, \rho} a\_{1, \sigma}-0,1 a ^ {\abger}\_{6, \sigma} a ^ {\abger}\_{1, \rho} a\_{3, \rho} a\_{2, \sigma}-0,1 a ^ {\abger}\_{6, \sigma} a ^ {\dağılım ger}\_{1, \rho} a\_{2 , \rho} a\_{3, \sigma}-0,1 a ^ {\hanger}\_{1, \sigma} a ^ {\abger}\_{6, \rho} a\_{3, \rho} a\_{2, \sigma}-0,1 a ^ {\abger}\_{1, \sigma} a ^ {\dağılım}\_{6, \rho} a\_{2, \rho} a\_{3, \sigma} $ $ $ $-0,1 a ^ {\hanger}\_{3, \sigma} a ^ {\dağılım}\_{2, \rho} a\_{6, \rho} a\_{1, \sigma}-0,1 a ^ {\hanger}\_{3 , \sigma} a ^ {\abger}\_{2, \rho} a\_{1, \rho} a\_{6, \sigma}-0,1 a ^ {\abger}\_{2, \sigma} a ^ {\dağılım}\_{3, \rho} a\_{6, \rho} a\_{1, \sigma}-0,1 a ^ {\abger}\_{2, \sigma} a ^ {\dağılım}\_{3, \rho} a\_{1, \rho} a\_{6, \sigma}\Biggr)\\, \Textrm{ha}.</span><span class="sxs-lookup"><span data-stu-id="91470-197">$$ H = \frac12 \sum\_{\sigma,\rho\in\\{\uparrow,\downarrow\\}}\Biggr( 1.6 a^{\dagger}\_{1,\sigma} a^{\dagger}\_{1,\rho} a\_{1,\rho} a\_{1,\sigma}- 0.1 a^{\dagger}\_{6,\sigma} a^{\dagger}\_{1,\rho} a\_{3,\rho} a\_{2,\sigma}- 0.1 a^{\dagger}\_{6,\sigma} a^{\dagger}\_{1,\rho} a\_{2,\rho} a\_{3,\sigma}- 0.1 a^{\dagger}\_{1,\sigma} a^{\dagger}\_{6,\rho} a\_{3,\rho} a\_{2,\sigma}- 0.1 a^{\dagger}\_{1,\sigma} a^{\dagger}\_{6,\rho} a\_{2,\rho} a\_{3,\sigma} $$ $$- 0.1 a^{\dagger}\_{3,\sigma} a^{\dagger}\_{2,\rho} a\_{6,\rho} a\_{1,\sigma}- 0.1 a^{\dagger}\_{3,\sigma} a^{\dagger}\_{2,\rho} a\_{1,\rho} a\_{6,\sigma}- 0.1 a^{\dagger}\_{2,\sigma} a^{\dagger}\_{3,\rho} a\_{6,\rho} a\_{1,\sigma}- 0.1 a^{\dagger}\_{2,\sigma} a^{\dagger}\_{3,\rho} a\_{1,\rho} a\_{6,\sigma}\Biggr)\\,\textrm{Ha}.</span></span>
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

##### <a name="particlehole-representation-object"></a><span data-ttu-id="91470-198">Parçacık – delik gösterimi nesnesi</span><span class="sxs-lookup"><span data-stu-id="91470-198">Particle–Hole Representation Object</span></span> #####

<span data-ttu-id="91470-199">Bu bölüm normatıve 'dir.</span><span class="sxs-lookup"><span data-stu-id="91470-199">This section is normative.</span></span>

<span data-ttu-id="91470-200">Parçacık-delik gösterimi nesnesi, depolanan integrallerin, oluşturma ve Ayla ilgili operatörlerin, bir Hartree gibi kullanılan başvuru durumundan uzakta olduğunu belirten, parçacık delik gösterimine göre tanımlandığını belirtir – Fock durumu.</span><span class="sxs-lookup"><span data-stu-id="91470-200">The particle–hole representation object specifies that the integrals stored are defined with respect to particle hole representation wherein the creation and annihilation operators describe excitations away from the reference state used, such as a Hartree–Fock state.</span></span>
<span data-ttu-id="91470-201">Nesne Isteğe bağlıdır.</span><span class="sxs-lookup"><span data-stu-id="91470-201">The object is OPTIONAL.</span></span>
<span data-ttu-id="91470-202">Nesne belirtilmediyse Hamiltonian, parçacık deliği gösteriminde verilmemiş olarak yorumlanacaktır.</span><span class="sxs-lookup"><span data-stu-id="91470-202">If the object is not specified then the Hamiltonian is to be interpreted as not given in particle-hole representation.</span></span>
<span data-ttu-id="91470-203">Varsa, `particle_hole_representation` değeri, dizinleri dört tamsayı olan ve değerleri bir sayı ve bir dize olan seyrek dizi miktarı nesnesi OLMALıDıR.</span><span class="sxs-lookup"><span data-stu-id="91470-203">If present, the value of `particle_hole_representation` MUST be a sparse array quantity object whose indices are four integers, and whose values are a number and a string.</span></span>
<span data-ttu-id="91470-204">Her bir öğe değerinin dize kısmı yalnızca `'+'` karakterler içermelidir `'-'` ve bu terimin belirli bir faktörün, parçacık-delik temsilinde bir oluşturma veya yıllık bir operatör olması GEREKTIĞINI belirtir.</span><span class="sxs-lookup"><span data-stu-id="91470-204">The string portion of the value of each element MUST contain only the characters `'+'` and `'-'` which specifies whether a given factor in the term is a creation or annihilation operator in the particle–hole representation.</span></span>  <span data-ttu-id="91470-205">Örneğin `"-+++"`, site $i $ ve sitelerde oluşturulan parçacık $j, k $ ve $l $ konumunda oluşturulan bir deliğe yanıt verir.</span><span class="sxs-lookup"><span data-stu-id="91470-205">For example `"-+++"` coresponds to a hole being created at site $i$ and particles being created at sites $j,k$ and $l$.</span></span>

> [!NOTE]
> <span data-ttu-id="91470-206">`particle_hole_representation` değeri bir seyrek dizi miktarı nesnesi olduğundan, `unit` ve `format` özellikleri belirtilmelidir.</span><span class="sxs-lookup"><span data-stu-id="91470-206">As the value of the `particle_hole_representation` is a sparse array quantity object, the `unit` and `format` properties must be specified.</span></span>
> <span data-ttu-id="91470-207">Kabul edilebilir birimler dahil olmak üzere tablo 1 ' de listelenmiştir.</span><span class="sxs-lookup"><span data-stu-id="91470-207">Acceptable units include are listed in Table 1.</span></span>
> <span data-ttu-id="91470-208">`format` özelliği gereklidir ve Hamiltonian katlarının yoğun mı yoksa seyrek dizi olarak mı belirtilmediğini gösterir.</span><span class="sxs-lookup"><span data-stu-id="91470-208">The `format` property is required, and indicates whether the Hamiltonian coefficients are specified as a dense or sparse array.</span></span>
> <span data-ttu-id="91470-209">Geçerli sürümde, tüm belirtilmemiş öğelerin $0 $ olduğunu yorumlamayı içeren yalnızca seyrek diziler desteklenir, ancak gelecekteki sürümlerde `format` özelliğinin ek değerleri için destek eklenebilir.</span><span class="sxs-lookup"><span data-stu-id="91470-209">In the current version, only sparse arrays are supported, with interpretation that all unspecified elements are $0$, but future versions may add support for additional values of the `format` property.</span></span>

### <a name="initial-state-section"></a><span data-ttu-id="91470-210">İlk durum bölümü</span><span class="sxs-lookup"><span data-stu-id="91470-210">Initial State Section</span></span> ###

<span data-ttu-id="91470-211">İnitial_state_suggestion nesnesi, belirtilen Hamiltonian ile ilgilenilen ilk hisse durumlarını belirler.</span><span class="sxs-lookup"><span data-stu-id="91470-211">The initial_state_suggestion object specifies initial quantum states of interest to the specified Hamiltonian.</span></span> <span data-ttu-id="91470-212">Bu nesne bir JSON `state` nesneleri dizisi olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="91470-212">This object must be an array of JSON `state` objects.</span></span>

#### <a name="state-object"></a><span data-ttu-id="91470-213">Durum nesnesi</span><span class="sxs-lookup"><span data-stu-id="91470-213">State object</span></span> ####

<span data-ttu-id="91470-214">Her durum, dolu orbitlerin üst konumunu temsil eder.</span><span class="sxs-lookup"><span data-stu-id="91470-214">Each states represents a superposition of occupied orbitals.</span></span> <span data-ttu-id="91470-215">Her durum nesnesinin bir dize içeren bir `label` özelliği OLMALıDıR.</span><span class="sxs-lookup"><span data-stu-id="91470-215">Each state object MUST have a `label` property containing a string.</span></span> <span data-ttu-id="91470-216">Her bir durum nesnesi bir temel durum dizisi ve bunların Normalleştirilmemiş yükseltilmiş tudes dizisini içeren bir `superposition` özelliğine sahip OLMALıDıR.</span><span class="sxs-lookup"><span data-stu-id="91470-216">Each state object MUST have a `superposition` property containing an array of basis states and their unnormalized amplitudes.</span></span>

<span data-ttu-id="91470-217">Örneğin, ilk durumlar $ $ \ket{G0} = \ket{G1} = \ket{G2} = (a ^ {\abger}\_{1, \upoklu} a ^ {\gger}\_{2, \upok} a ^ {\abger}\_{2, \downok}) \ayraç{0} $ $ $ $ \ket{E} = \frac{0.exe} (bir ^ {\gesger}\_{1, \upoklu} a ^ {\abger}\_{2, \upoklu} a ^ {\abger}\_{2, \downok}) + 0.2 (a ^ {\dağılım}\_{1, \upoklu}a ^ {\dağılım}\_{3, \upoklu}a ^ {\dağılım}\_{2, \downok})} {\sqrt{| 0.1 | ^ 2 + | 0.2 | ^ 2}} \demet{0} $ $ gösteriliyor tarafından</span><span class="sxs-lookup"><span data-stu-id="91470-217">For example, the initial states $$ \ket{G0}=\ket{G1}=\ket{G2}=(a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{2,\uparrow}a^{\dagger}\_{2,\downarrow})\ket{0} $$ $$ \ket{E}=\frac{0.1 (a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{2,\uparrow}a^{\dagger}\_{2,\downarrow})+0.2 (a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{3,\uparrow}a^{\dagger}\_{2,\downarrow})}{\sqrt{|0.1|^2+|0.2|^2}}\ket{0} $$ are represented by</span></span>
```yaml
initial_state_suggestions: # optional. If not provided, spin-orbitals will be filled to minimize one-body diagonal term energies.
    - state:
        label: "|G0>"
        superposition:
            - [1.0, "(1a)+","(2a)+","(2b)+","|vacuum>"]
    - state:
        label: "|G1>"
        superposition:
            - [-1.0, "(2a)+","(1a)+","(2b)+","|vacuum>"]
    - state:
        label: "|G2>"
        superposition:
            - [1.0, "(3a)","(1a)+","(2a)+","(3a)+","(2b)+","|vacuum>"]
    - state:
        label: "|E>"
        superposition:
            - [0.1, "(1a)+","(2a)+","(2b)+","|vacuum>"]
            - [0.2, "(1a)+","(3a)+","(2b)+","|vacuum>"]
```

#### <a name="basis-set-object"></a><span data-ttu-id="91470-218">Taban kümesi nesnesi</span><span class="sxs-lookup"><span data-stu-id="91470-218">Basis Set Object</span></span> ####

<span data-ttu-id="91470-219">Bu bölüm normatıve 'dir.</span><span class="sxs-lookup"><span data-stu-id="91470-219">This section is normative.</span></span>

<span data-ttu-id="91470-220">Her integral kümesi nesnesinin bir `basis_set` özelliği olabılır.</span><span class="sxs-lookup"><span data-stu-id="91470-220">Each integral set object MAY have a `basis_set` property.</span></span>
<span data-ttu-id="91470-221">Varsa, `basis_set` özelliğinin değeri, `type` ve `name`iki özelliği olan bir nesne olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="91470-221">If present, the value of the `basis_set` property MUST be an object with two properties, `type` and `name`.</span></span>

<span data-ttu-id="91470-222">`basis_set` özelliğinin değeri ile tanımlanan temel işlevler gerçek değerli olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="91470-222">The basis functions identified by the value of the `basis_set` property MUST be real-valued.</span></span>

> [!NOTE]
> <span data-ttu-id="91470-223">Tüm temel işlevlerin gerçek değerli olduğu varsayımını bu belirtimin gelecekteki sürümlerinde gevşek olabilir.</span><span class="sxs-lookup"><span data-stu-id="91470-223">The assumption that all basis functions are real-valued may be relaxed in future versions of this specification.</span></span>

## <a name="tables-and-lists"></a><span data-ttu-id="91470-224">Tablolar ve listeler</span><span class="sxs-lookup"><span data-stu-id="91470-224">Tables and Lists</span></span> ##

### <a name="table-1-allowed-physical-units"></a><span data-ttu-id="91470-225">Tablo 1.</span><span class="sxs-lookup"><span data-stu-id="91470-225">Table 1.</span></span> <span data-ttu-id="91470-226">İzin verilen fiziksel birimler</span><span class="sxs-lookup"><span data-stu-id="91470-226">Allowed Physical Units</span></span> ###

<span data-ttu-id="91470-227">Bu bölüm normatıve 'dir.</span><span class="sxs-lookup"><span data-stu-id="91470-227">This section is normative.</span></span>

<span data-ttu-id="91470-228">Bir birimi belirten herhangi bir dize aşağıdakilerden biri OLMALıDıR:</span><span class="sxs-lookup"><span data-stu-id="91470-228">Any string specifying a unit MUST be one of the following:</span></span>

- `hartree`
- `ev`

<span data-ttu-id="91470-229">Çözümleyiciler ve üreticileri, aşağıdaki basit miktar nesnelerini eşdeğer olarak kabul ETMELIDIR:</span><span class="sxs-lookup"><span data-stu-id="91470-229">Parsers and producers MUST treat the following simple quantity objects as equivalent:</span></span>

```yaml
- {"units": "hartree", "value": 1}
- {"units": "ev", "value": 27.2113831301723}
```

### <a name="table-2-allowed-index-conventions"></a><span data-ttu-id="91470-230">Tablo 2.</span><span class="sxs-lookup"><span data-stu-id="91470-230">Table 2.</span></span> <span data-ttu-id="91470-231">İzin verilen dizin kuralları</span><span class="sxs-lookup"><span data-stu-id="91470-231">Allowed Index Conventions</span></span> ###

<span data-ttu-id="91470-232">Bu bölüm normatıve 'dir.</span><span class="sxs-lookup"><span data-stu-id="91470-232">This section is normative.</span></span>

<span data-ttu-id="91470-233">Bir dizin kuralını belirten herhangi bir dize aşağıdakilerden biri OLMALıDıR:</span><span class="sxs-lookup"><span data-stu-id="91470-233">Any string specifying an index convention MUST be one of the following:</span></span>

- `mulliken`

<span data-ttu-id="91470-234">Bu bölüm bilgilendirme.</span><span class="sxs-lookup"><span data-stu-id="91470-234">This section is informative.</span></span>

<span data-ttu-id="91470-235">Ek dizin kuralları bu belirtimin gelecek sürümlerinde kullanıma sunulacak olabilir.</span><span class="sxs-lookup"><span data-stu-id="91470-235">Additional index conventions may be introduced in future versions of this specification.</span></span>

#### <a name="interpretation-of-index-conventions"></a><span data-ttu-id="91470-236">Dizin kurallarının yorumu</span><span class="sxs-lookup"><span data-stu-id="91470-236">Interpretation of Index Conventions</span></span> ####

<span data-ttu-id="91470-237">Bu bölüm bilgilendirme.</span><span class="sxs-lookup"><span data-stu-id="91470-237">This section is informative.</span></span>
