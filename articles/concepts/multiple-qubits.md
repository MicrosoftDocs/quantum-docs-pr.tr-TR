---
title: Birden çok qubit | Microsoft Docs
description: Birden çok kubit
author: QuantumWriter
uid: microsoft.quantum.concepts.multiple-qubits
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: e9c043f4ee41a878b9544a27d5ea052fce29f06e
ms.sourcegitcommit: 27c9bf1aae923527aa5adeaee073cb27d35c0ca1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74863225"
---
# <a name="multiple-qubits"></a>Birden çok qubit

Tek-qubit kapıları, belirli bir zamanda birden fazla durumda olma yeteneği gibi bazı sayaç sezgisel özelliklere sahip olsa da, bir hisse başında bir bilgisayar tek qubit kapıları olsaydı, bu, şu kadar bir işlem gücü olan bir cihazımız bir hesaplayıcı, tek başına klasik bir süper bilgisayara izin verir.
Yalnızca Lem bilgi işlemin doğru gücü, qubits sayısını artırdığımız için yalnızca daha açık hale gelir.
Bu güç, parça devlet vektörlerine ait vektör alanı boyutu, qubit sayısıyla üstel olarak artmıştır.
Yani, tek bir qubit, bir 50-qubit hisse hesaplamasının benzetimini yapan, mevcut süper bilgisayarların sınırlarını eşit bir şekilde iletebileceği anlamına gelir.
Hesaplama boyutunu yalnızca bir ek qubit ile artırmak, durumu depolamak için gereken belleği *iki katına çıkarır* ve hesaplama süresini kabaca *ikiye katlanır* .
Hesaplama gücü 'nin bu hızlı katmasının nedeni nispeten az sayıda qubit olan bir hisse bilgisayarının, bazı hesaplama görevleri için yarın ve daha fazla en güçlü süper bilgisayarı daha fazla artırabileceğini tahmin edebilirsiniz.

Hisse madevlet vektörlerine neden üstel büyümemiz gerekir?  Bu bölümde, tek qubit durumlarından çok qubit durumları oluşturmak için kullanılan kuralların yanı sıra, bir evrensel çok değerli-qubit bilgisayar oluşturmak için bir geçit kümesine dahil etmemiz gereken geçit işlemlerini tartışmaktır.
Bu araçların, Q # kodunda yaygın olarak kullanılan kapı kümelerini anlaması ve ayrıca, entanglement veya girişim oluşturma maliyeti gibi ne kadar hisse yaradığına ilişkin öngörülere, klasik bilgi işlem ile daha güçlü bir şekilde bilgi elde etmek için kesinlikle gereklidir.

## <a name="representing-two-qubits"></a>Iki qubit 'i temsil etme
Bir-ve iki-qubit durumu arasındaki temel fark, iki-qubit durumlarının iki boyut yerine dört boyutlu olması gerektiğidir.
Bunun nedeni, iki-qubit durumlarının hesaplama temelinin, tek qubit durumlarının tencursor ürünleri tarafından oluşturulmuş olmasından kaynaklanır.  Örneğin, \begin{hizalaması} 00 \ EQUIV \ Begin{bmatrix}1 \\var \\ 0 \ End{bmatrix}\otimes \begin{bmatrix}1 \\\\ 0 \end{bmatrix} & = \begin{bmatrix}1 \\\\ 0\\\\ 0\\\\ 0 \end{bmatrix}, \qdörtlü 01 \equk\begin{bmatrix}1 \\\\ 0 \end{bmatrix}\otimes \begin{bmatrix}0 \\\\ 1 \end{bmatrix} = \begin{bmatrix}0 \\\\ 1\\\\ 0\\\\ 0 \end{bmatrix},\\\\ 10 \equk\begin{bmatrix}0 \\\\ 1 \end{bmatrix}\otimes \begin{bmatrix}1 \\\\ 0 \end{bmatrix} & = \begin{bmatrix}0 \\\\ 0\\\\ 1\\\\ 0 \ End{bmatrix}, \qdörtlü 11 \equıv \begin{bmatrix}0 \\\\ 1 \end{bmatrix}\otimes \begin{bmatrix}0 \\\\ 1 \end{bmatrix} = \begin{bmatrix}0 \\\\ 0\\\\ 0 @no__ t_40_ \\ 1 \ End{bmatrix}.
\end{hizalaması}

Bu oluşturma kullanılarak, $n $ qubits 'in hisse boyutunun, $2 ^ n $ boyutundaki bir birim vektörü ile temsil edildiği kolayca görüyordu.  Vektör

$ $ \begin{bmatrix} \ alpha_{00} \\\\ \ alpha_{01} \\\\ \ alpha_{10} \\\\ \ alpha_{11} \end{bmatrix} $ $

$ | \ alpha_{00}| ^ 2 + | \ alpha_{01}| ^ 2 + | \ alpha_{10}| ^ 2 + | \ alpha_{11}| ^ 2 = 1 $ için iki qubitde bir hisse durumu temsil eder. Tek qubit 'de olduğu gibi, birden çok qubit için hisse durum vektörü, sistemin davranışını anlatmak için gereken tüm bilgileri tutar.

Biri $ \begin{bmatrix} \Alpha \\\\ \beta \end{bmatrix} $ ve $ \begin{bmatrix} \gama \\\\ \delta \end{bmatrix} $ durumunda iki ayrı qubit verilirse, karşılık gelen iki-qubit durumu

$ $ \begin{bmatrix} \Alpha \\\\ \beta \end{bmatrix} \otimes \begin{bmatrix} \gama \\\\ \delta \end{bmatrix} = \begin{bmatrix} \Alpha \begin{bmatrix} \gama \\\\ \delta \end{bmatrix} \\\\ \beta \begin{bmatrix}\gamma \\\\ \delta \end{bmatrix} \end{bmatrix} = \begin{bmatrix} \harflerden \gama \\\\ \harflerden \delta \\\\ \beta\gama \\\\ \beta\delta \end{bmatrix} , $$

$ \otimes $ işleminin, vektörlerin Tensor ürünü (veya Kronecker ürünü) olarak adlandırıldığını burada belirtin. İki adet tek qubit durumunun her zaman bir iki-qubit durumu oluşturmak için her zaman götürebileceğine, iki-qubit hisse senedi durumlarının iki adet tek qubit eyaletinin tencursor ürünü olarak yazılamayacağını unutmayın.
Örneğin, bir durum $ \psı = \begin{bmatrix} \Alpha \\\\ \beta \end{bmatrix} $ ve $ \phi = \begin{bmatrix} \gama \\\\ \delta \end{bmatrix} $ gibi durumlar yoktur 

$ $ \psı\otimes \phi = \begin{bmatrix} 1/\ sqrt{2} \\\\ 0 \\\\ 0 \\\\ 1/\ sqrt{2} \end{bmatrix}. $ $ 

Bu tür bir iki-qubit durumu, tek qubit durumlarının tencursor ürünü olarak yazılamaz, "entangled State" olarak adlandırılır; iki qubit, [*bağımsız olarak kabul edilir.* ](https://en.wikipedia.org/wiki/Quantum_entanglement)  Gevşekle, hisse Eyaleti tek qubit durumları için bir Tensor ürünü olarak düşünülmediği için, durumun tuttuğu bilgiler tek tek qubits 'e göre sınırlandırmaz.  Bunun yerine, bilgiler, iki durum arasındaki eş ilişkilerdeki yerel olmayan bir şekilde depolanır.  Bu bilgilerin yer aldığı, klasik bilgi işlem üzerinden hisse bilgi işlem özelliklerinin büyük ayrım özelliklerinden biridir ve [hisse maporsyon](https://github.com/microsoft/Quantum/tree/master/samples/getting-started/teleportation) ve hisse ansız [hata düzeltmesi](xref:microsoft.quantum.libraries.error-correction)dahil olmak üzere bir dizi hisse protokolde gereklidir.

## <a name="measuring-two-qubit-states"></a>Iki-qubit durumu ölçme ##
İki-qubit durumu ölçme, tek qubit ölçümlerine çok benzer. Durumu ölçme

$ $ \begin{bmatrix} \ alpha_{00} \\\\ \ alpha_{01} \\\\ \ alpha_{10} \\\\ \ alpha_{11} \end{bmatrix} $ $

olasılık $ | \ alpha_{00}| ^ $2, $1 $, olasılık $ | \ alpha_{01}| ^ $2, $10 $ ile olasılık $ | \ alpha_{10}| ^ $2 ve $11 $ | \ alpha_{11}| ^ $2 ile $0 $ verir. $ \ Alpha_{00}, \ alpha_{01}, \ alpha_{10}, $ ve $ \ alpha_{11}$ değişkenleri bu bağlantıyı açık hale getirmek için kasıtlı olarak adlandırılmıştı. Ölçüden sonra, sonuç $0 $ ise, iki-qubit sistemin hisse TI durumu daraltıldı ve şu anda

$ $0 \equıv \begin{bmatrix} 1 \\\\ 0 \\\\ 0 \\\\ 0 \end{bmatrix}.
$$

İki-qubit hisse durumunun yalnızca bir qubitinin ölçülmesi de mümkündür. Yalnızca bir alt sisteme daraltılacağından, her bir qubits 'in yalnızca bir kısmını ölçecek şekilde, ölçümün etkileri çok daha farklı bir durumdur.  Diğer bir deyişle, bu gibi durumlarda yalnızca bir qubit yalnızca bir qubit, alt sistemlerden yalnızca birini daraltır ancak bunların tümünü kullanmaz.  

Bunu görmek için, ilk olarak iki qubit üzerinde $H $, başlangıçta "0" durumuna ayarlanan Hadamard Transform $ ' i uygulayarak oluşturulan aşağıdaki durumun ilk qubit 'i ölçmesini düşünün: $ $ H ^ {\otimes 2} \left (\begin{bmatrix}1 \\\\ 0 \end{bmatrix}\otimes \begin{bmatrix}1 \\\\ 0 \end{bmatrix} \ sağ) = \frac{1}{2}\begin{bmatrix}1 & 1 & 1 & 1 \\\\ 1 &-1 & 1 &-1 \\\\ 1 & 1 &-1 &-1 \\\\ 1 &- 1 &-1 & 1 \end{bmatrix}\begin{bmatrix}1\\\\ 0\\\\ 0\\\\ 0 \ End {bmatris} = \frac{1}{2}\begin{bmatrix}1\\\\ 1\\\\ 1\\\\ 1 \ End {bmatrix} \mapsto \begin{Cases}\Text{Outcome} = 0 & \frac{1}{\sqrt{2}} \begin{bmatrix}1\\\\ 1\\\\ 0\\\\ 0 \end{bmatrix}\\\\ \Text{outcome} = 1 & \frac{1}{\sqrt{2}} \begin{bmatrix}0\\\\ 0\\\\ 1\\\\ 1 \end{bmatrix}\\\\ \end{Cases}.
$ $ Her iki sonuç da %50 oranında meydana gelen bir olasılıktır.  Her ikisi için %50 olasılık olan sonuç, ilk zbit üzerinde $0 $ ile $1 $ değiştirme altında ilk hisse

Birinci veya ikinci qubit ölçmeye yönelik matematik kuralı basittir.  $E _k $ $k ^ {\rm TH} $ hesaplama tabanlı vektörün olmasına izin vermemiz ve $S $ $e $ değerinin bu değeri için $1 $ değerini almasını sağlamak üzere tüm _k $k $ $ olarak izin verir.  Örneğin, ilk qubit ' i ölçmeye ilgileniyorsanız $S $ $e _2 \ equ$10 ve $e _3 \ equ$11 ' den oluşur.  Benzer şekilde, ikinci qubit ile ilgileniyorsanız $S $ $e _1 \ EQUIV $1 ve $e _3 \ equ$11 ' den oluşur.  Ardından, seçilen qubit 'i $1 $ olarak ölçmeye olasılığı, durum vektörü $ \psı $ şeklindedir

$ $ P (\Text{outcome} = 1) = \ sum_ {e_k \Text{set} S} \psı ^ \hanger e_k e_k ^ \gesger \ PSI.
$$

Her qubit ölçümü yalnızca $0 $ veya $1 $ ' i sağlayabileceğinizden, $0 $ ölçmesinin olasılığı yalnızca $1-P (\Text{outcome} = 1) $ olur.  Bu nedenle, $1 $ ölçmesinin olasılığı için yalnızca açık olarak bir formül sağlıyoruz.

Bu tür bir ölçümün durumunda olduğu eylem matematiksel olarak ifade edilebilir

$ $ \psı \mapsto \frac{\ sum_ {e_k \Text{set} S} e_k e_k ^ \hanger \Psı}{\sqrt{p (\Text{outcome} = 1)}}.
$$

Ölçüm olasılığı sıfır olduğunda, dikkatli olan okuyucu ne olacağı hakkında endişelenmeye başlayabilir.  Bu durumda, sonuçta elde edilen durum teknik olarak tanımsız olsa da, olasılık sıfır olduğundan bu tür bir durumla uğraşmak zorunda kaldık!


Yukarıda verilen Tekdüzen durum vektörü olarak $ \psı $ ' i alırsak ve ilk qubit ' i ölçmeye ilgileniyorsa, 

$ $ P (ilk qubit} = 1) = (\psı ^ \hanger e_2) (e_2 ^ \gesger \ PSI) + (\psı ^ \dağılım e_3) (e_3 ^ \dağılım \ PSI) = | e_2 ^ \dağılım \ psi | ^ 2 + | e_3 ^ \ dağılım \ PSI | ^ 2.
$$

Bunun yalnızca, $10 $ ve $11 $ değerlerinin ölçülmesi için beklenen iki olasılıkların toplamı olduğunu unutmayın.
Örneğimiz için, bu değerlendirme

$ $ \frac{1}{4}\left | \begin{bmatrix}0 & 0 & 1 & 0 \ End {bmatrix} \ BEGIN {bmatrix} 1\\\\ 1\\\\ 1\\\\ 1 \ End {bmatrix} \ doğru | ^ 2 + \frac{1}{4}\left | \begin{bmatrix}0 & 0 & 0 & 1 \ End {bmatrix} \ başlangıç {bmatris} 1\\\\ 1\\\\ 1\\\\ 1 \ End {bmatrix} \right | ^ 2 = \frac{1}{2}.
$$

ıntuetdiğimiz anlamı bize söylerken, olasılık olması gerekir.  Benzer şekilde, durum şöyle yazılabilir

$ $ \frac{\frac{e_2}{2}+ \frac{e_3}{2}} {\sqrt{\frac{1}{2}}} = \frac{1}{\sqrt{2}} \begin{bmatrix} 0\\\\ 0\\\\ 1\\\\ 1 \ End {bmatrix} $ $

ıntuize uygun olarak tekrar.

## <a name="two-qubit-operations"></a>İki-qubit Işlemleri
Tek qubit durumunda olduğu gibi, herhangi bir Unitary dönüştürmesi qubits üzerinde geçerli bir işlemdir. Genel olarak, $n $ qubits üzerindeki bir Unitary dönüştürmesi, $2 ^ n \ Süre2 ^ n $ ($ 2 ^ n $ boyutundaki vektörlerde çalışır), yani $U ^{-1} = U ^ \linger $ gibi bir matris $U $. Örneğin, CNOT (denetlenen) geçidi, yaygın olarak kullanılan iki-qubit kapısı ve aşağıdaki Unitary matrisi tarafından temsil edilir:

$ $ \operatorname{CNOT} = \begin{bmatrix} 1 \ 0 \ 0 \ 0 \\\\ 0 \ 1 \ 0 \ 0 \\\\ 0 \ 0 \ 0 \ 1 \\\\ 0 \ 0 \ 1 \ 0 \ End{bmatrix} $ $

Ayrıca, her iki qubit üzerinde tek qubit kapıları uygulayarak iki-qubit geçitleri de oluşturabilirsiniz. Örneğin, kapıları uygulıyoruz 

$ $ \begin{bmatrix} a \ b\\\\ c \ d \end{bmatrix} $ $

'nı ve

$ $ \begin{bmatrix} e \ f\\\\ g \ h \ End{bmatrix} $ $

ilk ve ikinci qubits 'e sırasıyla, bu, Tensor ürünü tarafından verilen iki-qubit Unitary 'i uygulamaya eşdeğerdir: $ $ \begin{bmatrix} a \ b\\\\ c \ d \end{bmatrix} \otimes \begin{bmatrix} e \ f\\\\ g \ h \end{bmatrix} = \begin{bmatrix} AE \ AF \, \ BF \\olmalıdır \\ AG \ Ah \ bg \ BH \\\\ CE \ CF \ de \ df \\\\ CG \ ch \ DG \ DH \ End{bmatrix}. $ $ bu nedenle, bilinen bazı tek qubit kapıları 'ın tencursor ürününü alarak iki-qubit kapıları form oluştururuz. İki-qubit kapıları bazı örnekleri şunlardır $H \otimes H $, $X \otimes \cıvadone $ ve $X \otimes Z $.

İki adet tek qubit kapısı, tenslı ürününü alarak iki qubit ağ geçidi tanımlalarken, listesiyse 'nin doğru olmadığını unutmayın. Her iki-qubit kapıları tek qubit kapıları 'ın Tensor ürünü olarak yazılabilir.  Bu tür bir ağ geçidi, bir *entrini* geçidi olarak adlandırılır. Bir entrini kapısı örneği, CNOT Kapısı ' dir.

Denetlenen bir kapı arkasındaki ıntuun, rastgele kapıların genelleştirilemez.  Genel olarak denetlenen bir geçit, belirli bir qubit $1 $ olmadığı sürece kimlik (yani, hiçbir eylemde yok) davranan bir kapıdır.  Bu durumda, bir $ \Lambda\_x (U) $ ile $x $ etiketli qubit üzerinde denetlenen bir Unitary olduğunu belirledik.  Örnek olarak, bir $ \ Lambda_0 (U) e\_{1}\otimes {\psı} = e\_{1}\otimes U {\psı} $ ve $ \Lambda\_0 (U) e\_{0}\otimes {\psı} = e\_{0}\otimes{\psı} $, $e\_$0 ve $e\_$1, $0 $ ve $1 $ değerlerine karşılık gelen tek bir qubit için hesaplama tabanlı vektörlerdir.  Örneğin, aşağıdaki denetlenen-$Z $ Gate ' i göz önünde bulundurun. bunu $ $ \Lambda\_0 (Z) = \begin{bmatrix}1 & 0 & 0 & 0\\\\0 olarak ifade edebiliriz & 1 & 0 & 0\\\\0 & 0 & 1 & 0\\\\0 & 0 & 0 &-1 \end{bmatrix} = (\boldone\otimes H) \operatorname{CNOT} (\boldone\otimes H).
$$

Denetimli birimlere verimli bir şekilde derleme, önemli bir zorluktur.  Bunu yapmanın en kolay yolu, temel kapıların denetlenen sürümlerinin bir veritabanının ayarlanmasını ve orijinal Unitary işlemindeki tüm temel kapıları denetimli karşılığına göre değiştirmeyi gerektirir.  Bu çoğunlukla, aynı etkiyi elde etmek için yalnızca birkaç kapıya denetimli sürümlerle değiştirmek üzere kullanılabilir.  Bu nedenle, en iyi duruma getirilmiş bir sürüm tanındığı takdirde, iskemizdeki kullanıcının Unitary 'ın denetimli bir sürümünü tanımlamasına veya bağlanmasına izin veren Naïve yöntemini gerçekleştirme olanağı sunuyoruz.

Kapılar, klasik bilgiler kullanılarak da denetlenebilir.  Sınıf denetimli olmayan bir not kapısı, örneğin, yalnızca sıradan olmayan bir kapıdır, ancak yalnızca klasik bir bit, bir hisse bitin aksine $1 $ ise geçerlidir.  Bu anlamda, sınıf tarafından denetlenen bir geçit, kapıdaki hisse amayan bir bildirim yalnızca kodun bir dalında uygulanırsa bir if bildirisi olarak düşünülebilir.


Tek qubit durumunda olduğu gibi, herhangi bir $4 \ süre$4 Unitary matrisi, bu kümeden rastgele duyarlığa kadar olan bir kapı ürünüyle ilgili olarak, iki-qubit kapısı kümesi Universal olur.
Bir Evrensel kapı kümesi örneği, Hadamard kapısı, T kapısı ve CNOT kapısı. Bu kapıların ürünlerini alarak, iki qubit üzerinde her türlü Unitary matrisini yaklaşık olarak kullanabiliriz.

## <a name="many-qubit-systems"></a>Birçok-qubit sistem
Daha küçük sistemlerden birçok qubit hisse durumu oluşturmak için iki-qubit durumunda araştırılan aynı desenleri izliyoruz.  Bu tür durumlar, daha küçük durumlardan oluşan tencursor ürünleri kullanılarak oluşturulmuştur.  Örneğin, bir hisse bilgisayarında $1011001 $ bit dizesini kodlamayı değerlendirin.  Bunu şöyle kodlayabiliriz

$ $1011001 \equıv \begin{bmatrix} 0 \\\\ 1 \end{bmatrix}\otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}\otimes \begin{bmatrix} 0 \\\\ 1 \end{bmatrix}\otimes \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} \otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}\otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}\otimes \begin{bmatrix} 0 \\\\ 1 \end{bmatrix}.
$$

Hisse kapıları tamamen aynı şekilde çalışır.  Örneğin, $X $ geçidini ilk qubit 'e uygulamak ve sonra ikinci ve üçüncü qugeler arasında bir CNOT gerçekleştirmek istiyorsanız bu dönüşümü şu şekilde ifade eteceğiz

\begin{hizalaması} & (X \otimes \operatorname{CNOT}_{12}\otimes \boldone\otimes \cıvadone \otimes \cıvadone \otimes \cıvadone) \begin{bmatrix} 0 \\\\ 1 \end{bmatrix}\otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}\otimes \begin{bmatrix} 0 \\\\ 1 \end{bmatrix}\otimes \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} \otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}\otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}\otimes \begin{bmatrix} 0 \\\\ 1 \end{bmatrix}\\\\ & \qquad\qquad\equ0011001.
\end{hizalaması}

Birçok qubit sistemde, genellikle hisse bilgisayarı için geçici bellek olarak çalışan qubits 'i ayırmak ve serbest bırakmak yeterlidir.  Böyle bir qubit, anyala olarak adlandırılır.  Varsayılan olarak, qubit durumunun ayırma sonrasında $e _0 $ olarak başlatıldığını varsaytık.  Geri döndürülmeden önce $e _0 $ ' a yeniden döndürüldüğünü varsayalım.  Bu varsayım önemlidir çünkü bir anıllanla, geçersiz hale geldiğinde, başka bir qubit yazmaç ile ayrılmış hale gelirse, serbest bırakma işlemi de anyala 'ya zarar verir.  Bu nedenle, bu tür qubits 'in yayınlanmadan önce ilk durumuna döndürüldüğünü varsaydık.

Son olarak, iki qubit hisse bilgisayarı için evrensel hisse bilgi işlem düzeyine ulaşmak üzere, geçit kümesine yeni kapılar eklenmesi gerektiğinden, Multi-qubit durumunda yeni bir kapı tanıtılmalıdır.  Herhangi bir genel Unitary dönüştürmesi bir dizi iki qubit döndürme dizisine bölünebildiğinden, $H $, $T $ ve CNOT, birçok qubit üzerinde evrensel bir kapı kümesi kümesidir.  Daha sonra, iki-qubit durumu için geliştirilmiş olan teorik 'ten yararlanabilir ve çok sayıda qubit olduğunda bunu burada tekrar kullanabilirsiniz.

Şimdiye kadar kullanmakta olduğumuz doğrusal cebirsel gösterimi, çok qubit durumlarını anlatmak için kesinlikle kullanılabilir, ancak durumların boyutunu arttık.  Bir uzunluk 7 bit dizesinin ortaya çıkan sütun vektörü, örneğin, daha önce çok daha önce açıklanan gösterimi kullanarak ifade eden $128 $ boyutlu.  Bu nedenle, daha sonra bu yüksek boyutlu vektörleri öz konusunda bize izin veren hisse alım durumunda daha sonra genel bir gösterim sunuyoruz.
