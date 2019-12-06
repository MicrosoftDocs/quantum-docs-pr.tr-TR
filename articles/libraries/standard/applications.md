---
title: 'Q # standart kitaplıklar-uygulamalar | Microsoft Docs'
description: Q# standart kitaplıkları
author: QuantumWriter
uid: microsoft.quantum.libraries.applications
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: ef22460a5bca63ebaf32c0ba21984e103ec8ebdd
ms.sourcegitcommit: 27c9bf1aae923527aa5adeaee073cb27d35c0ca1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74864398"
---
# <a name="applications"></a>Uygulamalar #

## <a name="hamiltonian-simulation"></a>Hamilton Benzetimi ##

Hisse sistemlerinin simülasyonu, hisse hesaplamanýn en heyecan verici uygulamalarından biridir.
Klasik bir bilgisayarda, genel olarak hisse kutları benzetimi yapma zorluğunu, durumu vektör gösteriminin boyut $N $ ' i ile ölçeklendirir.
Bu gösterim $n $ qubitleri $N = 2 ^ n $ ile üstel olarak artdıkça [, nitelik](xref:microsoft.quantum.concepts.multiple-qubits)bir şekilde bilinen, klasik donanımda hisse benzeme olarak da bilinir.

Ancak, bu durum hisse uygun şekilde çok farklı olabilir. Hisse benzetiminin en yaygın çeşitine, zaman bağımsız Hamiltonian benzetim sorunu olarak adlandırılır. Burada, bir hermitian matrisi olan System Hamiltonian $H $, ve bir hisse bilgisayarında $n $ qubits 'e göre bazı ilk hisse miktarı $ \ket{\psı (0)} $ şeklinde kodlanmış bir açıklama verilmiştir. Kapalı sistemlerdeki hisse makineleri Schrödinger denklemi $ $ \begin{hizalaması} ı\frac {d \ket{\psı (t)}} {d t} & = H \ket{\psı (t)} altında geliştikçe, \end{hizalaması} $ $ amaç, bir sabit zamanda $U (t) = e ^ {-iHt} $ $t Unitary zaman-uç işlecini uygulamaktır. Burada $ \ket{\psı (t)} = U (t) \ket{\psı (0)} $, Schrödinger denklemini çözer.
Benzer şekilde, zamana bağlı Hamiltonian benzetim sorunu aynı denklemi çözer, ancak $H (t) $ ile artık bir zaman işlevidir.

Hamiltonian simülasyonu, diğer birçok hisse simülasyonu sorununun önemli bir bileşenidir ve Hamiltonian simülasyonu sorununa yönelik çözümler, 1 $\\| \tilde{U}-U (t)\\| [Spectral norm](xref:microsoft.quantum.concepts.matrix-advanced)içindeki \le \ Epsilon $. Bu algoritmaların karmaşıklığı, bir hisse bilgisayar tarafından nasıl erişilebilen Hamilton açıklamasına göre çok daha güçlü bir şekilde yapılır. Örneğin, en kötü durumda, $n $ qubitleri üzerinde işlem yapan $H $, her matris öğesi için bir tane olmak üzere $2 ^ n \times 2 ^ n $ sayı listesi olarak sağlanacaksa, yalnızca verilerin okunması üstel bir süre gerektirir. En iyi durumda, biri $O \ket{t}\ket{\psi (0)} = \ket{t}U (t) \ket{\psı (0)} $, sorunu çözen bir siyah kutu Unitary erişimi varsayabilir. Bu giriş modellerinin hiçbiri özellikle ilgi çekici değildir. Bu, klasik yaklaşımlardan daha iyi olmadığı ve ikinci olarak siyah kutu olarak, uygulamanın temel kapı karmaşıklığını, bu da qubit sayısında üstel hale getirebileceği şekilde gizler.

### <a name="descriptions-of-hamiltonians"></a>Hamiltonians açıklamaları ###

Bu nedenle, girişin biçimi için ek varsayımlar gereklidir. Gerçekçi fiziksel sistemler veya ilginç hesaplama sorunlarıyla ilgili olanlar ve yeterince kısıtlayıcı olan giriş modelleri gibi ilginç Hamiltonians için yeterince tanımlayıcı olan giriş modelleri arasında ince bir denge olmalıdır bir hisse bilgisayar üzerinde verimli bir şekilde ımplemenbu tablo. Çok sayıda önemsiz olmayan giriş modeli, belgeler içinde bulunabilir ve bu, hisse miktarı ile klasik arasında değişir. 

Hisse giriş modelinin örnekleri olarak, [örnek tabanlı Hamiltonian simülasyonu](http://www.nature.com/articles/s41534-017-0013-7) , hamiltonian $H $ olmak üzere gerçekleştirilen bir yoğunluk matrisi $ \rho $ ' ın kopyalarını üreten hisse ışlarına kara kutu erişimi olduğunu varsayar. [Unitary erişim modelinde](https://arxiv.org/abs/1202.5822) tek bir Işlem, Hamiltonian 'ın toplam unitcg $ $ \begin{hizalaması} H & = \sum ^ {d-1}\_{j = 0} a\_j \hat{U}\_j olduğunu ortadan kaldırır. \end{hizalaması} $ $; burada $a\_j > 0 $ katlardır ve $ \hat{U}\_j $, birimlerdir. Daha sonra, bir birinin, istenen $ \hat{U}\_j $ öğesini seçen Unitary Oracle $V = \sum ^ {d-1}\_{j = 0} \ket{j}\bra{j}\otimes \hat{U}\_j $ 'a siyah box erişimi olduğunu varsaymıştır. ve Oracle $A \demet{0}= \sum ^ {d-1}\_{j = 0} \sqrt{a\_j/\ Sum ^ {d-1}\_{k = 0} \Alpha\_j} \ket{j} $ Bu katışlarını kodlayan bir hisse durumu oluşturur. [Seyrek Hamiltonian simülasyonu](https://arxiv.org/abs/quant-ph/0301023)durumunda, tek bir Hamiltonian 'ın her satırda yalnızca $d = \mathcal{O} (\Text{Polylog} (N)) $ sıfır olmayan öğe içeren bir seyrek matris olduğunu varsaymaktadır. Üstelik, bir diğeri, bu sıfır olmayan öğelerin konumunu ve değerlerini izleyen etkin hisse devreleri varlığını kabul eder. [Hamiltonian benzetim algoritmalarının](xref:microsoft.quantum.more-information) karmaşıklığı, bu siyah kutulara yönelik sorgu sayısı bakımından değerlendirilir ve temel kapı karmaşıklığı, bu siyah kutuları uygulama zorluklarını çok daha fazla farklılık gösterir.

> [!NOTE]
> Büyük O gösterimi, algoritmaların karmaşıklık ölçeklemesini betimleyen yaygın olarak kullanılır. İki gerçek işlev $f, g $ $g (x) = \mathcal{O} (f (x)) $ ifadesi, tüm > \ge x $g $0 için $x (x) \le c f (x) $ gibi mutlak pozitif bir sabit $x\_0, c\_0 $ olduğunu gösterir. 

En pratik uygulamalarda, bir hisse bilgisayarında uygulanacak olan bu siyah kutular, $ \mathcal{O} (\Text{Polylog} (N)) $ ilkel hisse kapıları bulunan etkin bir şekilde ımplemenanabilir olmalıdır. Daha güçlü, verimli simulable Hamiltonians, yeterince seyrek klasik açıklama içermelidir. Bu tür bir formülde, Hamiltonian 'ın toplam hermitian parça $ $ \begin{hizalaması} H & = \sum ^ {d-1} _ {j = 0} H_j bir toplamına işaret eden varsayılır.
\end{hizalaması} $ $ Üstelik, her parçanın, bir Hamiltonian $H\_j $, benzetimini yapmak için kolay olduğu varsayılır. Bu, herhangi bir zaman için $e ^ {-IH\_j t} $ $t $ 'nin tam olarak $ \mathcal{O} (1) $ temel hisse kapıları kullanılarak uygulantığını gösterir. Örneğin, her bir $H\_j $ yerel Pauli işleçleri olduğu özel durumda bu durum geçerlidir. Yani, ı\mathcal{O} (1) $ kimlik olmayan ve ı (1) $ kimliği olmayan Pauli işleçleri, istenmeyen açık qubit üzerinde işlem gören, Bu model, sınırlı ve yerel etkileşime sahip fiziksel sistemlere özellikle uygulanabilir, çünkü koşulların sayısı $d = \mathcal{O} (\Text{Polylog} (N)) $ olur ve açıkça aşağı yazılabilir ve yani polinom zaman içinde açıklanabilir.

> [!TIP]
> Bir parçalar toplamı içine oluşturan Hamiltonians, Dynamical Oluşturucu temsili kitaplığı kullanılarak açıklanabilir. Daha fazla bilgi için [veri yapılarının](xref:microsoft.quantum.libraries.data-structures)Dynamical Oluşturucu temsili bölümüne bakın.

### <a name="simulation-algorithms"></a>Simülasyon algoritmaları ###

Bir hisse simülasyonu algoritması, bir Hamiltonian 'nin verilen açıklamasını, bir bütün olarak, yaklaşık olarak görünen Hamiltonian, yaklaşık bir zaman evrimi dizisine dönüştürür.

Hamiltonian, hermitian parçalarının toplamına işaret eden özel bir durumda, Trour-Suzuki ayrıştırma, hermitian bileşenleri toplamını oluşturan Hamiltonians benzetimi için özellikle basit ve sezgisel bir algoritmadır. Örneğin, bu aileye ait ilk sipariş tümleştiricisi $ $ \begin{hizalaması} U (t) & = \left (e ^ {-iH\_0 t/r} e ^ {-iH).\_1 t/r} \cnoktalar e ^ {-IH\_{d-1} t/r} \ right) ^ {r} + \mathcal{O} (d ^ 2 \ max_j\\| H\_j\\| ^ 2 t ^ 2/r), \end{hizalaması} $ $ $r d $ terimlerinin bir ürününü kullanıyor. 

> [!TIP]
> Trour-Suzuki simülasyon algoritmasının uygulamaları örneklerde ele alınmıştır.
> Yalnızca her bir hedef makine tarafından sunulan iç işlemleri kullanan, şaşırtıcı model için lütfen [ **simplefon** örneğine](https://github.com/microsoft/Quantum/blob/master/samples/simulation/ising/simple)bakın.
> Trour-Suzuki kitaplık denetim yapısını kullanan, şaşırtıcı model için lütfen [ **ısingtrour** örneğine](https://github.com/microsoft/Quantum/tree/master/samples/simulation/ising/trotter-evolution)bakın.
> Trour-Suzuki kitaplık denetim yapısını kullanarak molesel Hydrogen için lütfen [ **H2 simülasyon** örneğine](https://github.com/microsoft/Quantum/tree/master/samples/simulation/h2/command-line)bakın.

Çoğu durumda benzetim algoritmasını uygulamak istiyoruz, ancak uygulamasının ayrıntıları ile ilgilenmez. Örneğin, ikinci sipariş tümleştirici; $ $ \begin{hizalaması} U (t) & = \left (e ^ {-iH\_0 t/2R} e ^ {-iH\_1 t/2R} \cnoktalar e ^ {-iH\_{d-1} t/2 ' ye yaklaştırır r} e ^ {-iH\_{d-1} t/2R} \cnoktalar e ^ {-iH\_1 t/2R} e ^ {-iH\_0 t/2R} \right) ^ {r} + \mathcal{O} (d ^ 3 \ max_j\\| H\_j\\| ^ 3 t ^ 3/r ^ 2), \end{hizalaması} $ $, $2rd $ terimlerinin bir ürününü kullanıyor. Daha büyük siparişler daha fazla hüküm ve en iyi duruma getirilmiş varyantlar, üs lerde yüksek düzeyde önemsiz olmayan sıralar gerektirebilir. Ayrıca, diğer gelişmiş algoritmalar ara adımlarda anyala qubits kullanımını da içerebilir. Bu nedenle, Kullanıcı tanımlı tür olarak Canon 'daki benzetim algoritmalarını paketliyoruz

```qsharp
newtype SimulationAlgorithm = ((Double, EvolutionGenerator, Qubit[]) => Unit is Adj + Ctl);
```

İlk parametre `Double` simülasyonudur, [veri yapılarının](xref:microsoft.quantum.libraries.data-structures)Dynamical Oluşturucu temsili bölümünde ele alınan ikinci parametre `EvolutionGenerator`, bir zaman bağımsız Hamiltonian 'ın, Hamiltonian içindeki her bir terimin bir hisse devpopdan nasıl benzetildiği hakkında yönergeler içeren klasik bir açıklamadır. Bu formun türleri, sanal parametre `Qubit[]`$e ^ {-IHV t} $ olan Unitary işlemini yaklaşık olarak, sanal sistemin hisse ma durumunu depolayan yazmaç olan bir işlemdir. Benzer şekilde zamana bağlı durumda, bir zamana bağlı Hamiltonian 'ın klasik açıklaması olan bunun yerine `EvolutionSchedule` türü ile Kullanıcı tanımlı bir tür tanımladık.

```qsharp
newtype TimeDependentSimulationAlgorithm = ((Double, EvolutionSchedule, Qubit[]) => Unit : Adjoint, Controlled);
```

Örnek olarak, Trour-Suzuki ayrıştırma aşağıdaki Canon işlevleri kullanılarak çağrılabilir. Bu, her üstel içindeki benzetimin süresini değiştirme `trotterStepSize` ve istenen integral alanının sırası için `trotterOrder`.

```qsharp
function TrotterSimulationAlgorithm(
    trotterStepSize: Double, 
    trotterOrder: Int) 
    : SimulationAlgorithm {
    ...
}
function TimeDependentTrotterSimulationAlgorithm(
    trotterStepSize: Double, 
    trotterOrder: Int) 
    : TimeDependentSimulationAlgorithm {
    ...
}
```

> [!TIP]
> Simülasyon kitaplığının uygulamaları örneklerde ele alınmıştır. `SimulationAlgorithm`kullanarak, elde eden modeldeki aşama tahmini için lütfen [ **ıingphasetahmine** örnek örneğine](https://github.com/microsoft/Quantum/tree/master/samples/simulation/ising/phase-estimation)bakın.
> `TimeDependentSimulationAlgorithm`kullanarak, şaşırtıcı modelde Adiabatik durum hazırlığı için lütfen bkz. [ **Adiabaticfon** örneği](https://github.com/microsoft/Quantum/tree/master/samples/simulation/ising/adiabatic).


### <a name="adiabatic-state-preparation--phase-estimation"></a>Adiabatik durum hazırlığı & aşama tahmini ###

Hamiltonian benzetiminin yaygın bir uygulaması, Adiabatik durum hazırlığından biridir. Burada, bir tane iki Hamiltonians $H\_{\Text{Start} $ ve $H\_{\Text{End}} $, ve başlangıç Hamiltonian $H\_{\Text{start}} $ öğesinin zemin durumu $ \ket{\psı (0)} $ ile birlikte sağlanır. Genellikle, $H\_{\Text{Start}} $, $ \ket{\psı (0)} $ hesaplama tabanlı bir durumdan $ \ket{0\cnoktalar 0} $ üzerinden hazırlanmaya kolay bir şekilde seçilir. Zamana bağlı simülasyon sorununun bu Hamiltonians arasında enterpolasyonuna kadar yavaş, yüksek olasılığa sahip, son Hamiltonian $H\_{\Text{End}} $. Hamiltonian zemin durumlarında iyi bir yaklaşımlar hazırlarken bu şekilde zamana bağlı Hamiltonian simülasyon algoritmalarından sonra, farklı şekilde değişen bir yaklaşım gibi diğer kavramsal farklı yaklaşımlara çağrı yaparak bu şekilde devam edebilirsiniz. eigençözücü mümkündür.

Yine de, bir başka uygulama de, Hamiltonians 'in, kimyasal yeniden eyleminin ara adımlarını temsil eden, 'in zemin durumu enerji düzeyini tahmin ediyor. Örneğin, bu tür bir düzen, zemin durumunu oluşturmak için Adiabatik durum hazırlanmasını kullanır ve ardından zaman bağımsız Hamilton benzetimini, daha sınırlı bir hata ile bu enerji çıkaran bir altyordam ve başarılı olma olasılığı. 

Simülasyon algoritmalarının Kullanıcı tanımlı türler `SimulationAlgorithm` soyutlamalarını ve `TimeDependentSimulationAlgorithm` işlevselliğini daha karmaşık hisse algoritmalarına kolayca eklemesine olanak tanır. Bu, yaygın olarak kullanılan bu alt yordamlar için aynı yapmamızı ister.

Bu nedenle uygun işlevi tanımladık

```qsharp
function InterpolatedEvolution(
        interpolationTime: Double, 
        evolutionGeneratorStart: EvolutionGenerator,
        evolutionGeneratorEnd: EvolutionGenerator,
        timeDependentSimulationAlgorithm: TimeDependentSimulationAlgorithm)
        : (Qubit[] => Unit is Adj + Ctl) {
        ...
}
 
```

Bu, Adiabatik durum hazırlığının tüm adımlarını uygulayan bir Unitary işlemi döndürür. İlk parametre `interpolatedTime`, ikinci parametre `evolutionGeneratorStart` tarafından tanımlanan başlangıç Hamiltonian ve üçüncü parametre `evolutionGeneratorEnd`tarafından tanımlanan bitiş Hamiltonian arasında ilk olarak daha fazla enterpoladığımız süreyi tanımlar. Dördüncü parametre `timeDependentSimulationAlgorithm`, bir benzetim algoritması seçimini yaptığı yerdir. `interpolatedTime` yeterince uzunsa, ilk zemin durumunun zamana bağlı benzetim süresi boyunca Hamiltonian 'nin anlık bir durumunun kaldığını ve bu nedenle son Hamiltonian 'in baş durumunda bittiğini unutmayın.

Ayrıca tipik bir hisse ansız deneme denemesinin tüm adımlarını otomatik olarak gerçekleştiren yararlı bir işlem de tanımladık. Örneğin, Adiabatik durum hazırlığı tarafından üretilen durumun enerji tahminini döndüren aşağıda verilmiştir:

```qsharp
operation AdiabaticStateEnergyEstimate( 
    nQubits : Int, 
    statePrepUnitary: (Qubit[] => Unit),
    adiabaticUnitary: (Qubit[] => Unit),
    qpeUnitary: (Qubit[] => Unit is Adj + Ctl),
    phaseEstAlgorithm : ((DiscreteOracle, Qubit[]) => Double)) 
    : Double {
...
}
```

`nQubits`, ilk hisse durumu kodlamak için kullanılan qubits sayısıdır. `statePrepUnitary` başlangıç durumunu hesaplama tabanlı $ \ket{0\cnoktalar 0} $ ' dan hazırlar. `adiabaticUnitary`, `InterpolatedEvolution` işlevi tarafından üretilen Adiabatik durum hazırlanmasını uygulayan Unitary işlemidir. `qpeUnitary`, sonuçta elde edilen hisse için aşama tahmini gerçekleştirmek üzere kullanılan Unitary işlemidir. `phaseEstAlgorithm`, aşama tahmini algoritması seçimimize ait.

> [!TIP]
> Adiabatik durum hazırlığının uygulamaları örneklerde ele alınmıştır. `AdiabaticEvolution` işlevi kullanılarak Adiabatik durum hazırlığının el ile uygulanmasını kullanan, şaşırtıcı model için lütfen [ **Adiabaticfon** örneğine](https://github.com/microsoft/Quantum/tree/master/samples/simulation/ising/adiabatic)bakın.
> Şaşırtıcı modelde aşama tahmini ve Adiabatik durum hazırlığı için lütfen [ **ıingphasetahmine** örnek](https://github.com/microsoft/Quantum/tree/master/samples/simulation/ising/phase-estimation)bölümüne bakın.

> [!TIP]
> [Molesel Hydrogen benzetimi](https://github.com/microsoft/Quantum/tree/master/samples/simulation/h2/command-line) , ilginç bir ve kısa bir örnektir. $ [Malley et. Al](https://arxiv.org/abs/1512.06860) içinde bildirilen model ve deneysel sonuçlar. yalnızca Pauli matrislerini gerektirir ve $ \hat H = g\_{0}ı\_0I\_1 + g\_1 {Z\_1} + g\_2 {Z\_1} + g\_3 {Z\_0} {Z\_1} + g\_4 {Y\_0} {Y\_1} + g\_5 {X\_0} {X\_1} $. Bu geçerli bir Hamiltonian yalnızca yalnızca 2 qubit gerektirir; burada $g $ sabitleri, iki Hydrogen alar arasında $R $ ile hesaplanır. Canon işlevleri kullanılarak Paulıs, unitcihazlarına dönüştürülür ve sonra da Trour-Suzuki ayrıştırma kullanılarak kısa süreler üzerinde bulunur. $H _2 $ zemin durumunun bir önemi, Adiabatik durum hazırlığı kullanılmadan oluşturulabilir ve bu nedenle, Canon 'nin aşama tahmininden yararlanarak doğrudan devlet enerjisi bulunabilir.

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

$A $ ve $N $ $ $a < N $, burada bulma sırası olarak da adlandırılan, bulma dönemi hedefi $r $ mod $a _$ $N $_ $r $, $a $ $. \equ1 \Text{mod} N $ gibi en az pozitif tamsayı olacak şekilde tanımlanır.  

Bir hisse bilgisayarı kullanarak siparişi bulmak için şu Unitary işlecine uygulanan aşama tahmini algoritmasını kullanabiliriz $U _a $: $ $ U_a \ket{x} \equteket{(AX) \Text{mod} N}. $ $ $U _a $ öğesinin eigenvektörler tamsayı $s $ ve $0 \ LEQ s \leq r-$1, $ $ \ket{x_s} \equ1/\sqrt{r} \sum\_{k = 0} ^ {r-1} e ^ {\frac{-2\pı i SK} {r}} \ket{a ^ k\text {mod} N}, $ _$, $U_ _a $.
$U _a $ ' nin eigenvalues değeri $ $ U\_a \ket{x\_s} = e ^ {2 \ Pi i s/r} \ket{x\_s}. $$

Bu nedenle, aşama tahmini, $s/r $ ' den [devam eden kesirleri](https://en.wikipedia.org/wiki/Continued_fraction) kullanarak $r $ tarafından verimli bir şekilde öğrenildiği ^ {2 \ Pi i s/r} $ $e eigenvalues verir.

Hisse dönemi bulma için devre diyagramı:

![](./../../media/QPE.svg)

Burada $2n $ qubit $ \tus{0}$ olarak başlatılır $n ve $ qubits, $ \gre{1}$ olarak başlatılır.
Okuyucu yeniden, eigenstates 'i tutmak üzere hisse kayıt 'nın $ \tus{1}$ olarak başlatıldığını merak edebilir.
Bir biri $r $ sırasını önceden değil, aslında $ \ket{x_s} $ durumlarını doğrudan hazırlayamıyoruz.
Luckily, bu $1/\ sqrt {r} \sum\_{s = 0} ^ {r-1} \ket{x\_s} = \tus{1}$ öğesini kapatır.
Gerçekten $ \ket{x} $ ' i hazırlamak zorunda değildir.
$N $ qubits 'in, State $ \tus{1}$ içinde yalnızca bir hisse kayıt hazırlayabiliriz. 

Devre, QFT ve çeşitli kontrollü kapıları içerir.
QFT kapısı [daha önce](xref:microsoft.quantum.libraries.standard.algorithms)açıklanmıştı.
Denetim qubit $ \tus{1}$ ise ve $ \ket{x} $ ' i $ \ket{x} $ ' e eşler $ \ket{x} $ ' a $ _a $U

$ (A ^ NX) \Text{mod} N $ ' ı elde etmek için, yalnızca $a ^ n \Text{mod} N $ sınıfındaki $U.  
Bu tür Modüler aritmetik elde etme devrelerine [, özellikle](./algorithms.md#arithmetic)de denetlenen-$U\_{a ^ ı} $ işlemlerini uygulamak için modüler üs bir devreniz olması gerekir.

Yukarıdaki devre, [hisse miktarı tahminine](xref:microsoft.quantum.characterization.quantumphaseestimation) karşılık gelir ve açıkça sıra bulma imkanı sağladığından, gereken qubits sayısını azaltabiliriz. Beauregard 'in [, Arxıv: Quant-pH/, 5095v3 sayfa 8](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=8)' de açıklandığı gibi sipariş bulma yöntemini takip edebilir veya Microsoft. hisse. Canon ' de bulunan aşama tahmini yordamlardan birini kullanabilirsiniz. Örneğin, [sağlam aşama tahmini](xref:microsoft.quantum.characterization.robustphaseestimation) de bir ek qubit kullanır.
 
### <a name="factoring"></a>Düzenleme ###
Düzenleme 'in hedefi, $N $ tam sayı çarpanlarının belirlenmesi, burada $N $ bir $n $ bit sayıdır.  
Düzenleme, aşağıda açıklanan adımlardan oluşur. Adımlar üç parçaya ayrılır: klasik bir ön işleme yordamı (1-4); $a \Text{mod} N $ (5); sırasını bulmak için bir hisse bilgi işlem yordamı ve sıra (6-9) ile aynı ana faktörleri türetmede bir klasik özelleştirmediğiniz yordamı.

Klasik ön işleme yordamı aşağıdaki adımlardan oluşur:
1. $N $ çiftse, ana faktör $2 $ ' i döndürün.
2. $P \geq1 $, $q \geq2 $ için $N = p ^ q $, ana faktör $p $ döndürün.  Bu adım sınıf aracılığıyla yapılır.
3. $1 < N-$1 < $a rastgele bir sayı seçin.
4. $ \Text{GCD} (a, N) > 1 $ ise, $ \Text{GCD} (a, N) $ ana faktörünü döndürün. Bu adım Euclid 'nin algoritması kullanılarak hesaplanır.
Hiçbir ana faktör döndürülmezse, hisse için bu yordama devam ediyoruz:
5. $A \Text{mod} N $ öğesinin $r $ sırasını hesaplamak için hisse dönemi bulma algoritmasını çağırın. Ana faktörleri öğrenmek için klasik özelleştirmediğiniz yordamında $r $ kullanın:
6. $R $ tek ise, ön işleme adımına geri dönün (3).
7. $R $ çift ve $a ^ {r/2} =-1 \ metin {mod} N $, ön işleme adımına geri dönün (3).
8. $ \Text{GCD} (bir ^ {r/2} + 1, N) $, $N $, return $ \Text{GCD} (a ^ {r/2} + 1, N) $ olan önemsiz olmayan bir faktördür.
9. $ \Text{GCD} (a ^ {r/2}-1, N) $, $N $, return $ \Text{GCD} (a ^ {r/2}-1, N) $ olan basit olmayan bir faktördür.


Düzenleme algoritması dayalı: en az bir yarısı, $r $ 'nin eşit olduğu $a ve ^ {r/2} \neq-1 \ Text{mod} N $, bu nedenle de asal bir faktör üreten bir yarı olasılık ile gösterilmiştir.  (Daha fazla bilgi Için bkz. [Shor 'ın özgün kağıdına](https://doi.org/10.1109/SFCS.1994.365700) veya [daha fazla bilgi için](xref:microsoft.quantum.more-information)içindeki *temel hisse bilgi işlem* metinlarından biri).
Bir asal faktör döndürülmezse, (1) adımından algoritmayı tekrarlıyoruz.  $N $ deneme sonrasında, her girişim başarısız olma olasılığı en fazla $2 ^ {-n} $ olur.
Bu nedenle, algoritmayı tekrarladıktan sonra çok az sayıda başarı oluşur.
