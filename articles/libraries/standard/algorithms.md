---
title: 'Q # standart kitaplıkları-algoritmalar | Microsoft Docs'
description: Q# standart kitaplıkları
author: QuantumWriter
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.libraries.standard.algorithms
ms.openlocfilehash: 91f65b05c83367c2d2ece93212369dc448d8c2a8
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76821023"
---
# <a name="quantum-algorithms"></a>Hisse algoritmaları #

## <a name="amplitude-amplification"></a>Genliğini Yükseltme ##

*Genliği yükseltme* , hisse bilgi işlem aracının temel araçlarından biridir. Bu, Grover 'in arama, genlik tahmini ve birçok hisse makine öğrenimi algoritmalarının temelini oluşturan temel bir fikirdir.  Birçok çeşit vardır ve soru-cevap bölümünde, uygulamanın en geniş bölümünde izin verilen kısmi yansımalar ile yükümlülüğü düzeyini temel alan genel bir sürüm sağlıyoruz.

Genizme 'nin arkasındaki orta düşünce, bir dizi yansıma gerçekleştirerek istenen sonucun oluşma olasılığını artırmakta.  Bu yansıtılamalar, ilk durumu, genellikle işaretli bir durum olarak adlandırılan istenen hedef durumuna yaklaştırır.  Özellikle, ilk durumu işaretli bir durumda olacak şekilde ölçmeye olasılığı $ \sin ^ 2 (\teta) $ ise, gen$m liği yükseltme işleminden sonra, başarı olasılığı $ \sin ^ 2 ((2m + 1) \teta) $ olur.  Bu, bazı $n $ \teta = \ Pi/[2 (2n + 1)] $ ' in değeri için $ \ teta = \ Pi/[2 (2n + 1)] $ olduğunda, genliği yükseltme $n, genliği yükseltme $100 ' den sonra% $\\% $  $ \Teta = \sin ^{-1}(\sqrt{\Pr (success)}) $ bu yana, başarılı bir şekilde elde etmek için gereken yineleme sayısının rastgele örnekleme kullanılarak belirleyici olmayan bir şekilde bulunması gereken beklenen sayıdan çok daha düşük olması anlamına gelir.

Her genden yükseltme yinelemesi iki yansıma işleci belirtilmesini gerektirir. Özellikle, $Q $, genliği yükseltme yinelecidir ve $P _0 $, başlangıç alt alanına bir projektör operatörü ve $P _1 $, işaretlenen alt alana yönelik projektör, $Q =-(\boldone-2P_0) (\cıvadone-2P_1) $.  Bir projektörün, egenvalues $ + $1 ve $0 $ olduğunu ve bir sonuç $ (\cıvadone-2P_0) $ olduğunu, Unity 'nin köklerinin kökleri olan (Bu durumda, $ \pm $1) bir hermitian işleci olduğunu unutmayın. Örnek olarak, Grover 'in ilk durumuyla arama durumunu göz önünde bulundurun $H ^ {\otimes n} \tus{0}$ ve işaretli durum $ \ket{m} $, $P _0 = H ^ {\otimes n} \tus{0}\bra{0}H ^ {\otimes n} $ ve $P _1 = \ket{m}\bra{m} $.  Çoğu genden yükseltme $P _0 $ uygulamalarında bir projektör, bazı vektör $ \ket{\psı} $; için $P _0 = \cıvadone-2 \ hayvan {\ PSI} \ köşeli {\ PSI} $ öğesinin bir başlangıç durumuna göre bir projektör olacaktır. Ancak, $P _0 $ olan zorunluluğun genliği, genellikle birçok hisse adına proje olur (yani, $ + $1 eigenvalue of $P _0 $ 'ın çoğulluğu $1 $ ' den büyüktür).

Genleştirme 'nın arkasındaki mantık, $Q $ ' ın Eigen ayrıştırma işleminden hemen sonra takip eder.  Özellikle, $Q $ ' ın eigenvektörler ilk durumun üzerinde sıfır olmayan desteği olduğunu, $P _0 $ ve $P _1 $ $ + $1 eigenvektörlerinin doğrusal bileşimleri olarak gösterilebiliyor.  Özellikle, genliği yükseltme için başlangıç durumu (bir $ + $1 eigenvector $P _0 $), $ $ \ket{\psı} = \frac{-olarak yazılabilir ı}{\sqrt{2}} \left (e ^ {i\teta} \ ayraç {\ psi_ +} + e ^ {-i\teta} \ ayraç {\ psi_-} \ right), $ $ burada $ \ket{\ psi_ \pm} $, $Q $ öğesinin eigenvalues $e ^ {\pm 2i \ teta} $ olduğunu ve yalnızca $P _0 $ ve $P _1 $ ' nin $ + $1 eigenvektörlerine yönelik destek sahibi olduğunu.  Eigenvalues $e ^ {\pm i \theta} $, $Q $ işlecinin iki projektör tarafından belirtilen iki boyutlu bir alt alanda bir döndürme ve döndürme açısının $2 \ teta $ olduğu ilk durum üzerinde bir döndürme gerçekleştirmesini anlamına gelir.  Bu neden, $Q $ $m $ yinelemelerinin $ \sin ^ 2 ([2m + 1] \teta) $ ' dır.

Bundan sonra gelen diğer yararlı bir özellik ise, eigenvalue $ \teta $, ilk durumun işaretleneceği olasılığa ($P _0 $ ' ın yalnızca ilk duruma kadar bir projektör olduğu durumlarda) doğrudan ilgilidir.  $Q $ ' nin eigenaşamaları $2 \ teta = 2 \ sin ^{-1}(\sqrt{\Pr (success)}) $ olduğundan, $Q $ öğesine aşama tahmini uyguladığımızda, bir Unitary yordamı için başarılı olma olasılığını öğreniyoruz.  Bu, daha az bir şekilde ihtiyaç duyulduğundan daha fazla bilgi edinmek için hisse prosedürü için en fazla sayıda daha az uygulama gerektirdiğinden yararlıdır.

S #, yükümlülüğü düzeyini en uygun özelleşmenin bir özelleştirmesi olarak sunar.  Yükümlülüğü, ilk egenliği olan Projektörün başlangıç durumuna bir projektör olmaması gerektiğinden, bu bilinen adı ortadan kaldırmaz.  Bu anlamda protokol, ilk duruma kadar zorunluluvou olur.  Yükümlülüğü nesnelerin anahtar uygulaması, ilk durumun bilinmediği, ancak simülasyon protokolünde bir anliksel kayıt ile ayrılmış hale geldiği Unitary Hamiltonian benzetim yöntemlerinin belirli *Doğrusal birleşimleridir* .  Bu anyater kaydı sabit bir değer olacak şekilde ölçüldüğünde, $0 $ deyin, bu tür benzetim yöntemleri, kalan qubits 'e istenen Unitary dönüşümünü uygular (sistem kaydı adı verilir).  Diğer tüm ölçüm sonuçları hataya yol açabilir.  Yükümlülüğü en çok genliği, bu ölçümün başarısı $100\\% $, yukarıdaki düşünmelerin kullanılması olasılığını artırır.  Ayrıca, normal genileri, sistem kaydının boş olduğu durumuna karşılık gelir.  Bu nedenle, soru-cevap, temel genliği yükseltme alt yordamı olarak yükümlülüğü en çok genliğini kullanır.

Genel yordamın (`AmpAmpObliviousByReflectionPhases`) `ancillaRegister` ve `systemRegister`çağırdığımız iki kaydı vardır. Ayrıca, gerekli yansıtımları için iki Oracles kabul eder. `ReflectionOracle`, `ObliviousOracle` her iki kasada de ortaklaşa hareket ederken `ancillaRegister` üzerinde çalışır. `ancillaRegister` giriş, $ \ cıvadone-2P_1 $ ilk yansıma işlecinin-1 eigenstate 'e başlatılmalıdır.

Genellikle, Oracle durumu hesaplama tabanlı $ \ket{0...0} $ olarak hazırlar. Uygulamamızda bir qubit (`flagQubit`) `ancillaRegister` consistes, bu da `stateOracle` ve istenen anyamarın geri kalanını denetler. `stateOracle`, `flagQubit` $ \ket{1}$ olduğunda uygulanır.

Ayrıca, bir `AmpAmpObliviousByOraclePhases`çağrısı aracılığıyla yansıma yerine Oracles `StateOracle` ve `ObliviousOracle` da sağlayabilir.

Belirtildiği gibi, geleneksel Genleştirmeler, `ObliviousOracle` kimlik operatörü olduğu ve sistem qubit (yani, `systemRegister` boş) olmadığı bu yordamların yalnızca özel bir durumdur. Kısmi yansıtımları için aşamalar almak istiyorsanız (örneğin, Grover araması için) `AmpAmpPhasesStandard` işlevi kullanılabilir. Lütfen Grover 'in algoritmasının örnek bir uygulamasına yönelik `DatabaseSearch.qs` başvurun.

Tek qubit döndürme aşamalarını, kağıt [G.H. Low, ı. L. Chuang](https://arxiv.org/abs/1707.05391)tarafından belirtilen şekilde, yansıma işleci aşamalarına ilişkilendirdik. Kullanılan sabit nokta aşamaları, düşük [, Yoder ve Chuang](https://arxiv.org/abs/1603.03996)aşamalarıyla birlikte [Yoder, Low ve Chuang](https://arxiv.org/abs/1409.3305) içinde ayrıntılıdır.

Arka plan için [Standart genliği](https://arxiv.org/abs/quant-ph/0005055) yükseltme ' den başlayıp, [düşük ve Chuang](https://arxiv.org/abs/1610.06546)' de [sunulan ve en](https://arxiv.org/abs/1312.1414) son genelleştirmeler için bir giriş konusuna geçebilirsiniz. Bu alanın tamamını (Hamiltonian simülasyonu ile ilişkili olduğu gibi), [Dominic Braz](http://www.dominicberry.org/presentations/Durban.pdf)tarafından verilen bir genel bakış sunumu.

## <a name="quantum-fourier-transform"></a>Hisse Fourier dönüşümü ##

Fourier Transform, klasik çözümlemenin temel bir aracıdır ve yalnızca hisse hesaplamalarında önemli bir araçtır.
Buna ek olarak, *hisse* uygun bir şekilde bir hisse algoritması tasarımı yaparken, her ne kadar, bir klasik makinede ne kadar verimli hale gelir.

QFT 'nin yaklaşık bir genelleştiri olarak, istenen algoritmik doğruluğu için kesinlikle gerekli olmayan döndürmeler ayıklanarak daha iyi iyileştirmeler sağlayan <xref:microsoft.quantum.canon.approximateqft> işlem sağlıyoruz.
Yaklaşık QFT, dyadic $Z $-döndürme <xref:microsoft.quantum.intrinsic.rfrac> işleminin yanı sıra <xref:microsoft.quantum.intrinsic.h> işlemini de gerektirir.
Giriş ve çıkışın big endian kodlamada kodlandığını varsayılır (en düşük bit/qubit, sol tarafta, [demet gösterimi](xref:microsoft.quantum.concepts.dirac)ile aynıdır).
$A $ yaklaşık parametresi, $Z $-döndürmeler, yani $a \içindeki [0.. n] $) ayıklama düzeyini belirler.
Bu durumda, tüm $Z $-Ros $2 \ pi/2 ^ k $, $k > bir $, QFT devresi öğesinden kaldırılır.
$K \ge \ log_2 (n) + \ log_2 (1/\epsilon) + $3 için şu şekilde bilinmektedir. biri $\\bağlanabilir | \operatorname{QFT}-\operatorname{AQFT} \\| < \epsilon $.
Burada $\\| \cdot\\| $, bu örnekte $ (\operatorname{QFT}-\operatorname{AQFT}) (\operatorname{QFT}-\operatorname{AQFT}) ^ \hanger $ en büyük [eigenvalue değerinin](xref:microsoft.quantum.concepts.matrix-advanced) karekökünü temel aldığı işleçtir.

## <a name="arithmetic"></a>Aritmetik ##

Aritmetik olarak klasik bilgi işlem 'da merkezi bir rol oynadığında, bu da hisse indispensible.  Shor 'ın düzenleme algoritması, hisse simülasyonu yöntemleri ve birçok Oracular algoritması gibi algoritmalar, tutarlı aritmetik işlemlere dayanır.  En çok bir aritmetik derleme, hisse açık bir devreden sonra.  En basit ekleyici, klasik bir giriş $b $ alır ve değeri $ \ket{a} $ tamsayı tutan bir hisse ma durumuna ekler.  Matematiksel olarak, bir Ekleyici (klasik giriş $b $ için $ \operatorname{Add} (b) $) değerini belirten bir özelliği vardır

$ $ \operatorname{Add} (b) \ket{a} = \ket{a + b}.
$ $ Bu temel Ekleyici devresi bir Ekleyici öğesinden daha fazla incrementer.
$ $ \Operatorname{Add}\ket{a}\ket{b} = \ket{a}\ket{a + b} aracılığıyla iki hisse girişi olan bir Ekleyici 'a dönüştürülebilir. $ $ \begin{hizalaması} \operatorname{Add} \ket{a} \ket{b} & = $n \lambda\_{a\_0} \left (\operatorname{Add} (1) \ right) \lambda\_{a\_1} \left (\operatorname{Add} (2) \right) \lambda\_{a\_2} \left (\operatorname{Add} (4) \right) \cnoktalar \lambda\_{a\_{n-1}} \left (\ operatorname {Add} ({{n-1}}) \right) \ket{a}\ket{b} \\\\ & = \ket{a} \ket{b + a}, \end{hizalaması} $n $-bit tamsayılar $a $ ve $b $ ve ek modül $2 ^ n $.  $ \Lambda\_x (A) $ öğesinin her türlü işlemi için $A $, qubit $x $ as denetimi ile bu işlemin denetlenen sürümüne olduğunu hatırlayın.

Benzer şekilde, parçalı olarak denetlenen çarpma (Shor 'ın düzenleme algoritması için temel olan modüler bir biçim), benzer bir denetimli ekleme dizisi kullanılarak gerçekleştirilebilir: \begin{hizalaması} \operatorname{Mult} (a) \ket{x}\ket{b} & = \Lambda\_{x\_0} \left (\operatorname{Add} (2 ^ 0 a) \ right) \ lambda\_{a\_1} \left (\operatorname{Add} (2 ^ 1a) \right) \Lambda\_{a\_2} \left (\operatorname{Add} (2 ^ 2 a) \ right) \cnoktalar \Lambda\_{x\_{ n-1}} \left (\operatorname{Add} ({2 ^ {n-1}} a) \ right) \ket{x}\ket{b} \\\\ & = \ket{x}\ket{b + AX}.
\end{hizalaması} yukarıdaki $ \operatorname{Mult} $ tanımından fark edebilmeniz gereken, hisse alınan çarpma ile bir alt ttize vardır.  Buna ek olarak, bu devrenin hisse sürümü, giriş kaydı yerine bir anakusli kayıt halinde girişlerin çarpımını depolar.  Bu örnekte, YAZMAÇ $b $ değeriyle başlatılır, ancak genellikle sıfır değerini tutmaya başlayacaktır.  Bu, genel $a $ ve $x $ için bir çarpma tersi olmadığından ' de gereklidir.  Tüm hisse işlemleri, ölçümü Kaydet, geri alınamaz ve çarpmadan ters çevirmek için yeterli bilgi tutmanız gerekir.  Bu nedenle, sonuç ayrı bir dizide depolanır.  Ayrı bir kayıttaki çarpma gibi geri alınamaz bir işlemin çıkışını kaydetmenin bu eli, Charlie Bennett sonrasında "Bennett eli" olarak bilinir ve hem ters çevrilebilir hem de hisse bilgi işlem ortamında temel bir araçtır.

Çok sayıda hisse kullanım için önerilir ve her biri, qubit sayısı (Space) ve gereken kapı işlemleri sayısı (süre) açısından farklı bir zorunluluğunu getirir araştırır.  Aşağıda, Draper Ekleyici ve Beauregard Ekleyici olarak bilinen iki son derece etkin ad inceliyoruz.

### <a name="draper-adder"></a>Draper Adder ###

Draper Ekleyici en zarif bir şekilde, ek hale getirmek üzere hisse özelliklerini doğrudan çağırdığı için en zarif hisse alıclardan biridir.  Draper 'ın arkasındaki Öngörüler, Fourier dönüştürmesinin, aşama vardiyalarının bir bit vardiyaya çevrilmesi için kullanılabileceğini sağlar.  Daha sonra bir Fourier dönüşümü uygulayarak, uygun aşama vardiyaları uygulayarak ve sonra bir Adder uygulayabileceğiniz Fourier dönüşümünü geri aldıktan sonra bunu izler.  Önerilmiş pek çok diğer adtan farklı olarak, Draper ekleyici, hisse bir biçimde sunulan hisse  Doğal bir klasik karşılığı yok.  Draper Ekleyici 'ın belirli adımları aşağıda verilmiştir.

İki $n $-bit qubit, $a $ ve $b $ değerlerinin tümünü $a $ $ $ $ $ $ $ $ $ \operatorname{QFT}\ket{a} = \frac{1}{\sqrt{2 ^ n}} \sum\_{j = 0} ^ {2 ^ n-1} e ^ {i2\pi (AIJ)
$ $ $ $ \Ket{\phi\_k (a)} = \frac{1}{\sqrt{2}} \left (\ket{0} + e ^ {i2\pi a/2 ^ k} \tus{1} \ right) tanımladığımızda, $ $ daha sonra bazı algeköşeli sonrasında $ $ \operatorname{QFT}\ket{a} = \ket{\phi\_1 (a)} \otimes \cnoktalar \otimes \ket{\phi\_n (a)} olduğunu görebilirsiniz.
$ $ Bir Ekleyici işlemi gerçekleştirmeye yönelik yol daha sonra, girişlerin toplamının $ $ \ket{a + b} = \operatorname{QFT} ^{-1}\ket{\fi\_1 (a + b)} \otimes \cnoktalar \otimes \ket{\phi\_n (a + b)} olarak yazılabileceğini gözlemledikten sonra net bir hale gelir.
$ $ $B $ ve $a $ tamsayısı, $b $ $ as denetimleri kullanılarak ayrıştırma içindeki her bir qubit üzerinde denetlenen aşama dönüşü gerçekleştirerek eklenebilir.

Bu genişleme, her tamsayı $j $ ve gerçek sayı $x $, $e ^ {i2\pi (x + j)} = e ^ {i2\pi x} $ olduğunu belirterek daha kolay bir şekilde basitleştirilebilir.  Bunun nedeni, $360 ^ {\circ} $ derece ($ 2 \ Pi $ radyan) bir daire içinde döndürmenize neden olur.  $E ^ {i2\pi x} $ için $x $ öğesinin yalnızca önemli bir parçası bu nedenle $x $ bölümünün kesirli kısmıdır.  Özellikle, formun ikili genişletmemiz varsa $x = y +0. x\_0x\_2 \ lnoktalar x\_n $, $e ^ {i2\pi x} = e ^ {i2\pi (0). x\_0x\_2 \ lnoktalar x\_{n-1})} $ ve bu nedenle $ $ \ket{\phi\_k (a + b)} = \frac{1}{\sqrt{2}} \left (\demet{0} + e ^ {i2\pi [a/2 ^ k +0. b\_k\ldots b\_1]} \ayraç{1} \right). $ $ Bu, her birinin $ \ket{a} $ öğesinin Fourier dönüştürmesinin genişletilmesinde tencursor faktörleri, döndürmeler sayısı $k $ düşüş olarak küçülür.  Bu, Adder 'de gerekli olan hisse kapıları sayısını önemli ölçüde azaltır.  Fourier dönüşümü, aşama ekleme ve ters Fourier Dönüştürme adımlarının $ \operatorname{QFT} ^{-1} \left (\fi\\\!\operatorname{ADD}\right) \operatorname{QFT} $ olarak olduğunu belirledik. İşlemin tamamını uygulamak için bu basitleştirme kullanan bir hisse devresini aşağıda görebilirsiniz.

![Devper, devre diyagramı olarak gösterilen Ekleyici](~/media/draper.png)

Bağlantı hattı 'ndaki her denetlenen $e ^ {I2 \ PI/k} $ kapısı, denetlenen aşama kapısı anlamına gelir.  Bu tür kapıları, $ \gre{00}\mapsto \tus{00}$ ancak $ \gre{11}\mapsto e ^ {I2 \ PI/k} \ tus{11}$ olan qubit çiftinde özelliği vardır.  Bu bağlantı hattı, giriş ve çıkışları depolamak için gerekenden başka bir qubit olmadan toplama işlemi gerçekleştirmemizi sağlar.

### <a name="beauregard-adder"></a>Beauregard Adder ###

Beauregard ekleyici, rastgele bir pozitif tamsayı $N $ için ek modül $N $ gerçekleştirmek üzere Draper Ekleyici ' i kullanan bir hisse modüler bir Ekleyici.  Beauregard Adder gibi hisse modüler kişilerin önemi, Adder gibi, kor 'ın düzenleme için algoritması içindeki modüler üs adım 'daki kullanımlarını büyük bir ölçüde kullanıyor.  Hisse modüler bir ekleyici, hisse girişi $ \ket{b} $ ve klasik giriş $a $ $a $ ve $b $ tamsayı mod $N $ olarak kabul edildiği ve $ [0, \lnoktalar, N-1] $ aralığında oldukları anlamına gelir.

$ $ \ket{b}\rightarrow \ket{b + a \Text{mod} N} = \begin{Cases} \ket{b + a}, & b + a < N\\\\ \ket{b + a-N}, & (b + a) \ge N \end{Cases}.
$$

Beauregard ekleyici, $a $ ve $b $ aşamasına eklemek için Draper Ekleyici veya daha özel olarak $ \fi\\\!\operatorname{Add} $ kullanır.  Daha sonra, $a + b-N < 0 $ ' ı çıkararak $a + b < N $ $N $ ve test etmeyi kaldırarak aynı işlemi kullanır.  Devre, bu bilgileri bir anılususılge içinde depolar ve sonra $a + b < N $ $N $ kaydı ekler.  Daha sonra bu işlem, bu ek bitin bitmemesini sağlar (Bu adım, Adder çağrıldıktan sonra, anıllanla 'nın de ayrılabileceği emin olmak için gereklidir).  Beauregard Ekleyici için devre aşağıda verilmiştir.

![Devre diyagramı olarak gösterilen Beauregard Ekleyici](~/media/beau.png)

Burada, $ \Fi\\\!\operatorname{ADD} $ kapısı $ \phi\\\!\operatorname{ADD} $ ile aynı şekilde sürer. Bu bağlamda, bu bağlamda, girişin hisse yerine  Bu, $ \Fi\\\!\operatorname{ADD} $ içindeki denetlenen aşamaların, hem qubit hem de Adder için gereken kapı sayısını azaltmak üzere daha az işlem halinde derlenebilecek aşama kapıları ile değiştirilmesini sağlar.

Daha fazla ayrıntı için lütfen [M. Roetteler, TH. Beth](http://doi.org/10.1007/s00200-008-0072-2 ) ve [D. Coppersmith](https://arxiv.org/abs/quant-ph/0201067)'e bakın.

### <a name="quantum-phase-estimation"></a>Kuantum Aşama Tahmini ###

Hisse daha önemli bir uygulama olan unitfourier dönüştürmesinin, *aşama tahmini*olarak bilinen bir sorun olan Unitary işleçlerinin eigendeğerlerini öğrenmesinin nedeni.
Bir Unitary $U $ ve $ \ket{\phi} $ gibi bir State $ \ket{\phi} $, bilinmeyen eigenvalue $ \phi $, \begin{Equation} U\tus{\ Fi} = \phi\ket{\phi} ile $U $ öğesinin bir eigenstate olduğunu düşünün.
\end{Equation} yalnızca bir Oracle olarak $U $ erişimi varsa, denetimli bir işlemin hedefine uygulanan $Z $ roetlerini denetimin üzerine geri yayarak $ \phi $ aşamasını öğreniyoruz.

$V $ öğesinin, \begin{hizalaması} V (\ayraç{0} \otimes \ket{\phi}) & = \tus{0} \otimes \ket{\phi} gibi kontrollü bir $U $ uygulaması olduğunu varsayalım. \\\\ \textrm{ve} V (\demet{1} \otimes \ket{\phi}) & = e ^ {i \phi} \tus{1} \otimes \ket{\phi}.
\end{hizalaması} sonra, şu şekilde, \begin{hizalaması} V (\ket{+} \otimes \ket{\phi}) & = \frac{(\tus{0} \otimes \ket{\phi}) + e ^ {ı \phi} (\demet{1} \otimes \ket{\phi})} {\sqrt{2}}.
\end{hizalaması} Bu \ Begin{hizalaması} V (\ket{+} \otimes \ket{\phi}) öğesini bulmak için şartlar toplayabiliyoruz & = \frac{\tus{0} + e ^ {ı \ Phi} \tus{1}} {\sqrt{2}} \otimes \ket{\phi} \\\\ & = (R_1 (\fi) \ket{+}) \otimes \ket{\phi}, \end{hizalaması}; burada $R _1 $, <xref:microsoft.quantum.intrinsic.r1> işlemi tarafından uygulanan Unitary.
Farklı şekilde, $V $ uygulamanın etkisi, yalnızca bir Oracle olarak $V $ erişimine sahip olduğumuz halde, bilinmeyen bir açıyla $R _1 $ ' ı uygulama ile tam olarak aynıdır.
Bu nedenle, bu tartışmanın geri kalanı için aşama tahmini $R _1 (\phi) *$ olarak tartışıyoruz.*

Denetim ve hedef kayıt bu işlemden sonra geri ılanmadan kaldığından, "_1 (2 \fi) \ket{+} $ $R durumunda ikinci bir denetim qubit hazırlamak için $U ^ $2 kontrollü bir uygulamasının hedefi olarak $ \ket{\phi} $ öğesini yeniden kullanabilirsiniz.
Bu şekilde devam ederek, \begin{hizalaması} \ket{\psı} & = \ sum_ {j = 0} ^ n R_1 (2 ^ j \ Fi) \ket{+} \\\\ & \propto \ bigotimes_ {j = 0} ^ {n} \left (\demet{0} + biçiminde bir kayıt edinebilirsiniz \exp (i 2 ^ {j} \fi) \gre{1}\right) \\\\ & \propto \ sum_ {k = 0} ^ {2 ^ n-1} \exp (i \phi k) \ket{k} \end{hizalaması}; burada $n $, gereken duyarlık bit sayısı olan ${} \propto {}$ ile $ 'ın normalleştirme faktörünü gizliyoruz 1/\ sqrt{2 ^ n} $.

$ \Phi = 2 \ Pi p/2 ^ k $ ' ı bir tamsayı $p $ olarak kabul ediyorsanız, bunu $ \ket{\psı} = \operatorname{QFT} \ket{p_0 p_1 \noktalar p_n} $ olarak tanıyacağız; burada $p _j $, $j ^ {\textrm{TH}} $ bit/$2 \pi \phi $ şeklindedir.
Bu nedenle, hisse dosyası miktarı olarak kodlanan aşamanın ikili gösterimini elde ettiğimiz için, bu nedenle hisse.

Q # içinde bu, $m $ $U pozitif tamsayıların bir işlevi olarak <xref:microsoft.quantum.oracles.discreteoracle> uygulamayı uygulayan <xref:microsoft.quantum.characterization.quantumphaseestimation> işlem tarafından uygulanır.
