---
title: Pauli ölçümleri
description: Pauli ölçümleri
author: QuantumWriter
uid: microsoft.quantum.concepts.pauli
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 0a3ee595022ec389ecadcab081ccd126cb3252ae
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76819918"
---
# <a name="pauli-measurements"></a>Pauli ölçümleri

Önceki tartışmalarda hesaplama tabanlı ölçümlere odaklandık.
Aslında, notational perspektifinden, işlem tabanlı ölçümlerde hızlı bir şekilde ifade etmek için uygun olan, hisse kullanımı açısından oluşan diğer yaygın ölçümler vardır.
Q # ile çalışırken, çalıştıracağınız en yaygın ölçüm türleri *Pauli ölçümleri*olacaktır, bu da diğer tabanlarda ölçümleri dahil etmek için hesaplama tabanlı ölçümleri genelleştirir ve farklı qugeler arasında eşlik sağlar.
Bu gibi durumlarda, bir Pauli işlecinin, genel olarak $X, Y, Z $ veya $Z \otimes Z, X\otimes X, X\otimes Y $ gibi bir operatör ölçmesi için yaygın olarak ele alınmıştır.

> [!TIP]
> Q # içinde, Multi-qubitpauli işleçleri genellikle `Pauli[]`türündeki diziler tarafından temsil edilir.
> Örneğin, $X \otimes Y $ 'ı göstermek için, dizi `[PauliX, PauliZ, PauliY]`kullanabilirsiniz.

Pauli işleçleri açısından ölçüm ele alınması, özellikle de hisse hata düzeltmesinin alt alanında ortaktır.
Q # ' da benzer bir kuralı izliyoruz; Artık ölçümlerin bu alternatif görünümünü açıkladık.

Pauli ölçüsünün nasıl düşündüğünün ayrıntılarına geçmeden önce, hisse bir bilgisayar içinde tek bir qubit 'in ne ölçmeye yönelik olduğunu düşünmek yararlı olur.
$N $-qubit hisse anımız olduğunu düşünün; ardından, bir qubit, bu durumun içinde olabilecek $2 ^ n $ olasılıklarının yarısını hemen ölçmelidir.
Diğer bir deyişle, ölçüm, hisse durumunu iki yarım boşluktan birine göre projeler.
Bu ıntut 'i yansıtmak için ölçüm hakkında düşündüğünüzden bahsede genelleştireceğiz.

Bu alt boşlukların öz belirlemek için, bunları açıklamak için bir dile ihtiyacımız var.
İki alt boşluğu tanımlamanın bir yolu, kural tarafından $ \pm $1 olacak şekilde yalnızca iki benzersiz eigenvalues içeren bir matris aracılığıyla belirtilerek belirlenir.
Alt boşlukları bu şekilde açıklayan basit bir örnek için $Z $:

$ $ \begin{hizalaması} Z & = \begin{bmatrix} 1 & 0 \\\\ 0 &-1 \end{bmatrix}.
\end{hizalaması} $ $

Pauli-$Z $ matrisinin köşegen öğelerini okuyarak, $Z $ 'ın, karşılık gelen eigenvalues $ \pm $1 ile iki eigenvektörün, $ \tus{0}$ ve $ \tus{1}$ olduğunu görebiliriz.
Bu nedenle, qubit ' i ölçyoruz ve `Zero` elde ediyorsanız ($ \demet{0}$ ' e karşılık gelir), qubitin durumunun $Z $ işlecinin $ + $1 eigenstate olduğunu biliyoruz.
Benzer şekilde, `One`elde ettiğimiz için, qubit durumunun bir $-$1 eigenstate $Z $ olduğunu biliyoruz.
Bu işlem, Pauli ölçümlerinin dilinde "ölçüm Pauli $Z $" olarak adlandırılır ve hesaplama tabanlı ölçüm gerçekleştirmeyle tamamen eşdeğerdir.

$Z $ ' ın bir Unitary dönüştürmesi olan her $2 \ kez $2 matrisi de bu ölçütleri karşılar.
Diğer bir deyişle, bir ölçünün $ \pm $1 eigenvektörlerinde iki sonucunu tanımlayan bir matris vermek için $U $ başka bir unitöğeli dizey olan $A = U ^ \linger Z U $ matrisini da kullanabiliriz.
Pauli ölçülerinin gösterimi, $X, Y, Z $ ölçümlerini, bir qubitden bilgi elde etmek için yaptığı eşdeğer ölçümler olarak tanımlayarak bu Unitary denkliğine başvurur.
Bu ölçümler, kolaylık sağlamak için aşağıda verilmiştir.


|Pauli ölçümü  |Unitary dönüştürmesi  |
|-------------------|------------------------|
| $Z $               | $ \ cıvabitti $             |
| $X $               | $H $                    |
| $Y $               | $HS ^ {\hanger} $         |

Diğer bir deyişle, bu dil kullanıldığında, "Measure $Y $", ^ \linger $ $HS uygulama ve daha sonra hesaplama temelinde ölçme ile eşdeğerdir; burada [`S`](xref:microsoft.quantum.intrinsic.s) , bazen "aşama kapısı" olarak adlandırılan ve Unitary matrisi tarafından benzetilen bir iç hisse dır

$ $ \begin{hizalaması} S = \begin{bmatrix} 1 & 0 \\\\ 0 & i \end{bmatrix}.
\end{hizalaması} $ $

Ayrıca, $HS ^ \dağılım $ öğesini hisse durum vektörüne uygulamak ve sonra $Z $ ölçüsüne benzer ve aşağıdaki işlem `Measure([PauliY], [q]])`eşdeğerdir:

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

Doğru durum daha sonra hesaplama temeline geri dönüştürülmesiyle, $SH $ ' i hisse Yukarıdaki kod parçacığında, işlem temelinde dönüştürme işlemi, `within … apply` bloğunun kullanımı tarafından otomatik olarak işlenir.

Q # ' da, sonucu---, durum---ile etkileşimde bulunarak ayıklanan klasik bilgiler `Result` bir değer $j \\\{\Texttt{dd}, \texttt{One}\\} $ değerinin Pauli işlecinin ölçülen $ (-1) ^ j $ eigenalanında olup olmadığını belirten bir değeri tarafından verilmiştir.


## <a name="multiple-qubit-measurements"></a>Birden çok qubit ölçümleri

Multi-qubitpauli işleçlerinin ölçümleri benzer şekilde, şöyle görüldüğü gibi tanımlanmıştır:

$ $ Z\otimes Z = \begin{bmatrix}1 & 0 & 0 & 0\\\\ 0 &-1 & 0 & 0\\\\ 0 & 0 &-1 & 0\\\\ 0 & 0 & 0 & 1 \ End {bmatrix}.
$$

Bu nedenle, iki Pauli-$Z $ işleçlerinin Tensor ürünleri, $ + $1 ve $-$1 eigenvalues içeren iki boşluktan oluşan bir matris oluşturur.
Tek qubit durumunda olduğu gibi, her ikisi de erişilebilir vektör alanının yarısını $ + $1 eigenspace ve $-$1 eigenspace 'e ait olan yarı boşluk anlamına gelir.
Genel olarak, Pauli-$Z $ işleçlerinin herhangi bir Tensor ürünü ve kimliğin bu şekilde bu şekilde uyumlu olması için, Tensor ürünü tanımından kolayca bakmak kolaydır.
Örneğin,

$ $ \begin{hizalaması} Z \otimes \cıvadone = \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 &-1 ' & 0 \\\\ 0 & 0 & 0 &-1 \end{bmatrix}.
\end{hizalaması} $ $

Daha önce olduğu gibi, bu tür Matrislerin her türlü Unitary dönüştürmesi, $ \pm $1 eigenvalues ile etiketlenmiş iki yarı boşluğu da açıklar.
Örneğin, $Z = HXH $ olan kimlikten $X \otimes X = H\otimes H (Z\otimes Z) H\otimes H $.
Tek qubit çalışmasına benzer şekilde, tüm iki-qubit Pauli-ölçümleri, $4 \ Times $4 Unitary $U $ için $U ^ \hanger (Z\otimes \ID) U $ olarak yazılabilir. Aşağıdaki tablodaki dönüşümleri numaralandırıyoruz.

> [!NOTE]
> Aşağıdaki tabloda, $ $ \begin{hizalaması} \operatorname{SWAP} & = \left (\begin{Matrix} 1 & 0 & 0 & 0 \\\\ 0 matrisini göstermek için $ \operatorname{SWAP} $ kullanırız. & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \end{Matrix}\right) \end{hizalaması} $ $, iç işlem [`SWAP`](xref:microsoft.quantum.intrinsic)benzetimini yapmak için kullanılır.

|Pauli ölçümü     |Unitary dönüştürmesi  |
|----------------------|------------------------|
| $Z \otimes \ cıvabitti $ | $ \ cıvabitti \otimes \cıvabitti $ |
| $Z \otimes \ cıvabitti $ | $ \boldone\otimes \ cıvabitti $ |
| $X \otimes \ cıvabitti $ | $H \otimes \ cıvabitti $ |
| $Y \otimes \ cıvabitti $ | $HS ^ \abger\otimes \ cıvabitti $ |
| $ \ cıvabitti \otimes Z $ | $ \operatorname{SWAP} $ |
| $ \ cıvabitti \otimes X $ | $ (H\otimes \cıvadone) \operatorname{SWAP} $ |
| $ \ bolbitti \otimes Y $ | $ (HS ^ \hanger\otimes \cıvadone) \operatorname{SWAP} $ |
| $Z \otimes Z $ | $ \operatorname{CNOT}\_{10}$ |
| $X \otimes Z $ | $ \operatorname{CNOT}\_{10}(H\otimes \ cıvabitti) $ |
| $Y \otimes Z $ | $ \operatorname{CNOT}\_{10}(HS ^ \hanger\otimes \ cıvadone) $ |
| $Z \otimes X $ | $ \operatorname{CNOT}\_{10}(\boldone\otimes H) $ |
| $X \otimes X $ | $ \operatorname{CNOT}\_{10}(H\otimes H) $ |
| $Y \otimes X $ | $ \operatorname{CNOT}\_{10}(HS ^ \hanger\otimes H) $ |
| $Z \otimes Y $ | $ \operatorname{CNOT}\_{10}(\cıvadone \otimes HS ^ \ dağılım) $ |
| $X \otimes Y $ | $ \operatorname{CNOT}\_{10}(H\otimes HS ^ \ dağılım) $ |
| $Y \otimes Y $ | $ \operatorname{CNOT}\_{10}(HS ^ \hanger\otimes HS ^ \ dağılım) $ |

Burada [`CNOT`](xref:microsoft.quantum.intrinsic.cnot) işlem aşağıdaki nedenlerden dolayı görüntülenir.
$ \Cıvadone $ matrisini içermeyen her bir Pauli ölçümü, yukarıdaki düşünene kadar \otimes Z $ $Z bir Unitary 'e eşittir.
$Z \otimes Z $ ' nin eigenvalues değeri yalnızca her bir hesaplama tabanlı vektörü oluşturan qubits 'in eşliği üzerine bağlıdır ve denetlenen işlemler bu eşliği hesaplamak ve ilk bit içinde saklamak için işlem yapar.
İlk bit ölçülene kadar, elde edilen yarı alanın kimliğini kurtararak Pauli işlecinin ölçülesiyle eşdeğerdir.

Bir ek notta: $Z \otimes Z $ ölçüyü, $Z \otimes \mathbb{1}$ ve sonra $ \mathbb{1} \otimes Z $ gibi bir şekilde ölçerek aynı olduğunu varsaymaya karşın, bu varsayım false olur.
Nedeni, bu işleçlerin her biri için $Z \otimes Z $ projelerini, bu işleçlerin $ + $1 veya $-$1 eigenstate.
$Z \otimes \mathbb{1}$ ve sonra $ \mathbb{1}, ilk olarak bir $Z \otimes \mathbb{1}$ ve daha sonra da $ \mathbb{1}
Dört hesaplama tabanlı vektör olduğu için, her iki ölçüm de durum, durumu çeyrek boşluk olarak azaltır ve bu nedenle tek bir hesaplama tabanlı vektöre düşürür.

## <a name="correlations-between-qubits"></a>Qubits arasında correlations
$X \otimes X $ veya $Z \otimes Z $ gibi Pauli matrislerini ölçmeye yönelik başka bir yöntem de, bu ölçümlerin iki qubit arasındaki bağıntılar içinde depolanan bilgilere bakmasına olanak tanır.
$X \otimes \ID $ ölçme, ilk qubit 'de yerel olarak saklanan bilgilere bakmanızı sağlar.
Her iki ölçüm türü de hisse bilgi işlem ortamında eşit olmakla birlikte, önceki bir deyişle hisse bilgi işlem gücünü güçlendirin.
Bu, bilgi işlem ortamında, genellikle öğrenmek istediğiniz bilgilerin tek bir qubit içinde depolanmadığını, ancak aynı anda tüm qubits 'de yerel olarak depolanmadığını ve bu nedenle yalnızca bir eklem ölçümü üzerinden arayarak (ör. $Z \otimes Z $) bunu yapmaz bilgi bildirim haline gelir.

Örneğin, hata düzeltilirken, korumamıza çalıştığımız durum hakkında hiçbir şey öğrenirken bir hata oluştuğunu öğrenmek istiyoruz.
[Bit-çevir kod örneği](https://github.com/microsoft/Quantum/tree/master/samples/error-correction/bit-flip-code) , $Z \otimes z \otimes \ID $ ve $ \ID \otimes z \otimes z $ gibi ölçümleri kullanarak bunu nasıl yapakullanabileceğinizi gösteren bir örnek gösterir.
<!-- TODO: change this to a link to the samples browser as soon as the bit-flip code sample is on-boarded. -->

$X \otimes Y \otimes Z \otimes \cıvadone $ gibi rastgele Pauli işleçleri de ölçülebilir.
Pauli işleçleri 'nin bu tür tüm tencursor ürünlerinin yalnızca iki eigenvalues $ \pm $1 ve her iki eigenspace, tüm vektör alanlarının yarı alanlarını oluşturur.
Bu nedenle, yukarıda belirtilen gereksinimlere başvurırlar.

Q # içinde, bu ölçümler $j $ $ (-1) ^ j $ işaret egenünde bir sonuç verir.
Bu tür işleçleri ölçmek, diagonalizing $ ve $ \ID $ ' $Z nin bir Tensor ürünü olarak işlemi ifade etmek için gereken $U $ Gate ' i açıklayan, denetlenen kapıların ve temel dönüştürmelerin uzun zincirlerine ihtiyaç duyduğundan, bu tür işleçlerin bir yerleşik özelliği olarak bulunması faydalı olabilir.
Önceden tanımlanmış Bu ölçülerden birini yapmak istediğinizi belirleyebilmeksizin, bir hesaplama tabanlı ölçüm için gerekli bilgileri sağlamak üzere temelinizi nasıl dönüştürebileceğinizi merak etmeniz gerekmez.
S #, sizin için gerekli tüm temel dönüştürmeleri otomatik olarak işler.
Daha fazla bilgi için [`Measure`](xref:microsoft.quantum.intrinsic.measure) ve [`MeasurePaulis`](xref:microsoft.quantum.measurement.measurepaulis) işlemlerine bakın.

## <a name="the-no-cloning-theorem"></a>Kopyalama olmayan bu Üyeler

Hisse bilgileri güçlüdür.
Faktör numaraları gibi harika şeyleri en iyi bilinen klasik algoritmalardan daha hızlı bir şekilde gerçekleştirebilmemizi veya düzgün bir şekilde benzetilmesini sağlayan bağıntılı elektron sistemlerinin verimli bir şekilde benzetimini yapmanızı sağlar.
Ancak, hisse bilgi işlem gücüyle ilgili sınırlamalar vardır.
Bu tür bir sınırlama, *hiçbir kopyalama olmayan kopya*tarafından verilir.

Kopyalama yok, hiçbir şekilde adlandırılır.
Genel hisse durumlarının bir hisse bilgisayar tarafından kopyalanmasına izin vermez.
Bunların kanıtı, genel olarak basittir.
Bu konu başlığı altında, hiçbir ek yardımcı qubit, bizim için çok fazla teknik olmadığı için, kapsamımızda ek bir yardımcı qubit yoktur (yardımcı qugeler, bir hesaplama sırasında karalama alanı için kullanılır ve bu durum, Q # ' da kolayca kullanılır ve yönetilir): <xref:microsoft.quantum.techniques.qubits>).

Bu tür bir hisse bilgisayar için kopyalama işlemi bir Unitary matrisi tarafından açıklanmalıdır.
Klonlamamız denendiğimiz hisse TI durumunu bozduğundan ölçüme izin vermeiyoruz.
Kopyalama işleminin benzetimini yapmak için, Unitary matrisinin $ $ U \ket{\psı} \tus{0} = \ket{\psi} \ket{\psı} $ $ öğesini herhangi bir durum $ \ket{\psı} $ için özelliği olmasını istiyoruz.
Matris çarpıda oluşan determinity özelliği, tüm ikinci hisse için $ \ket{\phi} $ olduğunu gösterir.

$ $ \begin{hizalaması} U \left [\frac{1}{\sqrt{2}} \left (\ket{\phi} + \ket{\psı} \right) \ right] \tus{0} & = \frac{1}{\sqrt{2}} U\ket {\ Fi} \ ayraç{0} + \frac{1}{\sqrt{2}} U\tus{\ PSI} \ demet{0} \\\\ & = \frac{1}{\sqrt{2}} \left (\ket{\phi} \ket{\phi} + \ket{\psı} \ket{\psı} \right) \\\\ & \ne \left (\frac{1}{\sqrt{2}} \left (\ket{\phi} + \ket{\psı} \right) \right) \otimes \ Left (\frac{1}{\sqrt{2}} \left (\ket{\phi} + \ket{\psı} \right) \ right).
\end{hizalaması} $ $

Bu, kopya olmaması gereken temel ıntutiye sahiptir: bilinmeyen bir hisse lık durumunu kopyalayan tüm cihazlar, kopyalayan durumların en az bir kısmında yer almalıdır.
Cloner 'ın giriş durumunda daha erken davranırken, bu durum yardımcı qubits 'in eklenmesi ve ölçümü aracılığıyla ihlal edilebilir, ancak bu tür etkileşimler Ayrıca ölçüm istatistikleri aracılığıyla sistem hakkında bilgi sızıntısına ve tam olarak engel olmasını önler Bu gibi durumlarda da kopyalama.
Daha fazla [bilgi için](xref:microsoft.quantum.more-information), kopyalamanın olmaması için daha kapsamlı bir kanıt için bkz.

Hisse uygun olmayan bir şekilde büyük ölçüde bir şekilde klonlamanız için, parça olmayan bir bilgi işlem için önemli değildir. bu nedenle, hisse durumlarından daha fazla bilgi edinebilirsiniz.
Aslında, Heısenberg 'nin vaunbelirsizlik ilkesini ihlal edebilirsiniz.
Alternatif olarak, bir karmaşık hisse dağılımla tek bir örnek almak ve yalnızca bir örnekten bu dağıtım hakkında bilgi edinmek istediğiniz her şeyi öğrenmek için en uygun bir Cloner kullanabilirsiniz.
Bu, bir para ve gözbaşları çevirmiş ve sonra yanıt vermeye yönelik bir arkadaşla ilgili bir arkadaşınız söyleirken "Ah 'nin dağıtımı $p = 0.512643 \ lnoktalar $!" ile aynı olmalıdır.  Bu tür bir ifade, bir veya daha fazla bilgi olmadan dağıtımı kodlamak için gereken pek çok bilgi sağlamadığı için sensik olmayan bir ifadedir.
Benzer şekilde, önceki bilgiler olmadan tıpkı $p $ ' i bilmeden bu tür kodların bir listesini hazırlayamuyoruz.

Bilgiler hisse bilgi işlem ortamında ücretsizdir.
Ölçülen her bir qubit, tek bir bilgi verir ve kopyalama olmaması durumunda, sistem hakkında elde edilen bilgiler ve üzerinde çağrılan saldırgan arasındaki temel zorunluluğunu getirir etrafında elde etmek için kullanılabilecek bir biriktirme listesi olmadığını gösterir.
