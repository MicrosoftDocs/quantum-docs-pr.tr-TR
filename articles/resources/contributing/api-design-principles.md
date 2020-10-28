---
title: Q# API tasarım Ilkeleri
description: Q# API tasarım Ilkeleri
author: cgranade
ms.author: chgranad
ms.date: 3/9/2020
ms.topic: article
uid: microsoft.quantum.contributing.api-design
no-loc:
- Q#
- $$v
ms.openlocfilehash: 6b196cf1be584a3157c7a9eb8cf497fe1121dd7a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691828"
---
# <a name="no-locq-api-design-principles"></a>Q# API tasarım Ilkeleri

## <a name="introduction"></a>Giriş

Bir dil ve platform olarak, Q# kullanıcılara hisse anları yazma, çalıştırma, anlama ve bunları keşfetmeye yönelik güç sağlar.
Kullanıcılara güç sağlamak için, kitaplıkları tasarlayacağız, Q# tasarımlarımıza kılavuzluk eden BIR API tasarım ilkeleri kümesi izledik ve hisse geliştirme topluluğu için kullanılabilir kitaplıklar oluşturmamıza yardımcı olun.
Bu makalede bu ilkeler listelenmekte ve API 'leri tasarlarken bunların nasıl uygulanacağını göstermeye yardımcı olacak örnekler verilmektedir Q# .

> [!TIP]
> Bu, kitaplık geliştirme ve ayrıntılı kitaplık katkılarına kılavuzluk eden oldukça ayrıntılı bir belgedir.
> Büyük olasılıkla, içinde kendi kitaplıklarınızı yazıyorsanız Q# veya [ Q# Kitaplıklar deposuna](https://github.com/microsoft/QuantumLibraries)daha büyük Özellikler katkısanız bile en yararlı bulacaksınız.
>
> Öte yandan, hisse geliştirme paketine daha genel katkıda bulunma hakkında daha fazla bilgi edinmek istiyorsanız, [katkı Kılavuzu](xref:microsoft.quantum.contributing)' nu kullanmaya başladık.
> Kodunuzun biçimlendirilmesini nasıl önerdiğimiz hakkında daha genel bilgiler arıyorsanız Q# , [Stil kılavuzunu](xref:microsoft.quantum.contributing.style)kullanıma almak isteyebilirsiniz.

## <a name="general-principles"></a>Genel Ilkeler

**Anahtar ilkesi:** , Odağı hisse. uygulamalara yerleştiren API 'Leri kullanıma sunun.

- ✅Algoritmaların ve uygulamaların üst düzey yapısını yansıtan işlem ve işlev **adlarını seçin.**
- ⛔️ birincil olarak alt düzey uygulama ayrıntılarına odaklanarak API 'Leri kullanıma **sunmayın** .

**Anahtar ilkesi:** API 'Lerin kullanım için sezgisel olduğundan emin olmak için her API tasarımını örnek kullanım durumları ile başlatın.

- ✅Bir ortak API 'nin her bileşeninin, başlangıçtan itibaren olası tüm kullanımlar için tasarım denemesi yerine karşılık gelen bir kullanım örneğine sahip **olduğundan emin olun** .
    Farklı bir şekilde, yararlı olmaları durumunda ortak API 'Ler oluşturmayın, ancak bir API 'nin her bölümünün yararlı olacağı *somut* bir örneğe sahip olduğundan emin olun.

  *Örnekler:*
  - @"microsoft.quantum.canon.applytoeachca"`ApplyToEachCA(H, _)`, çok sayıda hisse algoritmasında ortak bir görev olan bir Tekdüzen üst konum durumunda Yazmaçları hazırlamak için olarak kullanılabilir. Aynı işlem, hazırlık, sayı ve Oracle tabanlı algoritmalarda birçok diğer görev için de kullanılabilir.

- ✅Tek bir kez beyin fırtınası **yapın** ve yeni API tasarımları oluşturun ve bunları sezgisel olarak kontrol edin ve önerilen kullanım durumlarını karşılayın.

  *Örnekler:*
  - \#Yenı API tasarımlarının mevcut uygulamaları nasıl basitleştireceğinizi ve açıklanmadığını görmek için geçerli Q kodunu inceleyin.
  - Birincil hedef kitleleri temsilcileriyle önerilen API tasarımlarını gözden geçirin.

**Anahtar ilkesi:** Okunabilir kodu desteklemek ve teşvik etmek için API 'Ler tasarlayın.

- ✅Kodun etki alanı uzmanları ve uzman olmayanlar tarafından okunabilir **olduğundan emin olun** .
- ✅Uygulama ayrıntılarına uygun şekilde **Delve yapmak için** belgeleri kullanarak her bir işlemin ve yüksek düzeyli algoritmadaki işlevin etkilerine odaklanın.
- ✅Uygun olan her durumda ortak [Q \# stili kılavuzunu](xref:microsoft.quantum.contributing.style) **izleyin.**

**Anahtar ilkesi:** API 'Leri kararlı olacak şekilde tasarlayın ve ileriye dönük uyumluluk sağlayın.

- ✅Önemli değişiklikler gerektiğinde eski API 'Leri sorunsuz bir **şekilde kullanımdan kaldırır** .

- ✅Kullanımdan kaldırma sırasında mevcut kullanıcı kodunun doğru çalışmasına izin veren "dolgu" işlemleri ve **işlevleri sağlar.**

  *Örnekler:*
  - Öğesine adlı bir işlemi yeniden `EstimateExpectation` adlandırırken   `EstimateAverage` ,   `EstimateExpectation` var olan kodun doğru şekilde çalışmaya devam edebilmesi için özgün işlemi yeni adında çağıran adlı yeni bir işlem tanıtın.

- ✅**DO** Kullanıcı kullanım dışı @"microsoft.quantum.core.deprecated" Bırakıla iletişim kurmak için özniteliğini kullanın.

- ✅ Bir işlemi veya işlevi yeniden adlandırırken, yeni adı bir dize girişi **olarak sağlayın** `@Deprecated` .

- ⛔️, önizleme sürümleri için en az altı aya veya desteklenen yayınlar için en az iki yıla kadar kullanım süresi olmadan mevcut işlevleri veya **işlemleri kaldırmayın.**

## <a name="functions-and-operations"></a>İşlevler ve Işlemler

**Anahtar ilkesi:** her işlev ve işlemin API içinde iyi tanımlanmış tek bir amaca sahip olduğundan emin olun.

- ⛔️, birden çok ilgisiz görevi gerçekleştiren işlevleri ve işlemleri **kullanıma sunmaz.**

**Anahtar ilkesi:** işlevleri ve işlemleri mümkün olduğunca yeniden kullanılabilir olacak şekilde tasarlayın ve gelecekteki ihtiyaçları tahmin edin.

- ✅Aynı API 'de ve daha önce var olan kitaplıklarda diğer işlevler ve işlemlerle birlikte oluşturmak için işlevler ve **işlemler tasarlayın.**

  *Örnekler:*
  - @"microsoft.quantum.canon.delay"İşlem, girişi hakkında en az varsayımlar yapar ve bu nedenle, Q# Standart kitaplıkta veya kullanıcılar tarafından tanımlanan işlemlerin uygulamalarını geciktirmek için kullanılabilir.
    <!-- TODO: define bad example. -->

- ✅İşlemler yerine işlev olarak yalnızca belirleyici klasik **mantığı sergileme** .

  *Örnekler:*
  - Kayan nokta girişini gösteren bir alt yordam, `Squared : Double -> Double` bir işlem olarak değil, kullanıcıya gösterilmelidir `Square : Double => Double` . Bu, alt yordamın daha fazla yerde (örneğin, diğer işlevlerin içinde) çağrılmasına izin verir ve derleyiciye performansı ve iyileştirmeleri etkileyebilecek yararlı iyileştirme bilgileri sağlar.
  - `ForEach<'TInput, 'TOutput>('TInput => 'TOutput, 'TInput[]) => 'TOutput[]` ve `Mapped<'TInput, 'TOutput>('TInput -> 'TOutput, 'TInput[]) -> 'TOutput[]` belirleyici bir şekilde yapılan garantilere göre farklılık gösterir; her ikisi de farklı koşullarda yararlıdır.
  - Hisse alma işlemlerinin uygulamasını dönüştüren API yordamları, genellikle belirleyici bir şekilde gerçekleştirilebilir ve bu nedenle, gibi işlevler olarak kullanılabilir hale getirilebilir   `CControlled<'T>(op : 'T => Unit) => ((Bool, 'T) => Unit)` .

- ✅Gerektiğinde tür parametrelerini kullanarak, her bir işlev ve işlem için giriş türünü makul **şekilde genelleştirin** .

  *Örnekler:*
  - `ApplyToEach``<'T>(('T => Unit), 'T[]) => Unit`en yaygın uygulamasının belirli türü yerine türü vardır `((Qubit => Unit), Qubit[]) => Unit` .

> [!TIP]
> Gelecekteki ihtiyaçları tahmin etmek önemlidir, ancak kullanıcılarınız için somut sorunları çözmenin de önemlidir.
> Bu nedenle bu temel prensibi, her zaman dikkatli bir değerlendirme gerektirir ve API 'Leri geliştirmekten kaçınmak için "Tıpkı büyük/küçük"

**Anahtar ilkesi:** öngörülebilir ve çağrılabilir amacını ileten işlevler ve işlemler için giriş ve çıkış türlerini seçin.

- ✅Yalnızca bir arada kabul edildiğinde önemli olan giriş ve çıkışları mantıksal olarak gruplamak için demet **türlerini kullanın.** Bu durumlarda Kullanıcı tanımlı bir tür kullanmayı düşünün.

  *Örnekler:*
  - Başka bir işlevin yerel en düşük değerleri çıktısını almak için bir işlev, uygun bir imza olabilecek bir arama aralığının bir giriş olarak sınırlarını gerektirebilir `LocalMinima(fn : (Double -> Double), (left : Double, right : Double)) : Double` .
  - Bir makine öğrenimi sınıflandırmasının bir türevi olan parametre kaydırma tekniğinin bir türevini tahmin etmeye yönelik bir işlem, hem kaydırılan hem de geriye doğru olmayan parametre vektörlerini giriş olarak alamaz. Şuna benzer bir giriş `(unshifted : Double[], shifted : Double[])` Bu durumda uygun olabilir.

- ✅Giriş ve çıkış tanımlama alanlarında öğeleri farklı işlevler ve işlemler arasında tutarlı bir **şekilde sıralayın.**

  *Örnekler:*
  - İki veya işlev ya da her biri bir döndürme açısı ve bir hedef qubit girişi olarak düşünüyorsa, bunların her giriş grubu için aynı sıralandıklarından emin olun. Diğer bir deyişle, ve ' yi tercih eder `ApplyRotation(angle : Double, target : Qubit) : Unit is Adj + Ctl` `DelayedRotation(angle : Double, target : Qubit) : (Unit => Unit is Adj + Ctl)` `ApplyRotation(target : Qubit, angle : Double) : Unit is Adj + Ctl` `DelayedRotation(angle : Double, target : Qubit) : (Unit => Unit is Adj + Ctl)` .

**Anahtar ilkesi:** kısmi uygulama gibi Q dil özellikleriyle iyi çalışmak için işlevler ve işlemler tasarlayın \# .

- ✅Giriş tanımlama grupları içindeki öğeleri, en yaygın olarak uygulanan girdilerin önce gerçekleşmesi (yani, kısmi uygulamanın currying 'e benzer şekilde davranması) **için sıralayın.**

  *Örnekler:*
  - Kayan noktalı bir `ApplyRotation` sayı ve bir qubit girişi olan bir işlem, genellikle, türü bir girişi bekleyen işlemlerle kullanım için ilk olarak kayan nokta girişi ile kısmen uygulanabilir `Qubit => Unit` . Bu nedenle, bir imzası `operation ApplyRotation(angle : Double, target : Qubit) : Unit is Adj + Ctl`
      kısmi uygulamayla en tutarlı şekilde çalışır.
  - Genellikle, bu kılavuz, tüm klasik verilerin giriş tanımlama grupları 'ndaki tüm qugeler öncesine yerleştirilmesi anlamına gelir, ancak iyi bir deneyim kullanır ve API 'nizin uygulamada nasıl çağrıldığını inceleyin.

## <a name="user-defined-types"></a>User-Defined türleri

**Anahtar ilkesi:** API 'leri daha açıklayıcı ve kullanımı kolay hale getirmenize yardımcı olması için Kullanıcı tanımlı türleri kullanın.

- ✅Uzun ve/veya karmaşık türler için yararlı bir Özet sağlamak üzere Kullanıcı tanımlı yeni türler **ortaya çıkarabilir.**

  *Örnekler:*
  - Üç qubit dizi girişi olan bir işlem türünün genellikle giriş olarak alındığı veya çıkış olarak döndürüldüğü durumlarda, gibi bir UDT sağlayarak `newtype TimeDependentBlockEncoding = ((Qubit[], Qubit[], Qubit[]) => Unit is Adj + Ctl)`
      yararlı bir Özet sağlamaya yardımcı olabilir.

- ✅Belirli bir temel türün yalnızca belirli bir anlamda kullanılması gerektiğini göstermek için Kullanıcı tanımlı yeni **türler tanıtılmalıdır** .

  *Örnekler:*
  - Özellikle, klasik verileri bir hisse kaydına kodlayan bir işlem olarak yorumlanan bir işlem, Kullanıcı tanımlı bir türle etiketlemek için uygun olabilir `newtype InputEncoder = (Apply : (Qubit[] => Unit))` .

- ✅Sonraki genişletilebilirliğe izin veren adlandırılmış öğelerle Yeni Kullanıcı tanımlı türler (ör.: gelecekte ek adlandırılmış öğeler içerebilen bir sonuç yapısı **) tanıtılmalıdır** .

  *Örnekler:*
  - Bir işlem `TrainModel` çok sayıda yapılandırma seçeneği kullanıma sunarsa, bu seçeneklerin yeni bir udt olarak kullanıma   `TrainingOptions` sunulmasına ve yeni bir işlev sağlamaya yönelik olarak,   `DefaultTrainingOptions : Unit -> TrainingOptions` kitaplık geliştiricilerinin uygun şekilde yeni udt öğeleri eklemesine izin verirken, kullanıcıların Traıningoptions udt değerlerinde belirli adlandırılmış öğeleri geçersiz kılmasına izin verir.

- ✅**DO** Kullanıcı tanımlı yeni türler için adlandırılmış öğeleri, kullanıcıların doğru demet oluşturmayı bilmesini gerektirmek için tercih edin.

  *Örnekler:*
  - Kutupsal ayrıştırma içinde karmaşık bir sayıyı temsil ettiğinizde, tercih edilir   `newtype ComplexPolar = (Magnitude: Double, Argument: Double)`   `newtype ComplexPolar = (Double, Double)` .

**Anahtar ilkesi:** bilişsel yükün azaltılması ve kullanıcının ek kavramlar ve terminoloji öğrenmesini gerektirmeyen yollarla Kullanıcı tanımlı türleri kullanın.

- ⛔️ **DON'T** , kullanıcının bir unsarmadan işlecini () sık kullanmasını gerektiren `!` ya da genellikle birden çok düzey sarmalama düzeyi gerektiren Kullanıcı tanımlı türler sunmaz. Olası risk azaltma stratejileri şunlardır:

  - Kullanıcı tanımlı bir türü tek bir öğe ile kullanıma sunmadığında, bu öğe için bir ad tanımlamayı göz önünde bulundurun. Örneğin, tercih edin `newtype Encoder = (Apply : (Qubit[] => Unit is Adj + Ctl))` `newtype Encoder = (Qubit[] => Unit is Adj + Ctl)` .

  - Diğer işlevlerin ve işlemlerin "sarmalanmış" UDT örneklerini doğrudan kabul edebilmesini sağlama.

- ⛔️ **,** ek ifade sağlamadan yerleşik türleri yinelenen yeni kullanıcı tanımlı türler sunmaz.

  *Örnekler:*
  - Bir UDT `newtype QubitRegister = Qubit[]` , daha fazla ifade sunmaz ve bu `Qubit[]` nedenle, hiç bir avantaj olmadan kullanımı zorlaştırır.
  - Bir UDT, `newtype LittleEndian = Qubit[]` temel kaydın nasıl kullanılacağını ve yorumlanması gerektiğini belgelemektedir ve bu nedenle temel türü üzerinde ek ifade sağlar.

- ⛔️ **,** kesinlikle gerekli olmadığı takdirde erişimci işlevleri sunmaz;   Bu durumda adlandırılmış öğeleri kesin olarak tercih edin.

  *Örnekler:*
  - Bir UDT 'ye giriş yaparken `newtype Complex = (Double, Double)` ,   `newtype Complex = (Real : Double, Imag : Double)` işlevleri ve işlevlerine giriş yapmak için tanımını değiştirmeyi tercih edin `GetReal : Complex -> Double`   `GetImag : Complex -> Double` .

## <a name="namespaces-and-organization"></a>Ad alanları ve kuruluş

**Anahtar ilkesi:** her bir ad alanındaki işlevlerin, işlemlerin ve Kullanıcı tanımlı türlerin amacını açıkça ileten, tahmin edilen ve ad alanı adlarını seçin.

- ✅**Ad alanlarını olarak** adlandırın `Publisher.Product.DomainArea` .

  *Örnekler:*
  - Hisse geliştirme seti 'nin hisse bir parçası olarak Microsoft tarafından yayımlanan işlevler, işlemler ve UDTs 'ler   `Microsoft.Quantum.Simulation` ad alanına yerleştirilir.
  - `Microsoft.Quantum.Math` Microsoft tarafından, matematik etki alanı alanıyla ilgili olan hisse geliştirme setinin bir parçası olarak yayımlanan bir ad alanını temsil eder.

- ✅Belirli işlevler için kullanılan işlemler, işlevler ve Kullanıcı tanımlı türler, bu işlevselliği farklı sorun etki alanlarında kullanıldığında bile bu işlevselliği açıklayan bir ad **alanına yerleştirir.**

  *Örnekler:*
  - Microsoft tarafından, hisse alım geliştirme seti 'nin bir parçası olarak yayımlanan durum hazırlama API 'Leri içine yerleştirilir   `Microsoft.Quantum.Preparation` .
  - Hisse geliştirme setinin bir parçası olarak Microsoft tarafından yayımlanan hisse simülasyonu API 'Leri içine yerleştirilir   `Microsoft.Quantum.Simulation` .

- ✅Yalnızca belirli etki alanlarında kullanılan işlemler, işlevler ve Kullanıcı tanımlı türler, yardımcı programı etki alanlarını gösteren ad **alanlarına yerleştirir.** Gerekirse, etki alanına özgü her ad alanı içinde odaklanmış görevleri belirtmek için alt ad alanlarını kullanın.

  *Örnekler:*
  - Microsoft tarafından yayımlanan hisse makine öğrenimi kitaplığı, büyük ölçüde @"microsoft.quantum.machinelearning" ad alanına yerleştirildi, ancak örnek veri kümeleri @"microsoft.quantum.machinelearning.datasets"   ad alanı tarafından sağlanır.
  - Hisse uygun olarak Microsoft tarafından yayınlanan hisse uyumlu API 'Leri, hisse geliştirme seti 'nin bir parçası olarak içine yerleştirilmelidir `Microsoft.Quantum.Chemistry` . Ürdün--Wigner ayrıştırma işlevinin uygulamaya özgü işlevselliği ' de yerleştirilebilecek `Microsoft.Quantum.Chemistry.JordanWigner` ve bu sayede hisse dili Mistry etki alanı alanının birincil arabiriminin uygulamalarla ilgilenmemesi sağlanır.

**Anahtar ilkesi:** Kullanıcılara sunulan API yüzeyine bilerek yönelik olarak ad alanlarını ve erişim değiştiricilerini kullanın ve API 'lerinizi uygulamayla ve test etme ile ilgili dahili ayrıntıları gizleyin.

- ✅ Makul her durumda **, uygulanan** API ile aynı ad ALANıNA bir API uygulamak için gereken tüm işlevleri ve işlemleri, ancak bir kitaplık IÇIN genel API yüzeyinin bir parçası olmadığını belirtmek için "özel" veya "iç" anahtar sözcükleriyle işaretlenir. `_`Özel ve iç işlemleri ve işlevleri ortak callables 'den görsel olarak ayırt etmek için alt çizgi () ile başlayan bir ad kullanın.

  *Örnekler:*
  - İşlem adı, `_Features` belirli bir ad alanı ve derleme için özel bir işlevi belirtir ve `internal` anahtar kelimesiyle birlikte gelmelidir.

- ✅ Belirli bir ad alanı için API 'YI uygulamak üzere çok sayıda özel işlev veya işlemin gerekli olduğu nadir bir durumda, bunları uygulanan ve biten ad alanıyla eşleşen yeni bir ad **alanına yerleştirin** `.Private` .

- ✅Tüm birim testlerini test ve bitiş altındaki ad alanıyla eşleşen ad **alanlarına yerleştirin** `.Tests` .

## <a name="naming-conventions-and-vocabulary"></a>Adlandırma kuralları ve sözlük

**Anahtar ilkesi:** NET, erişilebilir ve farklı bir hedef kitle genelinde okunabilir olan adları ve terminolojiyi, hem hisse nunovıces hem de uzmanlar dahil olmak üzere seçin.

- ⛔️ Discriminatory veya exclusionary tanımlayıcı adlarını veya API belge açıklamalarındaki **terminolojiyi kullanmayın.**

- ✅Özellikle daha zor kavramlar için ilgili bağlamı, örnekleri ve başvuruları sağlamak üzere API belge **açıklamalarını kullanın.**

- ⛔️ gereksiz esoteric olan veya okumak için önemli hisse algoritmaları bilgisi gerektiren tanımlayıcı **adlarını kullanmayın.**

  *Örnekler:*
  - "Genver yineleme" olarak "genonu yineleme" olarak tercih edin.

- ✅Bir çağrılabilir uygulamanın amaçlanan etkisini açıkça iletişim kuran işlemler ve işlev adları ' **nı seçin.** Uygulamanın [API belge açıklamalarında](xref:microsoft.quantum.guide.filestructure#documentation-comments)ve belgelendiğini unutmayın.

  *Örnekler:*
  - "Hadamard test" için "tahmini örtüşme" yı tercih edin, ikincisi ise eski 'ın nasıl uygulandığını iletir.

- ✅Tüm Q API 'lerinde tutarlı bir biçimde **sözcükler kullanın** \# :

  - **Eylemlerinin**

    - Onay **: büyük** olasılıkla fiziksel olmayan kaynakları kullanarak bir hedef makinenin ve qubits 'in durumu hakkında bir varsayım olduğunu denetleyin. Bu fiili kullanan işlemler, kitaplıkların ve yürütülebilir programların işlevselliğini etkilemeden her zaman güvenli bir şekilde kaldırılabilir. Olguların aksine, genel olarak, bir qubit kayıt durumu, çalıştırma ortamı veya benzeri bir durum gibi, genel olarak, onay olabilir. Dış durum bağımlılığı bir tür yan etkildir, ancak onaylar işlevler yerine işlemler olarak gösterilmelidir.

    - **Tahmin** : bir veya daha fazla tekrarlanmış ölçüm kullanarak, ölçüm sonuçlarından bir klasik miktarı tahmin edin.

      *Örnekler:*
      - @"microsoft.quantum.characterization.estimatefrequency"
      - @"microsoft.quantum.characterization.estimateoverlapbetweenstates"

    - **Hazırlama** : belirli bir başlangıç durumunda (genellikle $ \ket{00\cnoktalar 0} $) başlayan bir veya daha fazla qubits 'e bir hisse veya işlem dizisi uygulayın, bu qubits 'in durumunun istenen bir bitiş durumuna gelişmesine neden olur. Genel olarak, verili **başlangıç durumundan farklı** durumlara göre işlem, tanımsız bir Unitary dönüştürmesi ile sonuçlanabilir, ancak yine de bir işlemin ve kendi adjoint "iptal etmeyi" ve hiçbir op **uygulamamalıdır** .

      *Örnekler:*
      - @"microsoft.quantum.preparation.preparearbitrarystate"
      - @"microsoft.quantum.preparation.prepareuniformsuperposition"

    - **Measure** : bir veya daha fazla qubits 'e bir hisse veya işlem dizisi uygulayarak klasik veri geri alma işlemini okuyun.

      *Örnekler:*
      - @"Microsoft.Quantum.Intrinsic.Measure"
      - @"microsoft.quantum.arithmetic.measurefxp"
      - @"microsoft.quantum.arithmetic.measureinteger"

    - **Uygula** : bir veya daha fazla qubits 'e hisse veya işlem dizisi uygulayın ve bu qubits 'in durumunun tutarlı bir şekilde değişmesine neden olur. Bu fiil, Q terminolojinin en genel fiildir \# ve daha **SHOULD NOT BE** belirli bir fiil daha doğrudan ilgili olduğunda kullanılmamalıdır.

  - **İsimler** :

    - **Olgu** : bir hedef makinenin, ortamının veya makine qubits 'in durumunda değil, yalnızca kendi girdilerine bağlı olan bir Boolean koşulu. Bir onaylama işlemi aksine, olgu yalnızca söz konusu olgusuna belirtilen *değerlere* duyarlıdır. Örneğin:

      *Örnekler:*
      - @"microsoft.quantum.diagnostics.equalityfacti": iki tamsayı girişi hakkında bir eşitlik olgusu temsil eder; giriş olarak girilen tamsayılar birbirlerine eşittir ya da başka bir program durumundan bağımsız olarak değildir.

    - **Seçenekler:** Bir işlev veya işleme "isteğe bağlı bağımsız değişkenler" gibi davranan, birkaç adlandırılmış öğe içeren bir UDT. Örneğin:

      *Örnekler:*
      - @"microsoft.quantum.machinelearning.trainingoptions"Udt, öğrenme oranı, Mini toplu iş boyutu ve ml eğitimi için diğer yapılandırılabilir parametreler için adlandırılmış öğeler içerir.

  - **Sıfatlar** :

    - **yeni** ⛔️: Bu sıfatıcı, birçok programlama dilinde (ör.: C++, C#, Java, TypeScript, PowerShell), kullanımıyla ilgili bir fiil olarak karışıklık oluşmasını önlemek **için kullanılmamalıdır.**

  - **Ön pozisyonlar:** Bazı durumlarda, işlev ve işlem adlarında isimler ve fiillerin rollerini daha fazla netleştirmek veya netleştirmek için ön pozisyonlar kullanılabilir. Bununla birlikte, dikkatli ve tutarlı şekilde yapılması gerekir.

    - **Şöyle:** Bir işlevin giriş ve çıktısının aynı bilgileri temsil ettiğini, ancak çıktının özgün temsili yerine bu bilgileri bir *X* **olarak** temsil ettiğini temsil eder. Bu özellikle tür dönüştürme işlevleri için ortaktır.

      *Örnekler:*
      - `IntAsDouble(2)` hem Input ( `2` ) hem de Output ( `2.0` ) 'ın aynı bilgileri qualitatively temsil ettiğini, ancak \# bunu yapmak için farklı Q veri türlerini kullandığını gösterir.

    - **Kimden:** Tutarlılığı sağlamak için bu ön pozisyon, tür dönüştürme işlevlerini veya uygun **olduğu yerde başka** bir durumu belirtmek **için kullanılmamalıdır.**

    - ⛔️ **:** bu ön pozisyon, birçok programlama dilinde fiil olarak kullanımıyla ilgili karışıklık olmaması **için kullanılmamalıdır.**
