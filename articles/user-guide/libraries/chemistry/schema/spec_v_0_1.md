---
title: Broombridge şema belirtimi (ver 0,1)
description: Microsoft hisse dili Mistry kitaplığı için Broombridge hisse
author: cgranade
ms.author: chgranad
ms.date: 10/17/2018
ms.topic: conceptual
uid: microsoft.quantum.libraries.chemistry.schema.spec_v_0_1
no-loc:
- Q#
- $$v
ms.openlocfilehash: 0a306f59a823e76ba0518d023a41f1f9d5670e7a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858189"
---
# <a name="broombridge-specification-v01"></a>Broombridge belirtimi v 0.1 #

"", "" Gerekli değildir "," gerekli "," Bu "," zorunlu değildir "," durum ",", "ve" Isteğe bağlı "anahtar sözcükleri, [RFC 2119](https://tools.ietf.org/html/rfc2119)' de açıklandığı gibi yorumlanmalıdır.

"NOTE", "ıNFORMATION" veya "WARNING" başlıklı tüm kenar çubuğu bilgilendirici.

## <a name="introduction"></a>Giriş ##

Bu bölüm bilgilendirme.

Broombridge belgelerinin, hisse simülasyonu ve programlama araç zincirlerini kullanarak, işleme için hisse deneçlerinde simülasyon sorunlarının örneklerine iletişim kurması amaçlanmıştır.

## <a name="serialization"></a>Serileştirme ##

Bu bölüm normatıve 'dir.

Bir Broombridge belgesi 2,2 [4627](https://tools.ietf.org/html/rfc4627) , bir JSON nesnesini temsil eden bir [YAML 1,2 belgesi](http://yaml.org/spec/) olarak serileştirilmelidir.
YAML 'ye seri hale getirilen nesnenin değeri olan bir özelliği OLMALıDıR `"$schema"` `"https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/qchem-0.1.schema.json"` ve JSON şeması taslağına göre geçerli olmalıdır-06 belirtimleri [[1](https://tools.ietf.org/html/draft-wright-json-schema-01), [2](https://tools.ietf.org/html/draft-wright-json-schema-validation-01)].

Bu belirtimin geri kalanı için, "Broombridge nesnesi", bir Brombridge YAML belgesinden Serisi kaldırılan JSON nesnesine başvuracaktır.

Aksi belirtilmedikçe, nesneler bu belgede açıkça belirtilenlerin ötesinde ek özelliklere sahip olmamalıdır.

## <a name="additional-definitions"></a>Ek tanımlar ##

Bu bölüm normatıve 'dir.

### <a name="quantity-objects"></a>Miktar nesneleri ###

Bu bölüm normatıve 'dir.

Bir _Quantity_ NESNESI bir JSON nesnesidir ve `units` değeri tablo 1 ' de listelenen izin verilen değerlerden biri olan BIR özelliğine sahip olmalıdır.

Bir Quantity nesnesi, özelliğine ek olarak tek bir özelliği varsa _basit bir Quantity nesnesidir_ `value` `units` .
`value`Özelliğin değeri bir sayı olmalıdır.

Bir Quantity nesnesi, özelliklerine ve özelliğine ek olarak, _sınırlanmış bir Quantity nesnesidir_ `lower` `upper` `units` .
`lower`Ve özelliklerinin değerleri sayı olmalıdır `upper` .
Sınırlanmış bir miktar nesnesi değeri sayı olan bir özelliğe sahip olabılır `value` .

Bir Quantity nesnesi, özelliği ve özelliğine ek olarak özelliği varsa _seyrek dizi miktar nesnesidir_ `format` `values` `units` .
Değeri dize olmalıdır `format` `sparse` .
`values`Özelliğin değeri bir dızı olmalıdır.
Her öğesi, `values` seyrek dizi miktarının dizinlerini ve değerini temsil eden bir dizi olmalıdır.

Seyrek dizi miktarı nesnesinin her bir öğesi için dizinler, tüm seyrek dizi miktarı nesnesi genelinde benzersiz OLMALıDıR.
Bir dizin bir değeri ile mevcutsa `0` , bir Ayrıştırıcı seyrek dizi Quantity nesnesini aynı dizinde bulunmayan bir seyrek dizi Quantity nesnesine aynı şekilde işlemelidir.


Bir Quantity nesnesi olmalıdır

- basit bir miktar nesnesi,
- sınırlanmış bir miktar nesnesi veya
- seyrek dizi miktarı nesnesi.


### <a name="examples"></a>Örnekler ###

Bu bölüm bilgilendirme.

$1.9844146837 \Mathrm{ha} $ öğesini temsil eden basit bir miktar \, :

```yaml
coulomb_repulsion:
    value: 1.9844146837
    units: hartree
```

$ [-7,-6] \Mathrm{ha} $ aralığında tek bir dağılımı temsil eden sınırlanmış bir miktar \, .

```yaml
fci_energy:
    upper: -6
    lower: -7
    units: hartree
```

Aşağıda öğesine `[1, 2]` eşit öğe `hello` ve `[3, 4]` Şuna eşit bir öğe olan seyrek dizi miktarı verilmiştir `world` :

```yaml
sparse_example:
    format: sparse
    units: hartree
    values:
    - [1, 2, "hello"]
    - [3, 4, "world"]
```

## <a name="format-section"></a>Biçim bölümü ##

Bu bölüm normatıve 'dir.

Broombridge nesnesi, `format` değeri bir bir özelliği olan JSON nesnesi olan bir özelliğe sahıp olmalıdır `version` .
`version`Özelliğin değeri olmalıdır `"0.1"` .

### <a name="example"></a>Örnek ###

Bu bölüm bilgilendirme.

```yaml
format:                        # required
    version: "0.1"             # must match exactly
```

## <a name="integral-sets-section"></a>Integral kümeleri bölümü ##

Bu bölüm normatıve 'dir.

Broombridge nesnesi, `integral_sets` değeri BIR JSON dizisi olan bir özelliğe sahıp olmalıdır.
Özelliğin değerindeki her öğe, `integral_sets` Bu bölümün geri kalanında açıklandığı gibi bir integralleri kümesini açıklayan BIR JSON nesnesi olmalıdır.
Bu bölümün geri kalanında, "integral kümesi nesnesi" terimi, `integral_sets` Broombridge nesnesinin özelliğinin değerindeki bir öğeye başvuracaktır.

Her integral kümesi nesnesinin değeri JSON nesnesi olan bir özelliği OLMALıDıR `metadata` .
Değeri `metadata` boş JSON nesnesi (yani `{}` ) olabilir veya uygulayıcısı tarafından tanımlanan ek özellikleri içerebilir.

### <a name="hamiltonian-section"></a>Hamiltonian bölümü ###

#### <a name="overview"></a>Genel Bakış ####

Bu bölüm bilgilendirme.

`hamiltonian`Her bir integral kümesi nesnesinin özelliği, belirli bir hisse dili hatası Için Hamiltonian 'yi, tek ve iki gövdedeki terimleri gerçek sayıların seyrek dizileri olarak listeleyerek açıklar.
Her bir integral kümesi nesnesi tarafından tanımlanan Hamiltonian işleçleri formu alır

$ $ H = \sum \_ \{ i, j \} \ Sum \_ {\sigma\in \\ {\upok, \downok \\ }} H \_ \{ ij \} a ^ \{ \gesger \} \_ {i, \sigma} a \_ {j, \sigma} + \frac {1} {2} \sum \_ \{ i, j, k, l \} \ Sum \_ {\sigma, \rho\in \\ {\upok, \downok \\ }} H \_ {ijkl} a ^ \gesger \_ {i, \sigma} a ^ \dağılım \_ {k, \rho} a \_ {l, \rho} a \_ {j, \sigma}, $ $

Burada _ {ijkl} = (ij | KL) $ Mullikliksiz kuralına göre $h.

Netlik açısından, tek bir elektron dönemi

$ $ h_ {ij} = \int {\mathrm d} x \psi ^ * \_ ı (x) \left (\frac {1} {2} \nabla ^ 2 + \ Sum \_ {A} \frac{Z \_ A} {| x-x \_ A |}  \ sağ) \psı \_ j (x), $ $

ve iki elektron terimi

$ $ h \_ \{ ijkl \} = \iınt \{ \mathrm d \} x ^ 2 \psi ^ \{ \* \} \_ i (x \_ 1) \psı \_ j (x \_ 1) \frac \{ 1 \} \{ \| x \_ 1-x \_ 2 \| \} \ PSI \_ k ^ \{ \* \} (x \_ 2) \psı \_ l (x \_ 2).
$$

Özelliğin her bir öğesinin [ `basis_set` özelliğinin](#basis-set-object) açıklamamız bölümünde belirtildiği gibi `integral_sets` , kullanılan temel işlevlerin gerçek değerli olduğunu açıkça varsaydık.
Bu, Hamiltonian 'ın gösterimini sıkıştırmak için terimler arasında aşağıdaki symmetries kullanmamızı sağlar.

$ $ h_ {ijkl} = h_ {ijlk} = h_ {JIKL} = h_ {jılb} = h_ {klij} = h_ {klji} = h_ {lkij} = h_ {lkji}.
$$


#### <a name="contents"></a>İçindekiler ####

Bu bölüm normatıve 'dir.

Her integral kümesi `hamiltonian` , değeri BIR JSON nesnesi olan bir özelliğe sahıp olmalıdır.
`hamiltonian`Özelliğin değeri Hamiltonian nesnesi olarak bilinir ve `one_electron_integrals` `two_electron_integrals` Bu bölümün geri kalanında açıklanan özelliklere ve özelliklerine sahip olmalıdır.
Hamiltonian nesnesi de bir özelliğe sahip olabılır `particle_hole_representation` .
Varsa, değeri `particle_hole_representation` Bu bölümün geri kalanında açıklanan biçimi izlemelidir.

##### <a name="one-electron-integrals-object"></a>One-Electron Integrals nesnesi #####

Bu bölüm normatıve 'dir.

`one_electron_integrals`Hamiltonian nesnesinin özelliği, dizinleri iki tamsayı olan ve değerleri sayı olan bir seyrek dizi miktarı olmalıdır.
Her dönemde dizinler bulunmalıdır `[i, j]` `i >= j` .

> NOTUN Bu, Hamiltonian 'ın hermitian olduğu olgunun bir sonucu olan $h _ {ij} = h_ {Ji} $ olan simetriyi yansıtır.


###### <a name="example"></a>Örnek ######

Bu bölüm bilgilendirme.

Şu seyrek dizi miktarı Hamiltonian $ $ H = \left (-5,0 (a ^ \{ \dağılım {1) temsil eder. \} \_ \upoklu} a \_ {1, \upoklu} + bir ^ \{ \dağılım \} \_ {1, \downok} a \_ {1, \downoklu}) + 0,17 (bir ^ \{ \dağılım \} \_ {2, \upoklu} a \_ {1, \upoklu} + bir ^ \{ \dağılım \} \_ {1, \upoklu} a \_ {2, \upoklu} + bir ^ \{ \dağılım \} \_ {2, \downok} a \_ {1, \downok} + bir ^ \{ \dağılım \} \_ {1, \downok} a \_ {2, \downok}) \right) \\ , \mathrm{ha}.
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
> Broombridge, 1 tabanlı dizin oluşturma kullanır.


##### <a name="two-electron-integrals-object"></a>Two-Electron Integrals nesnesi #####

Bu bölüm normatıve 'dir.

`two_electron_integrals`Hamiltonian nesnesinin özelliği, adlı bir ek özelliğe sahip bir seyrek dizi miktarı olmalıdır `index_convention` .
Değerinin her öğesinin `two_electron_integrals` dört dizini olmalıdır.

Her `two_electron_integrals` özelliğin bir ÖZELLIĞI olmalıdır `index_convention` .
Özelliğin değeri, `index_convention` Tablo 1 ' de listelenen izin verilen değerlerden bırı olmalıdır.
Değeri `index_convention` ise `mulliken` , seyrek dizi miktarının her bir öğesi için, `two_electron_integrals` bir Broombridge belgesi yükleyen bir ayrıştırıcıda iki elektron Işlecine eşit bir Hamiltonian terimi oluşturmalıdır $h _ {i, j, k, l} a ^ \ dagger_i a ^ \ dagger_j a_k a_l $, burada $i $, $j $, $k $ ve $l $, 1 ' den çok sayıda tamsayı olmalıdır `n_electrons` ve $h _ {i, j, k, l} $, `[i, j, k, l, h(i, j, k, l)]` seyrek dizi miktarının öğesidir.

###### <a name="symmetries"></a>Symmetries ######

Bu bölüm normatıve 'dir.

`index_convention`Bir `two_electron_integrals` nesnenin özelliği öğesine eşitse `mulliken` , dizinler içeren bir öğe varsa, `[i, j, k, l]` Şuna eşit olmadıkları takdirde aşağıdaki dizinler mevcut olmamalıdır `[i, j, k, l]` :

- `[i, j, l, k]`
- `[j, i, k, l]`
- `[j, i, l, k]`
- `[k, l, i, j]`
- `[k, l, j, i]`
- `[l, k, j, i]`

> [!NOTE]
> `index_convention`Özelliği seyrek bir Quantity nesnesi olduğundan, farklı öğelerde hiçbir dizin tekrarlanmayabilir.
> Özellikle, dizinler içeren bir öğe varsa `[i, j, k, l]` , başka bir öğe bu dizinleri içeremez.


<!-- h_{ijkl} = h_{ijlk}=h_{jikl}=h_{jilk}=h_{klij}=h_{klji}=h_{lkji}. -->

###### <a name="example"></a>Örnek #######

Bu bölüm bilgilendirme.

Aşağıdaki nesne Hamiltonian 'yi belirtir

$$ H = \frac12 \sum \_ {\sigma,\rho\in \\ {\uparrow,\downarrow \\ }}\Biggr( 1.6 a^{\dagger} \_ {1,\sigma} a^{\dagger} \_ {1,\rho} a \_ {1,\rho} a \_ {1,\sigma}- 0.1 a^{\dagger} \_ {6,\sigma} a^{\dagger} \_ {1,\rho} a \_ {3,\rho} a \_ {2,\sigma}- 0.1 a^{\dagger} \_ {6,\sigma} a^{\dagger} \_ {1,\rho} a \_ {2,\rho} a \_ {3,\sigma}- 0.1 a^{\dagger} \_ {1,\sigma} a^{\dagger} \_ {6,\rho} a \_ {3,\rho} a \_ {2,\sigma}- 0.1 a^{\dagger} \_ {1,\sigma} a^{\dagger} \_ {6,\rho} a \_ {2,\rho} a \_ {3,\sigma} $$ $$- 0.1 a^{\dagger} \_ {3,\sigma} a^{\dagger} \_ {2,\rho} a \_ {6,\rho} a \_ {1,\sigma}- 0.1 a^{\dagger} \_ {3,\sigma} a^{\dagger} \_ {2,\rho} a \_ {1,\rho} a \_ {6,\sigma}- 0.1 a^{\dagger} \_ {2,\sigma} a^{\dagger} \_ {3 , \rho} a \_ {6, \rho} a \_ {1, \sigma}-0,1 a ^ {\abger} \_ {2, \sigma} a ^ {\dağılım} \_ {3, \rho} a \_ {1, \Rho} a \_ {6, \Sigma}\Biggr) \\ , \Textrm{ha}.
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

##### <a name="particlehole-representation-object"></a>Parçacık – delik gösterimi nesnesi #####

Bu bölüm normatıve 'dir.

Parçacık-delik gösterimi nesnesi, depolanan integrallerin, oluşturma ve Ayla ilgili bir durum gibi, kullanılan başvuru durumundan daha fazla bir şekilde tanımlandığına göre tanımlandığını belirtir.
Nesne Isteğe bağlıdır.
Nesne belirtilmediyse Hamiltonian, parçacık deliği gösteriminde verilmemiş olarak yorumlanacaktır.
Varsa, değeri, `particle_hole_representation` dizinleri dört tamsayı olan ve değerleri sayı ve dize olan bir seyrek dizi miktar nesnesi olmalıdır.
Her bir öğe değerinin dize kısmı yalnızca karakterleri içermelidir `'+'` ve `'-'` Bu, terimdeki belirli bir faktörün, parçacık gösterimi temsilinde bir oluşturma veya yıllık bir operatör olması gerektiğini belirtir.  Örneğin `"-+++"` , site $i $ ve $j, k $ ve $l $ sitelerinde oluşturulan parçacıkların oluşturulduğu bir deliğe yanıt verir.

> [!NOTE]
> Değeri `particle_hole_representation` bir seyrek dizi miktarı nesnesi olduğundan, `unit` ve `format` özellikleri belirtilmelidir.
> Kabul edilebilir birimler dahil olmak üzere tablo 1 ' de listelenmiştir.
> `format`Özelliği gereklidir ve Hamiltonian katlarının yoğun mı yoksa seyrek dizi olarak mı belirtilmediğini gösterir.
> Geçerli sürümde, tüm belirtilmemiş öğelerin $0 $ olduğunu yorumlamayı içeren yalnızca seyrek diziler desteklenir, ancak gelecekteki sürümler özelliğin ek değerleri için destek ekleyebilir `format` .

### <a name="initial-state-section"></a>İlk durum bölümü ###

İnitial_state_suggestion nesnesi, belirtilen Hamiltonian ile ilgilenilen ilk hisse durumlarını belirler. Bu nesne bir JSON nesneleri dizisi olmalıdır `state` .

#### <a name="state-object"></a>Durum nesnesi ####

Her durum, dolu orbitlerin üst konumunu temsil eder. Her durum nesnesinin bir `label` dize içeren bir ÖZELLIĞI olmalıdır. Her bir durum nesnesi, `superposition` temel bir durum dizisi ve Normalleştirilmemiş yükseltilmiş tudes içeren bir özelliğe sahıp olmalıdır.

Örneğin, ilk durumlar $ $ \ket{G0} = \ket{G1} = \ket{G2} = (bir ^ {\gger} \_ {1, \upoklu}a ^ {\abger} \_ {2, \upoklu} a ^ {\abger} {2, \upoklu \_ }) {0} \tus$ $ $ $ $ $ $ $ $ \Ket{e} = \frac{0.exe} (a ^ {\abger} { \_ 1, \upoklu}a ^ {\dağılım} \_ {2 \upoklu}a ^ {\gesger} \_ {2, \downok}) + 0.2 (a ^ {\gesger} \_ {1, \upoklu} a ^ {\dağılım} \_ {3, \upoklu}a ^ {\gesger} \_ {2, \downok})} {\sqrt{| 0.1 | ^ 2 + | 0.2 | ^ 2}} {0} \tus$ $ tarafından gösteriliyor
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

#### <a name="basis-set-object"></a>Taban kümesi nesnesi ####

Bu bölüm normatıve 'dir.

Her integral kümesi nesnesinin bir özelliği olabılır `basis_set` .
Varsa, `basis_set` özelliğinin değeri iki özelliklerine sahip bir nesne olmalıdır `type` ve `name` .

Özelliğin değeri ile tanımlanan temel işlevler `basis_set` gerçek değerli olmalıdır.

> [!NOTE]
> Tüm temel işlevlerin gerçek değerli olduğu varsayımını bu belirtimin gelecekteki sürümlerinde gevşek olabilir.

## <a name="tables-and-lists"></a>Tablolar ve listeler ##

### <a name="table-1-allowed-physical-units"></a>Tablo 1. İzin verilen fiziksel birimler ###

Bu bölüm normatıve 'dir.

Bir birimi belirten herhangi bir dize aşağıdakilerden biri OLMALıDıR:

- `hartree`
- `ev`

Çözümleyiciler ve üreticileri, aşağıdaki basit miktar nesnelerini eşdeğer olarak kabul ETMELIDIR:

```yaml
- {"units": "hartree", "value": 1}
- {"units": "ev", "value": 27.2113831301723}
```

### <a name="table-2-allowed-index-conventions"></a>Tablo 2. İzin verilen dizin kuralları ###

Bu bölüm normatıve 'dir.

Bir dizin kuralını belirten herhangi bir dize aşağıdakilerden biri OLMALıDıR:

- `mulliken`

Bu bölüm bilgilendirme.

Ek dizin kuralları bu belirtimin gelecek sürümlerinde kullanıma sunulacak olabilir.

#### <a name="interpretation-of-index-conventions"></a>Dizin kurallarının yorumu ####

Bu bölüm bilgilendirme.
