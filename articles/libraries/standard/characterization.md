---
title: 'Q # standart kitaplıklar-karakter ayırma | Microsoft Docs'
description: 'Q # standart kitaplıkları-karakter ayırma'
author: QuantumWriter
uid: microsoft.quantum.libraries.characterization
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 1eb48da9d4ae2a730019e2707dcb2c69b998491e
ms.sourcegitcommit: 27c9bf1aae923527aa5adeaee073cb27d35c0ca1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74864381"
---
# <a name="quantum-characterization-and-statistics"></a>Hisse ve Istatistik #

Yararlı hisse algoritmaları geliştirmek için işlemlerin etkilerini niteleyen kritik öneme sahiptir.
Bu, bir hisse sisteminin her ölçümü en fazla bir bilgi elde ettiği için bu zor bir değer.
Bir eigenvalue öğrenmek için, tek başına bir hisse alım durumunda, kullanıcının bu kavramları temsil etmek için gereken pek çok bilgi bitini bir araya getirmek için birçok ölçüm sonucunun birlikte kullanılması gerekir.
Her [şey, bu](xref:microsoft.quantum.concepts.pauli#the-no-cloning-theorem) durum kopyasının tek bir kopyasından rastgele bir hisse alım durumu öğrenmenin bir yolu olmadığını ve bu nedenle durumun kopyalarını oluşturmanıza olanak sağladığından, hisse alma işlemleri özellikle sanal olarak kullanılır.
Bu hisse Sayın Kullanıcı tarafından bu şekilde gösterilmesi, Q # ' ın sergilemeyeceği veya hatta *bir durumun hisse* için ne kadar bir durum olduğunu belirtmeyeceğine göre yansıtılır.
Bu nedenle, işlemleri ve durumları siyah kutu olarak düşünerek hisse uygun hale getirme yaklaşıyoruz; Bu yaklaşım, hisse uygun, doğrulama ve doğrulamanın (QCVV) deneysel uygulaması ile ortak olarak çok daha yaygın bir şekilde paylaşır.

Daha önce ele alınan diğer kitaplıkların birçoğu karakter ayırma farklıdır.
Burada, bir durum vektörü üzerinde Unitary dönüştürmesi gerçekleştirmek yerine, sistem hakkında klasik bilgilerin öğrenmesinin daha az olması gerekir.
Bu kitaplıkların bu nedenle hem klasik hem de hisse bilgisi işlemesini Blend gerekir.


## <a name="iterative-phase-estimation"></a>Yinelemeli aşama tahmini ##

Hisse kullanım açısından hisse programlama, hisse miktarı tahmini için yararlı bir alternatif önerir.
Diğer bir deyişle, bir $n $-qubit kaydı hazırlamak yerine, aşamanın, hisse alma tahminiyle aynı şekilde bir ikili temsilini içermesi için, bir *Klasik* aracının ölçümler aracılığıyla bir hisse alma sisteminin özelliklerini öğrendiği işlem olarak görüntüleyebiliriz.
Bir siyah kutu işleminin uygulamalarını bilinmeyen bir açıda bir değere dönüştürmek için KickBack öğesini kullanarak ücretlendiriyoruz, ancak dönüşün hemen ardından her adımda döndürtiğimiz ansınla quge 'yı ölçecek.
Bu, her adımın bir yinelemeli bir şekilde açıklandığı aşamayı daha sonra öğrendiğimiz için, bu aşamada yalnızca bir adet ek qubit olması gereken avantajdan yararlanır.  
Aşağıda önerilen yöntemlerin her biri, aşamayı öğrenmek için denemeleri ve farklı veri işleme yöntemleri tasarlamak üzere farklı bir strateji kullanır.  Bunların her biri, ciddi bir hata sınırlarına sahip olmanın, önceki bilgileri birleştirme, hataları tolerans veya bellek için kabul edilen klasik bilgisayarlarda çalıştırma yeteneklerine kadar benzersiz bir avantajı vardır.

Yinelemeli aşama tahminlerini tartışmak için, bir siyah kutu işlemi olarak verilen bir Unitary $U $ ' i düşüneceğiz.
[Veri yapılarında](xref:microsoft.quantum.libraries.data-structures)Oracles 'daki bölümünde açıklandığı gibi, Q # canon, <xref:microsoft.quantum.oracles.discreteoracle> tanımlama grubu türü tarafından tanımlanan Kullanıcı tanımlı türe göre bu işlemleri modelleyerek `((Int, Qubit[]) => Unit : Adjoint, Controlled)`.
`U : DiscreteOracle`, `U(m)` $U, `m : Int`için ^ m $ uygular.

Bu tanım söz konusu olduğunda, yinelemeli aşama tahmininin her adımı, $ \ket{+} $ durumunda bulunan bir avılcal qubit, $U (m) $ ' nin [eigenvector](xref:microsoft.quantum.concepts.matrix-advanced) ' i olduğunu varsaydığımız ilk durum olan $ \ket{\phi} $, ör. $U (m) \ket{\phi} = e ^ {im\phi} \ demet {\ Fi} $.  
Daha sonra, $ \left (R\_1 (m \ Fi) \ket{+} \right) \ket{\phi} $ durumunu hazırlayan `U(m)` denetimli bir uygulaması kullanılır.
Hisse Vada olduğu gibi, Oracle `U(m)` denetimli bir uygulamanın etkisi, $ \ket{+} $ üzerinde bilinmeyen aşama için $R _1 $ ' ı uygulamanın etkileriyle aynı şekilde (Bu daha basit bir biçimde $U $ ' nin etkilerini açıklayabilir).
İsteğe bağlı olarak, algoritma $ \ket{\psı} = \left (R\_1 (m [\phi-\teta]) \ket{+} \ right) \ket{\phi} $ $ değerini almak için $R _1 (-m\teta) $ ' ı uygulayarak denetim qubit ' i döndürür.
`U(m)` için denetim olarak kullanılan gıılcal, daha sonra tek bir klasik `Result`elde etmek için $X $ temelinde ölçülür.

Bu noktada, yinelemeli aşama tahmini aracılığıyla elde edilen `Result` değerlerinden aşamayı yeniden oluşturmak, klasik istatistiksel bir sorundur.
Sabit bir çıkarım yöntemi verildiğinde elde edilen bilgileri en üst düzeye çıkaran $m $ değerini bulmak, istatistikte yalnızca bir sorundur.
Bunu, bu klasik çıkarım sorununu çözmek için Q # Canon ' de sunulan istatistiksel algoritmaları tanımlamaya devam etmeden önce, bu işlemi bir teorik olarak, Bayema parametresi tahmin formalronu 'da, bir teorik olarak, bir teorik özelliği olan bir teorik düzeyde

### <a name="iterative-phase-estimation-without-eigenstates"></a>Idgenstates olmadan yinelemeli aşama tahmini ###

$U (m) \ket{\phi\_j} = e ^ {im\phi\_j} $ olduğunda, aşama tahmini süreci, hisse kazanç işleminin tek bir enerji eigenstate 'e doğru bir şekilde bir değer olarak sunulmasıdır.  Sonuç olarak, gözlemlenen `Result`üreten eigenstate, gözlenen bir durumdur.

Özellikle, tek bir adım, şu Unitary olmayan dönüştürmeyi bir durum olan \begin{hizalaması} \ sum_j \sqrt{\Pr (\fi\_j)} \ket{\fi\_j} \mapsto \sum\_j\frac {\ sqrt {\ PR (\fi\_) gerçekleştirir j)} \sqrt{\Pr (\text{Result} | \phi\_j)} \ket{\fi\_j}} {\sqrt{\Pr (\fi\_j) \sum\_j \Pr (\text{Result} | \fi\_j)}}.
\end{hizalaması} bu işlem birden çok `Result` değeri üzerinde yinelendiği için, $ \ prod_k \Pr (\text{Result}\_k | \fi\_j) $ değerlerinin maxhayvan değerleri olmayan eigenstates, katlanarak bastırılır.
Sonuç olarak, denemeleri düzgün şekilde seçildiyse, çıkarım işlemi tek bir eigenvalue ile duruma yakınsama eğilimi gösterir.

Bayes ' teoreminin, aşama tahmininizden elde edilen durumun \begin{hizalaması} \frac{\sqrt{\pr (\ph\_j)} \sqrt{\pr (\Text{Result} | \fi\_j)} \ket{\\_Fi biçiminde yazılmasını önerir. j}} {\sqrt{\pr (\phi\_j) \sum\_j \pr (\Text{Result} | \phi\_j)}} = \ sum_j \sqrt{\pr (\phi\_j | \Text{Result})} \ket{\fi\_j}.
\end{hizalaması} burada $ \Pr (\phi\_j | \text{Result}) $, verilen eigenstates hakkında her bir varsayıma sahip olmak için bir olasılık olarak yorumlenebilir:

1. ölçümden önceki hisse bilgisi hakkında bilgi,
2. $U $ ve ' nin eigendurumları hakkında bilgi
3. $U $ öğesinin eigenvalues hakkında bilgi.

Bu üç şeyi öğrenirken, klasik bir bilgisayarda genellikle üstel olarak çok daha zordur.
Aşama tahmini yardımcı programı, küçük bir ölçüde bu şekilde, bu tür bir hisse öğrenme görevinin hiçbirini bilmeden gerçekleştirebilmesinin farkında olmadan ortaya çıkar.
Bu nedene yönelik aşama tahmini, üstel hızlı bir şekilde bir dizi algoritmalarda bulunur.

### <a name="bayesian-phase-estimation"></a>Bayeme aşaması tahmini ###

> [!TIP]
> Uygulamada Bayeme aşaması tahmini hakkında daha fazla bilgi için lütfen [**Phasetahmine**](https://github.com/microsoft/Quantum/tree/master/samples/characterization/phase-estimation) örnek bölümüne bakın.

Bayeme aşaması tahmini fikri basittir.
Aşama tahmini protokolünden Ölçüm istatistiklerini toplar ve ardından Bayeme çıkarımı kullanarak sonuçları işleyin ve bir tahmin parametresi sağlayabilirsiniz.
Bu işleme, bu tahmine ilişkin kesin bir değer elde etmek için eigenvalue ve belirsizlik sağlar.
Ayrıca, uyarlamalı denemeleri gerçekleştirmenizi ve önceki bilgileri kullanmanızı da sağlar.
Yöntemlerin prendezavantajları, hesaplama açısından yoğun hale gelir.

Bu Bayete çıkarım işleminin nasıl çalıştığını anlamak için, tek bir `Zero` sonucunu işleme durumunu göz önünde bulundurun.
$X = \ket{+} \bra{+}-\tus{-}\bra{-}$, yani $ \ket{+} $, `Zero`öğesine karşılık gelen $X $ öğesinin tek pozitif eigenstate olduğunu unutmayın.
İlk qubit üzerindeki bir [`PauliX` ölçümü](xref:microsoft.quantum.concepts.pauli) için `Zero`, bu nedenle \begin{Equation} \pr (\Texttt{sıfırlaması} | \psı) = \left | \braket{+ | \psı} \right | ^ 2.
\end{Equation} yinelemeli aşama tahmini durumunda, $ \ket{\psı} = R_1 (d [\phi-\teta]) \ket{+} $, \begin{hizalaması} \Pr (\Texttt{sıfırlaması} | \fi; e, \teta) & = \left | \braket{+ | R_1 (d [\phi-\teta]) | +} \ sağ | ^ 2 \\\\ & = \left | \frac12 \left (\bra{0} + \bra{1} \ sağ) \left (\ayraç{0} + e ^ {i m [\phi-\teta]} \demet{1} \ sağ) \ doğru | ^ 2 \\\\ & = \left | \frac{1 + e ^ {i m [\phi-\teta]}}{2} \ Right | ^ 2 \\\\ & = \cos ^ 2 (m [\phi-\teta]/2) \tag{★} \label{EQ: Phase-EST-olasılık}.
\end{hizalaması} diğer bir deyişle, yinelemeli aşama tahmini, bir sinusoidal işlevinin salınlation sıklığını öğrenmeden ve bu sinusoıd tarafından verilen bir ölçüle bir para ile bir para alanı çevirmenize olanak tanır.
Geleneksel klasik terminolojiye göre, $ \eqref{EQ: Phase-EST-olasılık} $ yinelemeli aşama tahmini için *olasılık işlevini* çağırıyoruz.

Yinelemeli aşama tahmini olma olasılığı işlevinden bir `Result` gözlemleniyorsa, bu gözlemyi takip eden aşamayı görmek için Bayes ' kuralını kullanabiliriz.
Concreary, \begin{Equation} \Pr (\phi | d) = \frac{\Pr (d | \fi) \Pr (\fi)} {\int \Pr (d | \fi) \Pr (\fi) {\mathrm d} \phi} \Pr (\fi), \end{Equation} burada $d \\\{\Texttt{dd}, \texttt{One}\\} $ bir `Result`ve $ \Pr (\fi) $, önceki inanılmaz EFS 'yi $ \fi $ hakkında açıklar.
Bu durumda, posterior Distribution $ \Pr (\phi | d) $, inanılmaz EFS 'yi bir sonraki `Result`gözlemmize hemen açıklayacaktır.

Bu yordam sırasında herhangi bir noktada, klasik denetleyici tarafından gösterilen $ \hat{\phi} $ aşamasını \begin{Equation} \hat{\phi} \mathrel{olarak bildirebiliriz: =} \beklenir [\phi | \Text{Data}] = \int \phi \Pr (\phi | \Text{Data}) {\mathrm d} \phi, \end{Equation}; burada $ \Text{Data} $, elde edilen tüm `Result` değerlerinin tamamına karşılık gelir.

Tam Bayeme çıkarımı, uygulama ıntrackingtable içinde.
Bu Imagine, bir $n $ bit değişkeni $x $ öğrenmek istiyoruz.
Önceki dağıtım $ \Pr (x) $, $x $ değerinin $2 ^ n $ kuramsal değerlerini destekler.
Bu, $x $ tam olarak doğru bir tahmine ihtiyaç duyduğumuz için Bayeme aşaması tahmininde, yüksek bellek ve işlem süresine ihtiyaç duyabileceği anlamına gelir.
Örneğin, hisse kaybı benzetimi gibi bazı uygulamalar için, bu tür yöntemler, Shor 'ın algoritması gibi diğer uygulamaların, aşama tahmini adımı içinde tam Bayeduyma çıkarımı kullanamaz.  Bu nedenle, [rastgele yürüme aşaması Tahmini (RWPE)](xref:microsoft.quantum.research.randomwalkphaseestimation.randomwalkphaseestimation) gibi yaklaşık bayeme yöntemlerine ve ayrıca [sağlam aşama tahmini](xref:microsoft.quantum.characterization.robustphaseestimation)gibi baysuz olmayan yaklaşımlara yönelik uygulamalar sunuyoruz.

### <a name="robust-phase-estimation"></a>Sağlam aşama tahmini ###

Ölçüm sonuçlarından bir aşamanın tahmin edilmesi için en büyük *bir posteriori* bayeder yeniden oluşturma, en kötü durum durumunda üstel olarak zordur. Bu nedenle, en pratik aşama tahmin algoritmaları, daha sonra, polynomially ' nin yapılan ölçüm sayısıyla ölçeklendirirken, bir miktar klasik post işleme için Exchange 'de yeniden oluşturma işleminin bazı kalitesini Fede bırakmıştır.

Bu tür bir örnek, etkin bir klasik işleme sonrası adımı, imzası ve yukarıda bahsedilen girdileri olan [güçlü aşama tahmini algoritmasıdır](https://arxiv.org/abs/1502.02677). Giriş Unitary siyah kutularının $U $ `DiscreteOracle` tür olarak paketlendiğinizi varsayar ve bu nedenle yalnızca denetlenen-$U $ tamsayı üslerini sorgular. `Qubit[]` kaydındaki giriş durumu bir eigenstate $U \ket{\psı} = e ^ {i\phi} \ demet {\ PSI} $ ise, güçlü aşama tahmin algoritması, `Double`olarak $ \phi $ $ \phi $ $ \/Fi $ değerini döndürür.

En önemli kapsamlı aşama tahmini özelliği, diğer birçok yararlı çeşitlerle paylaşılır. $ \hat{\phi} $ öğesinin yeniden yapım kalitesi, bazı sense Heıenberg-Limited ' dir. Yani, $ \hat{\phi} $ değerinin gerçek değerden $ \sigma $ sapmasıdır, sonra $ \sigma $ ölçeklendirirken, denetlenen-$U $, yani $ \sigma = \mathcal{O} (1/Q) $ ' a yapılan toplam sorgu sayısı ile orantılı olarak $Q. Şimdi, sapma tanımı farklı tahmin algoritmaları arasında farklılık gösterir. Bazı durumlarda, en az $ \mathcal{O} (1) $ olasılık, tahmin hatası $ | \hat{\phi}-\phi | anlamına gelebilir.\_\circ\le \sigma $ on döngüsel bir ölçüde $ \circ $. Sağlam aşama tahmini için, sapma tam olarak $ \sigma ^ 2 = \mathbb{E}\_\hat{\phi} [(\mod\_{2 \ Pi} (\hat{\phi}-\phi + \pı)-\pi) ^ 2] $ fark edilir. Daha kesin olarak, güçlü aşama tahmininde standart sapma, ınekaliteleri karşılar $ $ \begin{hizalaması} 2,0 \pı/Q \ Le \ Sigma \le 2 \ pi/2 ^ {n} \le 10.7 \ Pi/Q, \end{hizalaması} $ $, asentotik büyük $Q $ sınırında alt sınıra ulaşıldığında ve üst sınır küçük örnek boyutları için de garanti edilir.  `bitsPrecision` giriş tarafından seçilen $n $ $Q $ örtülü olarak tanımlayan unutmayın.

İlgili diğer ayrıntılar, yalnızca $1 $ anileri La qubit 'in küçük alan ek yükünü ya da yordamın Uyarlamalı olduğu anlamına gelir. bu da, gerekli hisse denemeleri dizisi ara ölçü sonuçlarının bağımsızdır. Bu ve daha sonra, aşama tahmin algoritması seçiminin önemli olduğu durumlarda, biri @"microsoft.quantum.canon.robustphaseestimation" gibi belgelere ve daha fazla bilgi edinmek ve bunların uygulamalarına başvurmalıdır.

> [!TIP]
> Sağlam aşama tahmini kullanıldığı birçok örnek vardır. Çeşitli fiziksel sistemin zemin durumu enerji düzeyini çıkartarak aşama tahmini için, lütfen [ **H2 simülasyon** örneğine](https://github.com/microsoft/Quantum/tree/master/samples/simulation/h2/command-line), [ **simplefon** örneğe](https://github.com/microsoft/Quantum/tree/master/samples/simulation/ising/simple)ve [ **Hubbard model** örneğine](https://github.com/microsoft/Quantum/tree/master/samples/simulation/hubbard)bakın.


### <a name="continuous-oracles"></a>Sürekli Oracles ###

Ayrıca, Canon türü <xref:microsoft.quantum.oracles.continuousoracle>modellenen sürekli zamanlı Oracles izin vermek için yukarıda kullanılan Oracle modelinden genelleştireceğiz.
Tek bir Unitary işleci yerine $U $, $U (t) U (s) $ = $U (t + s) $ gibi $t \\mathbb{R} $ için bir Unitary işleçleri $U (t) $ olduğunu düşünün.
Bu, ayrık bir durumdur çünkü bazı bir fixed $ \delta t $ için $t = d\,\delta t $ kısıtlaması yaparak bir <xref:microsoft.quantum.oracles.discreteoracle> oluşturuyoruz.
[Stone 'ın Theokal](https://en.wikipedia.org/wiki/Stone%27s_theorem_on_one-parameter_unitary_groups), $U (t) = \exp (i H t) $ işleci, $H $, burada $ \exp $, [Gelişmiş matrislerde](xref:microsoft.quantum.concepts.matrix-advanced)açıklanan matris üstel.
$H \ket{\phi} = \phi \ket{\phi} $ gibi bir eigenstate $ \ket{\phi} $H $, ayrıca tüm $t $ için bir $U (t) $, \begin{Equation} U (t) \ket{\phi} = e ^ {ı \phi t} \ket{\phi}.
\end{Equation}

[Bayek\phase tahmini](#bayesian-phase-estimation) için ele alınan tam aynı analizler uygulanabilir ve bu daha genel Oracle modeli için olasılık işlevi tam olarak aynıdır: $ $ \pr (\Texttt{sıfırlaması} | \fi; t, \teta) = \cos ^ 2 \ Left (\frac{t [\fi-\teta]}{2}\ right).
$ $ Üstelik, $U $ bir dinamik oluşturucusunun simülasyonu ise, [Hamiltonian simülasyonu](xref:microsoft.quantum.libraries.applications#hamiltonian-simulation)gibi, $ \phi $ değerini enerji olarak yorumlarız.
Bu nedenle, sürekli sorgular ile aşama tahmini kullanmak, $t $ ' ın bir tamsayı olmasını gerektirerek denemeleri seçimimizi tehlikeye duymadan, [kupacules](https://arxiv.org/abs/quant-ph/0604193), [malzemeler](https://arxiv.org/abs/1510.03859) veya [alan](https://arxiv.org/abs/1111.3633v2) törlerinin sanal enerji yelpazesini öğrenmemizi sağlar.

### <a name="random-walk-phase-estimation"></a>Rastgele yürüme aşaması tahmini ###

Q #, yinelemeli aşama tahmininizden elde edilen veri kaydı üzerinde rastgele bir adım adım şekilde çalışan hisse kullanımı için tasarlanan Bayeme aşaması tahmini için yararlı bir yaklaşık yol sağlar.
Bu yöntem hem Uyarlamalı hem de tamamen belirleyici olduğundan, tahmini aşama $ \hat{\phi} $ içindeki hataların neredeyse en iyi şekilde ölçeklendirilmesine olanak tanır.

Protokol, önceki dağıtımın Gauss olduğunu varsayan yaklaşık bir Bayeme çıkarım yöntemi kullanır.
Bu Gauss varsayım, posterior farkını en aza indiren deneme için bir analitik formül kullanmamızı sağlar.
Daha sonra bu deneme sonucuna bağlı olarak, $ \phi $ ' ın tahminini, önceden belirlenen bir miktara göre kaydırır ve varyansı önceden belirlenen bir miktara küçültür.
Bu ortalama ve varyans, sonraki deneyinin $ \phi $ ' den önceki bir Gauss belirtmek için gereken tüm bilgileri verir.
Beklenmeyen ölçüm hatası sayısı veya bunun öncesinde başlangıçtaki uçlar üzerinde olan gerçek sonuç, bu yöntemin başarısız olmasına neden olabilir.
Geçerli ortalama ve standart sapmanın sistem için uygun olup olmadığını test etmek için denemeleri gerçekleştirerek hata durumundan kurtarır.
Aksi takdirde, algoritma izlenecek bir ters adım yapar ve işlem devam eder.
Geriye doğru ilerleyebilme özelliği, ilk önceki standart sapma inapropriately küçük olsa bile algoritmanın öğrenmesi için de izin verir.

## <a name="calling-phase-estimation-algorithms"></a>Aşama tahmini algoritmaları çağırma ##

Q # Canon ile birlikte sunulan her aşama tahmin işlemi, son tahmin $ \hat{\phi} $ ' i talep ettiğimiz kaliteyi doğru bir şekilde parametreleştirirken farklı bir giriş kümesi alır.
Bununla birlikte, bu çeşitli girişler ortak bir şekilde yaygın bir şekilde yapılır, bu da kalite parametrelerinin üzerindeki kısmi uygulama ortak bir imzaya neden olur.
Örneğin, sonraki bölümde ele alınan <xref:microsoft.quantum.characterization.robustphaseestimation> işlemi aşağıdaki imzaya sahiptir:

```qsharp
operation RobustPhaseEstimation(bitsPrecision : Int, oracle : DiscreteOracle, eigenstate : Qubit[])  : Double
```

`bitsPrecision` girişi `RobustPhaseEstimation`, `oracle` ve `eigenstate` ortak olduğundan benzersizdir.
Bu nedenle, **H2Sample**' de görüldüğü gibi bir işlem, bir kullanıcının rastgele bir aşama tahmin algoritmaları belirtmesini sağlamak için `(DiscreteOracle, Qubit[]) => Unit` form girişi ile yinelemeli bir aşama tahmin algoritması kabul edebilir:

```qsharp
operation H2EstimateEnergy(
    idxBondLength : Int, 
    trotterStepSize : Double,
    phaseEstAlgorithm : ((DiscreteOracle, Qubit[]) => Double)) 
: Double
```

Bu sayısız aşaması tahmin algoritmaları, hedef uygulama için en iyi seçimi yapmak üzere anlaşılması gereken farklı özellikler ve giriş parametreleri için iyileştirilmiştir. Örneğin, bazı aşama tahmin algoritmaları Uyarlamalı olur. Bu, gelecekteki adımların önceki adımların ölçüm sonuçlarıyla ilgili olarak daha önce kontrol edilebileceği anlamına gelir. Bazıları, siyah kutu Unitary Oracle 'ı rastgele gerçek üslere göre üslendirir ve diğerleri yalnızca tamsayı gücüne ihtiyaç duyar, ancak yalnızca bir aşama tahmin mod $2 \ PI $ ' ı çözümleyebilir. Bazıları pek çok yardımcı qubit gerektirir ve diğeri yalnızca bir tane gerektirir.

Benzer şekilde, rastgele yürüme aşaması tahmini, Canon ile sunulan diğer algoritmalarda çok benzer şekilde devam eder:

```qsharp
operation ExampleOracle(eigenphase : Double, time : Double, register : Qubit[]) : Unit
is Adj + Ctl {
    Rz(2.0 * eigenphase * time, register[0]);
}

operation BayesianPhaseEstimationCanonSample(eigenphase : Double) : Double {

    let oracle = ContinuousOracle(ExampleOracle(eigenphase, _, _));
    using (eigenstate = Qubit()) {
        X(eigenstate);
        // The additional inputs here specify the mean and variance of the prior, the number of
        // iterations to perform, how many iterations to perform as a maximum, and how many
        // steps to roll back on an approximation failure.
        let est = RandomWalkPhaseEstimation(0.0, 1.0, 61, 100000, 1, oracle, [eigenstate]);
        Reset(eigenstate);
        return est;
    }
}
```
