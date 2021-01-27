---
title: İçindeki hisse algoritmaları Q#
description: Genliği yükseltme, Fourier dönüşümü, Draper ve Beauregard adders ve aşama tahmini dahil olmak üzere temel hisse bilgi işlem algoritmaları hakkında bilgi edinin.
author: QuantumWriter
ms.author: martinro
ms.date: 12/11/2017
ms.topic: conceptual
uid: microsoft.quantum.libraries.standard.algorithms
no-loc:
- Q#
- $$v
ms.openlocfilehash: d4d8c35b3196ffb9915c6da06116b3c7dfd0562a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98859017"
---
# <a name="quantum-algorithms"></a>Hisse algoritmaları #

## <a name="amplitude-amplification"></a>Genliğini Yükseltme ##

*Genliği yükseltme* , hisse bilgi işlem aracının temel araçlarından biridir. Bu, Grover 'in arama, genlik tahmini ve birçok hisse makine öğrenimi algoritmalarının temelini oluşturan temel bir fikirdir.  Birçok çeşit vardır ve ' de, Q# uygulamanın en geniş bölümünde izin verilen kısmi yansımalar Ile yükümlülüğü düzeyini temel alan genel bir sürüm sağlıyoruz.

Genizme 'nin arkasındaki orta düşünce, bir dizi yansıma gerçekleştirerek istenen sonucun oluşma olasılığını artırmakta.  Bu yansıtılamalar, ilk durumu, genellikle işaretli bir durum olarak adlandırılan istenen hedef durumuna yaklaştırır.  Özellikle, ilk durumu işaretli bir durumda olacak şekilde ölçmeye olasılığı $ \sin ^ 2 (\teta) $ ise, gen$m liği yükseltme işleminden sonra, başarı olasılığı $ \sin ^ 2 ((2m + 1) \teta) $ olur.  Bu, bazı $n $ \teta = \ Pi/[2 (2n + 1)] $ değeri için $ \ teta = \ Pi/[2 (2n + 1)] $ olduğunda, daha sonra genliği yükseltme \\ $n $ yineleme olan $ yinelemeden sonra% $100 ' a kadar başarı olasılığını  $ \Teta = \sin ^ {-1} (\Sqrt{\pr (success)}) $ bu yana, başarılı bir şekilde elde etmek için gereken yineleme sayısının rastgele örnekleme kullanılarak belirleyici olmayan işaretlenmiş bir durumu bulmak için gereken beklenen sayıdan çok daha düşük olduğu anlamına gelir.

Her genden yükseltme yinelemesi iki yansıma işleci belirtilmesini gerektirir. Özellikle, $Q $, genliği yükseltme yinelecidir ve $P _0 $, başlangıç alt alanına bir projektör operatörü ve $P _1 $, işaretlenen alt alana yönelik projektör, $Q =-(\boldone-2P_0) (\cıvadone-2P_1) $.  Bir projektörün, egenvalues $ + $1 ve $0 $ olduğunu ve bir sonuç $ (\cıvadone-2P_0) $ olduğunu, Unity 'nin köklerinin kökleri olan (Bu durumda, $ \pm $1) bir hermitian işleci olduğunu unutmayın. Örnek olarak, Grover 'in ilk durumu ile arama durumunu göz önünde bulundurun $H ^ {\otimes n} \ket {0} $ ve işaretli durum $ \ket{m} $, $P _0 = H ^ {\otimes n} {0} \tus\bra {0} H ^ {\otimes n} $ ve $P _1 = \ket{m}\bra{m} $.  Çoğu genden yükseltme $P _0 $ uygulamalarında bir projektör, bazı vektör $ \ket{\psı} $; için $P _0 = \cıvadone-2 \ hayvan {\ PSI} \ köşeli {\ PSI} $ öğesinin bir başlangıç durumuna göre bir projektör olacaktır. Ancak, $P _0 $ olan zorunluluğun genliği, genellikle birçok hisse adına proje olur (yani, $ + $1 eigenvalue of $P _0 $ 'ın çoğulluğu $1 $ ' den büyüktür).

Genleştirme 'nın arkasındaki mantık, $Q $ ' ın Eigen ayrıştırma işleminden hemen sonra takip eder.  Özellikle, $Q $ ' ın eigenvektörler ilk durumun üzerinde sıfır olmayan desteği olduğunu, $P _0 $ ve $P _1 $ $ + $1 eigenvektörlerinin doğrusal bileşimleri olarak gösterilebiliyor.  Özellikle, genliği yükseltme için başlangıç durumu (bir $ + $1 eigenvector $P _0 $) $ $ \ket{\psı} = \frac{olarak yazılabilir-i}{\sqrt {2} } \left (e ^ {i\teta} \ ayraç {\ psi_ +} + e ^ {-i\teta} \ yer {\ psi_-} \ right), $ $ burada $ \ket{\ psi_ \pm} $, $Q $ öğesinin eigenvalues $e ^ {\pm 2i \ teta} $ olduğunu ve yalnızca $P _0 $ ve $P _1 $ ' nin $ + $1 eigenvektörlerine yönelik destek sahibi olduğunu.  Eigenvalues $e ^ {\pm i \theta} $, $Q $ işlecinin iki projektör tarafından belirtilen iki boyutlu bir alt alanda bir döndürme ve döndürme açısının $2 \ teta $ olduğu ilk durum üzerinde bir döndürme gerçekleştirmesini anlamına gelir.  Bu neden, $Q $ $m $ yinelemelerinin $ \sin ^ 2 ([2m + 1] \teta) $ ' dır.

Bundan sonra gelen diğer yararlı bir özellik ise, eigenvalue $ \teta $, ilk durumun işaretleneceği olasılığa ($P _0 $ ' ın yalnızca ilk duruma kadar bir projektör olduğu durumlarda) doğrudan ilgilidir.  $Q $ 'nin ıdgenphase $2 \ teta = 2 \ sin ^ {-1} (\Sqrt{\pr (success)}) $ olduğundan, $Q $ öğesine aşama tahmini uyguladığımızda, bir Unitary yordamı için başarılı olma olasılığını öğreniyoruz.  Bu, daha az bir şekilde ihtiyaç duyulduğundan daha fazla bilgi edinmek için hisse prosedürü için en fazla sayıda daha az uygulama gerektirdiğinden yararlıdır.

Q# zorunluluklığın en çok genliği bir özelleştirmesi olarak genliğini tanıtır.  Yükümlülüğü, ilk egenliği olan Projektörün başlangıç durumuna bir projektör olmaması gerektiğinden, bu bilinen adı ortadan kaldırmaz.  Bu anlamda protokol, ilk duruma kadar zorunluluvou olur.  Yükümlülüğü nesnelerin anahtar uygulaması, ilk durumun bilinmediği, ancak simülasyon protokolünde bir anliksel kayıt ile ayrılmış hale geldiği Unitary Hamiltonian benzetim yöntemlerinin belirli *Doğrusal birleşimleridir* .  Bu anyater kaydı sabit bir değer olacak şekilde ölçüldüğünde, $0 $ deyin, bu tür benzetim yöntemleri, kalan qubits 'e istenen Unitary dönüşümünü uygular (sistem kaydı adı verilir).  Diğer tüm ölçüm sonuçları hataya yol açabilir.  Yükümlülüğü, genlik düzeyini yükseltme, bu ölçümün başarısı, \\ Yukarıdaki düşünmelerin $100% $ ' üne artırılmasından izin verir.  Ayrıca, normal genileri, sistem kaydının boş olduğu durumuna karşılık gelir.  Bunun nedeni, Q# temel genliği yükseltme alt yordamı olarak yükümlülüğü en çok genliğini kullanır.

Genel yordamın ( `AmpAmpObliviousByReflectionPhases` ), ve çağırdığımız iki kaydı vardır `ancillaRegister` `systemRegister` . Ayrıca, gerekli yansıtımları için iki Oracles kabul eder. `ReflectionOracle`Yalnızca üzerinde çalışır, ancak `ancillaRegister` `ObliviousOracle` her iki kasada de çalışır. Giriş, `ancillaRegister` ilk yansıma işlecinin $ \ cıvas-2P_1 $ ' i-1 eigenstate olarak başlatılmalıdır.

Genellikle, Oracle durumu hesaplama tabanlı $ \ket{0...0} $ olarak hazırlar. Uygulamamız içinde, `ancillaRegister` consistes of bir qubit ( `flagQubit` ), ve diğer bir deyişle, `stateOracle` istenen anyazu 'nin geri kalanını denetler. , `stateOracle` `flagQubit` $ \Ket $ olduğunda uygulanır {1} .

Ayrıca, bir `StateOracle` `ObliviousOracle` çağrısı aracılığıyla Oracles ve yansıtımları yerine `AmpAmpObliviousByOraclePhases`

Belirtildiği gibi, geleneksel Genüme, `ObliviousOracle` kimlik operatörü olduğu ve hiçbir sistem qubit (, boş) olmayan bu yordamların yalnızca özel bir durumdur `systemRegister` . Kısmi yansıtımları için aşamalar almak istiyorsanız (örneğin, Grover araması için), işlev `AmpAmpPhasesStandard` kullanılabilir. Lütfen `DatabaseSearch.qs` Grover 'in algoritmasının örnek bir uygulamasına başvurun.

Tek qubit döndürme aşamalarını, kağıt [G.H. Low, ı. L. Chuang](https://arxiv.org/abs/1707.05391)tarafından belirtilen şekilde, yansıma işleci aşamalarına ilişkilendirdik. Kullanılan sabit nokta aşamaları, düşük [, Yoder ve Chuang](https://arxiv.org/abs/1603.03996)aşamalarıyla birlikte [Yoder, Low ve Chuang](https://arxiv.org/abs/1409.3305) içinde ayrıntılıdır.

Arka plan için [Standart genliği](https://arxiv.org/abs/quant-ph/0005055) yükseltme ' den başlayıp, [düşük ve Chuang](https://arxiv.org/abs/1610.06546)' de [sunulan ve en](https://arxiv.org/abs/1312.1414) son genelleştirmeler için bir giriş konusuna geçebilirsiniz. Bu alanın tamamını (Hamiltonian simülasyonu ile ilişkili olduğu gibi), [Dominic Braz](http://www.dominicberry.org/presentations/Durban.pdf)tarafından verilen bir genel bakış sunumu.

## <a name="quantum-fourier-transform"></a>Hisse Fourier dönüşümü ##

Fourier Transform, klasik çözümlemenin temel bir aracıdır ve yalnızca hisse hesaplamalarında önemli bir araçtır.
Buna ek olarak, *hisse* uygun bir şekilde bir hisse algoritması tasarımı yaparken, her ne kadar, bir klasik makinede ne kadar verimli hale gelir.

QFT 'nin yaklaşık bir genelleştirme olarak, <xref:Microsoft.Quantum.Canon.ApproximateQFT> istenen algoritmik doğruluğu için kesinlikle gerekli olmayan döndürmeler ayıklanarak daha fazla iyileştirmeler sağlayan bir işlem sağlıyoruz.
Yaklaşık QFT, dyadic $Z $-Rotation işleminin <xref:Microsoft.Quantum.Intrinsic.RFrac> yanı sıra <xref:Microsoft.Quantum.Intrinsic.H> işlemi gerektirir.
Giriş ve çıkışın big endian kodlamada kodlandığını kabul edilir---Yani, index ile qubit, `0` ikili tamsayı gösteriminin en solundaki (en yüksek) bit olarak kodlanır.
Bu, [ayraç](xref:microsoft.quantum.concepts.dirac)ile hizalanır; $ \ket $ durumunda bulunan üç qubit kayıt olarak $ {100} \ket $, {1} $q _1 $ ve $q _2 $ her ikisi de $ \gre$ durumunda olan $q _0 $ {0} .
$A $ yaklaşık parametresi, $Z $-döndürmeler, yani $a \içindeki [0.. n] $) ayıklama düzeyini belirler.
Bu durumda, tüm $Z $-Ros $2 \ pi/2 ^ k $, $k > bir $, QFT devresi öğesinden kaldırılır.
$K \ge \ log_2 (n) + \ log_2 (1/\epsilon) + $3 için şu şekilde bilinmektedir. biri $ \\ | \operatorname{QFT}-\operatorname{AQFT} \\ | < \epsilon $ ile bağlanabilir.
Burada $ \\ | \cdot \\ | $, bu örnekte $ (\Operatorname{QFT}-\operatorname{AQFT}) (\Operatorname{QFT}-\operatorname{AQFT}) ^ \hanger $ en büyük [eigenvalue değerinin](xref:microsoft.quantum.concepts.matrix-advanced) karekökünü içeren bir işleçtir.

## <a name="arithmetic"></a>Aritmetik ##

Aritmetik olarak klasik bilgi işlem 'da merkezi bir rol oynadığında, bu da hisse olmazdır.  Shor 'ın düzenleme algoritması, hisse simülasyonu yöntemleri ve birçok Oracular algoritması gibi algoritmalar, tutarlı aritmetik işlemlere dayanır.  En çok bir aritmetik derleme, hisse açık bir devreden sonra.  En basit ekleyici, klasik bir giriş $b $ alır ve değeri $ \ket{a} $ tamsayı tutan bir hisse ma durumuna ekler.  Matematiksel olarak, bir Ekleyici (klasik giriş $b $ için $ \operatorname{Add} (b) $) değerini belirten bir özelliği vardır

$ $ \operatorname{Add} (b) \ket{a} = \ket{a + b}.
$ $ Bu temel Ekleyici devresi bir Ekleyici öğesinden daha fazla incrementer.
$ $ \Operatorname{Add}\ket{a}\ket{b} = \ket{a}\ket{a + b} aracılığıyla iki hisse girişi olan bir Ekleyici 'a dönüştürülebilir, $ $n $ \begin{hizalaması} \operatorname{Add} \ket{a} \ket{b} & = \lambda \_ {a \_ 0} \left (\operatorname{Add} (1) \right) \lambda \_ {a \_ 1} \left (\operatorname{Add} (2) \right) \lambda \_ {a \_ 2} \left (\operatorname{Add} (4) \ right) \cnoktalar \lambda \_ {a \_ {n-1}} \left (\operatorname{Add} ({{n-1}}) \right) \ket{a}\ket{b} \\ \\ & = \ket{a} \ket{b + a}, $n $ bit tamsayılar için \end{hizalaması} $a $ ve $b $ ve ek modül $2 ^ n $.  $ \Lambda \_ x (A) $ gösteriminin, her türlü işlem için $A $ olduğunu, qubit $x $ as denetimiyle bu işlemin denetimli sürümüne olduğunu hatırlayın.

Benzer şekilde, parçalı olarak denetlenen çarpma (Shor 'ın düzenleme algoritması için temel olan modüler bir biçim), benzer bir denetimli ekleme dizisi kullanılarak gerçekleştirilebilir: \begin{hizalaması} \operatorname{Mult} (a) \ket{x}\ket{b} & = \Lambda \_ {x \_ 0} \Left (\operatorname{Add} (2 ^ 0 a) \ right) \lambda \_ {a \_ 1} \left (\operatorname{Add} (2 ^ 1a) \Sağ) \lambda \_ {a \_ 2} \left (\operatorname{Add} (2 ^ 2 a) \ right) \cnoktalar \lambda \_ {x \_ {n-1}} \left (\operatorname{Add} ({2 ^ {n-1}} a) \ right) \ket{x}\ket{b} \\ \\ & = \ket{x}\ket{b + AX}.
\end{hizalaması} yukarıdaki $ \operatorname{Mult} $ tanımından fark edebilmeniz gereken, hisse alınan çarpma ile bir alt ttize vardır.  Buna ek olarak, bu devrenin hisse sürümü, giriş kaydı yerine bir anakusli kayıt halinde girişlerin çarpımını depolar.  Bu örnekte, YAZMAÇ $b $ değeriyle başlatılır, ancak genellikle sıfır değerini tutmaya başlayacaktır.  Bu, genel $a $ ve $x $ için bir çarpma tersi olmadığından ' de gereklidir.  Tüm hisse işlemleri, ölçümü Kaydet, geri alınamaz ve çarpmadan ters çevirmek için yeterli bilgi tutmanız gerekir.  Bu nedenle, sonuç ayrı bir dizide depolanır.  Ayrı bir kayıttaki çarpma gibi geri alınamaz bir işlemin çıkışını kaydetmenin bu eli, Charlie Bennett sonrasında "Bennett eli" olarak bilinir ve hem ters çevrilebilir hem de hisse bilgi işlem ortamında temel bir araçtır.

Çok sayıda hisse kullanım için önerilir ve her biri, qubit sayısı (Space) ve gereken kapı işlemleri sayısı (süre) açısından farklı bir zorunluluğunu getirir araştırır.  Aşağıda, Draper Ekleyici ve Beauregard Ekleyici olarak bilinen iki son derece etkin ad inceliyoruz.

### <a name="draper-adder"></a>Draper Adder ###

Draper Ekleyici en zarif bir şekilde, ek hale getirmek üzere hisse özelliklerini doğrudan çağırdığı için en zarif hisse alıclardan biridir.  Draper 'ın arkasındaki Öngörüler, Fourier dönüştürmesinin, aşama vardiyalarının bir bit vardiyaya çevrilmesi için kullanılabileceğini sağlar.  Daha sonra bir Fourier dönüşümü uygulayarak, uygun aşama vardiyaları uygulayarak ve sonra bir Adder uygulayabileceğiniz Fourier dönüşümünü geri aldıktan sonra bunu izler.  Önerilmiş pek çok diğer adtan farklı olarak, Draper ekleyici, hisse bir biçimde sunulan hisse  Doğal bir klasik karşılığı yok.  Draper Ekleyici 'ın belirli adımları aşağıda verilmiştir.

İki $n $-bit qubit, $a $ ve $b $ değerlerinin tümünü $a $ $ $ $ $ $ $ $ $ \operatorname{QFT}\ket{a} = \frac {1} {\sqrt{2 ^ n}} \sum \_ {j = 0} ^ {2 ^ n-1} e ^ {i2\pi (AJ)/2 ^ n} \ket{j} için, bu tamsayıları depolayan bir
$ $ $ $ \Ket{\phi \_ k (a)} = \frac {1} {\sqrt {2} } \left (\ket {0} + e ^ {i2\pi a/2 ^ k} \ket {1} \ right) tanımladığımızda, $ $ daha sonra bazı algeköşeli sonrasında $ $ \operatorname{QFT}\ket{a} = \ket{\phi \_ 1 (a)} \otimes \cnoktalar \otimes \ket{\phi \_ n (a)} olduğunu görebilirsiniz.
$ $ Bu durumda, bir Ekleyici işlemi gerçekleştirmeye yönelik yol, girişlerin toplamının $ $ \ket{a + b} = \operatorname{QFT} ^ {-1} \ket{\phi \_ 1 (a + b)} \otimes \cnoktalar \otimes \ket{\phi \_ n (a + b)} olarak yazılabileceğini gözlemledikten sonra net bir hale gelir.
$ $ $B $ ve $a $ tamsayısı, $b $ $ as denetimleri kullanılarak ayrıştırma içindeki her bir qubit üzerinde denetlenen aşama dönüşü gerçekleştirerek eklenebilir.

Bu genişleme, her tamsayı $j $ ve gerçek sayı $x $, $e ^ {i2\pi (x + j)} = e ^ {i2\pi x} $ olduğunu belirterek daha kolay bir şekilde basitleştirilebilir.  Bunun nedeni, $360 ^ {\circ} $ derece ($ 2 \ Pi $ radyan) bir daire içinde döndürmenize neden olur.  $E ^ {i2\pi x} $ için $x $ öğesinin yalnızca önemli bir parçası bu nedenle $x $ bölümünün kesirli kısmıdır.  Özellikle, formun ikili Genişlememiz varsa $x = y +0. x \_ 0x \_ 2 \ lnoktalar x \_ n $ then $e ^ {i2\pi x} = e ^ {i2\pi (0). x \_ 0x \_ 2 \ lnoktalar x \_ {n-1})} $ ve bu nedenle $ $ \ket{\phi \_ k (a + b)} = \frac {1} {\sqrt {2} } \left (\ket {0} + e ^ {i2\pi [a/2 ^ k +0. b \_ k\ldots b \_ 1]} \ ayraç {1} \ sağ). $ $ Bu, $ \ket{a} $ öğesinin Fourier dönüştürmesinin her birini arttırarak ekleme gerçekleştirdiğimiz anlamına gelir. Bu durumda, döndürmeler sayısının $k $ düşüş olduğunu küçültür.  Bu, Adder 'de gerekli olan hisse kapıları sayısını önemli ölçüde azaltır.  Fourier dönüşümü, aşama ekleme ve ters Fourier Dönüştürme adımlarını $ \operatorname{QFT} ^ {-1} \left (\fi \\ \! \operatorname{Add}\right) \operatorname{QFT} $ olarak gösteren bir. İşlemin tamamını uygulamak için bu basitleştirme kullanan bir hisse devresini aşağıda görebilirsiniz.

![Devper, devre diyagramı olarak gösterilen Ekleyici](~/media/draper.svg)

Bağlantı hattı 'ndaki her denetlenen $e ^ {I2 \ PI/k} $ kapısı, denetlenen aşama kapısı anlamına gelir.  Bu tür kapıları, $ {00} \gre\mapsto \tus$, $ {00} {11} \gre\mapsto e ^ {I2 \ Pi/k} \ {11} GRE$ ' a sahip oldukları qubit çiftinde özelliğine sahiptir.  Bu bağlantı hattı, giriş ve çıkışları depolamak için gerekenden başka bir qubit olmadan toplama işlemi gerçekleştirmemizi sağlar.

### <a name="beauregard-adder"></a>Beauregard Adder ###

Beauregard ekleyici, rastgele bir pozitif tamsayı $N $ için ek modül $N $ gerçekleştirmek üzere Draper Ekleyici ' i kullanan bir hisse modüler bir Ekleyici.  Beauregard Adder gibi hisse modüler kişilerin önemi, Adder gibi, kor 'ın düzenleme için algoritması içindeki modüler üs adım 'daki kullanımlarını büyük bir ölçüde kullanıyor.  Hisse modüler bir ekleyici, hisse girişi $ \ket{b} $ ve klasik giriş $a $ $a $ ve $b $ tamsayı mod $N $ olarak kabul edildiği ve $ [0, \lnoktalar, N-1] $ aralığında oldukları anlamına gelir.

$ $ \ket{b}\rightarrow \ket{b + a \Text{mod} N} = \begin{Cases} \ket{b + a}, & b + a < N \\ \\ \ket{b + a-N}, & (b + a) \Ge N \end{Cases}.
$$

Beauregard ekleyici, \\ \! $a $ ve $b $ aşamasına eklemek için Draper Ekleyici veya daha özel olarak $ \phi \operatorname{Add} $ kullanır.  Daha sonra, $a + b-N<$0 ' ı çıkararak $a + b <N $ $N $ ve test etmeyi kaldırarak aynı işlemi kullanır.  Devre, bu bilgileri bir anılususılge içinde depolar ve sonra $a + b<N $ $N $ kaydı ekler.  Daha sonra bu işlem, bu ek bitin bitmemesini sağlar (Bu adım, Adder çağrıldıktan sonra, anıllanla 'nın de ayrılabileceği emin olmak için gereklidir).  Beauregard Ekleyici için devre aşağıda verilmiştir.

![Devre diyagramı olarak gösterilen Beauregard Ekleyici](~/media/beau.svg)

Burada, $ \Fi \\ \! \operatorname{Add} $ kapısı $ \Phi \operatorname{Add} $ ile aynı şekilde sürer \\ \! . Bu bağlamda, girişin hisse yerine klasik olması hariç olur.  Bu, $ \Phi \Operatorname{Add} $ içindeki denetlenen aşamaların, \\ \! hem qubit sayısını hem de Adder için gereken kapı sayısını azaltmak üzere daha az işlem ile birlikte derlenebilecek aşama kapıları ile değiştirilmesini sağlar.

Daha fazla ayrıntı için lütfen [M. Roetteler, TH. Beth](http://doi.org/10.1007/s00200-008-0072-2 ) ve [D. Coppersmith](https://arxiv.org/abs/quant-ph/0201067)'e bakın.

### <a name="quantum-phase-estimation"></a>Kuantum Aşama Tahmini ###

Hisse daha önemli bir uygulama olan unitfourier dönüştürmesinin, *aşama tahmini* olarak bilinen bir sorun olan Unitary işleçlerinin eigendeğerlerini öğrenmesinin nedeni.
Bir Unitary $U $ ve $ \ket{\phi} $ gibi bir State $ \ket{\phi} $, bilinmeyen eigenvalue $ \phi $, \begin{Equation} U\tus{\ Fi} = \phi\ket{\phi} ile $U $ öğesinin bir eigenstate olduğunu düşünün.
\end{Equation} yalnızca bir Oracle olarak $U $ erişimi varsa, denetimli bir işlemin hedefine uygulanan $Z $ roetlerini denetimin üzerine geri yayarak $ \phi $ aşamasını öğreniyoruz.

$V $ öğesinin denetlenen bir $U $ uygulaması olduğunu varsayalım. bu şekilde \begin{hizalaması} V (\ket \otimes {0} \ket{\phi}) & = {0} \tus\otimes \ket{\phi} \\ \\ \textrm{ve} V (\ket {1} \otimes \ket{\phi}) & = e ^ {ı \ Phi} \ket {1} \otimes \ket{\phi}.
\end{hizalaması} sonra, şu şekilde, \begin{hizalaması} V (\ket{+} \otimes \ket{\phi}) & = \frac{( {0} \tus\otimes \ket{\phi}) + e ^ {ı \phi} (\demet {1} \otimes \ket{\phi})} {\sqrt {2} }.
\end{hizalaması} Bu \ Begin{hizalaması} V (\ket{+} \otimes \ket{\phi}) öğesini bulmak için şartlar toplayabiliriz & = \frac{\tus+ {0} e ^ {ı \phi} {1} \tus} {\sqrt {2} } \otimes \ket{\phi} \\ \\ & = (R_1 (\fi) \ket{+}) \otimes \ket{\phi}, \end{hizalaması}; burada $R _1 $, işlem tarafından uygulanan Unitary <xref:Microsoft.Quantum.Intrinsic.R1> .
Farklı şekilde, $V $ uygulamanın etkisi, yalnızca bir Oracle olarak $V $ erişimine sahip olduğumuz halde, bilinmeyen bir açıyla $R _1 $ ' ı uygulama ile tam olarak aynıdır.
Bu nedenle, bu tartışmanın geri kalanı için aşama tahmini $R _1 (\phi) *$ olarak tartışıyoruz.*

Denetim ve hedef kayıt bu işlemden sonra geri ılanmadan kaldığından, "_1 (2 \fi) \ket{+} $ $R durumunda ikinci bir denetim qubit hazırlamak için $U ^ $2 kontrollü bir uygulamasının hedefi olarak $ \ket{\phi} $ öğesini yeniden kullanabilirsiniz.
Bu şekilde devam ederek, \begin{hizalaması} \ket{\psı} & = \ sum_ {j = 0} ^ n R_1 (2 ^ j \ Fi) \ket{+} \\ \\ & \propto \ bigotimes_ {j = 0} ^ {n} \left (\ket + biçiminde) bir kayıt edinebilirsiniz. \exp {0} (i 2 ^ {j} \fi) \ket \ {1} right) & \\ \\ \propto \ sum_ {k = 0} ^ {2 ^ n-1} \exp (i \phi k $n ve {} {} $1/\sqrt{2 ^ n} $ normalleştirme faktörünü gizliyoruz.

$ \Phi = 2 \ Pi p/2 ^ k $ ' ı bir tamsayı $p $ olarak kabul ediyorsanız, bunu $ \ket{\psı} = \operatorname{QFT} \ket{p_0 p_1 \noktalar p_n} $ olarak tanıyacağız; burada $p _j $, $j ^ {\textrm{TH}} $ bit/$2 \pi \phi $ şeklindedir.
Bu nedenle, hisse dosyası miktarı olarak kodlanan aşamanın ikili gösterimini elde ettiğimiz için, bu nedenle hisse.

' De Q# , bu işlem tarafından uygulanır <xref:Microsoft.Quantum.Characterization.QuantumPhaseEstimation> , bu, <xref:Microsoft.Quantum.Oracles.DiscreteOracle> $m $ pozitif tamsayılar işlevi olarak $U ^ d $ uygulayan bir uygulama alır.
