---
title: 'Q # API tasarım Ilkeleri'
description: 'Q # API tasarım Ilkeleri'
author: cgranade
ms.author: chgranad
ms.date: 3/9/2020
ms.topic: article
uid: microsoft.quantum.contributing.api-design
ms.openlocfilehash: 03c32331f8988181ec6fedcfc207d752b4a880b2
ms.sourcegitcommit: d61b388651351e5abd4bfe7a672e88b84a6697f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/10/2020
ms.locfileid: "79024211"
---
# <a name="q-api-design-principles"></a>Q # API tasarım Ilkeleri

## <a name="introduction"></a>Giriş

Bir dil ve platform olarak, soru-cevap kullanıcılara hisse, çalışma, anlama ve bilgi edinme
Kullanıcılara güç sağlamak için, Q # kitaplıklarını tasarlarken, tasarımlarımıza kılavuzluk eden bir API tasarım ilkeleri kümesi izler ve hisse geliştirme topluluğu için kullanılabilir kitaplıklar oluşturmamıza yardımcı olun.
Bu makalede bu ilkeler listelenmekte ve soru-cevap API 'Leri tasarlarken nasıl uygulanabilmenize yardımcı olacak örnekler verilmektedir.

> [!TIP]
> Bu, kitaplık geliştirme ve ayrıntılı kitaplık katkılarına kılavuzluk eden oldukça ayrıntılı bir belgedir.
> Büyük olasılıkla, Q # ' da kendi kitaplıklarınızı yazıyorsanız veya [q # kitaplıkları deposuna](https://github.com/microsoft/QuantumLibraries)daha büyük Özellikler katkıdıysanız en çok yararlı bulacaksınız.
>
> Öte yandan, hisse geliştirme paketine daha genel katkıda bulunma hakkında daha fazla bilgi edinmek istiyorsanız, [katkı Kılavuzu](xref:microsoft.quantum.contributing)' nu kullanmaya başladık.
> Q # kodunuzun biçimlendirilmesini nasıl önerdiğimiz hakkında daha genel bilgiler arıyorsanız, [Stil kılavuzunu](xref:microsoft.quantum.contributing.style)kullanıma almak isteyebilirsiniz.

## <a name="general-principles"></a>Genel Ilkeler

**Anahtar ilkesi:** , Odağı hisse. uygulamalara yerleştiren API 'Leri kullanıma sunun.

- ✅ **,** algoritmaların ve uygulamaların üst düzey yapısını yansıtan işlem ve işlev adlarını seçin.
- ⛔️ birincil olarak alt düzey uygulama ayrıntılarına odaklanarak API 'Leri kullanıma **sunmayın** .

**Anahtar ilkesi:** API 'Lerin kullanım için sezgisel olduğundan emin olmak için her API tasarımını örnek kullanım durumları ile başlatın.

- ✅ **,** başlangıçtan itibaren tüm olası kullanımlar için tasarlamayı denemek yerine ortak bir API 'nin her bileşeninin karşılık gelen bir kullanım örneğine sahip olduğundan emin olun.
    Farklı bir şekilde, yararlı olmaları durumunda ortak API 'Ler oluşturmayın, ancak bir API 'nin her bölümünün yararlı olacağı *somut* bir örneğe sahip olduğundan emin olun.

  *Örnekler*
  - @"microsoft.quantum.canon.applytoeachca", çok sayıda hisse algoritmasında ortak bir görev olan tek bir üst konum durumunda Yazmaçları hazırlamak için `ApplyToEachCA(H, _)` olarak kullanılabilir. Aynı işlem, hazırlık, sayı ve Oracle tabanlı algoritmalarda birçok diğer görev için de kullanılabilir.

- ✅, beyin **Fırtınmlarını** ve yeni API tasarımlarını kullanarak, sezgisel olduğunu ve önerilen kullanım durumlarını karşıladıklarından emin olun.

  *Örnekler*
  - Yeni API tasarımlarının mevcut uygulamaları nasıl basitleştireceğinizi ve açıklanmadığını görmek için geçerli Q\# kodunu inceleyin.
  - Birincil hedef kitleleri temsilcileriyle önerilen API tasarımlarını gözden geçirin.

**Anahtar ilkesi:** Okunabilir kodu desteklemek ve teşvik etmek için API 'Ler tasarlayın.

- ✅ **,** kodun etki alanı uzmanları ve uzman olmayanlar tarafından okunabilir olmasını sağlamaktır.
- ✅, uygulama ayrıntılarını uygun şekilde Delve altına almak için belgeleri kullanarak her bir işlemin ve yüksek düzeyli algoritmadaki işlevin efektlerine **odaklanmanızı sağlar** .
- ✅ **,** uygun olan her durumda ortak [Q\# stil kılavuzunu](xref:microsoft.quantum.contributing.style) izleyin.

**Anahtar ilkesi:** API 'Leri kararlı olacak şekilde tasarlayın ve ileriye dönük uyumluluk sağlayın.

- ✅ **,** önemli değişiklikler gerektiğinde eski API 'leri sorunsuz şekilde kullanımdan kaldırır.

- ✅ **,** mevcut kullanıcı kodunun kullanımdan kaldırma sırasında doğru çalışmasına izin veren "dolgu" işlemlerini ve işlevleri sağlar.

  *Örnekler*
  - `EstimateAverage``EstimateExpectation` adlı bir işlemi yeniden adlandırırken, var olan kodun doğru şekilde çalışmaya devam edebilmesi için yeni adında özgün işlemi çağıran `EstimateExpectation` adlı yeni bir işlem tanıtın.

- ✅ **, kullanıcıya kullanım dışı** Bırakıla iletmek için @"microsoft.quantum.core.deprecated" özniteliğini kullanır.

- bir işlemi veya işlevi yeniden adlandırırken ✅, `@Deprecated`için bir dize girişi olarak yeni bir **ad sağlayın.**

- ⛔️, önizleme sürümleri için en az altı aya veya desteklenen yayınlar için en az iki yıla kadar kullanım süresi olmadan mevcut işlevleri veya **işlemleri kaldırmayın.**

## <a name="functions-and-operations"></a>İşlevler ve Işlemler

**Anahtar ilkesi:** her işlev ve işlemin API içinde iyi tanımlanmış tek bir amaca sahip olduğundan emin olun.

- ⛔️, birden çok ilgisiz görevi gerçekleştiren işlevleri ve işlemleri **kullanıma sunmaz.**

**Anahtar ilkesi:** işlevleri ve işlemleri mümkün olduğunca yeniden kullanılabilir olacak şekilde tasarlayın ve gelecekteki ihtiyaçları tahmin edin.

- aynı API 'de ve daha önce var olan kitaplıklarda, diğer işlevler ve işlemlerle birlikte oluşturmak için **, tasarım işlevleri** ve işlemler ✅.

  *Örnekler*
  - @"microsoft.quantum.canon.delay" işlemi, kendi girişi hakkında en düşük varsayımlar yapar ve bu nedenle, her iki işlemin veya Kullanıcı tarafından tanımlanan uygulamaların uygulamalarını geciktirmek için kullanılabilir.
    <!-- TODO: define bad example. -->

- ✅ **işlemler** yerine işlev olarak yalnızca belirleyici klasik mantığı kullanıma sunar.

  *Örnekler*
  - Kayan nokta girişinin karelerinin ne kadar gerçekçi yazıldığını gösteren bir altyordam ve bu nedenle kullanıcıya işlem `Square : Double => Double`yerine `Squared : Double -> Double` olarak sunulmalıdır. Bu, alt yordamın daha fazla yerde (örneğin, diğer işlevlerin içinde) çağrılmasına izin verir ve derleyiciye performansı ve iyileştirmeleri etkileyebilecek yararlı iyileştirme bilgileri sağlar.
  - `ForEach<'TInput, 'TOutput>('TInput => 'TOutput, 'TInput[]) => 'TOutput[]` ve `Mapped<'TInput, 'TOutput>('TInput -> 'TOutput, 'TInput[]) -> 'TOutput[]`, belirleyici bir şekilde yapılan garantilere göre farklılık gösterir; her ikisi de farklı koşullarda yararlı olur.
  - Hisse alma işlemlerinin uygulamasını dönüştüren API yordamları, genellikle belirleyici bir biçimde gerçekleştirilebilir ve bu nedenle `CControlled<'T>(op : 'T => Unit) => ((Bool, 'T) => Unit)`gibi işlevler olarak kullanılabilir hale getirilebilir.

- ✅ **,** her bir işlev ve işlem için, gerektiğinde tür parametrelerini kullanarak giriş türünü genelleştirir.

  *Örnekler*
  - `ApplyToEach` en yaygın uygulaması olan `((Qubit => Unit), Qubit[]) => Unit`türü yerine tür `<'T>(('T => Unit), 'T[]) => Unit` vardır.

> [!TIP]
> Gelecekteki ihtiyaçları tahmin etmek önemlidir, ancak kullanıcılarınız için somut sorunları çözmenin de önemlidir.
> Bu nedenle bu temel prensibi, her zaman dikkatli bir değerlendirme gerektirir ve API 'Leri geliştirmekten kaçınmak için "Tıpkı büyük/küçük"

**Anahtar ilkesi:** öngörülebilir ve çağrılabilir amacını ileten işlevler ve işlemler için giriş ve çıkış türlerini seçin.

- ✅ **,** yalnızca bir arada kabul edildiğinde önemli olan giriş ve çıkışları mantıksal olarak gruplamak için demet türlerini kullanır. Bu durumlarda Kullanıcı tanımlı bir tür kullanmayı düşünün.

  *Örnekler*
  - Başka bir işlevin yerel en düşük değerleri çıktısını almak için bir işlev, `LocalMinima(fn : (Double -> Double), (left : Double, right : Double)) : Double` uygun bir imza olabileceği gibi, bir arama aralığının bir giriş olarak sınırlarını gerektirebilir.
  - Bir makine öğrenimi sınıflandırmasının bir türevi olan parametre kaydırma tekniğinin bir türevini tahmin etmeye yönelik bir işlem, hem kaydırılan hem de geriye doğru olmayan parametre vektörlerini giriş olarak alamaz. `(unshifted : Double[], shifted : Double[])` benzer bir giriş bu durumda uygun olabilir.

- giriş ve çıkış tanımlama alanlarındaki öğeleri farklı işlevler ve işlemler arasında tutarlı bir **şekilde ✅.**

  *Örnekler*
  - İki veya işlev ya da her biri bir döndürme açısı ve bir hedef qubit girişi olarak düşünüyorsa, bunların her giriş grubu için aynı sıralandıklarından emin olun. Diğer bir deyişle, `ApplyRotation(target : Qubit, angle : Double) : Unit is Adj + Ctl` ve `DelayedRotation(angle : Double, target : Qubit) : (Unit => Unit is Adj + Ctl)``ApplyRotation(angle : Double, target : Qubit) : Unit is Adj + Ctl` ve `DelayedRotation(angle : Double, target : Qubit) : (Unit => Unit is Adj + Ctl)` tercih eder.

**Anahtar ilkesi:** kısmi uygulama gibi Q\# dil özellikleriyle iyi çalışmak için işlevler ve işlemler tasarlayın.

- ✅ **giriş** dizklardaki öğeleri, en yaygın olarak uygulanan girdilerin önce gerçekleşmesi (yani, kısmi uygulamanın currying 'e benzer şekilde davranması) için.

  *Örnekler*
  - Kayan noktalı bir sayı ve bir qubit girişi olan bir işlem `ApplyRotation`, genellikle, `Qubit => Unit`türünde bir girişi bekleyen işlemlerle kullanım için ilk olarak kayan nokta girişi ile kısmen uygulanabilir. Bu nedenle, `operation ApplyRotation(angle : Double, target : Qubit) : Unit is Adj + Ctl` imzası
      kısmi uygulamayla en tutarlı şekilde çalışır.
  - Genellikle, bu kılavuz, tüm klasik verilerin giriş tanımlama grupları 'ndaki tüm qugeler öncesine yerleştirilmesi anlamına gelir, ancak iyi bir deneyim kullanır ve API 'nizin uygulamada nasıl çağrıldığını inceleyin.

## <a name="user-defined-types"></a>Kullanıcı tanımlı türler

**Anahtar ilkesi:** API 'leri daha açıklayıcı ve kullanımı kolay hale getirmenize yardımcı olması için Kullanıcı tanımlı türleri kullanın.

- ✅ **uzun** ve/veya karmaşık türler için yararlı bir toplu değer sağlamak üzere yeni kullanıcı tanımlı türler tanıtılmaktadır.

  *Örnekler*
  - Üç qubit dizi girişi olan bir işlem türünün genellikle giriş olarak alındığı veya çıkış olarak döndürüldüğü durumlarda, `newtype TimeDependentBlockEncoding = ((Qubit[], Qubit[], Qubit[]) => Unit is Adj + Ctl)` gibi bir UDT sağlar
      yararlı bir Özet sağlamaya yardımcı olabilir.

- ✅ **,** belirli bir temel türün yalnızca belirli bir anlamda kullanılması gerektiğini belirtmek için yeni kullanıcı tanımlı türler tanıtılmalıdır.

  *Örnekler*
  - Özellikle, klasik verileri bir hisse kaydına kodlayan bir işlem olarak yorumlanan bir işlem, Kullanıcı tanımlı bir tür `newtype InputEncoder = (Apply : (Qubit[] => Unit))`etiketlemek için uygun olabilir.

- ✅ **gelecek** genişletilebilirlik için izin veren adlandırılmış öğelerle Yeni Kullanıcı tanımlı türler (örneğin, gelecekte ek adlandırılmış öğeler içerebilen bir sonuç yapısı) tanıtılmaktadır.

  *Örnekler*
  - Bir işlem `TrainModel` çok sayıda yapılandırma seçeneği ortaya çıkardığı zaman, bu seçenekleri yeni bir `TrainingOptions` UDT olarak ortaya çıkarmak ve yeni bir işlev sağlamak `DefaultTrainingOptions : Unit -> TrainingOptions` kullanıcıların, kitaplık geliştiricilerinin yeni UDT öğelerini uygun şekilde eklemesine izin verirken, bu seçenekleri bir veya daha fazla.

- ✅ **,** Kullanıcı tanımlı yeni türler için adlandırılmış öğeleri, kullanıcıların doğru tanımlama grubu oluşturmayı bilmesini gerektirmek amacıyla tercih ediyor olarak bildirir.

  *Örnekler*
  - Kutupsal ayrıştırma sırasında karmaşık bir sayıyı temsil eden `newtype ComplexPolar = (Magnitude: Double, Argument: Double)` `newtype ComplexPolar = (Double, Double)`tercih edin.

**Anahtar ilkesi:** bilişsel yükün azaltılması ve kullanıcının ek kavramlar ve terminoloji öğrenmesini gerektirmeyen yollarla Kullanıcı tanımlı türleri kullanın.

- ⛔️, kullanıcının bir unsarmadan işlecini (`!`) sık kullanmasını gerektiren veya genellikle birden çok düzey sarmalama düzeyi gerektiren Kullanıcı tanımlı **türler sunmaz.** Olası risk azaltma stratejileri şunlardır:

  - Kullanıcı tanımlı bir türü tek bir öğe ile kullanıma sunmadığında, bu öğe için bir ad tanımlamayı göz önünde bulundurun. Örneğin, `newtype Encoder = (Qubit[] => Unit is Adj + Ctl)`için `newtype Encoder = (Apply : (Qubit[] => Unit is Adj + Ctl))` tercih edin.

  - Diğer işlevlerin ve işlemlerin "sarmalanmış" UDT örneklerini doğrudan kabul edebilmesini sağlama.

- ⛔️ **,** ek ifade sağlamadan yerleşik türleri yinelenen yeni kullanıcı tanımlı türler sunmaz.

  *Örnekler*
  - Bir UDT `newtype QubitRegister = Qubit[]` `Qubit[]`üzerinde ek ifade vermez ve bu nedenle, hiç bir avantaj olmadan kullanımı daha zordur.
  - UDT `newtype LittleEndian = Qubit[]`, temel kaydın nasıl kullanılacağını ve yorumlanacağını belgeler ve bu nedenle temel türü üzerinde ek ifade sağlar.

- ⛔️ **,** kesinlikle gerekli olmadığı takdirde erişimci işlevleri sunmaz;   Bu durumda adlandırılmış öğeleri kesin olarak tercih edin.

  *Örnekler*
  - Bir UDT `newtype Complex = (Double, Double)`oluştururken, `GetReal : Complex -> Double` ve `GetImag : Complex -> Double`işlevler sağlamak için tanımı `newtype Complex = (Real : Double, Imag : Double)` olarak değiştirmeyi tercih edin.

## <a name="namespaces-and-organization"></a>Ad alanları ve kuruluş

**Anahtar ilkesi:** her bir ad alanındaki işlevlerin, işlemlerin ve Kullanıcı tanımlı türlerin amacını açıkça ileten, tahmin edilen ve ad alanı adlarını seçin.

- ad alanlarını `Publisher.Product.DomainArea`**olarak ✅.**

  *Örnekler*
  - Hisse için Microsoft tarafından yayımlanan işlevler, işlemler ve UDTs, hisse geliştirme setinin hisse simülasyonu özelliğinin bir parçası olarak `Microsoft.Quantum.Simulation` ad alanına yerleştirilir.
  - `Microsoft.Quantum.Math`, Microsoft tarafından, matematik etki alanı alanıyla ilgili olan hisse geliştirme setinin bir parçası olarak yayımlanan bir ad alanını temsil eder.

- farklı sorun etki alanlarında kullanılması durumunda bile bu işlevselliği açıklayan bir ad alanına belirli işlevler için kullanılan işlemler, işlevler ve Kullanıcı tanımlı **türler ✅.**

  *Örnekler*
  - Hisse geliştirme setinin bir parçası olarak Microsoft tarafından yayımlanan durum hazırlama API 'Leri `Microsoft.Quantum.Preparation`içine yerleştirilir.
  - Hisse geliştirme seti 'nin bir parçası olarak Microsoft tarafından yayımlanan hisse simülasyonu API 'Leri `Microsoft.Quantum.Simulation`içine yerleştirilir.

- ✅ **işlemleri** , işlevleri ve yalnızca belirli etki alanlarında kullanılan Kullanıcı tanımlı türler, yardımcı programları olan ad alanları için kullanılır. Gerekirse, etki alanına özgü her ad alanı içinde odaklanmış görevleri belirtmek için alt ad alanlarını kullanın.

  *Örnekler*
  - Microsoft tarafından yayımlanan hisse makine öğrenimi kitaplığı, büyük ölçüde @"microsoft.quantum.machinelearning" ad alanına yerleştirildi, ancak örnek veri kümeleri @"microsoft.quantum.machinelearning.datasets" ad alanı tarafından sağlanır.
  - Hisse uygun olarak Microsoft tarafından yayımlanan hisse uyumlu API 'Leri, hisse geliştirme seti 'nin bir parçası olarak `Microsoft.Quantum.Chemistry`yerleştirilmelidir. Ürdün--Wigner ayrıştırma işlevinin uygulamaya özgü işlevselliği `Microsoft.Quantum.Chemistry.JordanWigner`yerleştirilebilecek ve bu sayede hisse dili Mistry etki alanı alanının birincil arabiriminin uygulamalarla ilgilenmemesi sağlanır.

**Anahtar ilkesi:** Kullanıcılara sunulan API yüzeyine bilerek yönelik olarak ad alanlarını ve erişim değiştiricilerini kullanın ve API 'lerinizi uygulamayla ve test etme ile ilgili dahili ayrıntıları gizleyin.

- Her ne kadar ✅ **, uygulanan** API ile aynı ad ALANıNA bir API uygulamak için gereken tüm işlevleri ve işlemleri, ancak bir KITAPLıĞıN ortak API yüzeyinin bir parçası olmadığını belirtmek için "özel" veya "iç" anahtar sözcükleriyle işaretlenir. Özel ve iç işlemleri ve işlevleri ortak callables 'den görsel açıdan ayırt etmek için alt çizgiyle başlayan bir ad kullanın (`_`).

  *Örnekler*
  - `_Features` işlem adı, belirli bir ad alanı ve derleme için özel bir işlevi belirtir ve `internal` anahtar kelimesiyle birlikte gelmelidir.

- belirli bir ad alanı için API 'YI uygulamak üzere çok sayıda özel işlev veya işlemin gerekli olduğu nadir bir durumda ✅, bunları, uygulanan ad alanıyla eşleşen ve `.Private`biten yeni bir ad **alanına yerleştirin.**

- ✅ **,** tüm birim testlerini test ve `.Tests`bitiş altındaki ad alanıyla eşleşen ad alanlarına yerleştirir.

## <a name="naming-conventions-and-vocabulary"></a>Adlandırma kuralları ve sözlük

**Anahtar ilkesi:** NET, erişilebilir ve farklı bir hedef kitle genelinde okunabilir olan adları ve terminolojiyi, hem hisse nunovıces hem de uzmanlar dahil olmak üzere seçin.

- ⛔️ Discriminatory veya exclusionary tanımlayıcı adlarını veya API belge açıklamalarındaki **terminolojiyi kullanmayın.**

- ✅ **,** özellikle daha zor kavramlar için ilgili bağlam, örnek ve başvuruları sağlamak üzere API belge açıklamalarını kullanır.

- ⛔️ gereksiz esoteric olan veya okumak için önemli hisse algoritmaları bilgisi gerektiren tanımlayıcı **adlarını kullanmayın.**

  *Örnekler*
  - "Genver yineleme" olarak "genonu yineleme" olarak tercih edin.

- ✅ **,** bir çağrılabilir uygulamanın amaçlanan etkisini açıkça iletme, uygulama değil, işlem ve işlev adlarını seçin. Uygulamanın şu şekilde olabileceğini ve olması gerektiğini unutmayın

  *Örnekler*
  - "Hadamard test" için "tahmini örtüşme" yı tercih edin, ikincisi ise eski 'ın nasıl uygulandığını iletir.

- ✅ **Tüm** Q\# API 'lerinde tutarlı bir şekilde sözcükleri kullanın:

  - **Eylemlerinin**

    - Onay **: büyük**olasılıkla fiziksel olmayan kaynakları kullanarak bir hedef makinenin ve qubits 'in durumu hakkında bir varsayım olduğunu denetleyin. Bu fiili kullanan işlemler, kitaplıkların ve yürütülebilir programların işlevselliğini etkilemeden her zaman güvenli bir şekilde kaldırılabilir. Olguların aksine, genel olarak, bir qubit kayıt durumu, yürütme ortamı veya benzeri bir durum gibi, genel olarak, onaylar genel olarak değişebilir. Dış durum bağımlılığı bir tür yan etkildir, ancak onaylar işlevler yerine işlemler olarak gösterilmelidir.

    - **Tahmin**: bir veya daha fazla tekrarlanmış ölçüm kullanarak, ölçüm sonuçlarından bir klasik miktarı tahmin edin.

      *Örnekler*
      - @"microsoft.quantum.characterization.estimatefrequency"
      - @"microsoft.quantum.characterization.estimateoverlapbetweenstates"

    - **Hazırlama**: belirli bir başlangıç durumunda (genellikle $ \ket{00\cnoktalar 0} $) başlayan bir veya daha fazla qubits 'e bir hisse veya işlem dizisi uygulayın, bu qubits 'in durumunun istenen bir bitiş durumuna gelişmesine neden olur. Genel olarak, verili **başlangıç durumundan farklı** durumlara göre işlem, tanımsız bir Unitary dönüştürmesi ile sonuçlanabilir, ancak yine de bir işlemin ve kendi adjoint "iptal etmeyi" ve hiçbir op **uygulamamalıdır** .

      *Örnekler*
      - @"microsoft.quantum.preparation.preparearbitrarystate"
      - @"microsoft.quantum.preparation.prepareuniformsuperposition"

    - **Measure**: bir veya daha fazla qubits 'e bir hisse veya işlem dizisi uygulayarak klasik veri geri alma işlemini okuyun.

      *Örnekler*
      - @"microsoft.quantum.intrinsic.measure"
      - @"microsoft.quantum.arithmetic.measurefxp"
      - @"microsoft.quantum.arithmetic.measureinteger"

    - **Uygula**: bir veya daha fazla qubits 'e hisse veya işlem dizisi uygulayın ve bu qubits 'in durumunun tutarlı bir şekilde değişmesine neden olur. Bu fiil, Q\# terminolojinin en genel fiildir **ve daha** belirli bir fiil daha doğrudan ilgili olduğunda kullanılmamalıdır.

  - **İsimler**:

    - **Olgu**: bir hedef makinenin, ortamının veya makine qubits 'in durumunda değil, yalnızca kendi girdilerine bağlı olan bir Boolean koşulu. Bir onaylama işlemi aksine, olgu yalnızca söz konusu olgusuna belirtilen *değerlere* duyarlıdır. Örnek:

      *Örnekler*
      - @"microsoft.quantum.diagnostics.equalityfacti": iki tamsayı girişi hakkında bir eşitlik olgusu temsil eder; giriş olarak girilen tamsayılar birbirlerine eşittir ya da başka bir program durumundan bağımsız olarak değildir.

    - **Seçenekler:** Bir işlev veya işleme "isteğe bağlı bağımsız değişkenler" gibi davranan, birkaç adlandırılmış öğe içeren bir UDT. Örnek:

      *Örnekler*
      - @"microsoft.quantum.machinelearning.trainingoptions" UDT, öğrenme oranı, Mini toplu iş boyutu ve ML eğitimi için diğer yapılandırılabilir parametreler için adlandırılmış öğeler içerir.

  - **Sıfatlar**:

    - **Yeni**⛔️: Bu **sıfatıcı,** birçok programlama dilinde (ör.: C++, C#Java, TypeScript, PowerShell), kullanımıyla ilgili bir fiil olarak karışıklık oluşmasını önlemek için kullanılmamalıdır.

  - **Ön pozisyonlar:** Bazı durumlarda, işlev ve işlem adlarında isimler ve fiillerin rollerini daha fazla netleştirmek veya netleştirmek için ön pozisyonlar kullanılabilir. Bununla birlikte, dikkatli ve tutarlı şekilde yapılması gerekir.

    - **Şöyle:** Bir işlevin giriş ve çıktısının aynı bilgileri temsil ettiğini, ancak çıktının özgün temsili yerine bu bilgileri bir *X* **olarak** temsil ettiğini temsil eder. Bu özellikle tür dönüştürme işlevleri için ortaktır.

      *Örnekler*
      - `IntAsDouble(2)` hem giriş (`2`) hem de çıkışın (`2.0`) aynı bilgileri temsil ettiğini, ancak bunu yapmak için farklı Q\# veri türlerini kullandığını gösterir.

    - **Kimden:** Tutarlılığı sağlamak için bu ön pozisyon, tür dönüştürme işlevlerini veya uygun **olduğu yerde başka** bir durumu belirtmek **için kullanılmamalıdır.**

    - ⛔️ **:** bu ön pozisyon, birçok programlama dilinde fiil olarak kullanımıyla ilgili karışıklık olmaması **için kullanılmamalıdır.**
