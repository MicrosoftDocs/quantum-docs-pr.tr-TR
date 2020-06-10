---
title: Birden çok kubit
description: İki veya daha fazla qubit üzerinde işlem gerçekleştirmeyi öğrenin.
author: QuantumWriter
uid: microsoft.quantum.concepts.multiple-qubits
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
no-loc:
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
ms.openlocfilehash: 224bd5165f508f6cd1fdb85fb5c14ba2e23e59ea
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630374"
---
# <a name="multiple-qubits"></a>Birden çok qubit

Tek-qubit kapıları, belirli bir zamanda birden fazla durumda olma yeteneği gibi bazı sayaç sezgisel özelliklere sahip olsa da, bir hisse başında bir bilgisayar tek qubit kapıları olsaydı, bir Hesaplayıcı yalnızca klasik bir süper bilgisayara izin vermekle birlikte, hesaplama gücüne sahip bir cihazımız olur.
Yalnızca Lem bilgi işlemin doğru gücü, qubits sayısını artırdığımız için yalnızca daha açık hale gelir.
Bu güç, parça devlet vektörlerine ait vektör alanı boyutu, qubit sayısıyla üstel olarak artmıştır.
Yani, tek bir qubit, bir 50-qubit hisse hesaplamasının benzetimini yapan, mevcut süper bilgisayarların sınırlarını eşit bir şekilde iletebileceği anlamına gelir.
Hesaplama boyutunu yalnızca bir ek qubit ile artırmak, durumu depolamak için gereken belleği *iki katına çıkarır* ve hesaplama süresini kabaca *ikiye katlanır* .
Hesaplama gücü 'nin bu hızlı katmasının nedeni nispeten az sayıda qubit olan bir hisse bilgisayarının, bazı hesaplama görevleri için yarın ve daha fazla en güçlü süper bilgisayarı daha fazla artırabileceğini tahmin edebilirsiniz.

Hisse madevlet vektörlerine neden üstel büyümemiz gerekir?  Bu bölümde, tek qubit durumlarından çok qubit durumları oluşturmak için kullanılan kuralların yanı sıra, bir evrensel çok değerli-qubit bilgisayar oluşturmak için bir geçit kümesine dahil etmemiz gereken geçit işlemlerini tartışmaktır.
Bu araçların, Q # kodunda yaygın olarak kullanılan kapı kümelerini anlaması ve ayrıca, entanglement veya girişim oluşturma maliyeti gibi ne kadar hisse yaradığına ilişkin öngörülere, klasik bilgi işlem ile daha güçlü bir şekilde bilgi elde etmek için kesinlikle gereklidir.

## <a name="representing-two-qubits"></a>Iki qubit 'i temsil etme
Bir-ve iki-qubit durumu arasındaki temel fark, iki-qubit durumlarının iki boyut yerine dört boyutlu olması gerektiğidir.
Bunun nedeni, iki-qubit durumlarının hesaplama temelinin, tek qubit durumlarının tencursor ürünleri tarafından oluşturulmuş olmasından kaynaklanır.  Örneğin, \begin{align}
00 \ EQUIV \ Begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } \otimes \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } &= \begin{ bmatrix } 1 \\ \\ 0 \\\\ 0 \\\\ 0 \end{ bmatrix } , \qdörtlü 01 \equk\begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } \otimes \begin{ bmatrix } 0 \\ \\ 1 \end{ bmatrix } = \begin{ bmatrix } 0 \\ \\ 1 \\\\ 0 \\\\ 0 \ End{ bmatrix } , \\ \\ 10 \equıv \begin{ bmatrix } 0 \\ \\ 1 \end{ bmatrix } \otimes \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } &= \begin{ bmatrix } 0 \\ \\ 0 \\\\ 1 \\\\ 0 \end{ bmatrix } , \qdörtlü 11 \equk\begin{ bmatrix } 0 \\ \\ 1 \end{ bmatrix } \otimes \begin{ bmatrix } 0 \\ \\ 1 \end{ bmatrix } = \begin{ bmatrix } 0 \\ \\ 0 \\\\ 0 \\\\ 1 \ End{ bmatrix } .
\end{align}

$Bu oluşturma kullanılarak, $n qubits 'in hisse boyutunun, $2 ^ n boyutundaki bir birim vektörü ile temsil edildiği kolayca görüyordu $ .  Vektör

$ $ \begin{ bmatrix } \ alpha_ {00 } \\ \\ \ alpha_ {01 } \\ \\ \ alpha_ {10 } \\ \\ \ alpha_ {11 } \end{bmatrix}
$$

$ | \ alpha_ {00 } | ^ 2 + | \ alpha_ {01 | ^ 2 + | \ } alpha_ {10 | ^ 2 } + | \ alpha_ {11 } | ^ 2 = 1 $ olduğunda iki qubitde bir hisse durumu temsil eder. Tek qubit 'de olduğu gibi, birden çok qubit için hisse durum vektörü, sistemin davranışını anlatmak için gereken tüm bilgileri tutar.

Biri $ \begin{ bmatrix } \Alpha \\ \\ \beta \end{$ durumunda iki ayrı qubit verildiyse bmatrix } ve $ \begin{ bmatrix } \gama \\ \\ \delta \end{$ durumunda bir ikinci qubit verilirse bmatrix } , karşılık gelen iki-qubit durumu

$ $ \begin{ bmatrix } \Alpha \\ \\ \beta \end{ bmatrix } \otimes \begin{ bmatrix } \gama \\ \\ \delta \end{bmatrix} 
= \begin{ bmatrix } \Alpha \begin{ bmatrix } \gama \\ \\ \ Delta \end{ bmatrix } \\ \\ \beta \begin{ bmatrix } \gama \\ \\ \delta \end{ bmatrix } \end{bmatrix}
= \begin{ bmatrix } \Alpha \gamma \\ \\ \ Alpha \delta \\ \\ \beta \gamma \\ \\ \beta \delta \end{ bmatrix } , $ $

Burada $ \otimes, $ vektörlerin Tensor ürünü (veya Kronecker ürünü) olarak adlandırılır. İki adet tek qubit durumunun her zaman bir iki-qubit durumu oluşturmak için her zaman götürebileceğine, iki-qubit hisse senedi durumlarının iki adet tek qubit eyaletinin tencursor ürünü olarak yazılamayacağını unutmayın.
Örneğin, = Tensor ürünü durum olduğu için $ \psı \begin{ bmatrix } \Alpha \\ \\ \beta \end{ bmatrix } $ ve $ \phi = \begin{ bmatrix } \gama \\ \\ \delta \end{ bmatrix } $ gibi durumlar yoktur 

$ $ \psı \otimes \phi = \begin{ bmatrix } 1/\ sqrt {2 } \\ \\ 0 \\ \\ 0 \\ \\ 1/\ sqrt {2 } \end{ bmatrix } . $ $ 

Bu tür bir iki-qubit durumu, tek qubit durumlarının tencursor ürünü olarak yazılamaz, "entangled State" olarak adlandırılır; iki qubit, [*bağımsız olarak kabul edilir.*](https://en.wikipedia.org/wiki/Quantum_entanglement)  Gevşekle, hisse Eyaleti tek qubit durumları için bir Tensor ürünü olarak düşünülmediği için, durumun tuttuğu bilgiler tek tek qubits 'e göre sınırlandırmaz.  Bunun yerine, bilgiler, iki durum arasındaki eş ilişkilerdeki yerel olmayan bir şekilde depolanır.  Bu bilgilerin yer aldığı, klasik bilgi işlem üzerinden hisse bilgi işlem özelliklerinin büyük ayrım özelliklerinden biridir ve [hisse maporsyon](https://github.com/microsoft/Quantum/tree/master/samples/getting-started/teleportation) ve hisse ansız [hata düzeltmesi](xref:microsoft.quantum.libraries.error-correction)dahil olmak üzere bir dizi hisse protokolde gereklidir.

## <a name="measuring-two-qubit-states"></a>Iki-qubit durumu ölçme ##
İki-qubit durumu ölçme, tek qubit ölçümlerine çok benzer. Durumu ölçme

$ $ \begin{bmatrix}
        \ alpha_ {00 } \\ \\ \ alpha_ {01 } \\ \\ \ alpha_ {10 } \\ \\ \ alpha_ {11}
    ererbmatrix}
$$

olasılık $ | \ $ alpha_ {00 } | ^ 2, $1 olasılık $ | \ $ $ alpha_ {01 } | ^ 2, $10, olasılık $ | \ $ $ alpha_ {10 } | ^ 2 ve $0, $ olasılık $ | \ $ alpha_ {11 | ^ 2 ile $11 } $ ile verir. $ \ Alpha_ {00 } , \ alpha_ {01 } , \ alpha_ {10 } , $ ve $ \ alpha_ {11 $ değişkenleri } Bu bağlantıyı açık hale getirmek için kasıtlı olarak adlandırılmıştı. Ölçüden sonra, sonuç $0 ise, $ iki-qubit sistemin hisse TI durumu daraltıldı ve şu anda

$ $0 \equıv \begin{bmatrix}
        1 \\ \\ 0 \\ \\ 0 \\ \\ 0 \ End{ bmatrix } .
$$

İki-qubit hisse durumunun yalnızca bir qubitinin ölçülmesi de mümkündür. Yalnızca bir alt sisteme daraltılacağından, her bir qubits 'in yalnızca bir kısmını ölçecek şekilde, ölçümün etkileri çok daha farklı bir durumdur.  Diğer bir deyişle, bu gibi durumlarda yalnızca bir qubit yalnızca bir qubit, alt sistemlerden yalnızca birini daraltır ancak bunların tümünü kullanmaz.  

Bu durumu görmek için, başlangıçta "0" durumuna ayarlanmış iki qubit üzerinde Hadamard Transform $H uygulanarak oluşturulan aşağıdaki durumun ilk qubit 'i ölçmesini düşünün $ : $ $ H ^ {\otimes 2 } \left (\begin{ bmatrix } 1 \\ \\ 0 \ End{ bmatrix } \otimes \begin{ bmatrix } 1 \\ \\ 0 \ End{ bmatrix } \right) = \frac{1 } {2 } \begin{ bmatrix } 1 & 1 & 1 & 1 \\ \\ 1 &-1 & 1 &-1 \\ \\ 1 & 1 &-1 &-1 \\ \\ 1 &-1 &-1 & 1 \ End{ bmatrix } \begin{ bmatrix } 1 \\\\ 0 \\\\ 0 \\\\ 0 \end { bmatrix } = \frac{1 } {2 } \begin{ bmatrix } 1 \\\\ 1 \\\\ 1 \\\\ 1 \end { bmatrix } \mapsto \begin{Cases } \Text{Outcome} = 0 & \frac{1 } {\sqrt{2 } } \begin{ bmatrix } 1 \\\\ 1 \\\\ 0 \\\\ 0 \end{ bmatrix } \\ \\ \Text{outcome} = 1 & \frac{1 } {\sqrt{2 } } \begin{ bmatrix } 0 \\\\ 0 \\\\ 1 \\\\ 1 \ End{ bmatrix } \\ \\ \end{Cases } .
$ $ Her iki sonuç da %50 oranında meydana gelen bir olasılıktır.  Her ikisi için %50 olasılık elde edilen sonuç, ilk bir değer olan $0 $ $ ' in ilk qubit üzerinde $1 ile değiştirme altında ilk hisse

Birinci veya ikinci qubit ölçmeye yönelik matematik kuralı basittir.  $E _k $ $k ^ {\rm TH } $ Hesaplama tabanlı vektörünün olmasına izin vermemiz ve $S $ tüm $e _K, $ söz konusu $k söz konusu değer için $1 değerini almasını sağlayan tüm kümesi $ olmasına izin veririz $ .  Örneğin, ilk qubit ' i ölçmeye ilgileniyorsanız, $S $ $e _1 \equiv 10 $ ve $e _3 11 ' den oluşur \equiv $ .  Benzer şekilde, ikinci qubit ile ilgileniyorsanız $S $ $e _2 \equiv 01 $ ve $e _3 \ equ11 ' den oluşur $ .  Ardından, seçilen qubit $1 olarak ölçme olasılığı $ durum vektörü $ \ PSI içindir$

$ $ P (\Text{Outcome } = 1) = \ sum_ {e_k \Text { } S } \psı ^ \dağılım e_k e_k ^ \dağılım \ psıger.
$$

> [!NOTE]
> Bu belgede, hesaplama temelini etiketlemek için küçük endian biçimini kullanıyoruz. Little endian biçiminde, önce en az önemli bitler gelir. Örneğin, küçük endian biçimindeki dört sayı, bit 001 dizesi tarafından temsil edilir.

Her qubit ölçümü yalnızca $0 $ veya $1 değerini sağlayabileceğinizden $ , $0 ölçmesinin olasılığı yalnızca $ $1-P (\Text{Outcome } = 1) $ şeklindedir.  Bu nedenle $1 ölçmesinin olasılığı için yalnızca açık olarak bir formül sağlıyoruz $ .

Bu tür bir ölçümün durumunda olduğu eylem matematiksel olarak ifade edilebilir

$ $ \psı \mapsto \frac { \ sum_ {e_k \Text { in set} S } e_k e_k ^ \hanger \Psı } {\Sqrt{p (\Text{Outcome } = 1)}}.
$$

Ölçüm olasılığı sıfır olduğunda, dikkatli olan okuyucu ne olacağı hakkında endişelenmeye başlayabilir.  Bu durumda, sonuçta elde edilen durum teknik olarak tanımsız olsa da, olasılık sıfır olduğundan bu tür bir durumla uğraşmak zorunda kaldık!


$Yukarıda verilen Tekdüzen durum vektörü $ \psı olarak ele alındığında ve ilk qubit 'i ölçmeye ilgileniyorsa, 

$ $ P (ilk qubit } = 1) = (\psı ^ \dağılım e_1) (e_1 ^ \dağılım \ PSI) + (\psı ^ \hanger e_3) (e_3 ^ \dağılım \ PSI) = | e_1 ^ \dağılım \psı | ^ 2 + | e_3 ^ \dağılım \ PSI ^ | 2.
$$

Bunun yalnızca, $10 sonuçlarını ölçmek için beklenen iki olasılıkların toplamı olduğunu $ ve $11 ' nin $ ölçülecek tüm qubits olduğunu unutmayın.
Örneğimiz için, bu değerlendirme

$ $ \frac{1 } {4 } \left | \begin{ bmatrix } 0&0&1&0 \end { bmatrix } \begin{ bmatrix } 1 \\\\ 1 \\\\ 1 \\\\ 1 \end { bmatrix } \ Right | ^ 2 + \frac{1 } {4 } \ Left | \begin{ bmatrix } 0&0&0&1 \end { bmatrix } \begin{ bmatrix } 1 \\\\ 1 \\\\ 1 \\\\ 1 \end { bmatrix } \ Right | ^ 2 = \frac{1 } {2 } .
$$

ıntuetdiğimiz anlamı bize söylerken, olasılık olması gerekir.  Benzer şekilde, durum şöyle yazılabilir

$ $ \frac { \frac{e_1 } {2 } + \frac{e_3 } {2 } } {\sqrt { \frac{1 { } 2 } }} = \frac{1 } {\sqrt{2 } } \begin{ bmatrix } 0 \\\\ 0 \\\\ 1 \\\\ 1 \end {bmatrix}
$$

ıntuize uygun olarak tekrar.

## <a name="two-qubit-operations"></a>İki-qubit Işlemleri
Tek qubit durumunda olduğu gibi, herhangi bir Unitary dönüştürmesi qubits üzerinde geçerli bir işlemdir. Genel olarak, $n qubits 'teki bir Unitary dönüştürmesi $ $ , $2 ^ n \times 2 ^ n $ (Bu nedenle, $2 ^ n boyutundaki vektörler üzerinde çalışır $ ), yani $U ^ {-1 } = U ^ \dağılım gibi $ bir matris $U.
Örneğin, CNOT (denetlenen) geçidi, yaygın olarak kullanılan iki-qubit kapısı ve aşağıdaki Unitary matrisi tarafından temsil edilir:

$ $ \operatorname{CNOT } = \begin{ bmatrix } 1 \ 0 \ 0 \ 0 \\ \\ 0 \ 1 \ 0 \ 0 \\ \\ 0 \ 0 \ 0 \ 1 \\ \\ 0 \ 0 \ 1 \ 0 \ End{bmatrix}
$$

Ayrıca, her iki qubit üzerinde tek qubit kapıları uygulayarak iki-qubit geçitleri de oluşturabilirsiniz. Örneğin, kapıları uygulıyoruz 

$ $ \begin{bmatrix}
a \ b \\\\ c \ d \end{bmatrix}
$$

ve

$ $ \begin{bmatrix}
e \ f \\\\ g \ h \end{bmatrix}
$$

ilk ve ikinci qubits 'e sırasıyla, bu, Tensor ürünü tarafından verilen iki-qubit Unitary 'i uygulamaya eşdeğerdir: $ $ \begin{bmatrix}
a \ b \\\\ c \ d \end{bmatrix}
\otimes \begin{bmatrix}
e \ f \\\\ g \ h \ End{ bmatrix } = \begin{bmatrix}
    AE \ AF \ be \ BF \\ \\ AG \ Ah \ bg \ BH \\ \\ CE \ CF \ de \ df \\ \\ CG \ ch \ DG \ DH \End{ bmatrix } . $ $ bu nedenle, bilinen bazı tek qubit kapıları 'ın tencursor ürününü alarak iki değerli bit kapıları. İki-qubit kapılarının bazı örnekleri şunlardır $H \otimes H $ , $X \otimes \cıvadone $ ve $X \Otimes Z $ .

İki adet tek qubit kapısı, tenslı ürününü alarak iki qubit ağ geçidi tanımlalarken, listesiyse 'nin doğru olmadığını unutmayın. Her iki-qubit kapıları tek qubit kapıları 'ın Tensor ürünü olarak yazılabilir.  Bu tür bir ağ geçidi, bir *entrini* geçidi olarak adlandırılır. Bir entrini kapısı örneği, CNOT Kapısı ' dir.

Denetlenen bir kapı arkasındaki ıntuun, rastgele kapıların genelleştirilemez.  Genel olarak denetlenen bir geçit, belirli bir qubit $1 değilse kimlik (yani, hiçbir eylemde yok) olarak davranan bir kapıdır $ .  Bu durumda, $ bir $ \Lambda \_ x (U) $ ile $x etiketli qubit üzerinde denetlenen bir Unitary olduğunu belirledik.  Örnek olarak \_ } } \_ } { } \_ \_ } } \_ } { } , \_ $ \_ $ $0 ve $1 değerlerine karşılık gelen tek bir qubit Için, $e 0 ve $e 1 ' in işlem temelinde vektörlerine $ $ sahip bir $ \ Lambda_0 (U) e {1 \Otimes {\psı = e {1 \otimes U \psı $ ve $ \lambda 0 (u) e {0 \otimes {\psı = e {0 \otimes \ PSI $.  Örneğin, aşağıdaki denetlenen $Z kapısını göz önünde bulundurun $ . bunu, $ $ \lambda \_ 0 (Z) = \begin{ bmatrix } 1&0&0&0 0&1&0 \\ \\&0 \\ \\ 0&0&1&0 \\ \\ 0&0&0 & -1 \ End{ bmatrix } = (\cıvadone \otimes h) \operatorname{CNOT } (\cıvadone \otimes h) olarak ifade edebiliyoruz.
$$

Denetimli birimlere verimli bir şekilde derleme, önemli bir zorluktur.  Bunu yapmanın en kolay yolu, temel kapıların denetlenen sürümlerinin bir veritabanının ayarlanmasını ve orijinal Unitary işlemindeki tüm temel kapıları denetimli karşılığına göre değiştirmeyi gerektirir.  Bu çoğunlukla, aynı etkiyi elde etmek için yalnızca birkaç kapıya denetimli sürümlerle değiştirmek üzere kullanılabilir.  Bu nedenle, en iyi duruma getirilmiş bir sürüm tanındığı takdirde, iskemizdeki kullanıcının Unitary 'ın denetimli bir sürümünü tanımlamasına veya bağlanmasına izin veren Naïve yöntemini gerçekleştirme olanağı sunuyoruz.

Kapılar, klasik bilgiler kullanılarak da denetlenebilir.  Sınıf denetimli olmayan bir not kapısı, örneğin, yalnızca sıradan olmayan bir kapıdır, ancak yalnızca klasik bir bit, bir $ hisse bitine karşılık $1 ise geçerlidir.  Bu anlamda, sınıf tarafından denetlenen bir geçit, kapıdaki hisse amayan bir bildirim yalnızca kodun bir dalında uygulanırsa bir if bildirisi olarak düşünülebilir.


Tek qubit durumunda olduğu gibi, $4 \times 4 $ Unitary kümesi, bu kümeden rastgele duyarlığa kadar olan bir kapıları ürünüyle ilgili olarak, bir iki-qubit kapısı kümesi evrensel bir durumdur.
Bir Evrensel kapı kümesi örneği, Hadamard kapısı, T kapısı ve CNOT kapısı. Bu kapıların ürünlerini alarak, iki qubit üzerinde her türlü Unitary matrisini yaklaşık olarak kullanabiliriz.

## <a name="many-qubit-systems"></a>Birçok-qubit sistem
Daha küçük sistemlerden birçok qubit hisse durumu oluşturmak için iki-qubit durumunda araştırılan aynı desenleri izliyoruz.  Bu tür durumlar, daha küçük durumlardan oluşan tencursor ürünleri kullanılarak oluşturulmuştur.  Örneğin, $1011001 bit dizesini $ bir hisse bilgisayar bilgisayarında kodlamayı göz önünde bulundurun.  Bunu şöyle kodlayabiliriz

$ $1011001 \equıv \begin{ bmatrix } 0 \\ 1 \end{\otimes \begin{1 0 \end{\otimes \begin{0 1 \end{\otimes \begin{0 1 \ End{\otimes \begin{1 0 \end{\otimes \begin{1 0 \end{ \\ bmatrix } bmatrix } \\ \\ bmatrix } bmatrix } \\ \\ bmatrix } bmatrix } \\ \\ bmatrix } bmatrix } \\ \\ bmatrix } bmatrix } \\ \\ bmatrix } \otimes \begin{ bmatrix } 0 \\ \\ 1 \end{ bmatrix } .
$$

Hisse kapıları tamamen aynı şekilde çalışır.  Örneğin, $X $ geçidini ilk qubit 'e uygulamak ve sonra ikinci ve üçüncü qugeler arasında BIR CNOT gerçekleştirmek istiyorsanız bu dönüşümü şu şekilde ifade eteceğiz

\begin{align}
& (X \otimes \operatorname{CNOT}_{12 \otimes \ bolbitti \ cıvabitti \otimes \cıvabitti \otimes } \otimes \cıvadone) \begin{ bmatrix } 0 \\ \\ 1 \end{ bmatrix } \otimes \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } \otimes \begin{ bmatrix } 0 \\ \\ 1 \end{ bmatrix } \otimes \begin{ bmatrix } 0 \\ \\ 1 \ End{ bmatrix } \otimes \begin{1 0 \ End{\otimes bmatrix } \\ \\ bmatrix } \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } \otimes \begin{ bmatrix } 0 \\ \\ 1 \end{ bmatrix } \\ \\ & \qdörtlü \qquad \equiv 0011001.
\end{align}

Birçok qubit sisteminde, genellikle hisse bilgisayarı için geçici bellek işlevi sunan qubit ve serbest bırakma gereksinimi vardır.  Böyle bir qubit, anyala olarak adlandırılır.  Varsayılan olarak, qubit durumunun ayırma sonrasında $e _0 olarak başlatıldığını varsaytık $ .  Yeniden ayırmayı yapmadan önce $e _0 ' a geri döndüğünü varsayalım $ .  Bu varsayım, bir anyalı qubit, serbest bırakıldığında başka bir qubit yazmaç ile birlikte eşit hale gelirse, ayırmayı kaldırma işlemi anakla 'ya zarar verir.  Bu nedenle, bu tür qubits 'in yayınlanmadan önce ilk durumuna döndürüldüğünü varsaydık.

Son olarak, iki qubit hisse bilgisayarı için evrensel hisse bilgi işlem düzeyine ulaşmak üzere, geçit kümesine yeni kapılar eklenmesi gerektiğinden, Multi-qubit durumunda yeni bir kapı tanıtılmalıdır.  $ $ Her türlü genel Unitary dönüştürmesi bir dizi iki qubit dönüşte parçalanabileceğinden, kapıların birçok qubit üzerinde bir Evrensel kapı kümesi $H $T ve cnot oluşturmamalıdır.  Daha sonra, iki-qubit durumu için geliştirilmiş olan teorik 'ten yararlanabilir ve çok sayıda qubit olduğunda bunu burada tekrar kullanabilirsiniz.

Şimdiye kadar kullanmakta olduğumuz doğrusal cebirsel gösterimi, çok qubit durumlarını anlatmak için kesinlikle kullanılabilir, ancak durumların boyutunu arttık.  Bir uzunluk 7 bit dizesinin ortaya çıkan sütun vektörü, örneğin, $ daha önce çok daha önce açıklanan gösterimi kullanarak ifade $128 boyutludur.  Bu nedenle, daha sonra bu yüksek boyutlu vektörleri öz konusunda bize izin veren hisse alım durumunda daha sonra genel bir gösterim sunuyoruz.
