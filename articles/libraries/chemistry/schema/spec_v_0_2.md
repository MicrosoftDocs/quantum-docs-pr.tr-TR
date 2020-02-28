---
title: Broombridge şema belirtimi (ver 0,2)
description: Microsoft hisse dili Mistry kitaplığı için broombridge hisse Kimya şeması v
author: guanghaolow
ms.author: gulow@microsoft.com
ms.date: 05/28/2019
ms.topic: article
uid: microsoft.quantum.libraries.chemistry.schema.spec_v_0_2
ms.openlocfilehash: df7e651b7d32e672c6e83346ff603132bd55c1a2
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907282"
---
# <a name="broombridge-specification-v02"></a>Broombridge belirtimi v 0.2 #

"", "" Gerekli değildir "," gerekli "," Bu "," zorunlu değildir "," durum ",", "ve" Isteğe bağlı "anahtar sözcükleri, [RFC 2119](https://tools.ietf.org/html/rfc2119)' de açıklandığı gibi yorumlanmalıdır.

"NOTE", "ıNFORMATION" veya "WARNING" başlıklı tüm kenar çubuğu bilgilendirici.

## <a name="introduction"></a>Giriş ##

Bu bölüm bilgilendirme.

Broombridge belgelerinin, hisse simülasyonu ve programlama araç zincirlerini kullanarak, işleme için hisse deneçlerinde simülasyon sorunlarının örneklerine iletişim kurması amaçlanmıştır.

## <a name="serialization"></a>Getir ##

Bu bölüm normatıve 'dir.

Bir Broombridge belgesi 2,2 [4627](https://tools.ietf.org/html/rfc4627) , bir JSON nesnesini temsil eden bir [YAML 1,2 belgesi](http://yaml.org/spec/) olarak serileştirilmelidir.
YAML 'ye seri hale getirilen nesne, değeri `"https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/qchem-0.2.schema.json"`olan bir özellik `"$schema"` sahip OLMALıDıR ve JSON şeması taslağına göre geçerli olmalıdır-06 belirtimleri [[1](https://tools.ietf.org/html/draft-wright-json-schema-01), [2](https://tools.ietf.org/html/draft-wright-json-schema-validation-01)].

Bu belirtimin geri kalanı için, "Broombridge nesnesi", bir Brombridge YAML belgesinden Serisi kaldırılan JSON nesnesine başvuracaktır.

Aksi belirtilmedikçe, nesneler bu belgede açıkça belirtilenlerin ötesinde ek özelliklere sahip olmamalıdır.

## <a name="additional-definitions"></a>Ek tanımlar ##

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
`version` özelliği `"0.2"`değerine sahip OLMALıDıR.

### <a name="example"></a>Örnek ###

Bu bölüm bilgilendirme.

```yaml
format:                        # required
    version: "0.2"             # must match exactly
```

## <a name="problem-description-section"></a>Sorun açıklaması bölümü ##

Bu bölüm normatıve 'dir.

Broombridge nesnesi değeri bir JSON dizisi olan bir özellik `problem_description` sahip OLMALıDıR.
`problem_description` özelliğinin değerindeki her öğe, bu bölümün geri kalanında açıklandığı gibi bir integralleri kümesini açıklayan bir JSON nesnesi olmalıdır.
Bu bölümün geri kalanında, "sorun açıklaması nesnesi" terimi, Broombridge nesnesinin `problem_description` özelliğinin değerindeki bir öğeye başvuracaktır.

Her sorun açıklaması nesnesinin değeri JSON nesnesi olan bir özellik `metadata` olması gerekır.
`metadata` değeri boş JSON nesnesi (yani, `{}`) olabilir veya uygulayıcısı tarafından tanımlanan ek özellikleri içerebilir.

### <a name="hamiltonian-section"></a>Hamiltonian bölümü ###

#### <a name="overview"></a>Genel Bakış ####

Bu bölüm bilgilendirme.

Her bir sorun açıklama nesnesinin `hamiltonian` özelliği, belirli bir hisse dili yanılma sorunu için Hamiltonian 'yi, tek ve iki gövdedeki terimleri gerçek sayıların seyrek dizileri olarak listeleyerek açıklar.
Her sorun açıklaması nesnesi tarafından tanımlanan Hamiltonian işleçleri formu alır

$ $ H = \sum\_\{ı, j\}\sum\_{\sigma\in\\{\upok, \downok\\}} H\_\{ij\} a ^\{\dağılım\}\_{i, \sigma} a\_{j, \sigma} + \frac{1}{2}\sum\_\{i, j, k, l\}\sum\_{\sigma, \rho\in\\{\upok, \downok\\}} H\_{ı , \sigma} a ^ \dağılım\_{k, \rho} a\_{l, \rho} a\_{j, \sigma}, $ $\_

Burada _ {ijkl} = (ij | KL) $ Mullikliksiz kuralına göre $h.

Netlik açısından, tek bir elektron dönemi

$ $ h_ {ij} = \int {\mathrm d} x \psi ^ *\_ı (x) \left (\frac{1}{2}\nabla ^ 2 + \ Sum\_{A} \frac{Z\_A} {| x-x\_A |}  \right) \psi\_j (x), $ $

ve iki elektron terimi

$ $ h\_\{ijkl\} = \iint \{\mathrm d\}x ^ 2 \psı ^\{\*\}\_ı (x\_1) \psi\_j (x\_1) \frac\{1\}\{\|x\_1-x\_2\|\}\psi\_k ^\{\*\}(x\_2) \psı\_l (x\_2).
$$

`integral_sets` özelliğinin her bir öğesinin [`basis_set` özelliğinin](#basis-set-object) açıklamamız bölümünde belirtildiği gibi, kullanılan temel işlevlerin gerçek değerli olduğunu açıkça varsaydık.
Bu, Hamiltonian 'ın gösterimini sıkıştırmak için terimler arasında aşağıdaki symmetries kullanmamızı sağlar.

$ $ h_ {ijkl} = h_ {ijlk} = h_ {JIKL} = h_ {jılb} = h_ {klij} = h_ {klji} = h_ {lkij} = h_ {lkji}.
$$


#### <a name="contents"></a>İçindekiler ####

Bu bölüm normatıve 'dir.

Her sorun açıklaması nesnesinin değeri JSON nesnesi olan bir özellik `hamiltonian` olması gerekır.
`hamiltonian` özelliğinin değeri Hamiltonian nesnesi olarak bilinir ve bu bölümün geri kalanında açıklanan şekilde Özellikler `one_electron_integrals` ve `two_electron_integrals` OLMALıDıR.

Her sorun açıklaması nesnesinin değeri basit bir miktar nesnesi olan bir özellik `coulomb_repulsion` olması gerekır.
Her sorun açıklaması nesnesinin değeri basit bir miktar nesnesi olan bir özellik `energy_offet` olması gerekır.
> NOTUN `coulomb_repulsion` ve `energy_offet` değerleri birlikte eklenen Hamiltonian 'nin kimlik terimini yakalar.

##### <a name="one-electron-integrals-object"></a>Tek bir elektron Integrals nesnesi #####

Bu bölüm normatıve 'dir.

Hamiltonian nesnesinin `one_electron_integrals` özelliği, dizinleri iki tamsayı olan ve değerleri sayı olan bir seyrek dizi miktarı olmalıdır.
Her dönemde `i >= j``[i, j]` dizinler OLMALıDıR.

> NOTUN Bu, Hamiltonian 'ın hermitian olduğu olgunun bir sonucu olan $h _ {ij} = h_ {Ji} $ olan simetriyi yansıtır.


###### <a name="example"></a>Örnek ######

Bu bölüm bilgilendirme.

Şu seyrek dizi miktarı Hamiltonian $ $ H = \left (-5,0 (bir ^\{\dağılım\}\_{1, \upoklu} bir\_{1, \upoklu} + bir ^\{\dağılım\}\_{1, \downok} a\_{1, \downok}) + 0,17 (bir ^\{\hanger\}\_{2, \upoklu} +\_{1, \upoklu} + bir ^\{\dağılım\}\_{1, \upoklu} +\_{2, \upoklu} + a ^\{\dağılım\}\_{2 , \downok} bir\_{1, \downok} + bir ^\{\dağılım\}\_{1, \down\mathrm{ha}.} a\_{2, \downok}) \right)\\,
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
`index_convention` değeri `mulliken`, sonra da `two_electron_integrals` seyrek dizi miktarının her bir öğesi için, bir Broombridge belgesi yükleyen bir ayrıştırıcıda bir Hamiltonian teriminin iki elektron işlecine eşit olması gerekir $h _ {i, j, k, l} a ^ \ dagger_i bir ^ \ dagger_j a_k a_l $, burada $i $, $j $, $k $ ve $l $ değeri en az 1 tamsayı olmalıdır ve $h _ {i, j, k, l} $, seyrek dizi miktarının öğe `[i, j, k, l, h(i, j, k, l)]`.

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

$ $ H = \frac12 \sum\_{\sigma, \rho\in\\{\upok, \downarrow\\}} \Biggr (1,6 a ^ {\abger}\_{1, \sigma} a ^ {\abger}\_{1, \rho} a\_{1, \rho} a\_{1, \sigma}-0,1 a ^ {\abger}\_{6, \sigma} a ^ {\abger}\_{1, \rho} a\_{3, \rho} a\_{2, \sigma}-0,1 a ^ {\abger}\_{6, \sigma} a ^ {\dağılım ger}\_{1, \rho} a\_{2 , \rho} a\_{3, \sigma}-0,1 a ^ {\hanger}\_{1, \sigma} a ^ {\abger}\_{6, \rho} a\_{3, \rho} a\_{2, \sigma}-0,1 a ^ {\abger}\_{1, \sigma} a ^ {\dağılım}\_{6, \rho} a\_{2, \rho} a\_{3, \sigma} $ $ $ $-0,1 a ^ {\hanger}\_{3, \sigma} a ^ {\dağılım}\_{2, \rho} a\_{6, \rho} a\_{1, \sigma}-0,1 a ^ {\hanger}\_{3 , \sigma} a ^ {\abger}\_{2, \rho} a\_{1, \rho} a\_{6, \sigma}-0,1 a ^ {\abger}\_{2, \sigma} a ^ {\dağılım}\_{3, \rho} a\_{6, \rho} a\_{1, \sigma}-0,1 a ^ {\abger}\_{2, \sigma} a ^ {\dağılım}\_{3, \rho} a\_{1, \rho} a\_{6, \sigma}\Biggr)\\, \Textrm{ha}.
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

### <a name="initial-state-section"></a>İlk durum bölümü ###

Bu bölüm normatıve 'dir.

Değeri bir JSON dizisi olan `initial_state_suggestion` nesnesi, belirtilen Hamiltonian ile ilgilenilen ilk hisse kazanç durumlarını belirtir. `initial_state_suggestion` özelliğinin değerindeki her öğe, bu bölümün geri kalanında açıklandığı gibi bir hisse miktarını açıklayan bir JSON nesnesi olmalıdır.
Bu bölümün geri kalanında, "durum nesnesi" terimi, Broombridge nesnesinin `initial_state_suggestion` özelliğinin değerindeki bir öğeye başvuracaktır.

#### <a name="state-object"></a>Durum nesnesi ####

Bu bölüm normatıve 'dir.

Her durum nesnesinin bir dize içeren bir `label` özelliği OLMALıDıR. Her durum nesnesinin bir `method` özelliği OLMALıDıR. `method` özelliğinin değeri, tablo 3 ' te listelenen izin verilen değerlerden biri OLMALıDıR.
Her durum nesnesi, değeri bir basit miktar nesnesi olması gereken bir özellik `energy` sahip olabilir.

`method` özelliğinin değeri `sparse_multi_configurational`ise, State nesnesinin bir temel durum dizisi ve bunların Normalleştirilmemiş yükseltilmiş tudes dizisini içeren bir `superposition` özelliğine sahip olması gerekır.

Örneğin, ilk durumlar $ $ \ket{G0} = \ket{G1} = \ket{G2} = (a ^ {\abger}\_{1, \upoklu} a ^ {\gger}\_{2, \upok} a ^ {\abger}\_{2, \downok}) \ayraç{0} $ $ $ $ \ket{E} = \frac{0.exe} (bir ^ {\gesger}\_{1, \upoklu} a ^ {\abger}\_{2, \upoklu} a ^ {\gesger}\_{2, \downok}) + 0.2 (a ^ {\dağılım}\_{1, \upoklu}a ^ {\abger}\_{3, \upoklu}\_{2, \downok})} {\sqrt{| 0.1 | ^ 2 + | 0.2 | ^ 2}} \demet{0}$ $ Burada $ \ket{E} $ enerji $0,987 \textrm{Ha} $, tarafından temsil edilir
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

`method` özelliğinin değeri `unitary_coupled_cluster`ise, durum nesnesinin değeri JSON nesnesi olan bir `cluster_operator` özelliğine sahip olması gerekir.
JSON nesnesi, değeri temel bir durum olan bir `reference_state` özelliğine sahip OLMALıDıR.
JSON nesnesi, değeri bir tek gövde kümesi işleçleri ve bunların yükseltilmiş tudes dizisi olan bir `one_body_amplitudes` özelliğine sahip olabılır.
JSON nesnesi, değeri iki boyutlu küme işleçleri dizisi olan bir `two_body_amplitudes` özelliğine ve bunların yükseltilmiş tudes 'lerine sahip olabılır.
temel durumlardan oluşan bir dizi ve bunların Normalleştirilmemiş yükseltilmiş tudes 'i içerir.

Örneğin, $ $ \ket{\Text{Reference}} = (a ^ {\abger}\_{1, \upoklu}\_{| {\hanger} {2, \upbir ^ {\gesger}\_{2, \downbir}) \ket{0}, $ $

$ $ \ket{\text{UCCSD}} = e ^ {T-T ^ \dagger}\ket{\Text{Reference}}, $ $

$ $ T = 0,1 a ^ {\dağılım}\_{3, \upoklu} a\_{2, \downok} + 0,2 a ^ {\hanger}\_{2, \upok} a\_{2, \downok}-0,3 a ^ {\dağılım}\_{1, \upoklu} a ^ {\abger}\_{3, \downoklu} bir\_{3, \upoklu} $ $ tarafından temsil edilir\_
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

#### <a name="basis-set-object"></a>Taban kümesi nesnesi ####

Bu bölüm normatıve 'dir.

Her sorun açıklaması nesnesinin bir `basis_set` özelliği olabılır.
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

### <a name="table-3-allowed-state-methods"></a>Tablo 3. İzin verilen durum metotları ###

Bu bölüm normatıve 'dir.

Bir durum yöntemini belirten herhangi bir dize aşağıdakilerden biri OLMALıDıR:

- `sparse_multi_configurational`
- `unitary_coupled_cluster`

Bu bölüm bilgilendirme.

Ek durum yöntemleri bu belirtimin gelecek sürümlerinde bulunabilir.
