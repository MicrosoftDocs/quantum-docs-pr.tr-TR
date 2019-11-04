---
title: Pauli ölçümleri | Microsoft Docs
description: Pauli ölçümleri
author: QuantumWriter
uid: microsoft.quantum.concepts.pauli
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 7bea821be7e26e72f2860278486d35be676ca63d
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183718"
---
# <a name="pauli-measurements"></a>Pauli ölçümleri

Önceki tartışmalarda hesaplama tabanlı ölçümlere odaklandık.  Aslında, notational perspektifinden, işlem tabanlı ölçümlerde hızlı bir şekilde ifade etmek için uygun olan, hisse kullanımı açısından oluşan diğer yaygın ölçümler vardır.  Bu ölçümlerin en yaygın kümesi *Pauli ölçümleridir*.  Bu gibi durumlarda, bir Pauli işlecinin, genel olarak $X, Y, Z $ veya $Z \otimes Z, X\otimes X, X\otimes Y $ gibi bir operatör ölçmesi için yaygın bir şekilde ele alınmıştır.  Pauli işleçleri açısından ölçüm ele alınması, özellikle de hisse hata düzeltmesinin alt alanında ortaktır. Soru-cevap bölümünde benzer bir kural izliyoruz; Artık ölçümlerin bu alternatif görünümünü açıkladık.

Pauli ölçüsünün nasıl düşündüğünün ayrıntılarına geçmeden önce, hisse bir bilgisayar içinde tek bir qubit 'in ne ölçmeye yönelik olduğunu düşünmek yararlı olur.  $N $-qubit hisse anımız olduğunu düşünün; ardından, bir qubit, bu durumun içinde olabilecek $2 ^ n $ olasılıklarının yarısını hemen ölçmelidir.  Diğer bir deyişle, ölçüm, hisse durumunu iki yarım boşluktan birine göre projeler.  Bunu yansıtmak için ölçüyle ilgili düşüntiğimiz yolu genelleştirebilirsiniz.

Bu alt boşlukların öz belirlemek için, bunları açıklamak için bir dile ihtiyacımız var.  Bunu yapmanın bir yolu, kural tarafından $ \pm $1 olacak şekilde yalnızca iki benzersiz eigenvalues içeren bir matris aracılığıyla belirterek iki alt boşluğu açıklamanız şeklindedir.  Bunun en basit örneği şunlardır:

$ $ Z = \begin{bmatrix} 1 & 0 \\\\ 0 &-1 \end{bmatrix}.
$$

Pauli-$Z $ matrisinde, egenvalues $ \pm $1 ile iki eigenvektör$ \ayraç{0}$ ve $ \tus{1}$ vardır.  Bu nedenle, qubit ' i ölçyoruz ve $ \ket{0}$ ' i elde ediyorsanız, işlecin $ + $1 eigenspace (yalnızca pozitif veya yalnızca negatif eigenvalues değerlerinin toplandığı tüm vektörler kümesi) ve $ \ket{1}$ ' i ölçyoruz $-$1 ei ' de $Z $ genboşluk.  Bu işlem, Pauli ölçümlerinin dilinde "ölçüm Pauli $Z $" olarak adlandırılır ve hesaplama tabanlı ölçüm gerçekleştirmeyle tamamen eşdeğerdir.

Kuşkusuz, $Z $ ' ın bir Unitary dönüştürmesi olan $2 \ Times $2 matrisi de bu ölçütleri karşılar.  Bu, bir ölçünün $ \pm $1 eigenvektörlerine göre iki sonucunu tanımlayan bir matris vermek üzere her türlü Unitary $U $ için matris $A = U ^ \gger Z U $ ' y i de göz önünde bulunduracağız.  Pauli ölçülerinin gösterimi, $X, Y, Z $ ölçümlerini, bir qubitden bilgi elde etmek için bir, eşdeğer ölçümler olarak tanımlayarak buna başvurur.  Bu ölçümler, kolaylık sağlamak için aşağıda verilmiştir.

$ $ \begin{Array}{| c | c |} \text{Pauli ölçüm} & U\\\\ Z & \cıvadone\\\\ X & H\\\\ Y & HS ^ \dağılım\\\\ \end{Array} $ $

Diğer bir deyişle, bu dil kullanıldığında, "Measure $Y $", ^ \hanger $ $HS uygulama ve sonra hesaplama temelinde ölçme ile eşdeğerdir; burada $S $, tarafından verilen aşama geçidi olarak adlandırılır

$ $ \begin{bmatrix}1 & 0\\\\ 0 & i\end {bmatrix}.
$$

Ayrıca, $HS ^ \hanger $ ' ı hisse durumu vektörüne uygulamak ve sonra $Z $ ölçmesine eşdeğerdir.  Doğru durum daha sonra hesaplama temeline geri dönüştürülmesiyle, $SH $, hisse

## <a name="q-outcome-classical-information-obtained-from-quantum-state"></a>S # hisse ınızdan elde edilen sonuç klasik bilgileri
Soru-cevap bölümünde, durum ile etkileşimde bulunarak ayıklanan klasik bilgiler, $\{0, 1\}$ kümesindeki $j $. sonuç, Pauli işlecinin ölçülen $ (-1) ^ j $ eigenspace 'daydı.

Multi-qubitpauli işleçlerinin ölçümleri benzer şekilde, şöyle görüldüğü gibi tanımlanmıştır:

$ $ Z\otimes Z = \begin{bmatrix}1 & 0 & 0 & 0\\\\ 0 &-1 & 0 & 0\\\\ 0 & 0 &-1 & 0\\\\ 0 & 0 & 0 & 1 \ End {bmatrix}.
$$

Bu nedenle, iki Pauli-$Z $ işleçlerinin Tensor ürünleri, $ + $1 ve $-$1 eigenvalues içeren iki boşluktan oluşan bir matris oluşturur.  Tek qubit durumunda olduğu gibi, her ikisi de erişilebilir vektör alanının yarısını $ + $1 eigenspace ve $-$1 eigenspace 'e ait olan yarı boşluk anlamına gelir.  Genel olarak, Pauli-$Z $ işleçlerinin herhangi bir Tensor ürünü ve kimliğin bu şekilde bu şekilde uyumlu olması için, Tensor ürünü tanımından kolayca bakmak kolaydır.  Örneğin,

$ $ Z\otimes\cıvadone = \begin{bmatrix} 1 & 0 & 0 & 0\\\\ 0 & 1 & 0 & 0\\\\ 0 & 0 &-1 & 0\\\\ 0 & 0 & 0 &-1 \ End {bmatrix}.
$$

Daha önce olduğu gibi, bu tür Matrislerin her türlü Unitary dönüştürmesi, $ \pm $1 eigenvalues ile etiketlenmiş iki yarı boşluğu da açıklar.  Örneğin, $Z = HXH $ olan kimlikten $X \otimes X = H\otimes H (Z\otimes Z) H\otimes H $.  Tek qubit çalışmasına benzer şekilde, tüm iki-qubit Pauli-ölçümleri, $4 \ Times $4 Unitary $U $ için $U ^ \hanger (Z\otimes \ID) U $ olarak yazılabilir.  Aşağıdaki tablodaki dönüştürmeleri, qubits $0 $ ve $1 $: $ \operatorname{SWAP} = \operatorname{CNOT}\_{01}\operatorname{CNOT}\_{10}CNOT}\_{01}$:

$ $ \begin{Array}{| c | c |} \text{Pauli ölçüm} & U\\\\ \hline Z\otimes \cıvadone & \boldone\otimes \cıvado\\\\ X\otimes \cıvado & H\otimes \cıvabitti otimes \cıvadone\\\\ \cıvadone \otimes Z & \operatorname{SWAP}\\\\ \cıvadone \otimes X & (H\otimes \cıvadone) \operatorname{SWAP}\\\\ \cıvadone \otimes Y & ( operatorname {SWAP}\\\\ Z\otimes Z & \operatorname{CNOT}\_{10}\\\\ X\otimes Z & \operatorname{CNOT}\_{10}(H\otimes \ cıvadone)\\\\ Yı\otimes Z & \ operatorname {CNOT}\_{10}(HS ^ \hanger\otimes \cıvadone)\\\\ Z\otimes X & \operatorname{CNOT}\_{10}(\boldone\otimes H)\\\\ X\otimes X & \operatorname{CNOT}\_@no__t _31_ (h\otimes H)\\\\ Y\otimes X & \operatorname{CNOT}\_{10}(HS ^ \hanger\otimes H)\\\\ Z\otimes Y & \operatorname{CNOT}\_{10}(\cıvalation\otimes HS ^ \ dağılım)\\\\ x\otimes Y & \operatorname{CNOT}\_{10}(H\otimes HS ^ \hanger)\\\\ Yı\otimes Y & \operatorname{CNOT}\_{10}(HS ^ \abger\otimes HS ^ \ dağılım)\\\\ \end{Array} $ $

Burada, $ \operatorname{CNOT}\_{10}$ kapısı aşağıdaki nedenle görüntülenir.  $ \Cıvadone $ matrisini içermeyen her bir Pauli ölçümü, yukarıdaki düşünene kadar \otimes Z $ $Z bir Unitary 'e eşittir.  $Z \otimes Z $ ' nin eigenvalues değeri yalnızca her bir hesaplama tabanlı vektörü oluşturan qubits 'in eşliği ve bu listede görünen denetlenen işlemler, bu eşliği hesaplamasını ve ilk bit içinde depolanmasını sağlar.  İlk bit ölçüldüğünde, Pauli işlecinin ölçülesiyle eşdeğer olan sonuçtaki yarı alanın kimliğini kurtarabilirsiniz.

Tek bir ek notta, $Z \otimes Z $ ' nin ölçü $Z \otimes \ID $ ile aynı olduğunu ve sonra da $ \ID \otimes Z $ olduğunu varsaymak için bu varsayım yanlış olur.  Nedeni, bu işleçlerin her biri için $Z \otimes Z $ projelerini, bu işleçlerin $ + $1 veya $-$1 eigenstate.  $Z \otimes \ID $ ve sonra $ \ID \otimes Z $ projeleri, ilk başta "\otimes \ID $ $Z bir yarı alana ve ardından $ \ID \otimes Z $ $ $ $ $ $ $ $ ' a kadar bir yarı alana kadar olan  Dört hesaplama tabanlı vektör olduğu için, her iki ölçüm de durum, durumu çeyrek boşluk olarak azaltır ve bu nedenle tek bir hesaplama tabanlı vektöre düşürür.


## <a name="correlations-between-qubits"></a>Qubits arasında correlations
$X \otimes X $ veya $Z \otimes Z $ gibi paulıs 'nin tencursor ürünlerini ölçmeye yönelik başka bir yöntem de, bu ölçümlerin iki qubit arasındaki bağıntılar içinde depolanan bilgilere bakmasına olanak tanır.  $X \otimes \ID $ ölçme, ilk qubit 'de yerel olarak saklanan bilgilere bakmanızı sağlar.  Her iki ölçüm türü de hisse bilgi işlem ortamında eşit olmakla birlikte, önceki bir deyişle hisse bilgi işlem gücünü güçlendirin. Bu, bilgi işlem sırasında öğrenmek istediğiniz bilgilerin herhangi bir tek qubit içinde depolanmadığını, ancak aynı anda tüm qubits 'de yerel olarak depolanmadığını ve yalnızca $Z \otimes Z $ olan bir eklem ölçümü aracılığıyla arayarak bu bilgilerin ne olduğunu gösterir bildirim.

$X \otimes Y \otimes Z \otimes \cıvadone $ gibi rastgele Pauli işleçleri de ölçülebilir.  Pauli işleçleri 'nin bu tür tüm tencursor ürünlerinin yalnızca iki eigenvalues $ \pm $1 ve her iki eigenspace, tüm vektör alanlarının yarı alanlarını oluşturur.  Bu nedenle, yukarıda belirtilen gereksinimlere başvurırlar.

Q # içinde, bu ölçümler $j $ $ (-1) ^ j $ işaret egenünde bir sonuç verir.  Bu tür işleçler, diagonalizing $ ve $ \ID $ ' $Z nin bir tenbir ürünü olarak işlemi ifade etmek için gereken $U $ Gate ' i anlatmak üzere, bir dizi denetlenen kapılara ve temel Dönüşümlere yönelik olarak bir yerleşik özellik olarak olması yararlı olacaktır.  Yalnızca bu önceden tanımlı ölçülerden birini yapmak istediğinizi belirtmek için, bir hesaplama tabanlı ölçüm için gerekli bilgileri sağlamak üzere temelinizi nasıl dönüştürebileceğinizi merak etmeniz gerekmez.  S #, sizin için gerekli tüm temel dönüştürmeleri otomatik olarak işler. Bkz. [Pauli ölçümleri Için Q # kitaplığı başvurusu](/qsharp/api/canon/microsoft.quantum.canon.measurepaulis)

## <a name="the-no-cloning-theorem"></a>Kopyalama olmayan bu Üyeler
Hisse bilgileri güçlüdür.  Faktör numaraları gibi harika şeyleri en iyi bilinen klasik algoritmalardan daha hızlı bir şekilde gerçekleştirebilmemizi veya düzgün bir şekilde benzetilmesini sağlayan bağıntılı elektron sistemlerinin verimli bir şekilde benzetimini yapmanızı sağlar.  Ancak, hisse bilgi işlem gücüyle ilgili sınırlamalar vardır.  Bu tür bir sınırlama, *hiçbir kopyalama olmayan kopya*tarafından verilir.

Kopyalama yok, hiçbir şekilde adlandırılır.
Genel hisse durumlarının bir hisse bilgisayar tarafından kopyalanmasına izin vermez.
Bunların kanıtı, genel olarak basittir.
Hiçbir kopyalama işlemi başarısız olursa, bu konu başlığı altında yer alan, söz konusu füzde, söz konusu füzde, söz konusu olan hisse cılığımızın içinde ek bir anonla bir hesaplama sırasında boşluk ve Q # ' da kolayca kullanılır ve yönetilir, bkz. <xref:microsoft.quantum.techniques.qubits>).
Bu tür bir hisse bilgisayar için kopyalama işlemi bir Unitary matrisi olmalıdır. Klonlamamız denendiğimiz hisse TI durumunu bozduğundan ölçüme izin vermeiyoruz. İstediğimiz Unitary matrisinde $ $ U \ket{\psi} \ket{0} = \ket{\psi} \ket{\psi}, $ $ herhangi bir durum $ \ket{\psı} $ için olan özelliğe sahip olmalıdır.
Matris çarpıda oluşan determinity özelliği, tüm ikinci hisse için $ \ket{\phi} $ olduğunu gösterir.

\begin{hizalaması} & Uı\left [\frac{1}{\sqrt{2}} \left (\ket{\phi} + \ket{\psı} \right) \ right] \demet{0}= \frac{1}{\sqrt{2}} U\tus{\ Fi} \ ayraç{0}+ \frac{1}{\sqrt{2}} U\tus{\ PSI} \ demet{0}@no__ t_9_ \\ & \qquad\qquad = \frac{1}{\sqrt{2}} \left (\ket{\phi}\ket{\phi} + \ket{\psi}\ket{\psi}\right)\\\\ & \qquad\qquad\s \left (\frac{1}{\sqrt{2}} \left (\ket{\phi} + \ket{\psı} \) sağ) \ sağdan) \otimes\left (\frac{1}{\sqrt{2}} \left (\ket{\phi} + \ket{\psı} \right) \ right).
\end{hizalaması}

Bu, kopya olmaması gereken temel ıntutiye sahiptir: bilinmeyen bir hisse lık durumunu kopyalayan tüm cihazlar, kopyalayan durumların en az bir kısmında yer almalıdır.  Cloner 'ın giriş durumunda herhangi bir şekilde hareket edeceği önemli varsayım, anyala ve daha fazla bilgi için, ölçüm istatistikleri aracılığıyla sistemle ilgili bilgileri de sızır ve bunu önler Bu gibi durumlarda da tam kopyalama.  Daha fazla [bilgi için](xref:microsoft.quantum.more-information), kopyalamanın olmaması için daha kapsamlı bir kanıt için bkz.

Hisse uygun olmayan bir şekilde büyük ölçüde bir şekilde klonlamanız için, parça olmayan bir bilgi işlem için önemli değildir. bu nedenle, hisse durumlarından daha fazla bilgi edinebilirsiniz.  Aslında, Heısenberg 'nin vaunbelirsizlik ilkesini ihlal edebilirsiniz.  Alternatif olarak, bir karmaşık hisse dağılımla tek bir örnek almak ve yalnızca bir örnekten bu dağıtım hakkında bilgi edinmek istediğiniz her şeyi öğrenmek için en uygun bir Cloner kullanabilirsiniz.  Bu, bir para ve gözbaşları çevirmiş ve sonra yanıt vermeye yönelik bir arkadaşla ilgili bir arkadaşınız söyleirken "Ah 'nin dağıtımı $p = 0.512643 \ lnoktalar $!" ile aynı olmalıdır.  Bu tür bir ifade, bir veya daha fazla bilgi olmadan dağıtımı kodlamak için gereken pek çok bilgi sağlamadığı için sensik olmayan bir ifadedir.  Benzer şekilde, önceki bilgiler olmadan tıpkı $p $ ' i bilmeden bu tür kodların bir listesini hazırlayamuyoruz.

Bilgiler hisse bilgi işlem ortamında ücretsizdir.  Ölçülen her bir qubit, tek bir bilgi verir ve kopyalama olmaması durumunda, sistem hakkında elde edilen bilgiler ve üzerinde çağrılan saldırgan arasındaki temel zorunluluğunu getirir etrafında elde etmek için kullanılabilecek bir biriktirme listesi olmadığını gösterir.

