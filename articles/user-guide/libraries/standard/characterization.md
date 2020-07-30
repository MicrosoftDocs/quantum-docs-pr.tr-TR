---
title: Hisse ve istatistik
description: Aşamalarda bulunan Ölçüm istatistiklerinin, hisse harcamalarda elde edilen sonuç değerlerini tahmin etmek için nasıl kullanıldığını öğrenin.
author: QuantumWriter
uid: microsoft.quantum.libraries.characterization
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 9d763d11ef9c08cc0941cade217dbb2942ef4bf9
ms.sourcegitcommit: 2f4c637e194dc2b5d18539469ed37444e2800199
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/30/2020
ms.locfileid: "87436535"
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
[Veri yapılarında](xref:microsoft.quantum.libraries.data-structures)Oracles bölümünde açıklandığı gibi, Q # Canon, <xref:microsoft.quantum.oracles.discreteoracle> kayıt düzeni türü tarafından tanımlanan Kullanıcı tanımlı tür ile bu işlemleri modeller `((Int, Qubit[]) => Unit : Adjoint, Controlled)` .
`U : DiscreteOracle`Daha sonra, `U(m)` için $U ^ m $ uygular `m : Int` .

Bu tanım söz konusu olduğunda, yinelemeli aşama tahmininin her adımı, $ \ket{+} $ durumunda bir yardımcı qubit, $U (m) $ ' nin [eigenvector](xref:microsoft.quantum.concepts.matrix-advanced) ' i olduğunu varsaydığımız ilk durum olan $ \ket{\phi} $, ör. $U (m) \ket{\phi} = e ^ {im\phi} \ demet {\ Fi} $.  
Daha sonra kontrollü bir uygulama, `U(m)` $ \left (R \_ 1 (m \ Fi) \ket{+} \right) \ket{\phi} $ durumunu hazırlayan kullanılır.
Hisse vakine benzer şekilde, Oracle 'ın denetlenen uygulamasının etkisi, `U(m)` Bu daha basit bir şekilde $U $ ' in etkilerini anlayabilmemiz gibi, $ \ket{+} $ üzerinde bilinmeyen aşama için $R _1 $ ' ı uygulamanın etkileriyle aynı şekilde aynıdır.
İsteğe bağlı olarak, algoritma $ \ket{\psı} = \left (R \_ 1 (m [\phi-\teta]) \ket{+} \right) \ket{\phi} $ $ değerini elde etmek için $R _1 (-m\teta) $ değerini uygulayarak denetim qubit 'i döndürür.
Denetim olarak kullanılan yardımcı qubit, `U(m)` tek bir klasik elde etmek için $X $ temelinde ölçülür `Result` .

Bu noktada, `Result` yinelemeli aşama tahmini aracılığıyla elde edilen değerlerden aşamayı yeniden oluşturmak, klasik istatistiksel çıkarım sorunudur.
Sabit bir çıkarım yöntemi verildiğinde elde edilen bilgileri en üst düzeye çıkaran $m $ değerini bulmak, istatistikte yalnızca bir sorundur.
Bunu, bu klasik çıkarım sorununu çözmek için Q # Canon ' de sunulan istatistiksel algoritmaları tanımlamaya devam etmeden önce, bu işlemi bir teorik olarak, Bayema parametresi tahmin formalronu 'da, bir teorik olarak, bir teorik özelliği olan bir teorik düzeyde

### <a name="iterative-phase-estimation-without-eigenstates"></a>Idgenstates olmadan yinelemeli aşama tahmini ###

Eğer $U (m) \ket{\phi \_ j} = e ^ {im\phi \_ j} $ olduğunda, aşama tahmini süreci her bir enerji egeninin doğru şekilde hisse ansız bir şekilde rehberlik eden bir giriş durumu sağlanırsa  Son olarak, gözegenlerin oluşma olasılığı en yüksek olan eigenstate `Result` .

Özellikle, tek bir adım, şu Unitary olmayan dönüştürmeyi bir durum olan \begin{hizalaması} \ sum_j \sqrt{\Pr (\phi \_ j)} \ket{\phi \_ j} \mapsto \sum \_ j\frac {\ sqrt {\ PR (\phi \_ j)} \sqrt{\Pr (\text{Result} | \phi \_ j)} \ket{\phi \_ j}} {\sqrt{\pr (\phj \_ ) \Sum \_ j \pr (\Text{Result} | \phi \_ j)}}.
\end{hizalaması} bu işlem birden çok değer üzerinde yinelendiğinden `Result` , $ \ prod_k \Pr (\text{Result} \_ k | \phi j) $ değerinin maxhayvan değeri olmayan eigenstates, \_ katlanarak bastırılır.
Sonuç olarak, denemeleri düzgün şekilde seçildiyse, çıkarım işlemi tek bir eigenvalue ile duruma yakınsama eğilimi gösterir.

Bayes ' teoreminin, aşama tahmininizden elde edilen durumun \begin{hizalaması} \frac{\sqrt{\pr ( \_ \phj)} \sqrt{\pr (\Text{Result} | \_ \phj)} \ket{\biçiminde yazılmasını önerir. Phi \_ j}} {\sqrt{\pr (\phi \_ j) \sum \_ j \pr (\Text{Result} | \phi \_ j)}} = \ sum_j \sqrt{\pr (\phi \_ j | \Text{Result})} \ket{\phi \_ j}.
\end{hizalaması} burada $ \Pr (\phi \_ j | \text{Result}) $, verilen eigenstates hakkında her bir varsayıma neden olacağı olasılığını göz önüne alabilir:

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

Bu Bayete çıkarım işleminin nasıl çalıştığını anlamak için, tek bir sonucu işleme durumunu göz önünde bulundurun `Zero` .
$X = \ket{+} \bra{+}- {-} \tus\bra {-} $, örneğin $ \ket{+} $, öğesine karşılık gelen $X $ öğesinin tek pozitif eigenstate olduğunu unutmayın `Zero` .
`Zero`İlk qubit üzerinde bir [ `PauliX` ölçümü](xref:microsoft.quantum.concepts.pauli) bir giriş durumu olan $ \ket{\psi}\ket{\phi} $ için gözlemleme olasılığı, bu nedenle \begin{Equation} \Pr (\Texttt{dd} | \psı) = \left | \braket{+ | \psı} \ Right | ^ 2.
\end{Equation} yinelemeli aşama tahmini durumunda, $ \ket{\psı} = R_1 (d [\phi-\teta]) \ket{+} $, \begin{hizalaması} \Pr (\Texttt{sıfırlaması} | \fi; e, \teta) & = \left | \braket{+ | R_1 (d [\phi-\teta]) | +} \ Right | ^ 2 \\ \\ & = \left | \frac12 \left (\bra {0} + \bra {1} \ sağ) \left (\ket {0} + e ^ {ı. [\phi-\teta]} \ayraç {1} \ right) \ doğru | ^ 2 \\ \\ & = \ Left | \frac{1 + e ^ {i m [\phi-\teta]}} {2} \ Right | ^ 2 \\ \\ & = \cos ^ 2 (m [\phi-\teta]/2) \tag{★} \label{EQ: Phase-EST-olasılık}.
\end{hizalaması} diğer bir deyişle, yinelemeli aşama tahmini, bir sinusoidal işlevinin salınlation sıklığını öğrenmeden ve bu sinusoıd tarafından verilen bir ölçüle bir para ile bir para alanı çevirmenize olanak tanır.
Geleneksel klasik terminolojiye göre, $ \eqref{EQ: Phase-EST-olasılık} $ yinelemeli aşama tahmini için *olasılık işlevini* çağırıyoruz.

`Result`Yinelemeli aşama tahmini olasılığı işlevinden bir gözlemleniyorsa, bu gözlemyi takip eden aşamayı ne kadar düşünmemiz gerektiğini görmek Için Bayes kuralını kullanabiliriz.
Concreary, \begin{Equation} \Pr (\phi | d) = \frac{\Pr (d | \fi) \Pr (\fi)} {\int \Pr (d | \fi) \Pr (\fi) {\mathrm d} \phi} \Pr (\fi), \end{Equation} burada $d \in \\ {\Texttt{dd}, \texttt{One} \\ } $ bir `Result` ' dır ve $ \pr (\fi) $ hakkında önceki inanılmaz EFS 'yi $ \phi $ hakkında açıklar.
Böylece, posterior Distribution $ \Pr (\phi | d) $, bir sonraki gözlemmize hemen önce inanılmaz EFS 'yi tanımlar `Result` .

Bu yordam sırasında herhangi bir noktada, klasik denetleyici tarafından gösterilen $ \hat{\phi} $ aşamasını \begin{Equation} \hat{\phi} \mathrel{olarak bildirebiliriz: =} \beklenir [\phi | \Text{Data}] = \int \phi \Pr (\phi | \Text{Data}) {\mathrm d} \phi, \end{Equation}; burada $ \Text{Data} $, elde edilen tüm değerlerin tüm kayıtlarını temsil eder `Result` .

Tam Bayeme çıkarımı, uygulama ıntrackingtable içinde.
Bu Imagine, bir $n $ bit değişkeni $x $ öğrenmek istiyoruz.
Önceki dağıtım $ \Pr (x) $, $x $ değerinin $2 ^ n $ kuramsal değerlerini destekler.
Bu, $x $ tam olarak doğru bir tahmine ihtiyaç duyduğumuz için Bayeme aşaması tahmininde, yüksek bellek ve işlem süresine ihtiyaç duyabileceği anlamına gelir.
Örneğin, hisse kaybı benzetimi gibi bazı uygulamalar için, bu tür yöntemler, Shor 'ın algoritması gibi diğer uygulamaların, aşama tahmini adımı içinde tam Bayeduyma çıkarımı kullanamaz.  Bu nedenle, [rastgele yürüme aşaması Tahmini (RWPE)](xref:microsoft.quantum.research.characterization.randomwalkphaseestimation) gibi yaklaşık bayeme yöntemlerine ve ayrıca [sağlam aşama tahmini](xref:microsoft.quantum.characterization.robustphaseestimation)gibi baysuz olmayan yaklaşımlara yönelik uygulamalar sunuyoruz.

### <a name="robust-phase-estimation"></a>Sağlam aşama tahmini ###

Ölçüm sonuçlarından bir aşamanın tahmin edilmesi için en büyük *bir posteriori* bayeder yeniden oluşturma, en kötü durum durumunda üstel olarak zordur. Bu nedenle, en pratik aşama tahmin algoritmaları, daha sonra, polynomially ' nin yapılan ölçüm sayısıyla ölçeklendirirken, bir miktar klasik post işleme için Exchange 'de yeniden oluşturma işleminin bazı kalitesini Fede bırakmıştır.

Bu tür bir örnek, etkin bir klasik işleme sonrası adımı, imzası ve yukarıda bahsedilen girdileri olan [güçlü aşama tahmini algoritmasıdır](https://arxiv.org/abs/1502.02677). $U $ giriş Unitary siyah kutularının tür olarak paketlenildiği `DiscreteOracle` ve bu nedenle yalnızca denetlenen-$U $ tamsayı üslerini sorgulayan varsayılır. Kayıttaki giriş durumu `Qubit[]` bir egenstate $U \ket{\psı} = e ^ {i\phi} \ demet {\ PSI} $ ise, güçlü aşama tahmin algoritması bir tahmin $ \hat{\phi}\in [-\pi, \pı) $ değerini $ \phi $ olarak döndürür `Double` .

En önemli kapsamlı aşama tahmini özelliği, diğer birçok yararlı çeşitlerle paylaşılır. $ \hat{\phi} $ öğesinin yeniden yapım kalitesi, bazı sense Heıenberg-Limited ' dir. Yani, $ \hat{\phi} $ değerinin gerçek değerden $ \sigma $ sapmasıdır, sonra $ \sigma $ ölçeklendirirken, denetlenen-$U $, yani $ \sigma = \mathcal{O} (1/Q) $ ' a yapılan toplam sorgu sayısı ile orantılı olarak $Q. Şimdi, sapma tanımı farklı tahmin algoritmaları arasında farklılık gösterir. Bazı durumlarda, en az $ \mathcal{O} (1) $ olasılık, tahmin hatası $ | \hat{\phi}-\phi | \_ anlamına gelebilir. \circ\le \sigma $ bir dairesel ölçüde $ \circ $. Sağlam aşama tahmini için, sapma tam olarak $ \sigma ^ 2 = \mathbb{E} \_ \hat{\phi} [(\mod \_ {2 \ PI} (\hat{\phi}-\phi + \pi)-\pi) ^ 2] $, düzenli aşamaları tek sonlu bir Aralık $ (-\pı Daha kesin olarak, güçlü aşama tahmininde standart sapma, ınekaliteleri karşılar $ $ \begin{hizalaması} 2,0 \pı/Q \ Le \ Sigma \le 2 \ pi/2 ^ {n} \le 10.7 \ Pi/Q, \end{hizalaması} $ $, asentotik büyük $Q $ sınırında alt sınıra ulaşıldığında ve üst sınır küçük örnek boyutları için de garanti edilir.  $N $ seçili olduğunu belirten `bitsPrecision` $Q $ öğesini örtülü olarak tanımlayan unutmayın.

İlgili diğer ayrıntılar, yalnızca $1 $ anileri La qubit 'in küçük alan ek yükünü ya da yordamın Uyarlamalı olduğu anlamına gelir. bu da, gerekli hisse denemeleri dizisi ara ölçü sonuçlarının bağımsızdır. Bu ve daha sonra, aşama tahmin algoritması seçiminin önemli olduğu durumlarda, bir diğeri gibi belgelere @"microsoft.quantum.characterization.robustphaseestimation" ve ilgili yayınlar hakkında daha fazla bilgi ve uygulama için başvuru yapmanız gerekir.

> [!TIP]
> Sağlam aşama tahmini kullanıldığı birçok örnek vardır. Çeşitli fiziksel sistemin zemin durumu enerji düzeyini çıkartarak aşama tahmini için, lütfen [ **H2 simülasyon** örneğine](https://github.com/microsoft/Quantum/tree/master/samples/simulation/h2/command-line), [ **simplefon** örneğe](https://github.com/microsoft/Quantum/tree/master/samples/simulation/ising/simple)ve [ **Hubbard model** örneğine](https://github.com/microsoft/Quantum/tree/master/samples/simulation/hubbard)bakın.


### <a name="continuous-oracles"></a>Sürekli Oracles ###

Ayrıca, Canon türüne göre modellenen sürekli zamanlı Oracles izin vermek için yukarıda kullanılan Oracle modelinden genelleştireceğiz <xref:microsoft.quantum.oracles.continuousoracle> .
Tek bir Unitary işleci yerine $U $, $U (t) U (s) $ = $U (t + s) $ gibi $t \\mathbb{R} $ için bir Unitary işleçleri $U (t) $ olduğunu düşünün.
Bu, ayrık bir durumdur çünkü <xref:microsoft.quantum.oracles.discreteoracle> \, bazı bir fixed $ \delta t $ için $t = d \ Delta t $ ' ı kısıtlayarak bir oluşturabileceğiz.
[Stone 'ın Theokal](https://en.wikipedia.org/wiki/Stone%27s_theorem_on_one-parameter_unitary_groups), $U (t) = \exp (i H t) $ işleci, $H $, burada $ \exp $, [Gelişmiş matrislerde](xref:microsoft.quantum.concepts.matrix-advanced)açıklanan matris üstel.
$H \ket{\phi} = \phi \ket{\phi} $ gibi bir eigenstate $ \ket{\phi} $H $, ayrıca tüm $t $ için bir $U (t) $, \begin{Equation} U (t) \ket{\phi} = e ^ {ı \phi t} \ket{\phi}.
\end{Equation}

[Bayeduyma aşaması tahmini](#bayesian-phase-estimation) için ele alınan tam aynı analiz uygulanabilir ve bu daha genel Oracle modeli için olasılık işlevi tam olarak aynıdır: $ $ \pr (\Texttt{sıfırlaması} | \fi; t, \teta) = \cos ^ 2 \ Left (\frac{t [\phi-\teta]} {2} \right).
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
Örneğin, <xref:microsoft.quantum.characterization.robustphaseestimation> sonraki bölümde ele alınan işlem aşağıdaki imzaya sahiptir:

```qsharp
operation RobustPhaseEstimation(bitsPrecision : Int, oracle : DiscreteOracle, eigenstate : Qubit[])  : Double
```

`bitsPrecision`Giriş, `RobustPhaseEstimation` ,, `oracle` ve `eigenstate` ortak olarak benzersizdir.
Bu nedenle, **H2Sample**' de görüldüğü gibi bir işlem, `(DiscreteOracle, Qubit[]) => Unit` bir kullanıcının rastgele aşama tahmin algoritmaları belirtmesini sağlamak için formun bir girişi ile yinelemeli bir aşama tahmini algoritması kabul edebilir:

```qsharp
operation H2EstimateEnergy(
    idxBondLength : Int,
    trotterStepSize : Double,
    phaseEstAlgorithm : ((DiscreteOracle, Qubit[]) => Double))
: Double
```

Bu sayısız aşaması tahmin algoritmaları, hedef uygulama için en iyi seçimi yapmak üzere anlaşılması gereken farklı özellikler ve giriş parametreleri için iyileştirilmiştir. Örneğin, bazı aşama tahmin algoritmaları Uyarlamalı olur. Bu, gelecekteki adımların önceki adımların ölçüm sonuçlarıyla ilgili olarak daha önce kontrol edilebileceği anlamına gelir. Bazıları, siyah kutu Unitary Oracle 'ı rastgele gerçek üslere göre üslendirir ve diğerleri yalnızca tamsayı gücüne ihtiyaç duyar, ancak yalnızca bir aşama tahmin mod $2 \ PI $ ' ı çözümleyebilir. Bazıları çok sayıda yardımcı qubit gerektirir ve diğerleri yalnızca bir tane gerektirir.

Benzer şekilde, rastgele yürüme aşaması tahmini, Canon ile sunulan diğer algoritmalarda çok benzer şekilde devam eder:

```qsharp
operation ApplyExampleOracle(
    eigenphase : Double,
    time : Double,
    register : Qubit[])
: Unit is Adj + Ctl {
    Rz(2.0 * eigenphase * time, register[0]);
}

operation EstimateBayesianPhase(eigenphase : Double) : Double {
    let oracle = ContinuousOracle(ApplyExampleOracle(eigenphase, _, _));
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
