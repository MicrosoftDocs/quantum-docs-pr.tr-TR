---
title: Broombridge şema belirtimi
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/17/2018
ms.topic: article
uid: microsoft.quantum.libraries.chemistry.schema.spec_v_0_1
ms.openlocfilehash: a950e04d44e5de8091b034214258d2c2fa663f58
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2019
ms.locfileid: "73185367"
---
# <a name="broombridge-specification-v01"></a>Broombridge belirtimi v 0.1 #

"", "" Gerekli değildir "," gerekli "," Bu "," zorunlu değildir "," durum ",", "ve" Isteğe bağlı "anahtar sözcükleri, [RFC 2119](https://tools.ietf.org/html/rfc2119)' de açıklandığı gibi yorumlanmalıdır.

"NOTE", "ıNFORMATION" veya "WARNING" başlıklı tüm kenar çubuğu bilgilendirici.

## <a name="introduction"></a>Tanıtım ##

Bu bölüm bilgilendirme.

Broombridge belgelerinin, hisse simülasyonu ve programlama araç zincirlerini kullanarak, işleme için hisse deneçlerinde simülasyon sorunlarının örneklerine iletişim kurması amaçlanmıştır.

## <a name="serialization"></a>Getir ##

Bu bölüm normatıve 'dir.

Bir Broombridge belgesi 2,2 [4627](https://tools.ietf.org/html/rfc4627) , bir JSON nesnesini temsil eden bir [YAML 1,2 belgesi](http://yaml.org/spec/) olarak serileştirilmelidir.
YAML 'ye seri hale getirilen nesne, değeri `"https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/qchem-0.1.schema.json"`olan bir özellik `"$schema"` sahip OLMALıDıR ve JSON şeması taslağına göre geçerli olmalıdır-06 belirtimleri [[1](https://tools.ietf.org/html/draft-wright-json-schema-01), [2](https://tools.ietf.org/html/draft-wright-json-schema-validation-01)].

Bu belirtimin geri kalanı için, "Broombridge nesnesi", bir Brombridge YAML belgesinden Serisi kaldırılan JSON nesnesine başvuracaktır.

Aksi belirtilmedikçe, nesneler bu belgede açıkça belirtilenlerin ötesinde ek özelliklere sahip olmamalıdır.

## <a name="additional-definitions"></a>Ek Tanımlar ##

Bu bölüm normatıve 'dir.

### <a name="quantity-objects"></a>Miktar nesneleri ###

Bu bölüm normatıve 'dir.

Bir _Quantity_ NESNESI bir JSON nesnesidir ve değeri tablo 1 ' de listelenen izin verilen değerlerden biri olan bir özellik `units` sahip olmalıdır.

Bir Quantity nesnesi, `units` özelliğine ek olarak `value` tek bir özelliğe sahipse _basit bir Quantity nesnesidir_ .
`value` özelliğinin değeri bir sayı olmalıdır.

Bir Quantity nesnesi, `lower` özellikler varsa ve `units` özelliğine ek olarak `upper` _sınırlanmış bir miktar nesnesidir_ .
`lower` ve `upper` özelliklerinin değerleri sayı olmalıdır.
Sınırlanmış bir miktar nesnesi değeri sayı olan bir özellik `value` olabılır.

Bir Quantity nesnesi, özelliğin `format` ve bir özelliğin `units` özelliğine ek olarak `values` varsa _seyrek dizi miktarı nesnesidir_ .
`format` değeri `sparse`dize OLMALıDıR.
`values` özelliğinin değeri bir dizi OLMALıDıR.
Her `values` öğesi, seyrek dizi miktarının indekslerini ve değerini temsil eden bir dizi OLMALıDıR.

Seyrek dizi miktarı nesnesinin her bir öğesi için dizinler, tüm seyrek dizi miktarı nesnesi genelinde benzersiz OLMALıDıR.
Bir dizin `0`bir değeri varsa, bir Ayrıştırıcı seyrek dizi Quantity nesnesini aynı dizinde yer alan bir seyrek dizi Quantity nesnesi ile aynı şekilde ele ALMALıDıR.


Bir Quantity nesnesi olmalıdır

- basit bir miktar nesnesi,
- sınırlanmış bir miktar nesnesi veya
- seyrek dizi miktarı nesnesi.


### <a name="examples"></a>Örnekler ###

Bu bölüm bilgilendirme.

$1.9844146837\,\mathrm{Ha} $ öğesini temsil eden basit bir miktar:

```yaml
coulomb_repulsion:
    value: 1.9844146837
    units: hartree
```

$ [-7,-6]\,\mathrm{Ha} $ aralığında tek bir dağılımı temsil eden sınırlanmış bir miktar.

```yaml
fci_energy:
    upper: -6
    lower: -7
    units: hartree
```

Aşağıda, bir öğesi `hello` eşit `[1, 2]` ve bir öğe `world``[3, 4]` eşit olan seyrek dizi miktarı verilmiştir:

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

Broombridge nesnesi, değeri `version`adlı bir özellik olan JSON nesnesi olan bir özellik `format` sahip OLMALıDıR.
`version` özelliği `"0.1"`değerine sahip OLMALıDıR.

### <a name="example"></a>Örnek ###

Bu bölüm bilgilendirme.

```yaml
format:                        # required
    version: "0.1"             # must match exactly
```

## <a name="integral-sets-section"></a>Integral kümeleri bölümü ##

Bu bölüm normatıve 'dir.

Broombridge nesnesi değeri bir JSON dizisi olan bir özellik `integral_sets` sahip OLMALıDıR.
`integral_sets` özelliğinin değerindeki her öğe, bu bölümün geri kalanında açıklandığı gibi bir integralleri kümesini açıklayan bir JSON nesnesi olmalıdır.
Bu bölümün geri kalanında, "integral kümesi nesnesi" terimi, Broombridge nesnesinin `integral_sets` özelliğinin değerindeki bir öğeye başvuracaktır.

Her integral kümesi nesnesi değeri JSON nesnesi olan bir özellik `metadata` sahip OLMALıDıR.
`metadata` değeri boş JSON nesnesi (yani, `{}`) olabilir veya uygulayıcısı tarafından tanımlanan ek özellikleri içerebilir.

### <a name="hamiltonian-section"></a>Hamiltonian bölümü ###

#### <a name="overview"></a>Genel Bakış ####

Bu bölüm bilgilendirme.

Her bir integral kümesi nesnesinin `hamiltonian` özelliği, belirli bir hisse dili hatası için Hamiltonian 'yi, tek ve iki gövdedeki terimleri gerçek sayıların seyrek dizileri olarak listeleyerek tanımlar.
Her bir integral kümesi nesnesi tarafından tanımlanan Hamiltonian işleçleri formu alır

$ $ H = \sum\_\{ı, j\}\sum\_{\sigma\in\\{\upok, \downok\\}} H\_\{ij\} a ^\{\dağılım\}\_{ı , \sigma} a\_{j, \sigma} + \frac{1}{2}\sum\_\{i, j, k, l\}\sum\_{\sigma, \rho\in\\{\upok, \downok\\}} h\_{ı , \sigma} a ^ \dağılım\_{k, \rho} a\_{l, \rho} a\_{j, \sigma}, $ $

Burada _ {ijkl} = (ij | KL) $ Mullikliksiz kuralına göre $h.

Netlik açısından, tek bir elektron dönemi

$ $ h_ {ij} = \int {\mathrm d} x \psi ^ *\_ı (x) \left (\frac{1}{2}\nabla ^ 2 + \ Sum\_{A} \frac{Z\_A} {| x-x\_A |}  \right) \psi\_j (x), $ $

ve iki elektron terimi

$ $ h\_\{ijkl\} = \iint \{\mathrm d\}x ^ 2 \psı ^\{\*\}\_ı (x\_1) \psi\_j (x\_1) \frac\{1\}\{\|x\_1-x\_2\|\}\psı\_k ^\{\*\}(x\_2) \psı\_l (x\_2).
$$

`integral_sets` özelliğinin her bir öğesinin [`basis_set` özelliğinin](#basis-set-object) açıklamamız bölümünde belirtildiği gibi, kullanılan temel işlevlerin gerçek değerli olduğunu açıkça varsaydık.
Bu, Hamiltonian 'ın gösterimini sıkıştırmak için terimler arasında aşağıdaki symmetries kullanmamızı sağlar.

$ $ h_ {ijkl} = h_ {ijlk} = h_ {JIKL} = h_ {jıld} = h_ {klij} = h_ {klji} = h_ {lkij} = h_ {lkji}.
$$


#### <a name="contents"></a>İçindekiler ####

Bu bölüm normatıve 'dir.

Her integral kümesi değeri bir JSON nesnesi olan bir özellik `hamiltonian` sahip OLMALıDıR.
`hamiltonian` özelliğinin değeri Hamiltonian nesnesi olarak bilinir ve bu bölümün geri kalanında açıklanan şekilde Özellikler `one_electron_integrals` ve `two_electron_integrals` OLMALıDıR.
Hamiltonian nesnesinin Ayrıca bir özelliği `particle_hole_representation`olabılır.
Varsa, `particle_hole_representation` değeri bu bölümün geri kalanında açıklanan biçimi izlemelidir.

##### <a name="one-electron-integrals-object"></a>Tek bir elektron Integrals nesnesi #####

Bu bölüm normatıve 'dir.

Hamiltonian nesnesinin `one_electron_integrals` özelliği, dizinleri iki tamsayı olan ve değerleri sayı olan bir seyrek dizi miktarı olmalıdır.
Her dönemde `i >= j``[i, j]` dizinler OLMALıDıR.

> NOTUN Bu, Hamiltonian 'nin hermitian olduğu olgunun bir sonucu olan $h _ {ij} = h_ {Ji} $ olan simetriyi yansıtır.


###### <a name="example"></a>Örnek ######

Bu bölüm bilgilendirme.

Şu seyrek dizi miktarı Hamiltonian $ $ H = \left (-5,0 (a ^\{\alger\}\_{1, \upoklu} bir\_{1, \upoklu} + bir ^\{\dağılım\}\_{1, \downok} a\_{1) temsil eder , \downok}) + 0,17 (bir ^\{\dağılım\}\_{2, \upoklu} bir\_{1, \upoklu} + bir ^\{\dağılım\}\_{1, \upoklu} +\_{2, \upoklu} + bir ^\{\dağılım\}\_{2 , \downok} bir\_{1, \downok} + bir ^\{\dağılım\}\_{1, \down\mathrm{ha}.} a\_{2, \downok}) \right)\\,
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


##### <a name="two-electron-integrals-object"></a>İki elektron Integrals nesnesi #####

Bu bölüm normatıve 'dir.

Hamiltonian nesnesinin `two_electron_integrals` özelliği, `index_convention`adlı bir ek özelliğe sahip bir seyrek dizi miktarı olmalıdır.
`two_electron_integrals` değerinin her bir öğesi dört Dizin IÇERMELIDIR.

Her `two_electron_integrals` özelliği bir `index_convention` özelliğine sahip OLMALıDıR.
`index_convention` özelliğinin değeri tablo 1 ' de listelenen izin verilen değerlerden biri OLMALıDıR.
`index_convention` değeri `mulliken`, sonra da `two_electron_integrals` seyrek dizi miktarının her öğesi için, bir Broombridge belgesi yükleyen bir Ayrıştırıcı, iki elektron işlecine eşit bir Hamiltonian terimi oluşturmalıdır $h _ {i, j, k, l} a ^ \abger_i a ^ \leger_j a_k a_l $ Burada $i $, $j $, $k $ ve $l $, tamsayı kümesi nesnesinin `n_electrons` özelliği tarafından belirtilen elektriklerin sayısına ve $h _ {i, j, k, l} $ ' ın seyrek dizi miktarının öğe `[i, j, k, l, h(i, j, k, l)]` olduğu, 1 ' den fazla tamsayı olması gerekır.

###### <a name="symmetries"></a>Symmetries ######

Bu bölüm normatıve 'dir.

Bir `two_electron_integrals` nesnesinin `index_convention` özelliği `mulliken`eşitse, dizinler `[i, j, k, l]` olan bir öğe varsa, `[i, j, k, l]`eşit olmadıkları takdirde aşağıdaki dizinler bulunmamalıdır:

- `[i, j, l, k]`
- `[j, i, k, l]`
- `[j, i, l, k]`
- `[k, l, i, j]`
- `[k, l, j, i]`
- `[l, k, j, i]`

> [!NOTE]
> `index_convention` özelliği seyrek bir Quantity nesnesi olduğundan, farklı öğelerde hiçbir dizin tekrarlanmayabilir.
> Özellikle, Dizin `[i, j, k, l]` olan bir öğe varsa, başka bir öğe bu dizinleri içeremez.


<!-- h_{ijkl} = h_{ijlk}=h_{jikl}=h_{jilk}=h_{klij}=h_{klji}=h_{lkji}. -->

###### <a name="example"></a>Örnek #######

Bu bölüm bilgilendirme.

Aşağıdaki nesne Hamiltonian 'yi belirtir

$ $ H = \frac12 \sum\_{\sigma, \rho\in\\{\upok, \downarrow\\}} \Biggr (1,6 a ^ {\abger}\_{1, \sigma} a ^ {\abger}\_{1, \rho} a\_{1, \rho} a\_{1, \sigma}-0,1 a ^ {\abger}\_{6 , \sigma} a ^ {\hanger}\_{1, \rho} a\_{3, \rho} a\_{2, \sigma}-0,1 a ^ {\abger}\_{6, \sigma} a ^ {\dağılım}\_{1, \rho} a\_{2, \rho} a\_{3 , \sigma}-0,1 a ^ {\hanger}\_{1, \sigma} a ^ {\abger}\_{6, \rho} a\_{3, \rho} a\_{2, \sigma}-0,1 a ^ {\abger}\_{1, \sigma} a ^ {\dağılım ger}\_{6, \rho} a\_{2 , \rho} a\_{3, \sigma} $ $ $ $-0,1 a ^ {\hanger}\_{3, \sigma} a ^ {\abger}\_{2, \rho} a\_{6, \rho} a\_{1, \sigma}-0,1 a ^ {\dağılım}\_{3, \sigma} a ^ {\gesger}\_{2 , \rho} a\_{1, \rho} a\_{6, \sigma}-0,1 a ^ {\abger}\_{2, \sigma} a ^ {\abger}\_{3, \rho} a\_{6, \rho} a\_{1, \sigma}-0,1 a ^ {\hanger}\_{2 , \sigma} a ^ {\hanger}\_{3, \rho} a\_{1, \rho} a\_{6, \sigma}\Biggr)\\, \textrm{Ha}.
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

Parçacık-delik gösterimi nesnesi, depolanan integrallerin, oluşturma ve Ayla ilgili operatörlerin, bir Hartree gibi kullanılan başvuru durumundan uzakta olduğunu belirten, parçacık delik gösterimine göre tanımlandığını belirtir – Fock durumu.
Nesne Isteğe bağlıdır.
Nesne belirtilmediyse Hamiltonian, parçacık deliği gösteriminde verilmemiş olarak yorumlanacaktır.
Varsa, `particle_hole_representation` değeri, dizinleri dört tamsayı olan ve değerleri bir sayı ve bir dize olan seyrek dizi miktarı nesnesi OLMALıDıR.
Her bir öğe değerinin dize kısmı yalnızca `'+'` karakterler içermelidir `'-'` ve bu terimin belirli bir faktörün, parçacık-delik temsilinde bir oluşturma veya yıllık bir operatör olması GEREKTIĞINI belirtir.  Örneğin `"-+++"`, site $i $ ve sitelerde oluşturulan parçacık $j, k $ ve $l $ konumunda oluşturulan bir deliğe yanıt verir.

> [!NOTE]
> `particle_hole_representation` değeri bir seyrek dizi miktarı nesnesi olduğundan, `unit` ve `format` özellikleri belirtilmelidir.
> Kabul edilebilir birimler dahil olmak üzere tablo 1 ' de listelenmiştir.
> `format` özelliği gereklidir ve Hamiltonian katlarının yoğun mı yoksa seyrek dizi olarak mı belirtilmediğini gösterir.
> Geçerli sürümde, tüm belirtilmemiş öğelerin $0 $ olduğunu yorumlamayı içeren yalnızca seyrek diziler desteklenir, ancak gelecekteki sürümlerde `format` özelliğinin ek değerleri için destek eklenebilir.

### <a name="initial-state-section"></a>İlk durum bölümü ###

İnitial_state_suggestion nesnesi, belirtilen Hamiltonian ile ilgilenilen ilk hisse durumlarını belirler. Bu nesne bir JSON `state` nesneleri dizisi olmalıdır.

#### <a name="state-object"></a>Durum nesnesi ####

Her durum, dolu orbitlerin üst konumunu temsil eder. Her durum nesnesinin bir dize içeren bir `label` özelliği OLMALıDıR. Her bir durum nesnesi bir temel durum dizisi ve bunların Normalleştirilmemiş yükseltilmiş tudes dizisini içeren bir `superposition` özelliğine sahip OLMALıDıR.

Örneğin, ilk durumlar $ $ \ket{G0} = \ket{G1} = \ket{G2} = (a ^ {\gger}\_{1) \upok} a ^ {\abger}\_{2, \upoklu} a ^ {\abger}\_{2, \downok}) \demet{0} $ $ $ $ \ket{E} = \frac{0.exe} (a ^ {\dağılım}\_{1 , \upoklu}a ^ {\abger}\_{2, \upoklu}a ^ {\gesger}\_{2, \downok}) + 0.2 (a ^ {\abger}\_{1, \upok} a ^ {\abger}\_{3, \upoklu} a ^ {\gesger}\_{2, \downok})} {\sqrt{| 0.1 | ^ 2 + | 0.2 | ^ 2}} \tus{0} $ $, temsil eden
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

Her integral kümesi nesnesinin bir `basis_set` özelliği olabılır.
Varsa, `basis_set` özelliğinin değeri, `type` ve `name`iki özelliği olan bir nesne olmalıdır.

`basis_set` özelliğinin değeri ile tanımlanan temel işlevler gerçek değerli olmalıdır.

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
