---
title: Q#Standart kitaplıklardaki uygulamalar
description: Hisse bilgi işlem-Hamiltonian simülasyonu ve Shor 'ın arama algoritmasındaki iki temel uygulama hakkında bilgi edinin.
author: QuantumWriter
uid: microsoft.quantum.libraries.applications
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
no-loc:
- Q#
- $$v
ms.openlocfilehash: 4caacaad127f8a4d3b6f77efe35ebe7d3b97cacf
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868772"
---
# <a name="applications"></a>Uygulamalar #

## <a name="hamiltonian-simulation"></a>Hamilton Benzetimi ##

Hisse sistemlerinin simülasyonu, hisse hesaplamanýn en heyecan verici uygulamalarından biridir.
Klasik bir bilgisayarda, genel olarak hisse kutları benzetimi yapma zorluğunu, durumu vektör gösteriminin boyut $N $ ' i ile ölçeklendirir.
Bu gösterim $n $ qubitleri $N = 2 ^ n $ ile üstel olarak artdıkça [, nitelik](xref:microsoft.quantum.concepts.multiple-qubits)bir şekilde bilinen, klasik donanımda hisse benzeme olarak da bilinir.

Ancak, bu durum hisse uygun şekilde çok farklı olabilir. Hisse benzetiminin en yaygın çeşitine, zaman bağımsız Hamiltonian benzetim sorunu olarak adlandırılır. Burada, bir hermitian matrisi olan System Hamiltonian $H $, ve bir hisse bilgisayarında $n $ qubits 'e göre bazı ilk hisse miktarı $ \ket{\psı (0)} $ şeklinde kodlanmış bir açıklama verilmiştir. Kapalı sistemlerdeki hisse makineleri Schrödinger denklemi $ $ \begin{hizalaması} ı\frac {d \ket{\psı (t)}} {d t} & = H \ket{\psı (t)} altında geliştikçe, \end{hizalaması} $ $ hedef, Unitary zaman-uç işlecinin $U (t) = e ^ {-IHV t} $ $t $, burada $ \ket{\psı (t)} = U (t) \ket{\psı (0)} $, Schrödinger denklemi çözer.
Benzer şekilde, zamana bağlı Hamiltonian benzetim sorunu aynı denklemi çözer, ancak $H (t) $ ile artık bir zaman işlevidir.

Hamiltonian simülasyonu, diğer birçok hisse simülasyonu sorununun önemli bir bileşenidir. Hamiltonian simülasyonu sorununa yönelik çözümler, \\ \\ [Spectral norm](xref:microsoft.quantum.concepts.matrix-advanced)' de hata $ | \tilde{u}-U (t) | \le \epsilon $ hatası ile yaklaşık bir değer içeren Unitary $ \tilde{u} $ öğesini birleştirme için bir dizi temel miktarı açıklayan algoritmalardır. Bu algoritmaların karmaşıklığı, bir hisse bilgisayar tarafından nasıl erişilebilen Hamilton açıklamasına göre çok daha güçlü bir şekilde yapılır. Örneğin, en kötü durumda, $n $ qubitleri üzerinde işlem yapan $H $, her matris öğesi için bir tane olmak üzere $2 ^ n \times 2 ^ n $ sayı listesi olarak sağlanacaksa, yalnızca verilerin okunması üstel bir süre gerektirir. En iyi durumda, biri $O \ket{t}\ket{\psi (0)} = \ket{t}U (t) \ket{\psı (0)} $, sorunu çözen bir siyah kutu Unitary erişimi varsayabilir. Bu giriş modellerinin hiçbiri özellikle ilgi çekici değildir. Bu, klasik yaklaşımlardan daha iyi olmadığı ve ikinci olarak siyah kutu olarak, uygulamanın temel kapı karmaşıklığını, bu da qubit sayısında üstel hale getirebileceği şekilde gizler.

### <a name="descriptions-of-hamiltonians"></a>Hamiltonians açıklamaları ###

Bu nedenle, girişin biçimi için ek varsayımlar gereklidir. Gerçekçi fiziksel sistemler veya ilginç bilgi işlem sorunları gibi ilgi çekici bir şekilde açıklayıcı olan giriş modelleri arasında ince bir denge olmalıdır ve bir hisse bilgisayar üzerinde etkin bir şekilde uygulanacak şekilde kısıtlayıcı olan giriş modelleri. Çok sayıda önemsiz olmayan giriş modeli, belgeler içinde bulunabilir ve bu, hisse miktarı ile klasik arasında değişir. 

Hisse giriş modelinin örnekleri olarak, [örnek tabanlı Hamiltonian simülasyonu](http://www.nature.com/articles/s41534-017-0013-7) , hamiltonian $H $ olmak üzere gerçekleştirilen bir yoğunluk matrisi $ \rho $ ' ın kopyalarını üreten hisse ışlarına kara kutu erişimi olduğunu varsayar. [Unitary erişim modelinde](https://arxiv.org/abs/1202.5822) tek bir Işlem, Hamiltonian 'nin bir toplam unitcg $ $ \Begin{hizalaması} H & = \sum ^ {d-1} \_ {j = 0} a \_ j \hat{U} \_ j, \end{hizalaması} $ $, $a \_ j>$0, ve $ \hat{U} \_ j $ olan birimlere göre değil. Daha sonra, bir birinin, istenen $ \hat{U} j $ öğesini seçen Unitary Oracle $V = \sum ^ {d-1} \_ {j = 0} \Ket{j}\bra{j}\otimes \hat{U} j $ öğesine siyah box erişimi olduğunu varsaymıştır. \_ \_ ve Oracle $A \ket {0} = \ Sum ^ {d-1} \_ {j = 0} \sqrt{a \_ j/\ Sum ^ {d-1} \_ {k = 0} \Alpha \_ j} \ket{j} $ Bu katışlarını kodlayan bir hisse durumu oluşturur. [Seyrek Hamiltonian simülasyonu](https://arxiv.org/abs/quant-ph/0301023)durumunda, tek bir Hamiltonian 'ın her satırda yalnızca $d = \mathcal{O} (\Text{Polylog} (N)) $ sıfır olmayan öğe içeren bir seyrek matris olduğunu varsaymaktadır. Üstelik, bir diğeri, bu sıfır olmayan öğelerin konumunu ve değerlerini izleyen etkin hisse devreleri varlığını kabul eder. [Hamiltonian benzetim algoritmalarının](xref:microsoft.quantum.more-information) karmaşıklığı, bu siyah kutulara yönelik sorgu sayısı bakımından değerlendirilir ve temel kapı karmaşıklığı, bu siyah kutuları uygulama zorluklarını çok daha fazla farklılık gösterir.

> [!NOTE]
> Büyük O gösterimi, algoritmaların karmaşıklık ölçeklemesini betimleyen yaygın olarak kullanılır. İki gerçek işlev $f, g $ $g (x) = \mathcal{O} (f (x)) $ ifadesi, \_ tüm $g \ge x $0 için $x (x) \le c f (x) $ gibi mutlak pozitif bir sabit değer $x 0, c>$0 olduğunu gösterir \_ . 

En pratik uygulamalarda, bir hisse bilgisayarında uygulanacak olan bu siyah kutular, $ \mathcal{O} (\Text{Polylog} (N)) $ ilkel hisse kapıları bulunan etkin bir şekilde ımplemenanabilir olmalıdır. Daha güçlü, verimli simulable Hamiltonians, yeterince seyrek klasik açıklama içermelidir. Bu tür bir formülde, Hamiltonian 'ın toplam hermitian parça $ $ \begin{hizalaması} H & = \sum ^ {d-1} _ {j = 0} H_j bir toplamına işaret eden varsayılır.
\end{hizalaması} $ $ Üstelik, her parçanın bir Hamiltonian $H \_ j $, benzetimini yapmak için kolay olduğunu varsaymaktadır. Bu, herhangi bir zaman için $e ^ {-iH \_ j t} $ $t $ 'in yalnızca $ \mathcal{O} (1) $ temel hisse kapıları kullanılarak tam olarak uygulanabileceği anlamına gelir. Örneğin, bu, her bir $H \_ j $ 'ın yerel Pauli işleçleri olduğu, yani (yani, ı\mathcal{O} (1) $ Identity olmayan Pauli işleçleri olan ve gereksiz kapalı qubit üzerinde işlem yapan, yani, bu durum geçerlidir. Bu model, sınırlı ve yerel etkileşime sahip fiziksel sistemlere özellikle uygulanabilir, çünkü koşulların sayısı $d = \mathcal{O} (\Text{Polylog} (N)) $ olur ve açıkça aşağı yazılabilir ve yani polinom zaman içinde açıklanabilir.

> [!TIP]
> Bir parçalar toplamı içine oluşturan Hamiltonians, Dynamical Oluşturucu temsili kitaplığı kullanılarak açıklanabilir. Daha fazla bilgi için [veri yapılarının](xref:microsoft.quantum.libraries.data-structures)Dynamical Oluşturucu temsili bölümüne bakın.

### <a name="simulation-algorithms"></a>Simülasyon algoritmaları ###

Bir hisse simülasyonu algoritması, bir Hamiltonian 'nin verilen açıklamasını, bir bütün olarak, yaklaşık olarak görünen Hamiltonian, yaklaşık bir zaman evrimi dizisine dönüştürür.

Hamiltonian, hermitian parçalarının toplamına işaret eden özel bir durumda, Trour-Suzuki ayrıştırma, hermitian bileşenleri toplamını oluşturan Hamiltonians benzetimi için özellikle basit ve sezgisel bir algoritmadır. Örneğin, bu aileye ait ilk sipariş tümleştiricisi $ $ \begin{hizalaması} U (t) & = \left (e ^ {-iH \_ 0 t/r} e ^ {-ih \_ 1 t/r} \cnoktalar e ^ {-IH \_ {d-1} t/r} \ right) ^ {r} + \mathcal{O} (d ^ 2 \ max_j \\ | H \_ j \\ | ^ 2 t ^ 2/r), \end{hizalaması} $ $ $r d $ terimlerinin bir ürününü kullanıyor. 

> [!TIP]
> Trour-Suzuki simülasyon algoritmasının uygulamaları örneklerde ele alınmıştır.
> Yalnızca her bir hedef makine tarafından sunulan iç işlemleri kullanan, şaşırtıcı model için lütfen [ **simplefon** örneğine](https://github.com/microsoft/Quantum/blob/master/samples/simulation/ising/simple)bakın.
> Trour-Suzuki kitaplık denetim yapısını kullanan, şaşırtıcı model için lütfen [ **ısingtrour** örneğine](https://github.com/microsoft/Quantum/tree/master/samples/simulation/ising/trotter-evolution)bakın.
> Trour-Suzuki kitaplık denetim yapısını kullanarak molesel Hydrogen için lütfen [ **H2 simülasyon** örneğine](https://github.com/microsoft/Quantum/tree/master/samples/simulation/h2/command-line)bakın.

Çoğu durumda benzetim algoritmasını uygulamak istiyoruz, ancak uygulamasının ayrıntıları ile ilgilenmez. Örneğin, ikinci sipariş tümleştiricisi $ $ \begin{hizalaması} U (t) & = \left (e ^ {-iH \_ 0 t/2R} e ^ {-ih \_ 1 t/2R} \cnoktalar e ^ {-ih \_ {d-1} t/2R} e ^ {-ih \_ {d-1} t/2R} \cnoktalar e ^ {-ih \_ 1 t/2R} e ^ {-ih \_ 0 t/2R} \right) ^ {r} + \mathcal{O} (d ^ 3 \ max_j \\ | H \_ j \\ | ^ 3 t ^ 3/r ^ 2), \end{hizalaması} $ $ $2rd $ terimlerinin bir ürününü kullanıyor. Daha büyük siparişler daha fazla hüküm ve en iyi duruma getirilmiş varyantlar, üs lerde yüksek düzeyde önemsiz olmayan sıralar gerektirebilir. Ayrıca, diğer gelişmiş algoritmalar ara adımlarda anyala qubits kullanımını da içerebilir. Bu nedenle, Kullanıcı tanımlı tür olarak Canon 'daki benzetim algoritmalarını paketliyoruz

```qsharp
newtype SimulationAlgorithm = ((Double, EvolutionGenerator, Qubit[]) => Unit is Adj + Ctl);
```

İlk parametre `Double` Benzetim `EvolutionGenerator` zamanındır, [veri yapılarının](xref:microsoft.quantum.libraries.data-structures)Dynamical Oluşturucu temsili bölümünde ele alınan ikinci parametre, zaman bağımsız bir Hamiltonian 'ın, Hamiltonian içindeki her bir terimin bir hisse bağlantı hattı tarafından nasıl benzetildiği hakkında yönergeler içeren klasik bir açıklamadır. Bu formun türleri, sanal parametre üzerinde ^ {-IHV t} $ $e, `Qubit[]` sanal sistemin hisse ma durumunu depolayan yazmaç olan Unitary işlemini yaklaşık olarak yaklaşık olarak. Benzer şekilde zamana bağlı durumda, bir `EvolutionSchedule` zamana bağlı Hamiltonian 'ın klasik açıklaması olan, bir tür ile Kullanıcı tanımlı bir tür tanımlıyoruz.

```qsharp
newtype TimeDependentSimulationAlgorithm = ((Double, EvolutionSchedule, Qubit[]) => Unit : Adjoint, Controlled);
```

Örnek olarak, Trour-Suzuki ayrıştırma aşağıdaki Canon işlevleri kullanılarak, `trotterStepSize` her bir üstel içindeki benzetimin süresini değiştiren parametrelerle ve `trotterOrder` istenen integral alanının sırası için çağrılabilir.

```qsharp
function TrotterSimulationAlgorithm(
    trotterStepSize : Double, 
    trotterOrder : Int) 
: SimulationAlgorithm {
    ...
}

function TimeDependentTrotterSimulationAlgorithm(
    trotterStepSize : Double, 
    trotterOrder : Int) 
: TimeDependentSimulationAlgorithm {
    ...
}
```

> [!TIP]
> Simülasyon kitaplığının uygulamaları örneklerde ele alınmıştır. Kullanarak, elde eden modeldeki aşama tahmini için `SimulationAlgorithm` lütfen [ **ıingphasetahmine** örnek örneğine](https://github.com/microsoft/Quantum/tree/master/samples/simulation/ising/phase-estimation)bakın.
> Kullanarak, şaşırtıcı modeldeki Adiabatik durum hazırlığı için `TimeDependentSimulationAlgorithm` lütfen bkz. [ **Adiabaticfon** örneği](https://github.com/microsoft/Quantum/tree/master/samples/simulation/ising/adiabatic).


### <a name="adiabatic-state-preparation--phase-estimation"></a>Adiabatik durum hazırlığı & aşama tahmini ###

Hamiltonian benzetiminin yaygın bir uygulaması, Adiabatik durum hazırlığından biridir. Burada, bir tane iki Hamiltonians $H \_ {\Text{Start}} ve $H \_ {\Text{End}} $ ve başlangıç Hamiltonian $H \_ {\Text{Start}} $ adlı bir zemin durumu $ \ket{\psı (0)} $ ile birlikte sağlanır. Genellikle, \_ {\Text{start}} $ $H, $ \ket{\psı (0)} $, hesaplama tabanlı bir durumdan $ \ket{0\cnoktalar 0} $ üzerinden hazırlanmaya kolay bir şekilde seçilir. Zamana bağlı simülasyon sorununun bu Hamiltonians arasında enterpolasyona çok yavaş, son Hamiltonian $H {\Text{End}} $ 'ın zemin durumunda yüksek olasılığa sahip olmak mümkün \_ . Hamiltonian zemin durumlarında iyi bir yaklaşımlar hazırlarken, zamana bağlı Hafretonian simülasyon algoritmalarından sonra bir altyordam olarak arayarak bu şekilde devam edebilse de, değişen hisse dili gibi diğer kavramsal farklı yaklaşımlar mümkündür.

Yine de, bir başka uygulama de, Hamiltonians 'in, kimyasal yeniden eyleminin ara adımlarını temsil eden, 'in zemin durumu enerji düzeyini tahmin ediyor. Örneğin, bu tür bir düzen, zemin durumunu oluşturmak için Adiabatik durum hazırlanmasını kullanır ve ardından zaman bağımsız Hamilton benzetimini, daha sınırlı bir hata ve başarılı olma olasılığı ile bu enerji çıkarmak için aşama tahmini karakter oluşturma bölümünde yer alan bir altyordam olarak birleştirebilirler. 

Simülasyon algoritmalarının Kullanıcı tanımlı türler olarak `SimulationAlgorithm` `TimeDependentSimulationAlgorithm` soyutlamalarını sağlar ve kendi işlevlerini daha karmaşık hisse algoritmalara kolayca dahil etmemizi sağlar. Bu, yaygın olarak kullanılan bu alt yordamlar için aynı yapmamızı ister.

Bu nedenle uygun işlevi tanımladık

```qsharp
function InterpolatedEvolution(
        interpolationTime : Double, 
        evolutionGeneratorStart : EvolutionGenerator,
        evolutionGeneratorEnd : EvolutionGenerator,
        timeDependentSimulationAlgorithm : TimeDependentSimulationAlgorithm)
: (Qubit[] => Unit is Adj + Ctl) {
        ...
}
 
```

Bu, Adiabatik durum hazırlığının tüm adımlarını uygulayan bir Unitary işlemi döndürür. İlk parametre, `interpolatedTime` ikinci parametre tarafından tanımlanan başlangıç Hamiltonian `evolutionGeneratorStart` ve üçüncü parametre tarafından tanımlanan End Hamiltonian arasında ilk olarak daha önce enterpoladığımız süreyi tanımlar `evolutionGeneratorEnd` . Dördüncü parametre, `timeDependentSimulationAlgorithm` birinin benzetim algoritması seçimini yaptığı yerdir. Eğer `interpolatedTime` yeterince uzunsa, ilk zemin durumunun zamana bağlı simülasyon süresinin tamamına kadar Hamiltonian 'ın anlık bir durumunun kaldığını ve bu nedenle son Hamiltonian 'in baş durumunda bittiğini unutmayın.

Ayrıca tipik bir hisse ansız deneme denemesinin tüm adımlarını otomatik olarak gerçekleştiren yararlı bir işlem de tanımladık. Örneğin, Adiabatik durum hazırlığı tarafından üretilen durumun enerji tahminini döndüren aşağıda verilmiştir:

```qsharp
operation EstimateAdiabaticStateEnergy(
    nQubits : Int,
    statePrepUnitary : (Qubit[] => Unit),
    adiabaticUnitary : (Qubit[] => Unit),
    qpeUnitary: (Qubit[] => Unit is Adj + Ctl),
    phaseEstAlgorithm : ((DiscreteOracle, Qubit[]) => Double))
: Double {
...
}
```

`nQubits`, ilk hisse durumu kodlamak için kullanılan qubits sayısıdır. `statePrepUnitary`başlangıç durumunu hesaplama tabanlı $ \ket{0\cnoktalar 0} $ ' dan hazırlar. `adiabaticUnitary`, işlev tarafından üretilen Adiabatik durum hazırlanmasını uygulayan Unitary işlemidir `InterpolatedEvolution` . `qpeUnitary`, sonuçta elde edilen hisse için aşama tahmini gerçekleştirmek üzere kullanılan Unitary işlemidir. `phaseEstAlgorithm`, aşama tahmini algoritması seçimimize ait.

> [!TIP]
> Adiabatik durum hazırlığının uygulamaları örneklerde ele alınmıştır. İşlevi kullanarak Adiabatik durum hazırlığının el ile uygulanmasını kullanan, şaşırtıcı model için `AdiabaticEvolution` lütfen bkz. [ **Adiabaticfon** örneği](https://github.com/microsoft/Quantum/tree/master/samples/simulation/ising/adiabatic).
> Şaşırtıcı modelde aşama tahmini ve Adiabatik durum hazırlığı için lütfen [ **ıingphasetahmine** örnek](https://github.com/microsoft/Quantum/tree/master/samples/simulation/ising/phase-estimation)bölümüne bakın.

> [!TIP]
> [Molesel Hydrogen benzetimi](https://github.com/microsoft/Quantum/tree/master/samples/simulation/h2/command-line) , ilginç bir ve kısa bir örnektir. $ [Malley et. Al](https://arxiv.org/abs/1512.06860) içinde bildirilen model ve deneysel sonuçlar. yalnızca Pauli matrislerini gerektirir ve $ \hat H = g \_ {0} i \_ 0i \_ 1 + g \_ 1 {Z \_ 0} + g \_ 2 {Z \_ 1} + g \_ 3 {z \_ 0} {z \_ 1} + g \_ 4 {y \_ 0} {y \_ 1} + g \_ 5 {x \_ 0} {x \_ 1} $ biçimini alır. Bu geçerli bir Hamiltonian yalnızca yalnızca 2 qubit gerektirir; burada $g $ sabitleri, iki Hydrogen alar arasında $R $ ile hesaplanır. Canon işlevleri kullanılarak Paulıs, unitcihazlarına dönüştürülür ve sonra da Trour-Suzuki ayrıştırma kullanılarak kısa süreler üzerinde bulunur. $H _2 $ zemin durumunun bir önemi, Adiabatik durum hazırlığı kullanılmadan oluşturulabilir ve bu nedenle, Canon 'nin aşama tahmininden yararlanarak doğrudan devlet enerjisi bulunabilir.

## <a name="shors-algorithm"></a>Shor Algoritması ##
Shor 'nin algoritması, hisse ve şu anda sınıflardaki sorunları gidermek için hisse bilgisayarlarının kullanılabileceğini gösterdi, bu, hisse alım açısından en önemli geliştirmelerin birine sahiptir.
Shor 'ın algoritması, *düzenleme*adlı bir sorun olan bir hisse bilgisayarı kullanarak büyük sayıları çarpanlarına yönelik hızlı bir yol sağlar.
Birçok mevcut günlük cryptosystems güvenliği, düzenleme için hızlı algoritma yok varsayımına dayanır.
Bu nedenle, Shor 'nın algoritması, bir hisse alım dünyasının güvenliğini nasıl düşündüğimizi gösteren bir etkiye sahip oldu.

Shor 'ın algoritması karma algoritma olarak düşünülebilir.
Hisse bilgisayar, dönem bulma olarak bilinen bir hesaplama sabit görevi gerçekleştirmek için kullanılır.
Süre bulmanın sonuçları, faktörleri tahmin etmek için sınıfda olarak işlenir.
Bu iki adımı aşağıda gözden geçiririz.

### <a name="period-finding"></a>Süre bulma ###

Hisse maadı ve aşama tahmini 'nin nasıl çalıştığını (bkz. [hisse algoritmaları](xref:microsoft.quantum.libraries.standard.algorithms)) gördük, bu araçları, *Dönem bulma*adlı bir sınıf olarak zor hesaplama sorununu çözmek için kullanabiliriz.  Sonraki bölümde, düzenleme ' ye nasıl bir süre bulmayı uygulayacağınızı inceleyeceğiz.

$A $ ve $N $ $ $a<N $, burada bulma sırası olarak da adlandırılan, bulma dönemi hedefi $r $ mod $a _$ $N $_ $r $, $a $ $. \equ1 \Text{mod} N $ gibi en az pozitif tamsayı olacak şekilde tanımlanır.  

Bir hisse bilgisayarı kullanarak siparişi bulmak için şu Unitary işlecine uygulanan aşama tahmini algoritmasını kullanabiliriz $U _a $: $ $ U_a \ket{x} \equteket{(AX) \Text{mod} N}. $ $ $U _a $ öğesinin eigenvektörler tamsayı $s $ ve $0 \ LEQ s \leq r-$1, $ $ \ket{x_s} \equ1/\sqrt{r} \sum \_ {k = 0} ^ {r-1} e ^ {\frac{-2\pı i SK} {r}} \ket{a ^ k\text {mod} N}, $ $ $U _a $. _eigenstates_
$U _a $ öğesinin eigenvalues değeri $ $ U \_ a \ket{x \_ s} = e ^ {2 \ Pi i s/r} \ket{x \_ s} şeklindedir. $$

Bu nedenle, aşama tahmini, $s/r $ ' den [devam eden kesirleri](https://en.wikipedia.org/wiki/Continued_fraction) kullanarak $r $ tarafından verimli bir şekilde öğrenildiği ^ {2 \ Pi i s/r} $ $e eigenvalues verir.

Hisse dönemi bulma için devre diyagramı:

![Hisse dönemi bulma için devre diyagramı](~/media/QPE.svg)

Burada $2n $ qubit $ \ment $ olarak başlatılır {0} $n ve $ qubits $ \tus$ olarak başlatılır {1} .
Okuyucu yeniden, eigenstates 'i tutmak üzere hisse kayıt 'nın $ \tus$ olarak başlatıldığını merak edebilir {1} .
Bir biri $r $ sırasını önceden değil, aslında $ \ket{x_s} $ durumlarını doğrudan hazırlayamıyoruz.
Luckily, bu $1/\ sqrt {r} \sum \_ {s = 0} ^ {r-1} \ket{x \_ s} = \tus$ öğesini kapatır {1} .
Gerçekten $ \ket{x} $ ' i hazırlamak zorunda değildir.
Yalnızca $ \gre$ durumunda $n $ qubitleri için bir hisse kayıt hazırlayabiliriz {1} . 

Devre, QFT ve çeşitli kontrollü kapıları içerir.
QFT kapısı [daha önce](xref:microsoft.quantum.libraries.standard.algorithms)açıklanmıştı.
Denetlenen-$U _a $ Gate $ \ket{x} $ $ \ket{x} $ to $ \ket{(AX) \Text{mod} N} $, denetim qubit $ \ket {1} $ ve < \ket{x} $ ' i $ \ket{x} $ olarak eşleştirir.

$ (A ^ NX) \Text{mod} N $ ' ı elde etmek için, yalnızca $a ^ n \Text{mod} N $ sınıfındaki $U.  
Bu tür Modüler aritmetik elde etme [devreleri, özellikle](./algorithms.md#arithmetic)de denetlenen-$U \_ {a ^ ı} $ işlemlerini uygulamak için modüler bir üs bağlantı devresini gerektirir.

Yukarıdaki devre, [hisse miktarı tahminine](xref:microsoft.quantum.characterization.quantumphaseestimation) karşılık gelir ve açıkça sıra bulma imkanı sağladığından, gereken qubits sayısını azaltabiliriz. Beauregard 'in [, Arxıv: Quant-pH/, 5095v3 sayfa 8](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=8)' de açıklandığı gibi sipariş bulma yöntemini takip edebilir ya da Microsoft. hisse. Örneğin, [sağlam aşama tahmini](xref:microsoft.quantum.characterization.robustphaseestimation) de bir ek qubit kullanır.
 
### <a name="factoring"></a>Düzenleme ###
Düzenleme 'in hedefi, $N $ tam sayı çarpanlarının belirlenmesi, burada $N $ bir $n $ bit sayıdır.  
Düzenleme, aşağıda açıklanan adımlardan oluşur. Adımlar üç parçaya ayrılır: klasik bir ön işleme yordamı (1-4); $a \Text{mod} N $ (5); sırasını bulmak için bir hisse bilgi işlem yordamı ve sıra (6-9) ile aynı ana faktörleri türetmede bir klasik özelleştirmediğiniz yordamı.

Klasik ön işleme yordamı aşağıdaki adımlardan oluşur:
1. $N $ çiftse, ana faktör $2 $ ' i döndürün.
2. $P \geq1 $, $q \geq2 $ için $N = p ^ q $, ana faktör $p $ döndürün.  Bu adım sınıf aracılığıyla yapılır.
3. $1 < N-$1 < $a rastgele bir sayı seçin.
4. $ \Text{GCD} (a, N) >$1, ana faktörü $ \Text{GCD} (a, N) $ döndürür. Bu adım Euclid 'nin algoritması kullanılarak hesaplanır.
Hiçbir ana faktör döndürülmezse, hisse için bu yordama devam ediyoruz:
5. $A \Text{mod} N $ öğesinin $r $ sırasını hesaplamak için hisse dönemi bulma algoritmasını çağırın. Ana faktörleri öğrenmek için klasik özelleştirmediğiniz yordamında $r $ kullanın:
6. $R $ tek ise, ön işleme adımına geri dönün (3).
7. $R $ çift ve $a ^ {r/2} =-1 \ metin {mod} N $, ön işleme adımına geri dönün (3).
8. $ \Text{GCD} (bir ^ {r/2} + 1, N) $, $N $, return $ \Text{GCD} (a ^ {r/2} + 1, N) $ olan önemsiz olmayan bir faktördür.
9. $ \Text{GCD} (a ^ {r/2}-1, N) $, $N $, return $ \Text{GCD} (a ^ {r/2}-1, N) $ olan basit olmayan bir faktördür.


Düzenleme algoritması dayalı: en az bir yarısı, $r $ 'nin eşit olduğu $a ve ^ {r/2} \neq-1 \ Text{mod} N $, bu nedenle de asal bir faktör üreten bir yarı olasılık ile gösterilmiştir.  (Daha fazla bilgi Için bkz. [Shor 'ın özgün kağıdına](https://doi.org/10.1109/SFCS.1994.365700) veya [daha fazla bilgi için](xref:microsoft.quantum.more-information)içindeki *temel hisse bilgi işlem* metinlarından biri).
Bir asal faktör döndürülmezse, (1) adımından algoritmayı tekrarlıyoruz.  $N $ deneme sonrasında, her girişim başarısız olma olasılığı en fazla $2 ^ {-n} $ olur.
Bu nedenle, algoritmayı tekrarladıktan sonra çok az sayıda başarı oluşur.
