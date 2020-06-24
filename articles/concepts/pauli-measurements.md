---
title: Pauli ölçümleri
description: Tek ve Multi-qubit Pauli ölçüm işlemleriyle nasıl çalışacağınızı öğrenin.
author: QuantumWriter
uid: microsoft.quantum.concepts.pauli
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
no-loc:
- $
- $
- $
- $
- $
- $
- '\cdots'
- bmatrix
- '\ddots'
- '\equiv'
- '\sum'
- '\begin'
- '\end'
- '\sqrt'
- '\otimes'
- '{'
- '}'
- '\text'
- '\phi'
- '\kappa'
- '\psi'
- '\alpha'
- '\beta'
- '\gamma'
- '\delta'
- '\omega'
- '\bra'
- '\ket'
- '\boldone'
- '\\\\'
- '\\'
- =
- '\frac'
- '\text'
- '\mapsto'
- '\dagger'
- '\to'
- "\begin{cases}"
- "\end{cases}"
- '\operatorname'
- '\braket'
- '\id'
- '\expect'
- '\defeq'
- '\variance'
- '\dd'
- '&'
- "\begin{align}"
- "\end{align}"
- '\Lambda'
- '\lambda'
- '\Omega'
- '\mathrm'
- '\left'
- '\right'
- '\qquad'
- '\times'
- '\big'
- '\langle'
- '\rangle'
- '\bigg'
- '\Big'
- '|'
- '\mathbb'
- '\vec'
- '\in'
- '\texttt'
- '\ne'
- <
- '>'
- '\leq'
- '\geq'
- ~~
- "~"
- "\begin{bmatrix}"
- "\end{bmatrix}"
- '\_'
ms.openlocfilehash: 7f10c4ad5eb325da97552d60ff47ea89a699f08d
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85269482"
---
# <a name="pauli-measurements"></a>Pauli ölçümleri

Önceki tartışmalarda hesaplama tabanlı ölçümlere odaklandık.
Aslında, notational perspektifinden, işlem tabanlı ölçümlerde hızlı bir şekilde ifade etmek için uygun olan, hisse kullanımı açısından oluşan diğer yaygın ölçümler vardır.
Q # ile çalışırken, çalıştıracağınız en yaygın ölçüm türleri *Pauli ölçümleri*olacaktır, bu da diğer tabanlarda ölçümleri dahil etmek için hesaplama tabanlı ölçümleri genelleştirir ve farklı qugeler arasında eşlik sağlar.
Bu gibi durumlarda, bir Pauli işlecinin, genel olarak $X, Y, Z $ veya $Z \otimes Z, x \otimes x, x Y vb. gibi bir operatör \otimes $ ölçmesi konusunda tartışmak yaygındır.

> [!TIP]
> Q # içinde, Multi-qubit Pauli işleçleri genellikle türündeki diziler tarafından temsil edilir `Pauli[]` .
> Örneğin, $X \otimes Y. i 'yi göstermek için $ , diziyi kullanabilirsiniz `[PauliX, PauliZ, PauliY]` .

Pauli işleçleri açısından ölçüm ele alınması, özellikle de hisse hata düzeltmesinin alt alanında ortaktır.
Q # ' da benzer bir kuralı izliyoruz; Artık ölçümlerin bu alternatif görünümünü açıkladık.

Pauli ölçüsünün nasıl düşündüğünün ayrıntılarına geçmeden önce, hisse bir bilgisayar içinde tek bir qubit 'in ne ölçmeye yönelik olduğunu düşünmek yararlı olur.
$N $ -qubit hisse anımız olduğunu düşünün; ardından bir qubit, durumun içinde olabilecek $2 ^ n $ olasılıklarının yarısını hemen ölçmelidir.
Diğer bir deyişle, ölçüm, hisse durumunu iki yarım boşluktan birine göre projeler.
Bu ıntut 'i yansıtmak için ölçüm hakkında düşündüğünüzden bahsede genelleştireceğiz.

Bu alt boşlukların öz belirlemek için, bunları açıklamak için bir dile ihtiyacımız var.
İki alt boşluğu tanımlamanın bir yolu, kural tarafından $ \pm 1 olacak şekilde yalnızca iki benzersiz eigenvalues içeren bir matrisi belirtmektir $ .
Alt boşlukları bu şekilde açıklayan basit bir örnek için $Z göz önünde bulundurun $ :

$ $ \begin{align}
  Z & = \begin{ bmatrix } 1 & 0 \\ \\ 0 &-1 \ End{ bmatrix } .
\end{align}
$$

Pauli-$Z matrisinin köşegen öğelerini okuyarak, " $ $ } } karşılık gelen eigenvalues $ \pm 1 ile birlikte iki eigenvektörün, $ \ket{0 $ ve $ \ket{1 $ $Z olduğunu görebiliriz $ .
Bu nedenle, qubit ' i ölçyoruz ve elde ediyorsanız `Zero` ($ \ket{0 $ durumuna karşılık gelir } ), qubitin durumunun $Z işlecinin $ + 1 $ eigenstate olduğunu biliyoruz $ .
Benzer şekilde, elde etmemiz durumunda `One` , qubitimizin durumunun bir $-1 $ eigenstate $Z olduğunu biliyoruz $ .
Bu işlem, Pauli ölçümlerinin dilinde "ölçüm Pauli $Z" olarak adlandırılır $ ve hesaplama tabanlı ölçüm gerçekleştirmeye tamamen eşdeğerdir.

\times $ $Z bir Unitary dönüştürmesi olan $2 2 matrisi $ de bu ölçütleri karşılar.
Diğer bir deyişle, $ $ $ \pm 1 eigenvektörlerinde bir ölçünün iki sonucunu tanımlayan bir matris vermek için $U başka bir Unitary Z u olan matris $A de kullanabiliriz $ .
Pauli ölçülerinin gösterimi, $X, Y, Z $ ölçümlerini bir qubitden bilgi elde etmek için yaptığı eşdeğer ölçümler olarak tanımlayarak bu Unitary denklik 'e başvurur.
Bu ölçümler, kolaylık sağlamak için aşağıda verilmiştir.


|Pauli ölçümü  |Unitary dönüştürmesi  |
|-------------------|------------------------|
| $Z$               | $ \ cıvabitti$             |
| $X$               | $H$                    |
| $Y$               | $HS ^ {\dağılım}$         |

Diğer bir deyişle, bu dil kullanıldığında, "Measure $Y $ ", ^ \linger $HS uygulama $ ve sonra hesaplama temelinde ölçme ile eşdeğerdir; burada, [`S`](xref:microsoft.quantum.intrinsic.s) bazen "aşama kapısı" olarak adlandırılan ve Unitary matrisi tarafından benzetilen bir iç hisse dır

$ $ \begin{align}
    S = \begin{bmatrix}
        1 & 0 \\ \\ 0 & ı \end{ bmatrix } .
\end{align}
$$

Ayrıca, hisse için $HS ^ \dağılım $ $Z ve sonra da $ aşağıdaki işlem ile eşdeğer olacak şekilde ölçkla eşdeğerdir `Measure([PauliY], [q])` :

```Q#
operation MeasureY(qubit : Qubit) : Result {
    mutable result = Zero;
    within {
        H(q);
        Adjoint S(q);
    } apply {
        set result = M(q);
    }
    return result;
}
```

Doğru durum daha sonra hesaplama temeline geri dönüşümle, bu da hisse $SH. $ Yukarıdaki kod parçacığında, işlem temelinde yapılan dönüşüm, blok kullanılarak otomatik olarak işlenir `within … apply` .

Q # ' da, sonuç---, durum---ile etkileşimde bulunarak ayıklanan klasik bilgiler, `Result` \\ } } \\ sonucun Pauli işlecinin $ (-1) ^ j eigenin ' de olup olmadığını belirten bir değer olan $j \In {\Texttt{Zero, \Texttt{One} $ değeri tarafından verilir $ .


## <a name="multiple-qubit-measurements"></a>Birden çok qubit ölçümleri

Multi-qubitpauli işleçlerinin ölçümleri benzer şekilde, şöyle görüldüğü gibi tanımlanmıştır:

$ $ Z \otimes z = \begin{ bmatrix } 1 &0 &0&0 \\\\ 0 & -1&0&0 \\\\ 0&0 & -1 \\\\ \end{bmatrix}&0&0&1.
$$

Bu nedenle, iki Pauli-$Z işleçlerinin Tensor ürünleri, $ $ + 1 $ ve $-1 eigenvalues içeren iki boşluktan oluşan bir matris oluşturur $ .
Tek qubit durumunda olduğu gibi, her ikisi de erişilebilir vektör alanının yarısını $ + 1 $ eigenspace ve $-1 eigenspace 'e ait olan yarı boşluk anlamına gelir $ .
Genel olarak, Pauli-$Z işleçlerinin herhangi bir tencursor ürünüyle $ ve kimliğin buna uda ulaşana kadar, Tensor ürünü tanımından kolayca bakmak kolaydır.
Örneğin,

$ $ \begin{align}
    Z \otimes \cıvadone = \begin{bmatrix}
        1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 &-1 & 0 0 & 0 \\ \\ & 0 &-1 \end{ bmatrix } .
\end{align}
$$

Daha önce olduğu gibi, bu tür Matrislerin her türlü Unitary dönüştürmesi, $ \pm 1 eigenvalues ile etiketlenmiş iki yarı boşluğu da açıklar $ .
Örneğin, $X \otimes X = H \otimes h (z \otimes z) h h, \otimes $ $Z = HXH olan kimlikten $ .
Tek qubit durumuna benzer şekilde, tüm iki-qubit Pauli-ölçümleri, \otimes $ $4 \times 4 $ unitary $U için $U ^ \dağılım (Z \ID) U olarak yazılabilir $ . Aşağıdaki tablodaki dönüşümleri numaralandırıyoruz.

> [!NOTE]
> Aşağıdaki tabloda, $ } $ \begin{align matrisini göstermek için $ \operatorname{Swap $ kullanıyoruz}
>     \operatorname{SWAP } & = \left (\begin{Matrix}
>         1 & 0 & 0 & 0 \\ \\ 0 & 0 & 1 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 & 1 \ End{Matrix } \ right) \end{ALIGN}
> $ $ iç işlemin benzetimini yapmak için kullanılır [`SWAP`](xref:microsoft.quantum.intrinsic) .

|Pauli ölçümü     |Unitary dönüştürmesi  |
|----------------------|------------------------|
| $Z \otimes \ bolbitti$ | $ \ cıvalanma \otimes \cıvabitti$ |
| $Z \otimes \ cıvabitti$ | $ \ cıvabitti \otimes \ cıvabitti$ |
| $X \otimes \ cıvabitti$ | $H \otimes \ cıvabitti$ |
| $Y \otimes \ cıvabitti$ | $HS ^ \dağılım \otimes \ cıvataleti$ |
| $ \ cıvabitti \otimes Z$ | $ \operatorname{SWAP}$ |
| $ \ cıvabitti \otimes X$ | $ (H \otimes \ cıvabitti) \operatorname{swap}$ |
| $ \ bolbitti \otimes Y$ | $ (HS ^ \dağılım \otimes \ cıvabitti) \operatorname{swap}$ |
| $Z \otimes Z$ | $ \operatorname{CNOT } \_ {10}$ |
| $X \otimes Z$ | $ \operatorname{CNOT } \_ {10 } (H \otimes \ cıvabitti) $ |
| $Y \otimes Z$ | $ \operatorname{CNOT } \_ {10 } (HS ^ \dağılım \otimes \ cıvabitti) $ |
| $Z \otimes X$ | $ \operatorname{CNOT } \_ {10 } (\ cıvabitti \otimes H) $ |
| $X \otimes X$ | $ \operatorname{CNOT } \_ {10 } (h \otimes h) $ |
| $Y \otimes X$ | $ \operatorname{CNOT } \_ {10 } (HS ^ \Hanger \otimes H) $ |
| $Z \otimes Y$ | $ \operatorname{CNOT } \_ {10 } (\ cıvabitti \otimes HS ^ \ dağılım) $ |
| $X \otimes Y$ | $ \operatorname{CNOT } \_ {10 } (H \otimes HS ^ \ dağılım) $ |
| $Y \otimes Y$ | $ \operatorname{CNOT } \_ {10 } (HS ^ \dağılım \otimes HS ^ \ dağılım) $ |

Burada, [`CNOT`](xref:microsoft.quantum.intrinsic.cnot) işlem aşağıdaki nedenlerden dolayı görüntülenir.
$ \Cıvadone matrisini içermeyen her Pauli ölçümü, $ \otimes Yukarıdaki düşünyana $Z Z 'ye kadar bir Unitary 'e eşittir $ .
$Z Z 'nin eigenvalues \otimes değeri $ yalnızca her bir hesaplama tabanlı vektörü oluşturan qubits 'e bağlıdır ve denetlenen işlemler bu eşliği hesaplamak ve ilk bit içinde saklamak için işlem yapar.
İlk bit ölçülene kadar, elde edilen yarı alanın kimliğini kurtararak Pauli işlecinin ölçülesiyle eşdeğerdir.

Bir ek notta: $Z Z ölçüyü, \otimes $ ardışık olarak $Z \otimes \mathbb{1 } $ ve sonra $ \mathbb{1 \otimes Z ile aynı olduğunu varsaymaya rağmen } $ Bu varsayım yanlış olur.
Bunun nedeni, $Z \otimes Z $ 'yi Bu işleçlerin $ + 1 $ veya $-1 $ eigenstate ' i ile aynı şekilde ölçmeye yönelik bir durumdur.
$Z \otimes \mathbb{1 } $ ve sonra $ \mathbb{1 } \otimes z $ , ilk başta $Z \mathbb{1 $ bir yarı alana \otimes } ve sonra da $ \mathbb{1 } \otimes z 'nin bir yarı alanına kadar hisse $ Dört hesaplama tabanlı vektör olduğu için, her iki ölçüm de durum, durumu çeyrek boşluk olarak azaltır ve bu nedenle tek bir hesaplama tabanlı vektöre düşürür.

## <a name="correlations-between-qubits"></a>Qubits arasında correlations
$X X veya $Z Z gibi Pauli matrislerinin tencursor ürünlerini ölçmeye yönelik başka bir yöntem \otimes $ \otimes $ de, bu ölçümlerin iki qubit arasındaki eş ilişkilerdeki bilgilere bakmasına olanak tanır.
Ölçüm $X \otimes \ID $ , ilk qubit içinde yerel olarak saklanan bilgilere bakmanızı sağlar.
Her iki ölçüm türü de hisse bilgi işlem ortamında eşit olmakla birlikte, önceki bir deyişle hisse bilgi işlem gücünü güçlendirin.
Bu, bilgi işlem ortamında, genellikle öğrenmek istediğiniz bilgilerin herhangi bir tek qubit içinde depolanmadığını, ancak aynı anda tüm qubits 'de yerel olarak depolanmadığını ve bu bilgileri yalnızca bir eklem ölçümü (örn. $Z \otimes Z) aracılığıyla arayarak $ Bu bilgilerin bildirim haline gelmesini gösterir.

Örneğin, hata düzeltilirken, korumamıza çalıştığımız durum hakkında hiçbir şey öğrenirken bir hata oluştuğunu öğrenmek istiyoruz.
[Bit-çevir kod örneği](https://github.com/microsoft/Quantum/tree/master/samples/error-correction/bit-flip-code) , $Z \otimes z \otimes \ID $ ve $ \ ID \otimes $ z
<!-- TODO: change this to a link to the samples browser as soon as the bit-flip code sample is on-boarded. -->

$X \otimes Y \Otimes Z \otimes \cıvadone gibi rastgele Pauli işleçleri $ de ölçülebilir.
Pauli işleçlerinin tüm tencursor ürünlerinin her biri yalnızca iki eigenvalues $ \pm 1 $ ve her iki eigenon, vektör alanının tamamının yarı alanlarını oluşturur.
Bu nedenle, yukarıda belirtilen gereksinimlere başvurırlar.

Q # içinde, $ ölçüm, işaret $ (-1) ^ j olan egenspace 'te bir sonuç alıyorsa, bu tür ölçümler $j döndürür $ .
Bu tür işleçler, diagonalizing $ $ ve $ \ıd $Z 'nin bir Tensor ürünü olarak, işlemi ifade etmek için gereken $U geçidini açıklamaya yönelik, denetimli olmayan kapıları ve temel Dönüştürmelere yönelik bir yerleşik özellik olarak, Pauli ölçümleri olması yararlı olacaktır $ . Önceden tanımlanmış Bu ölçülerden birini yapmak istediğinizi belirleyebilmeksizin, bir hesaplama tabanlı ölçüm için gerekli bilgileri sağlamak üzere temelinizi nasıl dönüştürebileceğinizi merak etmeniz gerekmez.
S #, sizin için gerekli tüm temel dönüştürmeleri otomatik olarak işler.
Daha fazla bilgi için bkz [`Measure`](xref:microsoft.quantum.intrinsic.measure) . ve [`MeasurePaulis`](xref:microsoft.quantum.measurement.measurepaulis) işlemleri.

## <a name="the-no-cloning-theorem"></a>Kopyalama olmayan bu Üyeler

Hisse bilgileri güçlüdür.
Faktör numaraları gibi harika şeyleri en iyi bilinen klasik algoritmalardan daha hızlı bir şekilde gerçekleştirebilmemizi veya düzgün bir şekilde benzetilmesini sağlayan bağıntılı elektron sistemlerinin verimli bir şekilde benzetimini yapmanızı sağlar.
Ancak, hisse bilgi işlem gücüyle ilgili sınırlamalar vardır.
Bu tür bir sınırlama, *hiçbir kopyalama olmayan kopya*tarafından verilir.

Kopyalama yok, hiçbir şekilde adlandırılır.
Genel hisse durumlarının bir hisse bilgisayar tarafından kopyalanmasına izin vermez.
Bunların kanıtı, genel olarak basittir.
Bu konu başlığı altındaki bir çok teknik olmadığından, bu durum, hiçbir ek yardımcı qubit, kapsamımızda (bir hesaplama sırasında boş alan için kullanılan ve kolayca kullanıldığından ve Q # ' da yönetilir, bkz. [ödünç alınan qubit](xref:microsoft.quantum.guide.qubits#borrowed-qubits)) için çok fazla teknik değildir.

Bu tür bir hisse bilgisayar için kopyalama işlemi bir Unitary matrisi tarafından açıklanmalıdır.
Klonlamamız denendiğimiz hisse TI durumunu bozduğundan ölçüme izin vermeiyoruz.
Kopyalama işleminin benzetimini yapmak için, Unitary matrisinin $ $ U \ ayraç \ { PSI } \ket{0 } = \ demet { \ PSI } \ demet { \ PSI özelliğine sahip olması için kullanılmasını istiyoruz}
$ $ herhangi bir durum için $ $ { \psı } $.
Matris çarpın doğrululululu daha sonra tüm ikinci hisse için $ { \tus\phi } $,

$ $ \begin{align}
    U \left [\frac{1 } {\sqrt{2 } } \left (\ayraç { \ Fi } + \ ayraç { \ PSI } \ right) \ right] \ket{0}
    & = \frac{1 } {\sqrt{2 } } U \ket { } \ph\ket{0}
      + \frac{1 } {\sqrt{2 } } U \ket { \psı } \ket{0 } \\ \\ & = \frac{1 } {\sqrt{2 } } \left (\ket { \ Fi } \ { } { } {}
        \right) \\ \\ & \a \left (\frac{1 } {\sqrt{2 } } \left ( { \tus\fi } + { \tus\psı } \ right) \right) \otimes \left (\frac{1 } {\sqrt{2 } } \left ( { \tus\phi } + { \tus\psı } \ right) \ right).
\end{align}
$$

Bu, kopya olmaması gereken temel ıntutiye sahiptir: bilinmeyen bir hisse lık durumunu kopyalayan tüm cihazlar, kopyalayan durumların en az bir kısmında yer almalıdır.
Cloner 'ın giriş durumunda herhangi bir şekilde hareket ederken, bu durum yardımcı qubits 'in eklenmesi ve ölçümü aracılığıyla ihlal edilebilir, ancak bu tür etkileşimler Ayrıca sistem hakkında ölçüm istatistikleri üzerinden bilgi sızıntısına ve bu gibi durumlarda tam kopyalamayı önler.
Daha fazla [bilgi için](xref:microsoft.quantum.more-information), kopyalamanın olmaması için daha kapsamlı bir kanıt için bkz..

Hisse uygun olmayan bir şekilde büyük ölçüde bir şekilde klonlamanız için, parça olmayan bir bilgi işlem için önemli değildir. bu nedenle, hisse durumlarından daha fazla bilgi edinebilirsiniz.
Aslında, Heısenberg 'nin vaunbelirsizlik ilkesini ihlal edebilirsiniz.
Alternatif olarak, bir karmaşık hisse dağılımla tek bir örnek almak ve yalnızca bir örnekten bu dağıtım hakkında bilgi edinmek istediğiniz her şeyi öğrenmek için en uygun bir Cloner kullanabilirsiniz.
Bu, bir para ve gözbaşları ters çevirmiş ve sonra yanıt vermeye yönelik bir arkadaşla karşılaşmanız durumunda, "Ah 'nin dağılımı $p = 0.512643 \ lnoktalar!" ile Bernoulli olmalıdır. $  Bu tür bir ifade, bir veya daha fazla bilgi olmadan dağıtımı kodlamak için gereken pek çok bilgi sağlamadığı için sensik olmayan bir ifadedir.
Benzer şekilde, önceki bilgiler olmadan, bu tür kodların bir kısmını $p bilmeden hazırlayamazmız gibi, bir hisse bilgisini kusursuz bir şekilde klonlayamıyoruz $ .

Bilgiler hisse bilgi işlem ortamında ücretsizdir.
Ölçülen her bir qubit, tek bir bilgi verir ve kopyalama olmaması durumunda, sistem hakkında elde edilen bilgiler ve üzerinde çağrılan saldırgan arasındaki temel zorunluluğunu getirir etrafında elde etmek için kullanılabilecek bir biriktirme listesi olmadığını gösterir.
