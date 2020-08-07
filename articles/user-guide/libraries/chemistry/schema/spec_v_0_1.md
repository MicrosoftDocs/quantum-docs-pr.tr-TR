---
title: Broombridge şema belirtimi (ver 0,1)
description: Microsoft hisse dili Mistry kitaplığı için Broombridge hisse
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/17/2018
ms.topic: article
uid: microsoft.quantum.libraries.chemistry.schema.spec_v_0_1
no-loc:
- Q#
- $$v
ms.openlocfilehash: abbc63b8801c774e6ba06cff99b7382d64424b2c
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869146"
---
# <a name="broombridge-specification-v01"></a><span data-ttu-id="070ae-103">Broombridge belirtimi v 0.1</span><span class="sxs-lookup"><span data-stu-id="070ae-103">Broombridge Specification v0.1</span></span> #

<span data-ttu-id="070ae-104">"", "" Gerekli değildir "," gerekli "," Bu "," zorunlu değildir "," durum ",", "ve" Isteğe bağlı "anahtar sözcükleri, [RFC 2119](https://tools.ietf.org/html/rfc2119)' de açıklandığı gibi yorumlanmalıdır.</span><span class="sxs-lookup"><span data-stu-id="070ae-104">The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED",  "MAY", and "OPTIONAL" in this document are to be interpreted as described in [RFC 2119](https://tools.ietf.org/html/rfc2119).</span></span>

<span data-ttu-id="070ae-105">"NOTE", "ıNFORMATION" veya "WARNING" başlıklı tüm kenar çubuğu bilgilendirici.</span><span class="sxs-lookup"><span data-stu-id="070ae-105">Any sidebar with the headings "NOTE," "INFORMATION," or "WARNING" is informative.</span></span>

## <a name="introduction"></a><span data-ttu-id="070ae-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="070ae-106">Introduction</span></span> ##

<span data-ttu-id="070ae-107">Bu bölüm bilgilendirme.</span><span class="sxs-lookup"><span data-stu-id="070ae-107">This section is informative.</span></span>

<span data-ttu-id="070ae-108">Broombridge belgelerinin, hisse simülasyonu ve programlama araç zincirlerini kullanarak, işleme için hisse deneçlerinde simülasyon sorunlarının örneklerine iletişim kurması amaçlanmıştır.</span><span class="sxs-lookup"><span data-stu-id="070ae-108">Broombridge documents are intended to communicate instances of simulation problems in quantum chemistry for processing using quantum simulation and programming toolchains.</span></span>

## <a name="serialization"></a><span data-ttu-id="070ae-109">Serileştirme</span><span class="sxs-lookup"><span data-stu-id="070ae-109">Serialization</span></span> ##

<span data-ttu-id="070ae-110">Bu bölüm normatıve 'dir.</span><span class="sxs-lookup"><span data-stu-id="070ae-110">This section is normative.</span></span>

<span data-ttu-id="070ae-111">Bir Broombridge belgesi 2,2 [4627](https://tools.ietf.org/html/rfc4627) , bir JSON nesnesini temsil eden bir [YAML 1,2 belgesi](http://yaml.org/spec/) olarak serileştirilmelidir.</span><span class="sxs-lookup"><span data-stu-id="070ae-111">A Broombridge document MUST be serialized as a [YAML 1.2 document](http://yaml.org/spec/) representing a JSON object as described in [RFC 4627](https://tools.ietf.org/html/rfc4627) section 2.2.</span></span>
<span data-ttu-id="070ae-112">YAML 'ye seri hale getirilen nesnenin değeri olan bir özelliği OLMALıDıR `"$schema"` `"https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/qchem-0.1.schema.json"` ve JSON şeması taslağına göre geçerli olmalıdır-06 belirtimleri [[1](https://tools.ietf.org/html/draft-wright-json-schema-01), [2](https://tools.ietf.org/html/draft-wright-json-schema-validation-01)].</span><span class="sxs-lookup"><span data-stu-id="070ae-112">The object serialized to YAML MUST have a property `"$schema"` whose value is `"https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/qchem-0.1.schema.json"`, and MUST be valid according to the JSON Schema draft-06 specifications [[1](https://tools.ietf.org/html/draft-wright-json-schema-01), [2](https://tools.ietf.org/html/draft-wright-json-schema-validation-01)].</span></span>

<span data-ttu-id="070ae-113">Bu belirtimin geri kalanı için, "Broombridge nesnesi", bir Brombridge YAML belgesinden Serisi kaldırılan JSON nesnesine başvuracaktır.</span><span class="sxs-lookup"><span data-stu-id="070ae-113">For the remainder of this specification, "the Broombridge object" will refer to the JSON object deserialized from a Broombridge YAML document.</span></span>

<span data-ttu-id="070ae-114">Aksi belirtilmedikçe, nesneler bu belgede açıkça belirtilenlerin ötesinde ek özelliklere sahip olmamalıdır.</span><span class="sxs-lookup"><span data-stu-id="070ae-114">Unless otherwise explicitly noted, objects MUST NOT have additional properties beyond those specified explicitly in this document.</span></span>

## <a name="additional-definitions"></a><span data-ttu-id="070ae-115">Ek tanımlar</span><span class="sxs-lookup"><span data-stu-id="070ae-115">Additional Definitions</span></span> ##

<span data-ttu-id="070ae-116">Bu bölüm normatıve 'dir.</span><span class="sxs-lookup"><span data-stu-id="070ae-116">This section is normative.</span></span>

### <a name="quantity-objects"></a><span data-ttu-id="070ae-117">Miktar nesneleri</span><span class="sxs-lookup"><span data-stu-id="070ae-117">Quantity Objects</span></span> ###

<span data-ttu-id="070ae-118">Bu bölüm normatıve 'dir.</span><span class="sxs-lookup"><span data-stu-id="070ae-118">This section is normative.</span></span>

<span data-ttu-id="070ae-119">Bir _Quantity_ NESNESI bir JSON nesnesidir ve `units` değeri tablo 1 ' de listelenen izin verilen değerlerden biri olan BIR özelliğine sahip olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="070ae-119">A _quantity object_ is a JSON object, and MUST have a property `units` whose value is one of the allowed values listed in Table 1.</span></span>

<span data-ttu-id="070ae-120">Bir Quantity nesnesi, özelliğine ek olarak tek bir özelliği varsa _basit bir Quantity nesnesidir_ `value` `units` .</span><span class="sxs-lookup"><span data-stu-id="070ae-120">A quantity object is a _simple quantity object_ if it has a single property `value` in addition to its `units` property.</span></span>
<span data-ttu-id="070ae-121">`value`Özelliğin değeri bir sayı olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="070ae-121">The value of the `value` property MUST be a number.</span></span>

<span data-ttu-id="070ae-122">Bir Quantity nesnesi, özelliklerine ve özelliğine ek olarak, _sınırlanmış bir Quantity nesnesidir_ `lower` `upper` `units` .</span><span class="sxs-lookup"><span data-stu-id="070ae-122">A quantity object is a _bounded quantity object_ if it has the properties `lower` and `upper` in addition to its `units` property.</span></span>
<span data-ttu-id="070ae-123">`lower`Ve özelliklerinin değerleri sayı olmalıdır `upper` .</span><span class="sxs-lookup"><span data-stu-id="070ae-123">The values of the `lower` and `upper` properties MUST be numbers.</span></span>
<span data-ttu-id="070ae-124">Sınırlanmış bir miktar nesnesi değeri sayı olan bir özelliğe sahip olabılır `value` .</span><span class="sxs-lookup"><span data-stu-id="070ae-124">A bounded quantity object MAY have a property `value` whose value is a number.</span></span>

<span data-ttu-id="070ae-125">Bir Quantity nesnesi, özelliği ve özelliğine ek olarak özelliği varsa _seyrek dizi miktar nesnesidir_ `format` `values` `units` .</span><span class="sxs-lookup"><span data-stu-id="070ae-125">A quantity object is a _sparse array quantity object_ if it has the property `format` and a property `values` in addition to its `units` property.</span></span>
<span data-ttu-id="070ae-126">Değeri dize olmalıdır `format` `sparse` .</span><span class="sxs-lookup"><span data-stu-id="070ae-126">The value of `format` MUST be the string `sparse`.</span></span>
<span data-ttu-id="070ae-127">`values`Özelliğin değeri bir dızı olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="070ae-127">The value of the `values` property MUST be an array.</span></span>
<span data-ttu-id="070ae-128">Her öğesi, `values` seyrek dizi miktarının dizinlerini ve değerini temsil eden bir dizi olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="070ae-128">Each element of `values` MUST be an array representing the indices and value of the sparse array quantity.</span></span>

<span data-ttu-id="070ae-129">Seyrek dizi miktarı nesnesinin her bir öğesi için dizinler, tüm seyrek dizi miktarı nesnesi genelinde benzersiz OLMALıDıR.</span><span class="sxs-lookup"><span data-stu-id="070ae-129">The indices for each element of a sparse array quantity object MUST be unique across the entire sparse array quantity object.</span></span>
<span data-ttu-id="070ae-130">Bir dizin bir değeri ile mevcutsa `0` , bir Ayrıştırıcı seyrek dizi Quantity nesnesini aynı dizinde bulunmayan bir seyrek dizi Quantity nesnesine aynı şekilde işlemelidir.</span><span class="sxs-lookup"><span data-stu-id="070ae-130">If an index is present with a value of `0`, a parser MUST treat the sparse array quantity object identically to a sparse array quantity object in which that index is not present at all.</span></span>


<span data-ttu-id="070ae-131">Bir Quantity nesnesi olmalıdır</span><span class="sxs-lookup"><span data-stu-id="070ae-131">A quantity object MUST either be</span></span>

- <span data-ttu-id="070ae-132">basit bir miktar nesnesi,</span><span class="sxs-lookup"><span data-stu-id="070ae-132">a simple quantity object,</span></span>
- <span data-ttu-id="070ae-133">sınırlanmış bir miktar nesnesi veya</span><span class="sxs-lookup"><span data-stu-id="070ae-133">a bounded quantity object, or</span></span>
- <span data-ttu-id="070ae-134">seyrek dizi miktarı nesnesi.</span><span class="sxs-lookup"><span data-stu-id="070ae-134">a sparse array quantity object.</span></span>


### <a name="examples"></a><span data-ttu-id="070ae-135">Örnekler</span><span class="sxs-lookup"><span data-stu-id="070ae-135">Examples</span></span> ###

<span data-ttu-id="070ae-136">Bu bölüm bilgilendirme.</span><span class="sxs-lookup"><span data-stu-id="070ae-136">This section is informative.</span></span>

<span data-ttu-id="070ae-137">$1.9844146837 \Mathrm{ha} $ öğesini temsil eden basit bir miktar \, :</span><span class="sxs-lookup"><span data-stu-id="070ae-137">A simple quantity representing $1.9844146837\,\mathrm{Ha}$:</span></span>

```yaml
coulomb_repulsion:
    value: 1.9844146837
    units: hartree
```

<span data-ttu-id="070ae-138">$ [-7,-6] \Mathrm{ha} $ aralığında tek bir dağılımı temsil eden sınırlanmış bir miktar \, .</span><span class="sxs-lookup"><span data-stu-id="070ae-138">A bounded quantity representing a uniform distribution over the interval $[-7, -6]\,\mathrm{Ha}$:</span></span>

```yaml
fci_energy:
    upper: -6
    lower: -7
    units: hartree
```

<span data-ttu-id="070ae-139">Aşağıda öğesine `[1, 2]` eşit öğe `hello` ve `[3, 4]` Şuna eşit bir öğe olan seyrek dizi miktarı verilmiştir `world` :</span><span class="sxs-lookup"><span data-stu-id="070ae-139">The following is a sparse array quantity with an element `[1, 2]` equal to `hello` and an element `[3, 4]` equal to `world`:</span></span>

```yaml
sparse_example:
    format: sparse
    units: hartree
    values:
    - [1, 2, "hello"]
    - [3, 4, "world"]
```

## <a name="format-section"></a><span data-ttu-id="070ae-140">Biçim bölümü</span><span class="sxs-lookup"><span data-stu-id="070ae-140">Format Section</span></span> ##

<span data-ttu-id="070ae-141">Bu bölüm normatıve 'dir.</span><span class="sxs-lookup"><span data-stu-id="070ae-141">This section is normative.</span></span>

<span data-ttu-id="070ae-142">Broombridge nesnesi, `format` değeri bir bir özelliği olan JSON nesnesi olan bir özelliğe sahıp olmalıdır `version` .</span><span class="sxs-lookup"><span data-stu-id="070ae-142">The Broombridge object MUST have a property `format` whose value is a JSON object with one property called `version`.</span></span>
<span data-ttu-id="070ae-143">`version`Özelliğin değeri olmalıdır `"0.1"` .</span><span class="sxs-lookup"><span data-stu-id="070ae-143">The `version` property MUST have the value `"0.1"`.</span></span>

### <a name="example"></a><span data-ttu-id="070ae-144">Örnek</span><span class="sxs-lookup"><span data-stu-id="070ae-144">Example</span></span> ###

<span data-ttu-id="070ae-145">Bu bölüm bilgilendirme.</span><span class="sxs-lookup"><span data-stu-id="070ae-145">This section is informative.</span></span>

```yaml
format:                        # required
    version: "0.1"             # must match exactly
```

## <a name="integral-sets-section"></a><span data-ttu-id="070ae-146">Integral kümeleri bölümü</span><span class="sxs-lookup"><span data-stu-id="070ae-146">Integral Sets Section</span></span> ##

<span data-ttu-id="070ae-147">Bu bölüm normatıve 'dir.</span><span class="sxs-lookup"><span data-stu-id="070ae-147">This section is normative.</span></span>

<span data-ttu-id="070ae-148">Broombridge nesnesi, `integral_sets` değeri BIR JSON dizisi olan bir özelliğe sahıp olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="070ae-148">The Broombridge object MUST have a property `integral_sets` whose value is a JSON array.</span></span>
<span data-ttu-id="070ae-149">Özelliğin değerindeki her öğe, `integral_sets` Bu bölümün geri kalanında açıklandığı gibi bir integralleri kümesini açıklayan BIR JSON nesnesi olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="070ae-149">Each item in the value of the `integral_sets` property MUST be a JSON object describing one set of integrals, as described in the remainder of this section.</span></span>
<span data-ttu-id="070ae-150">Bu bölümün geri kalanında, "integral kümesi nesnesi" terimi, `integral_sets` Broombridge nesnesinin özelliğinin değerindeki bir öğeye başvuracaktır.</span><span class="sxs-lookup"><span data-stu-id="070ae-150">In the remainder of this section, the term "integral set object" will refer to an item in the value of the `integral_sets` property of the Broombridge object.</span></span>

<span data-ttu-id="070ae-151">Her integral kümesi nesnesinin değeri JSON nesnesi olan bir özelliği OLMALıDıR `metadata` .</span><span class="sxs-lookup"><span data-stu-id="070ae-151">Each integral set object MUST have a property `metadata` whose value is a JSON object.</span></span>
<span data-ttu-id="070ae-152">Değeri `metadata` boş JSON nesnesi (yani `{}` ) olabilir veya uygulayıcısı tarafından tanımlanan ek özellikleri içerebilir.</span><span class="sxs-lookup"><span data-stu-id="070ae-152">The value of `metadata` MAY be the empty JSON object (that is, `{}`), or MAY contain additional properties defined by the implementor.</span></span>

### <a name="hamiltonian-section"></a><span data-ttu-id="070ae-153">Hamiltonian bölümü</span><span class="sxs-lookup"><span data-stu-id="070ae-153">Hamiltonian Section</span></span> ###

#### <a name="overview"></a><span data-ttu-id="070ae-154">Genel Bakış</span><span class="sxs-lookup"><span data-stu-id="070ae-154">Overview</span></span> ####

<span data-ttu-id="070ae-155">Bu bölüm bilgilendirme.</span><span class="sxs-lookup"><span data-stu-id="070ae-155">This section is informative.</span></span>

<span data-ttu-id="070ae-156">`hamiltonian`Her bir integral kümesi nesnesinin özelliği, belirli bir hisse dili hatası Için Hamiltonian 'yi, tek ve iki gövdedeki terimleri gerçek sayıların seyrek dizileri olarak listeleyerek açıklar.</span><span class="sxs-lookup"><span data-stu-id="070ae-156">The `hamiltonian` property of each integral set object describes the Hamiltonian for a particular quantum chemistry problem by listing out its one- and two-body terms as sparse arrays of real numbers.</span></span>
<span data-ttu-id="070ae-157">Her bir integral kümesi nesnesi tarafından tanımlanan Hamiltonian işleçleri formu alır</span><span class="sxs-lookup"><span data-stu-id="070ae-157">The Hamiltonian operators described by each integral set object take the form</span></span>

<span data-ttu-id="070ae-158">$ $ H = \sum \_ \{ i, j \} \ Sum \_ {\sigma\in \\ {\upok, \downok \\ }} H \_ \{ ij \} a ^ \{ \gesger \} \_ {i, \sigma} a \_ {j, \sigma} + \frac {1} {2} \sum \_ \{ i, j, k, l \} \ Sum \_ {\sigma, \rho\in \\ {\upok, \downok \\ }} H \_ {ijkl} a ^ \gesger \_ {i, \sigma} a ^ \dağılım \_ {k, \rho} a \_ {l, \rho} a \_ {j, \sigma}, $ $</span><span class="sxs-lookup"><span data-stu-id="070ae-158">$$ H = \sum\_\{i,j\}\sum\_{\sigma\in\\{\uparrow,\downarrow\\}} h\_\{ij\} a^\{\dagger\}\_{i,\sigma} a\_{j,\sigma} + \frac{1}{2}\sum\_\{i,j,k,l\}\sum\_{\sigma,\rho\in\\{\uparrow,\downarrow\\}} h\_{ijkl} a^\dagger\_{i,\sigma} a^\dagger\_{k,\rho} a\_{l,\rho} a\_{j,\sigma}, $$</span></span>

<span data-ttu-id="070ae-159">Burada _ {ijkl} = (ij | KL) $ Mullikliksiz kuralına göre $h.</span><span class="sxs-lookup"><span data-stu-id="070ae-159">here $h_{ijkl}= (ij|kl)$ in Mulliken convention.</span></span>

<span data-ttu-id="070ae-160">Netlik açısından, tek bir elektron dönemi</span><span class="sxs-lookup"><span data-stu-id="070ae-160">For clarity, the one-electron term is</span></span>

<span data-ttu-id="070ae-161">$ $ h_ {ij} = \int {\mathrm d} x \psi ^ \* \_ ı (x) \left (\frac {1} {2} \nabla ^ 2 + \ Sum \_ {A} \frac{Z \_ A} {| x-x \_ A |}  \ sağ) \psı \_ j (x), $ $</span><span class="sxs-lookup"><span data-stu-id="070ae-161">$$ h_{ij} = \int {\mathrm d}x \psi^\*\_i(x) \left(\frac{1}{2}\nabla^2 + \sum\_{A}\frac{Z\_A}{|x-x\_A|}  \right) \psi\_j(x), $$</span></span>

<span data-ttu-id="070ae-162">ve iki elektron terimi</span><span class="sxs-lookup"><span data-stu-id="070ae-162">and the two-electron term is</span></span>

<span data-ttu-id="070ae-163">$ $ h \_ \{ ijkl \} = \iınt \{ \mathrm d \} x ^ 2 \psi ^ \{ \* \} \_ i (x \_ 1) \psı \_ j (x \_ 1) \frac \{ 1 \} \{ \| x \_ 1-x \_ 2 \| \} \ PSI \_ k ^ \{ \* \} (x \_ 2) \psı \_ l (x \_ 2).</span><span class="sxs-lookup"><span data-stu-id="070ae-163">$$ h\_\{ijkl\} = \iint \{\mathrm d\}x^2 \psi^\{\*\}\_i(x\_1)\psi\_j(x\_1) \frac\{1\}\{\|x\_1 -x\_2\|\}\psi\_k^\{\*\}(x\_2) \psi\_l(x\_2).</span></span>
$$

<span data-ttu-id="070ae-164">Özelliğin her bir öğesinin [ `basis_set` özelliğinin](#basis-set-object) açıklamamız bölümünde belirtildiği gibi `integral_sets` , kullanılan temel işlevlerin gerçek değerli olduğunu açıkça varsaydık.</span><span class="sxs-lookup"><span data-stu-id="070ae-164">As noted in our description of the [`basis_set` property](#basis-set-object) of each element of the `integral_sets` property, we further explicitly assume that the basis functions used are real-valued.</span></span>
<span data-ttu-id="070ae-165">Bu, Hamiltonian 'ın gösterimini sıkıştırmak için terimler arasında aşağıdaki symmetries kullanmamızı sağlar.</span><span class="sxs-lookup"><span data-stu-id="070ae-165">This allows us to use the following symmetries between the terms to compress the representation of the Hamiltonian.</span></span>

<span data-ttu-id="070ae-166">$ $ h_ {ijkl} = h_ {ijlk} = h_ {JIKL} = h_ {jılb} = h_ {klij} = h_ {klji} = h_ {lkij} = h_ {lkji}.</span><span class="sxs-lookup"><span data-stu-id="070ae-166">$$ h_{ijkl} = h_{ijlk}=h_{jikl}=h_{jilk}=h_{klij}=h_{klji}=h_{lkij}=h_{lkji}.</span></span>
$$


#### <a name="contents"></a><span data-ttu-id="070ae-167">İçindekiler</span><span class="sxs-lookup"><span data-stu-id="070ae-167">Contents</span></span> ####

<span data-ttu-id="070ae-168">Bu bölüm normatıve 'dir.</span><span class="sxs-lookup"><span data-stu-id="070ae-168">This section is normative.</span></span>

<span data-ttu-id="070ae-169">Her integral kümesi `hamiltonian` , değeri BIR JSON nesnesi olan bir özelliğe sahıp olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="070ae-169">Each integral set MUST have a property `hamiltonian` whose value is a JSON object.</span></span>
<span data-ttu-id="070ae-170">`hamiltonian`Özelliğin değeri Hamiltonian nesnesi olarak bilinir ve `one_electron_integrals` `two_electron_integrals` Bu bölümün geri kalanında açıklanan özelliklere ve özelliklerine sahip olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="070ae-170">The value of the `hamiltonian` property is known as a Hamiltonian object, and MUST have the properties `one_electron_integrals` and `two_electron_integrals` as described in the remainder of this section.</span></span>
<span data-ttu-id="070ae-171">Hamiltonian nesnesi de bir özelliğe sahip olabılır `particle_hole_representation` .</span><span class="sxs-lookup"><span data-stu-id="070ae-171">A Hamiltonian object MAY also have a property `particle_hole_representation`.</span></span>
<span data-ttu-id="070ae-172">Varsa, değeri `particle_hole_representation` Bu bölümün geri kalanında açıklanan biçimi izlemelidir.</span><span class="sxs-lookup"><span data-stu-id="070ae-172">If present, the value of `particle_hole_representation` MUST follow the format described in the remainder of this section.</span></span>

##### <a name="one-electron-integrals-object"></a><span data-ttu-id="070ae-173">Tek bir elektron Integrals nesnesi</span><span class="sxs-lookup"><span data-stu-id="070ae-173">One-Electron Integrals Object</span></span> #####

<span data-ttu-id="070ae-174">Bu bölüm normatıve 'dir.</span><span class="sxs-lookup"><span data-stu-id="070ae-174">This section is normative.</span></span>

<span data-ttu-id="070ae-175">`one_electron_integrals`Hamiltonian nesnesinin özelliği, dizinleri iki tamsayı olan ve değerleri sayı olan bir seyrek dizi miktarı olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="070ae-175">The `one_electron_integrals` property of the Hamiltonian object MUST be a sparse array quantity whose indices are two integers and whose values are numbers.</span></span>
<span data-ttu-id="070ae-176">Her dönemde dizinler bulunmalıdır `[i, j]` `i >= j` .</span><span class="sxs-lookup"><span data-stu-id="070ae-176">Every term MUST have indices `[i, j]` where `i >= j`.</span></span>

> <span data-ttu-id="070ae-177">NOTUN Bu, Hamiltonian 'ın hermitian olduğu olgunun bir sonucu olan $h _ {ij} = h_ {Ji} $ olan simetriyi yansıtır.</span><span class="sxs-lookup"><span data-stu-id="070ae-177">[NOTE] This reflects the symmetry that $h_{ij} = h_{ji}$ which is a consequence of the fact that the Hamiltonian is Hermitian.</span></span>


###### <a name="example"></a><span data-ttu-id="070ae-178">Örnek</span><span class="sxs-lookup"><span data-stu-id="070ae-178">Example</span></span> ######

<span data-ttu-id="070ae-179">Bu bölüm bilgilendirme.</span><span class="sxs-lookup"><span data-stu-id="070ae-179">This section is informative.</span></span>

<span data-ttu-id="070ae-180">Şu seyrek dizi miktarı Hamiltonian $ $ H = \left (-5,0 (a ^ \{ \dağılım {1) temsil eder. \} \_ \upoklu} a \_ {1, \upoklu} + bir ^ \{ \dağılım \} \_ {1, \downok} a \_ {1, \downoklu}) + 0,17 (bir ^ \{ \dağılım \} \_ {2, \upoklu} a \_ {1, \upoklu} + bir ^ \{ \dağılım \} \_ {1, \upoklu} a \_ {2, \upoklu} + bir ^ \{ \dağılım \} \_ {2, \downok} a \_ {1, \downok} + bir ^ \{ \dağılım \} \_ {1, \downok} a \_ {2, \downok}) \right) \\ , \mathrm{ha}.</span><span class="sxs-lookup"><span data-stu-id="070ae-180">The following sparse array quantity represents the Hamiltonian $$ H = \left(-5.0  (a^\{\dagger\}\_{1,\uparrow} a\_{1,\uparrow}+a^\{\dagger\}\_{1,\downarrow} a\_{1,\downarrow})+ 0.17 (a^\{\dagger\}\_{2,\uparrow} a\_{1,\uparrow}+ a^\{\dagger\}\_{1,\uparrow} a\_{2,\uparrow}+a^\{\dagger\}\_{2,\downarrow} a\_{1,\downarrow}+ a^\{\dagger\}\_{1,\downarrow} a\_{2,\downarrow})\right)\\,\mathrm{Ha}.</span></span>
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
> <span data-ttu-id="070ae-181">Broombridge, 1 tabanlı dizin oluşturma kullanır.</span><span class="sxs-lookup"><span data-stu-id="070ae-181">Broombridge uses 1-based indexing.</span></span>


##### <a name="two-electron-integrals-object"></a><span data-ttu-id="070ae-182">İki elektron Integrals nesnesi</span><span class="sxs-lookup"><span data-stu-id="070ae-182">Two-Electron Integrals Object</span></span> #####

<span data-ttu-id="070ae-183">Bu bölüm normatıve 'dir.</span><span class="sxs-lookup"><span data-stu-id="070ae-183">This section is normative.</span></span>

<span data-ttu-id="070ae-184">`two_electron_integrals`Hamiltonian nesnesinin özelliği, adlı bir ek özelliğe sahip bir seyrek dizi miktarı olmalıdır `index_convention` .</span><span class="sxs-lookup"><span data-stu-id="070ae-184">The `two_electron_integrals` property of the Hamiltonian object MUST be a sparse array quantity with one additional property called `index_convention`.</span></span>
<span data-ttu-id="070ae-185">Değerinin her öğesinin `two_electron_integrals` dört dizini olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="070ae-185">Each element of the value of `two_electron_integrals` MUST have four indices.</span></span>

<span data-ttu-id="070ae-186">Her `two_electron_integrals` özelliğin bir ÖZELLIĞI olmalıdır `index_convention` .</span><span class="sxs-lookup"><span data-stu-id="070ae-186">Each `two_electron_integrals` property MUST have a `index_convention` property.</span></span>
<span data-ttu-id="070ae-187">Özelliğin değeri, `index_convention` Tablo 1 ' de listelenen izin verilen değerlerden bırı olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="070ae-187">The value of the `index_convention` property MUST be one of the allowed values listed in Table 1.</span></span>
<span data-ttu-id="070ae-188">Değeri `index_convention` ise `mulliken` , seyrek dizi miktarının her bir öğesi için, `two_electron_integrals` bir Broombridge belgesi yükleyen bir ayrıştırıcıda iki elektron Işlecine eşit bir Hamiltonian terimi oluşturmalıdır $h _ {i, j, k, l} a ^ \ dagger_i a ^ \ dagger_j a_k a_l $, burada $i $, $j $, $k $ ve $l $, 1 ' den çok sayıda tamsayı olmalıdır `n_electrons` ve $h _ {i, j, k, l} $, `[i, j, k, l, h(i, j, k, l)]` seyrek dizi miktarının öğesidir.</span><span class="sxs-lookup"><span data-stu-id="070ae-188">If the value of `index_convention` is `mulliken`, then for each element of the `two_electron_integrals` sparse array quantity, a parser loading a Broombridge document MUST instantiate a Hamiltonian term equal to the two-electron operator $h_{i, j, k, l} a^\dagger_i a^\dagger_j a_k a_l$, where $i$, $j$, $k$, and $l$ MUST be integers in the inclusive range from 1 to the number of electrons specified by the `n_electrons` property of the integral set object, and where $h_{i, j, k, l}$ is the element `[i, j, k, l, h(i, j, k, l)]` of the sparse array quantity.</span></span>

###### <a name="symmetries"></a><span data-ttu-id="070ae-189">Symmetries</span><span class="sxs-lookup"><span data-stu-id="070ae-189">Symmetries</span></span> ######

<span data-ttu-id="070ae-190">Bu bölüm normatıve 'dir.</span><span class="sxs-lookup"><span data-stu-id="070ae-190">This section is normative.</span></span>

<span data-ttu-id="070ae-191">`index_convention`Bir `two_electron_integrals` nesnenin özelliği öğesine eşitse `mulliken` , dizinler içeren bir öğe varsa, `[i, j, k, l]` Şuna eşit olmadıkları takdirde aşağıdaki dizinler mevcut olmamalıdır `[i, j, k, l]` :</span><span class="sxs-lookup"><span data-stu-id="070ae-191">If the `index_convention` property of a `two_electron_integrals` object is equal to `mulliken`, then if an element with indices `[i, j, k, l]` is present, the following indices MUST NOT be present unless they are equal to `[i, j, k, l]`:</span></span>

- `[i, j, l, k]`
- `[j, i, k, l]`
- `[j, i, l, k]`
- `[k, l, i, j]`
- `[k, l, j, i]`
- `[l, k, j, i]`

> [!NOTE]
> <span data-ttu-id="070ae-192">`index_convention`Özelliği seyrek bir Quantity nesnesi olduğundan, farklı öğelerde hiçbir dizin tekrarlanmayabilir.</span><span class="sxs-lookup"><span data-stu-id="070ae-192">Because the `index_convention` property is a sparse quantity object, no indices may be repeated on different elements.</span></span>
> <span data-ttu-id="070ae-193">Özellikle, dizinler içeren bir öğe varsa `[i, j, k, l]` , başka bir öğe bu dizinleri içeremez.</span><span class="sxs-lookup"><span data-stu-id="070ae-193">In particular, if an element with indices `[i, j, k, l]` is present, no other element may have those indices.</span></span>


<!-- h_{ijkl} = h_{ijlk}=h_{jikl}=h_{jilk}=h_{klij}=h_{klji}=h_{lkji}. -->

###### <a name="example"></a><span data-ttu-id="070ae-194">Örnek</span><span class="sxs-lookup"><span data-stu-id="070ae-194">Example</span></span> #######

<span data-ttu-id="070ae-195">Bu bölüm bilgilendirme.</span><span class="sxs-lookup"><span data-stu-id="070ae-195">This section is informative.</span></span>

<span data-ttu-id="070ae-196">Aşağıdaki nesne Hamiltonian 'yi belirtir</span><span class="sxs-lookup"><span data-stu-id="070ae-196">The following object specifies the Hamiltonian</span></span>

<span data-ttu-id="070ae-197">$$ H = \frac12 \sum \_ {\sigma,\rho\in \\ {\uparrow,\downarrow \\ }}\Biggr( 1.6 a^{\dagger} \_ {1,\sigma} a^{\dagger} \_ {1,\rho} a \_ {1,\rho} a \_ {1,\sigma}- 0.1 a^{\dagger} \_ {6,\sigma} a^{\dagger} \_ {1,\rho} a \_ {3,\rho} a \_ {2,\sigma}- 0.1 a^{\dagger} \_ {6,\sigma} a^{\dagger} \_ {1,\rho} a \_ {2,\rho} a \_ {3,\sigma}- 0.1 a^{\dagger} \_ {1,\sigma} a^{\dagger} \_ {6,\rho} a \_ {3,\rho} a \_ {2,\sigma}- 0.1 a^{\dagger} \_ {1,\sigma} a^{\dagger} \_ {6,\rho} a \_ {2,\rho} a \_ {3,\sigma} $$ $$- 0.1 a^{\dagger} \_ {3,\sigma} a^{\dagger} \_ {2,\rho} a \_ {6,\rho} a \_ {1,\sigma}- 0.1 a^{\dagger} \_ {3,\sigma} a^{\dagger} \_ {2,\rho} a \_ {1,\rho} a \_ {6,\sigma}- 0.1 a^{\dagger} \_ {2,\sigma} a^{\dagger} \_ {3 , \rho} a \_ {6, \rho} a \_ {1, \sigma}-0,1 a ^ {\abger} \_ {2, \sigma} a ^ {\dağılım} \_ {3, \rho} a \_ {1, \Rho} a \_ {6, \Sigma}\Biggr) \\ , \Textrm{ha}.</span><span class="sxs-lookup"><span data-stu-id="070ae-197">$$ H = \frac12 \sum\_{\sigma,\rho\in\\{\uparrow,\downarrow\\}}\Biggr( 1.6 a^{\dagger}\_{1,\sigma} a^{\dagger}\_{1,\rho} a\_{1,\rho} a\_{1,\sigma}- 0.1 a^{\dagger}\_{6,\sigma} a^{\dagger}\_{1,\rho} a\_{3,\rho} a\_{2,\sigma}- 0.1 a^{\dagger}\_{6,\sigma} a^{\dagger}\_{1,\rho} a\_{2,\rho} a\_{3,\sigma}- 0.1 a^{\dagger}\_{1,\sigma} a^{\dagger}\_{6,\rho} a\_{3,\rho} a\_{2,\sigma}- 0.1 a^{\dagger}\_{1,\sigma} a^{\dagger}\_{6,\rho} a\_{2,\rho} a\_{3,\sigma} $$ $$- 0.1 a^{\dagger}\_{3,\sigma} a^{\dagger}\_{2,\rho} a\_{6,\rho} a\_{1,\sigma}- 0.1 a^{\dagger}\_{3,\sigma} a^{\dagger}\_{2,\rho} a\_{1,\rho} a\_{6,\sigma}- 0.1 a^{\dagger}\_{2,\sigma} a^{\dagger}\_{3,\rho} a\_{6,\rho} a\_{1,\sigma}- 0.1 a^{\dagger}\_{2,\sigma} a^{\dagger}\_{3,\rho} a\_{1,\rho} a\_{6,\sigma}\Biggr)\\,\textrm{Ha}.</span></span>
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

##### <a name="particlehole-representation-object"></a><span data-ttu-id="070ae-198">Parçacık – delik gösterimi nesnesi</span><span class="sxs-lookup"><span data-stu-id="070ae-198">Particle–Hole Representation Object</span></span> #####

<span data-ttu-id="070ae-199">Bu bölüm normatıve 'dir.</span><span class="sxs-lookup"><span data-stu-id="070ae-199">This section is normative.</span></span>

<span data-ttu-id="070ae-200">Parçacık-delik gösterimi nesnesi, depolanan integrallerin, oluşturma ve Ayla ilgili bir durum gibi, kullanılan başvuru durumundan daha fazla bir şekilde tanımlandığına göre tanımlandığını belirtir.</span><span class="sxs-lookup"><span data-stu-id="070ae-200">The particle–hole representation object specifies that the integrals stored are defined with respect to particle hole representation wherein the creation and annihilation operators describe excitations away from the reference state used, such as a Hartree–Fock state.</span></span>
<span data-ttu-id="070ae-201">Nesne Isteğe bağlıdır.</span><span class="sxs-lookup"><span data-stu-id="070ae-201">The object is OPTIONAL.</span></span>
<span data-ttu-id="070ae-202">Nesne belirtilmediyse Hamiltonian, parçacık deliği gösteriminde verilmemiş olarak yorumlanacaktır.</span><span class="sxs-lookup"><span data-stu-id="070ae-202">If the object is not specified then the Hamiltonian is to be interpreted as not given in particle-hole representation.</span></span>
<span data-ttu-id="070ae-203">Varsa, değeri, `particle_hole_representation` dizinleri dört tamsayı olan ve değerleri sayı ve dize olan bir seyrek dizi miktar nesnesi olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="070ae-203">If present, the value of `particle_hole_representation` MUST be a sparse array quantity object whose indices are four integers, and whose values are a number and a string.</span></span>
<span data-ttu-id="070ae-204">Her bir öğe değerinin dize kısmı yalnızca karakterleri içermelidir `'+'` ve `'-'` Bu, terimdeki belirli bir faktörün, parçacık gösterimi temsilinde bir oluşturma veya yıllık bir operatör olması gerektiğini belirtir.</span><span class="sxs-lookup"><span data-stu-id="070ae-204">The string portion of the value of each element MUST contain only the characters `'+'` and `'-'` which specifies whether a given factor in the term is a creation or annihilation operator in the particle–hole representation.</span></span>  <span data-ttu-id="070ae-205">Örneğin `"-+++"` , site $i $ ve $j, k $ ve $l $ sitelerinde oluşturulan parçacıkların oluşturulduğu bir deliğe yanıt verir.</span><span class="sxs-lookup"><span data-stu-id="070ae-205">For example `"-+++"` coresponds to a hole being created at site $i$ and particles being created at sites $j,k$ and $l$.</span></span>

> [!NOTE]
> <span data-ttu-id="070ae-206">Değeri `particle_hole_representation` bir seyrek dizi miktarı nesnesi olduğundan, `unit` ve `format` özellikleri belirtilmelidir.</span><span class="sxs-lookup"><span data-stu-id="070ae-206">As the value of the `particle_hole_representation` is a sparse array quantity object, the `unit` and `format` properties must be specified.</span></span>
> <span data-ttu-id="070ae-207">Kabul edilebilir birimler dahil olmak üzere tablo 1 ' de listelenmiştir.</span><span class="sxs-lookup"><span data-stu-id="070ae-207">Acceptable units include are listed in Table 1.</span></span>
> <span data-ttu-id="070ae-208">`format`Özelliği gereklidir ve Hamiltonian katlarının yoğun mı yoksa seyrek dizi olarak mı belirtilmediğini gösterir.</span><span class="sxs-lookup"><span data-stu-id="070ae-208">The `format` property is required, and indicates whether the Hamiltonian coefficients are specified as a dense or sparse array.</span></span>
> <span data-ttu-id="070ae-209">Geçerli sürümde, tüm belirtilmemiş öğelerin $0 $ olduğunu yorumlamayı içeren yalnızca seyrek diziler desteklenir, ancak gelecekteki sürümler özelliğin ek değerleri için destek ekleyebilir `format` .</span><span class="sxs-lookup"><span data-stu-id="070ae-209">In the current version, only sparse arrays are supported, with interpretation that all unspecified elements are $0$, but future versions may add support for additional values of the `format` property.</span></span>

### <a name="initial-state-section"></a><span data-ttu-id="070ae-210">İlk durum bölümü</span><span class="sxs-lookup"><span data-stu-id="070ae-210">Initial State Section</span></span> ###

<span data-ttu-id="070ae-211">İnitial_state_suggestion nesnesi, belirtilen Hamiltonian ile ilgilenilen ilk hisse durumlarını belirler.</span><span class="sxs-lookup"><span data-stu-id="070ae-211">The initial_state_suggestion object specifies initial quantum states of interest to the specified Hamiltonian.</span></span> <span data-ttu-id="070ae-212">Bu nesne bir JSON nesneleri dizisi olmalıdır `state` .</span><span class="sxs-lookup"><span data-stu-id="070ae-212">This object must be an array of JSON `state` objects.</span></span>

#### <a name="state-object"></a><span data-ttu-id="070ae-213">Durum nesnesi</span><span class="sxs-lookup"><span data-stu-id="070ae-213">State object</span></span> ####

<span data-ttu-id="070ae-214">Her durum, dolu orbitlerin üst konumunu temsil eder.</span><span class="sxs-lookup"><span data-stu-id="070ae-214">Each states represents a superposition of occupied orbitals.</span></span> <span data-ttu-id="070ae-215">Her durum nesnesinin bir `label` dize içeren bir ÖZELLIĞI olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="070ae-215">Each state object MUST have a `label` property containing a string.</span></span> <span data-ttu-id="070ae-216">Her bir durum nesnesi, `superposition` temel bir durum dizisi ve Normalleştirilmemiş yükseltilmiş tudes içeren bir özelliğe sahıp olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="070ae-216">Each state object MUST have a `superposition` property containing an array of basis states and their unnormalized amplitudes.</span></span>

<span data-ttu-id="070ae-217">Örneğin, ilk durumlar $ $ \ket{G0} = \ket{G1} = \ket{G2} = (bir ^ {\gger} \_ {1, \upoklu}a ^ {\abger} \_ {2, \upoklu} a ^ {\abger} {2, \upoklu \_ }) {0} \tus$ $ $ $ $ $ $ $ $ \Ket{e} = \frac{0.exe} (a ^ {\abger} { \_ 1, \upoklu}a ^ {\dağılım} \_ {2 \upoklu}a ^ {\gesger} \_ {2, \downok}) + 0.2 (a ^ {\gesger} \_ {1, \upoklu} a ^ {\dağılım} \_ {3, \upoklu}a ^ {\gesger} \_ {2, \downok})} {\sqrt{| 0.1 | ^ 2 + | 0.2 | ^ 2}} {0} \tus$ $ tarafından gösteriliyor</span><span class="sxs-lookup"><span data-stu-id="070ae-217">For example, the initial states $$ \ket{G0}=\ket{G1}=\ket{G2}=(a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{2,\uparrow}a^{\dagger}\_{2,\downarrow})\ket{0} $$ $$ \ket{E}=\frac{0.1 (a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{2,\uparrow}a^{\dagger}\_{2,\downarrow})+0.2 (a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{3,\uparrow}a^{\dagger}\_{2,\downarrow})}{\sqrt{|0.1|^2+|0.2|^2}}\ket{0} $$ are represented by</span></span>
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

#### <a name="basis-set-object"></a><span data-ttu-id="070ae-218">Taban kümesi nesnesi</span><span class="sxs-lookup"><span data-stu-id="070ae-218">Basis Set Object</span></span> ####

<span data-ttu-id="070ae-219">Bu bölüm normatıve 'dir.</span><span class="sxs-lookup"><span data-stu-id="070ae-219">This section is normative.</span></span>

<span data-ttu-id="070ae-220">Her integral kümesi nesnesinin bir özelliği olabılır `basis_set` .</span><span class="sxs-lookup"><span data-stu-id="070ae-220">Each integral set object MAY have a `basis_set` property.</span></span>
<span data-ttu-id="070ae-221">Varsa, `basis_set` özelliğinin değeri iki özelliklerine sahip bir nesne olmalıdır `type` ve `name` .</span><span class="sxs-lookup"><span data-stu-id="070ae-221">If present, the value of the `basis_set` property MUST be an object with two properties, `type` and `name`.</span></span>

<span data-ttu-id="070ae-222">Özelliğin değeri ile tanımlanan temel işlevler `basis_set` gerçek değerli olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="070ae-222">The basis functions identified by the value of the `basis_set` property MUST be real-valued.</span></span>

> [!NOTE]
> <span data-ttu-id="070ae-223">Tüm temel işlevlerin gerçek değerli olduğu varsayımını bu belirtimin gelecekteki sürümlerinde gevşek olabilir.</span><span class="sxs-lookup"><span data-stu-id="070ae-223">The assumption that all basis functions are real-valued may be relaxed in future versions of this specification.</span></span>

## <a name="tables-and-lists"></a><span data-ttu-id="070ae-224">Tablolar ve listeler</span><span class="sxs-lookup"><span data-stu-id="070ae-224">Tables and Lists</span></span> ##

### <a name="table-1-allowed-physical-units"></a><span data-ttu-id="070ae-225">Tablo 1.</span><span class="sxs-lookup"><span data-stu-id="070ae-225">Table 1.</span></span> <span data-ttu-id="070ae-226">İzin verilen fiziksel birimler</span><span class="sxs-lookup"><span data-stu-id="070ae-226">Allowed Physical Units</span></span> ###

<span data-ttu-id="070ae-227">Bu bölüm normatıve 'dir.</span><span class="sxs-lookup"><span data-stu-id="070ae-227">This section is normative.</span></span>

<span data-ttu-id="070ae-228">Bir birimi belirten herhangi bir dize aşağıdakilerden biri OLMALıDıR:</span><span class="sxs-lookup"><span data-stu-id="070ae-228">Any string specifying a unit MUST be one of the following:</span></span>

- `hartree`
- `ev`

<span data-ttu-id="070ae-229">Çözümleyiciler ve üreticileri, aşağıdaki basit miktar nesnelerini eşdeğer olarak kabul ETMELIDIR:</span><span class="sxs-lookup"><span data-stu-id="070ae-229">Parsers and producers MUST treat the following simple quantity objects as equivalent:</span></span>

```yaml
- {"units": "hartree", "value": 1}
- {"units": "ev", "value": 27.2113831301723}
```

### <a name="table-2-allowed-index-conventions"></a><span data-ttu-id="070ae-230">Tablo 2.</span><span class="sxs-lookup"><span data-stu-id="070ae-230">Table 2.</span></span> <span data-ttu-id="070ae-231">İzin verilen dizin kuralları</span><span class="sxs-lookup"><span data-stu-id="070ae-231">Allowed Index Conventions</span></span> ###

<span data-ttu-id="070ae-232">Bu bölüm normatıve 'dir.</span><span class="sxs-lookup"><span data-stu-id="070ae-232">This section is normative.</span></span>

<span data-ttu-id="070ae-233">Bir dizin kuralını belirten herhangi bir dize aşağıdakilerden biri OLMALıDıR:</span><span class="sxs-lookup"><span data-stu-id="070ae-233">Any string specifying an index convention MUST be one of the following:</span></span>

- `mulliken`

<span data-ttu-id="070ae-234">Bu bölüm bilgilendirme.</span><span class="sxs-lookup"><span data-stu-id="070ae-234">This section is informative.</span></span>

<span data-ttu-id="070ae-235">Ek dizin kuralları bu belirtimin gelecek sürümlerinde kullanıma sunulacak olabilir.</span><span class="sxs-lookup"><span data-stu-id="070ae-235">Additional index conventions may be introduced in future versions of this specification.</span></span>

#### <a name="interpretation-of-index-conventions"></a><span data-ttu-id="070ae-236">Dizin kurallarının yorumu</span><span class="sxs-lookup"><span data-stu-id="070ae-236">Interpretation of Index Conventions</span></span> ####

<span data-ttu-id="070ae-237">Bu bölüm bilgilendirme.</span><span class="sxs-lookup"><span data-stu-id="070ae-237">This section is informative.</span></span>
