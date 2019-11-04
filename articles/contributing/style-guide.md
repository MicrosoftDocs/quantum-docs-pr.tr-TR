---
title: 'S # stil kılavuzu | Microsoft Docs'
description: 'S # stil kılavuzu'
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.style
ms.openlocfilehash: 4050e2ee9e516aed7a8ba1398792562926808ee0
ms.sourcegitcommit: c93fea5980d1d46fbda1e7c7153831b9337134bf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73463312"
---
# <a name="q-style-guide"></a>S # stil kılavuzu #
## <a name="general-conventions"></a>Genel kurallar ##

Bu kılavuzda önerilen kurallar, Q # dilinde yazılmış program ve kitaplıkların okunmasını ve anlaşılması daha kolay hale getirmeye yardımcı olmak için tasarlanmıştır.

## <a name="guidance"></a>Kılavuz

Şunları öneririz:

- Kullanıcılarınız için daha okunaklı ve anlaşılır kod sağlamak üzere kasıtlı olarak yapmadığınız müddetçe hiçbir şekilde hiçbir kuralı yok saymayın.

## <a name="naming-conventions"></a>Adlandırma kuralları ##

Hisse geliştirme setini sunan bölümünde, hisse geliştiricilerin kolayca okunabilen ve aniden en aza indirecek programlar yazmasına yardımcı olan işlev ve işlem adları için çaba duyuyoruz.
Bunun önemli bir bölümü, işlevler, işlemler ve türler için ad seçtiğimiz durumlarda, programcıların expressconcepts için kullandığı *sözlüğü* oluşturacağız; seçimlerimiz sayesinde, bunlara açık bir şekilde iletişim kurma çabalarına yardımcı olur veya bu işlemleri de destekliyoruz.
Bu, sunduğumuz adların Saklılığı yerine netlik sağlamalarını sağlamak için bize bir sorumluluk koyar.
Bu bölümde, Q # geliştirme topluluğu tarafından en iyi şekilde buluşmamıza yardımcı olan açık yönergeler açısından bu yükümlülüğünüzü nasıl karşıladığımızdan ayrıntılıyoruz.

### <a name="operations-and-functions"></a>İşlemler ve Işlevler ###

Bir adın oluşturulması gereken ilk şeylerden biri, belirli bir sembolün bir işlevi veya işlemi temsil ettiğini belirtir.
İşlevler ve işlemler arasındaki fark, bir kod bloğunun nasıl davranacağını anlamak açısından önemlidir.
İşlevler ve işlemler arasındaki ayrımı kullanıcılara iletmek için, yan etkileri kullanılarak bu Q # model hisse işlemlerine güveniyoruz.
Diğer bir deyişle, bir işlem bir işlem *yapar* .

Buna karşılık işlevler, veriler arasındaki matematik ilişkilerini tanımlar.
`Sin(PI() / 2.0)` ifadesi `1.0`ve bir programın veya qubits *'in durumu* hakkında hiçbir şey anlamına gelir.

Özetleme, işlemler, işlevleri işler.
Bu ayrım, işlemleri fiiller olarak ve işlevler olarak işlev olarak adı vereceğiz.

> [!NOTE]
> Kullanıcı tanımlı bir tür bildirildiğinde, bu türün örneklerini oluşturan yeni bir işlev örtülü olarak aynı anda tanımlanır.
> Bu perspektiften, hem türün kendisi hem de Oluşturucu işlevinin tutarlı adlara sahip olması için Kullanıcı tanımlı türlerin adlarla adlandırılması gerekir.

Makul yerlerde, işlem adlarının işlem tarafından gerçekleştirilen etkiyi açıkça belirten fiiller ile başlayıp başlamadığından emin olun.
Örnek:

- `MeasureInteger`
- `EstimateEnergy`
- `SampleInt`

Özel bahsetmeye hizmet eden bir durum, bir işlem başka bir işlemi girdi olarak aldığında ve çağırdığında çağırır.
Bu gibi durumlarda, giriş işlemi tarafından gerçekleştirilen eylem, dış işlem tanımlandığında, doğru fiil hemen temizlenmediği için net değildir.
`ApplyIf`, `ApplyToEach`ve `ApplyToFirst`gibi fiil `Apply`önerilir.
Bu örnekte olduğu gibi diğer fiiller da yararlı olabilir `IterateThroughCartesianPower`.

| Ü | Beklenen efekt |
| ---- | ------ |
| Başvurun | Giriş olarak verilen bir işlem çağrılır |
| Assert | Olası bir hisse ölçüsünün sonucu hakkında bir varsayım simülatör tarafından denetlenir |
| Tahmin | Bir veya daha fazla ölçüden çizilen bir tahmini temsil eden klasik bir değer döndürüldü |
| Measure | Bir hisse ölçümü gerçekleştirilir ve sonucu kullanıcıya döndürülür |
| Hazırlanın | Belirli bir qubits kaydı belirli bir duruma başlatılır |
| Örnek | Klasik bir değer, bazı dağılılardan rasgele döndürülür |

İşlevler için, fiillerin ortak isimler yerine kullanılmasını önletireceğiz (aşağıdaki doğru isimler üzerinde rehberlik) veya sıfatlar:

- `ConstantArray`
- `Head`
- `LookupFunction`

Özellikle, neredeyse her durumda, bir işlev adının bir işleme veya bir hisse senedine bağlı olarak bir eyleme bağlı olduğunu göstermek için uygun olan geçmiş participles kullanmayı öneririz.
Örneğin, `ControlledOnInt` işlevin bağımsız değişkenini değiştirmek üzere sıfatıcı olarak davrandığını göstermek için, "Control" fiilinin bölüm participle formunu kullanır.
Bu ad, aşağıda açıklandığı gibi, yerleşik `Controlled` functor semantiğini eşleştirmesinin ek avantajına sahiptir.
Benzer şekilde, `Encode`ile ilişkili bir UDT için ad `Encoder` durumda olduğu gibi, işlem adlarından işlev ve UDT adları oluşturmak için _Aracı isimleri_ de kullanılabilir.

# <a name="guidancetabguidance"></a>[Rehber](#tab/guidance)

Şunları öneririz:

- İşlem adları için fiilleri kullanın.
- İşlev adları için isimleri veya sıfatları kullanın.
- Kullanıcı tanımlı türler ve öznitelikler için isimleri kullanın.
- Tüm çağrılabilir adlar için, `pascalCase`, `snake_case`veya `ANGRY_CASE`için güçlü bir tercih `CamelCase` kullanın. Özellikle, çağrılabilir adların büyük harfle başlayıp başlamadiğinden emin olun.
- Tüm yerel değişkenler için, `CamelCase`, `snake_case`veya `ANGRY_CASE`için güçlü bir tercih `pascalCase` kullanın. Özellikle, yerel değişkenlerin küçük harfle başlayıp başlamadiğinden emin olun.
- İşlev ve işlem adlarında alt çizgi `_` kullanmaktan kaçının; ek hiyerarşi düzeyleri gerekli olduğunda, ad alanları ve ad alanı diğer adları kullanın.

# <a name="examplestabexamples"></a>[Örnekler](#tab/examples)

|   | Adı | Açıklama |
|---|------|-------------|
| ☑ | `operation ReflectAboutStart` | İşlemin etkisini göstermek için bir fiil ("yansıtma") kullanımını temizleyin. |
| ☒ | <s>`operation XRotation`</s> | İsim ifadesi kullanımı, işlem yerine Function önerisinde bulunur. |
| ☒ | <s>`operation search_oracle`</s> | `snake_case` nvenes Q # gösterimi kullanımı. |
| ☒ | <s>`operation Search_Oracle`</s> | Alt çizgi kullanımı iç işlem adı nvenes Q # gösterimi. |
| ☑ | `function StatePreparationOracle` | İsim ifadesinin kullanılması işlevin bir işlem döndürdüğünü önerir. |
| ☑ | `function EqualityFact` | Bu işlevin bir işlev olduğunu göstermek için ("olgu"), sıfatı seçimini temizleyin. |
| ☒ | <s>`function GetRotationAngles`</s> | Fiil ("Get") kullanılması bunun bir işlem olduğunu önerir. |
| ☑ | `newtype GeneratorTerm` | Ad ifadesinin kullanımı, UDT oluşturucusunun çağrılması sonucunu açıkça ifade eder. |
| ☒ | <s>`@Attribute() newtype RunOnce()`</s> | Fiil ifadesinin kullanımı, UDT oluşturucusunun bir işlem olduğunu önerir. |
| ☑ | `@Attribute() newtype Deprecated(Reason : String)` | İsim ifadesinin kullanılması özniteliğin kullanımını iletişim kurar. |

***

### <a name="shorthand-and-abbreviations"></a>Özet ve kısaltmalar ###

Yukarıdaki önerinin, hisse yaramakta olan ortak ve kapsamlı kullanımı gösteren çok sayıda kısayol vardır.
Özellikle bir hedef makinenin işlemlerine iç işlemler için, var olan ve genel bir toplu işlemin bulunduğu yerde kullanmayı öneririz.
Örneğin, `ApplyX`yerine `X` adı ve `RotateAboutZ`yerine `Rz` seçeceğiz.
Bu tür bir kısayol kullanırken, işlem adları tümü büyük harfle yazılmalıdır (ör.: `MAJ`).

Bu kural, yaygın olarak kullanılan kısaltmalar ve başlangıçlar söz konusu olduğunda "hisse Fourier dönüştürmesi" için "QFT" gibi bazı durumlarda gereklidir.
Tam adlarda kısaltmalar ve ınitialisms 'lerin kullanılması için aşağıdaki genel .NET kurallarını öneririz:

- iki harfli kısaltmalar ve ınitialisms büyük harfle adlandırılır (örneğin, "Big-endian" için `BE`),
- daha uzun kısaltmalar ve ınitialisms 'ler `CamelCase` olarak adlandırılır (örn. "hisse Fourier dönüştürmesi" için `Qft`)

Bu nedenle, QFT 'yi uygulayan bir işlem, kısayol olarak `QFT` çağrılabilir veya `ApplyQft`olarak yazılabilir.

Özellikle yaygın olarak kullanılan işlemler ve işlevler için daha uzun bir form için bir _diğer_ ad olarak bir kısayol adı sağlanması istenebilir:

```qsharp
operation CCNOT(control0 : Qubit, control1 : Qubit, target : Qubit)
is Adj + Ctl {
    Controlled X([control0, control1], target);
}
```

# <a name="guidancetabguidance"></a>[Rehber](#tab/guidance)

Şunları öneririz:

- Uygun olduğunda genellikle kabul edilen ve yaygın olarak kullanılan toplu adları göz önünde bulundurun.
- Toplu değer için büyük harf kullanın.
- Kısa (iki harfli) kısaltmalar ve ınitialisms için büyük harf kullanın.
- Daha uzun (üç veya daha fazla harf) kısaltmalar ve ınitialisms için `CamelCase` kullanın.

# <a name="examplestabexamples"></a>[Örnekler](#tab/examples)

|   | Adı | Açıklama |
|---|------|-------------|
| ☑ | `X` | "Bir $X $ dönüşümü Uygula" için iyi anlaşılan toplu değer |
| ☑ | `CNOT` | "Denetimli-NOT" için iyi anlaşılan toplu değer |
| ☒ | <s>`Cnot`</s> | Kısayol `CamelCase`olmamalıdır. |
| ☑ | `ApplyQft` | "QFT" ortak ınitialroni uzun biçimli bir adın parçası olarak görünür. |
| ☑ | `QFT` | Genel ınitialısm "QFT", bir kısayol adının parçası olarak görünür. |



***


### <a name="proper-nouns-in-names"></a>Adlarda doğru adlar ###

Fizik durumunda, bunlar hakkında ilk kişiden sonra yayımlanmayan kişilerin adlarını ve tüm geçmişi öğrenmelerini sağlamak yaygın bir şekilde yapılıyor.
Daha fazla bilgi için, diğer arka planlardaki kullanıcıların, genel işlemleri ve kavramları kullanabilmesi için çok sayıda donuk opak ad öğrenmelidir.
<!-- An important part of the task of reducing confusion is to make code more accessible.
Especially in a field such as quantum computing that is rich with domain expertise, we must at all times be cognizant of the demands we place on that expertise as we design quantum software.
In naming code symbols, one way that this cognizance expresses itself is as an awareness of the convention from physics of adopting as the names of algorithms and operations the names of their original publishers.
While we must maintain the history and intellectual provenance of concepts in quantum computing, demanding that all users be versed in this history to use even the most basic of functions and operations places a barrier to entry that is in most cases severe enough to even present an ethical compromise. -->
Bu nedenle, bir kavramı tanımlayan makul, yaygın isimler kavramı, bir kavramın yayın geçmişini tanımlayan doğru isimler için güçlü bir tercih halinde benimsemesi önerilir.
Belirli bir örnek olarak, listedir kontrollü DEĞIŞTIRME ve buna uygun olmayan işlemler, genellikle akademik belgelerinde "Fredkaş" ve "Toffoli" işlemleri olarak adlandırılır, ancak `CSWAP` ve `CCNOT`olarak Q # içinde tanımlanır.
Her iki durumda da, API belgesi açıklamaları uygun adlara göre eş anlamlı adlar sağlar ve tüm uygun alıntıları birlikte kapsar.

Bu tercih, bazı uygun isimler kullanımının her zaman gerekli olacağı bir şekilde önemlidir. Q #, örneğin birçok klasik dile göre gelenek kümesini izler ve daha sonra değer olarak adlandırılan Boolean mantığına başvuru `Bool` türlerine başvurur. George Boole.
Benzer şekilde, örneğin, Q # diline yerleşik `Pauli` türü de dahil olmak üzere, benzer bir şekilde adlandırılmış birkaç hisse kavramdır.
Bu kullanım açısından gerekli olan doğru isimler kullanımını en aza indirerek, doğru isimleri kabul etmeyeceğinden etkiyi azalttık.

# <a name="guidancetabguidance"></a>[Rehber](#tab/guidance) 

Şunları öneririz:

- Adlarda doğru isimler kullanmaktan kaçının.

# <a name="examplestabexamples"></a>[Örnekler](#tab/examples)

***

### <a name="type-conversions"></a>Tür dönüştürmeleri ###

Q #, kesin ve statik olarak yazılmış bir dil olduğundan, bir tür değeri yalnızca bir tür dönüştürme işlevine açık bir çağrı kullanılarak başka bir türün değeri olarak kullanılabilir.
Bu, değerlerin örtük olarak (ör. tür promosyonu) veya atama yoluyla türlerin değiştirilmesini sağlayan dillere karşılık gelir.
Sonuç olarak, tür dönüştürme işlevleri Q # kitaplığı geliştirme bölümünde önemli bir rol oynar ve adlandırma hakkında yaygın olarak karşılaşılan kararlardan birini içerir.
Ancak, tür dönüştürmeleri her zaman _belirleyici_olduğundan, bunlar işlev olarak yazılabilecekleri ve bu nedenle yukarıdaki önerinin altına düşecek.
Özellikle, tür dönüştürme işlevlerinin fiiller (ör.: `ConvertToX`) veya duyurusu b önceden konumsal ifadeler (`ToX`) olarak adlandırılmaması, ancak kaynak ve hedef türlerini belirten sıfatıcı önceden konumsal ifadeler olarak adlandırılması (`XAsY`).
Tür dönüştürme işlevi adlarında dizi türleri listelenirken, toplu `Arr`önerilir.
Tüm tür dönüştürme işlevlerinin hızla tanımlanabilmesi için `As` kullanılarak adlandırılması önerilir.

# <a name="guidancetabguidance"></a>[Rehber](#tab/guidance)

Şunları öneririz:

- Bir işlev `X` türündeki bir değeri `Y`türünde bir değere dönüştürdüğünde, `AsY` ya da `XAsY`adını kullanın.

# <a name="examplestabexamples"></a>[Örnekler](#tab/examples)

|   | Adı | Açıklama |
|---|------|-------------|
| ☒ | <s>`ToDouble`</s> | "To" ön konumu, bir işlevi değil bir işlem belirten bir fiil ifadesi içinde sonuçlanır. |
| ☒ | <s>`AsDouble`</s> | Giriş türü, işlev adından net değildir. |
| ☒ | <s>`PauliArrFromBoolArr`</s> | Giriş ve çıkış türleri yanlış sırada görünüyor. |
| ☑ | `ResultArrAsBoolArr` | Hem giriş türleri hem de çıkış türleri net. |

***

### <a name="private-or-internal-names"></a>Özel veya Iç adlar ###

Çoğu durumda, bir ad bir kitaplık veya proje için dahili olarak kullanılmak üzere veya bir kitaplık tarafından sunulan API 'nin garantili bir parçası değildir.
Yalnızca iç kodda yanlışlıkla bağımlılıklara açık hale getirilmeleri için işlevleri ve işlemleri adlandırırken bu durumun büyük bir zaman olduğunu açıkça belirtmek faydalı olur.
Bir işlem veya işlev doğrudan kullanılmak üzere tasarlanmamıştır, ancak kısmi uygulama tarafından davranan, eşleşen bir çağrılabilir tarafından kullanılması gerekiyorsa, kısmen uygulanmış çağrılabilir için `_` başlayarak bir ad kullanmayı düşünün.

# <a name="guidancetabguidance"></a>[Rehber](#tab/guidance)

Şunları öneririz:

- Bir işlev, işlem veya Kullanıcı tanımlı tür, bir Q # kitaplığı veya programı için ortak API 'nin bir parçası olmadığında, adının öndeki alt çizgiyle (`_`) başladığından emin olun.

# <a name="examplestabexamples"></a>[Örnekler](#tab/examples)

|   | Adı | Açıklama |
|---|------|-------------|
| ☒ | <s>`ApplyDecomposedOperation_`</s> | Alt çizgi `_` adın sonunda görünmemelidir. |
| ☑ | `_ApplyDecomposedOperation` | Başındaki alt çizgi `_` açıkça bu işlemin yalnızca iç kullanım için olduğunu gösterir. |

***

### <a name="variants"></a>Değişken ###

Bu sınırlama gelecekteki bir soru-cevap sürümünde kalmayabilir, ancak bu durum genellikle, kendilerine ait oldukları veya bağımsız değişkenlerinin somut türleri tarafından kendilerine ait olan ilgili işlem veya işlev grupları olacaktır.
Bu gruplar, kendisini belirten bir veya iki harften sonra aynı kök adı kullanılarak ayırt edilebilir.

| Önekini | Anlamı |
|--------|---------|
| `A` | `Adjoint` desteklemesi beklenen giriş |
| `C` | `Controlled` desteklemesi beklenen giriş |
| `CA` | `Controlled` ve `Adjoint` desteklemek için giriş bekleniyor |
| `I` | Giriş veya girişler `Int` türündedir |
| `D` | Giriş veya girişler `Double` türündedir |
| `L` | Giriş veya girişler `BigInt` türündedir |

# <a name="guidancetabguidance"></a>[Rehber](#tab/guidance)

Şunları öneririz:

- Bir işlev veya işlem, girişlerinin türleri ve functor desteğiyle benzer işlevlerle veya işlemlerle ilişkili değilse, bir sonek kullanmayın.
- Bir işlev veya işlem, girişlerinin türleri ve functor desteğiyle benzer işlevlerle veya işlemlerle ilişkiliyse, sapmaları ayırt etmek için yukarıdaki tabloda olduğu gibi sonekleri kullanın.

# <a name="examplestabexamples"></a>[Örnekler](#tab/examples)

***

### <a name="arguments-and-variables"></a>Bağımsız değişkenler ve değişkenler ###

Bir işlev veya işlem için Q # kodunun anahtar hedefi kolayca okunabilme ve anlaşılmalıdır.
Benzer şekilde, giriş ve tür bağımsız değişkenlerinin adları, bir işlev veya bağımsız değişkenin sağlandığı bir şekilde nasıl kullanılacağını iletmelidir.


# <a name="guidancetabguidance"></a>[Rehber](#tab/guidance)

Şunları öneririz:

- Tüm değişken ve giriş adları için, `CamelCase`, `snake_case`veya `ANGRY_CASE`için güçlü bir tercih `pascalCase` kullanın.
- Giriş adları açıklayıcı olmalıdır; mümkün olduğunda bir veya iki harfli adlardan kaçının.
- Tam olarak bir tür bağımsız değişkeni kabul eden işlemler ve işlevler, rolü belirgin olduğunda `T` tarafından bu tür bağımsız değişkenini göstermelidir.
- Bir işlev veya işlem birden çok tür bağımsız değişkeni alırsa veya tek bir tür bağımsız değişkeninin rolü açık değilse, her tür için `T` (örn.: `TOutput`) kısa harfli bir sözcük kullanmayı düşünün.
- Bağımsız değişkene ve değişken adlarına tür adlarını eklemeyin; Bu bilgiler, geliştirme ortamınız tarafından sağlanmış ve sağlanmalıdır.
- Skalar türlerini sabit adlarına (`flagQubit`) ve dizi türlerini bir plural (`measResults`) göre gösterir.
  Belirli qubit dizileri için, adın bir şekilde daha yakından ilişkili bir qubit dizisine başvurduğu `Register`, bu tür türleri belirtmeyi göz önünde bulundurun.
- Dizilerde dizin olarak kullanılan değişkenler `idx` ile başlamalı ve tekil olmalıdır (örn.: `things[idxThing]`).
  Özellikle, tek harfli değişken adlarını dizin olarak kullanmaktan kesinlikle kaçının; en az `idx` kullanmayı göz önünde bulundurun.
- Dizi uzunluklarını tutmak için kullanılan değişkenler `n` ile başlamalı ve plurar olmalıdır (ör.: `nThings`).

# <a name="examplestabexamples"></a>[Örnekler](#tab/examples)

***

### <a name="user-defined-type-named-items"></a>Kullanıcı tanımlı tür öğe adı ###

Kullanıcı tanımlı türlerdeki adlandırılmış öğeler, UDT oluşturucularının girişinde bile `CamelCase`olarak adlandırılmalıdır.
Bu, erişimci gösterimini (ör.: `callable::Apply`) veya kopyalama ve güncelleştirme gösterimini (`set arr w/= Data <- newData`) kullanırken, adlandırılmış öğeleri yerel kapsamlı değişkenlere başvuruların açıkça ayrılması için yardımcı olur.

# <a name="guidancetabguidance"></a>[Rehber](#tab/guidance)

Şunları öneririz:

- UDT oluşturucularında adlandırılmış öğeler `CamelCase`olarak adlandırılmalıdır; diğer bir deyişle, ilk büyük harfle başlamalıdır.
- İşlemlere çözüm veren adlandırılmış öğeler fiil aşamaları olarak adlandırılmalıdır.
- İşlemlere çözümlenmez adlandırılmış öğeler, ad ifadeleri olarak adlandırılmalıdır.
- Sarmalı işlemler için `Apply` adlı tek bir adlandırılmış öğe tanımlanmalıdır.

# <a name="examplestabexamples"></a>[Örnekler](#tab/examples)

|   | Gösterildiği | Açıklama |
|---|---------|-------------|
| ☑ | `newtype Oracle = (Apply : Qubit[] => Unit is Adj + Ctl)` | `Apply` adı, adlandırılmış öğenin bir işlem olmasını öneren `CamelCase`biçimli bir fiil tümceciktir. |
| ☒ | <s>`newtype Oracle = (apply : Qubit[] => Unit is Adj + Ctl) `</s> | Adlandırılmış öğeler ilk büyük harfle başlamalıdır. |
| ☒ | <s>`newtype Collection = (Length : Int, Get : Int -> (Qubit => Unit)) `</s> | İşlevlerine çözüm veren adlandırılmış öğeler, fiil ifadeleri olarak değil, ad ifadeleri olarak adlandırılmalıdır. |

***

## <a name="input-conventions"></a>Giriş kuralları ##

Bir geliştirici bir işlem veya işleve çağırdığında, bu işlem veya işleve yönelik çeşitli girişler belirli bir sırada belirtilmelidir, bu da bir geliştiricinin bir kitaplığı kullanabilmesi için bir geliştiricinin yüzlü yükünü artırır.
Özellikle, giriş sıralamayı hatırlama görevi genellikle her seferinde bir, bir hisse algoritması uygulamasını programlama.
Zengin IDE desteği bunu büyük ölçüde azaltır, yaygın kurallara uygun tasarım ve bağlılığı, bir API tarafından uygulanan bilişsel yükün en aza indirilmesine yardımcı olabilir.

Mümkün olduğunda, bir işlem veya işlev tarafından beklenen giriş sayısını azaltmak faydalı olabilir, böylece her girdinin rolü hem bu işlem veya işlevi çağıran geliştiriciler için hem de bu kodu daha sonra okuyan geliştiriciler için daha fazla belirgin hale gelir.
Özellikle bir işlem veya işlev için bağımsız değişken sayısını azaltmak mümkün olmadığında veya makul olmadığında, bir kullanıcının giriş sırasını tahmin eden zaman şaşırmasını en aza indiren tutarlı bir sıralama olması önemlidir.

Büyük bir uygulamanın, f (x, y) ≡ f (x) (y) ile bir genelleştirme olarak düşünmekten büyük ölçüde türettiği bir giriş sıralaması kuralları öneririz.
Bu nedenle, ilk bağımsız değişkenlerin kısmen uygulanması, her ne kadar uygun olan her zaman kendi kendine yararlı bir çağrılabilir ile sonuçlanmalıdır.
Bu ilkeyi izleyerek aşağıdaki bağımsız değişken sırasını kullanmayı göz önünde bulundurun:

- Açılamayan, açıların vektörleri, üslerdeki vektörler vb. gibi çağrılabilir olmayan bağımsız değişkenler
- Çağrılabilir bağımsız değişkenler (işlevler ve bağımsız değişkenler).
  Her iki işlev ve işlem bağımsız değişken olarak götürülüyorsanız, işlemleri işlevlerden sonra yerleştirmeyi göz önünde bulundurun.
- `Map`, `Iter`, `Enumerate`ve `Fold`benzer bir şekilde çağrılabilir bağımsız değişkenlerle üzerinde işlem yapan Koleksiyonlar.
- Denetimler olarak kullanılan qubit bağımsız değişkenleri.
- Hedef olarak kullanılan qubit bağımsız değişkenleri.

Bir işlemi, bir açı ve bir Oracle alan bir dizi tahminde kullanmak üzere `ApplyPhaseEstimationIteration` değerlendirin, açısını farklı ölçekleme faktörlerinin bir dizisi tarafından değiştirilen `Rz` geçirir ve sonra Oracle 'ın uygulamalarını denetler.
Aşağıdaki şekilde `ApplyPhaseEstimationIteration` girdileri sıralarız:

```qsharp
operation ApplyPhaseEstimationIteration(
    angle : Double,
    callable : (Qubit => () is Ctl),
    scaleFactors : Double[],
    controlQubit : Qubit,
    targetQubits : Qubit[]
)
: Unit
...
```
Bazı işlevler ve işlemler aniden en aza indirmeden, bazı işlevler ve işlemler yerleşik komik `Adjoint` ve `Controlled`davranışını taklit ediyor.
Örneğin, `ControlledOnInt<'T>`, `ControlledOnInt<Qubit[]>(5, _)` `Controlled` functor gibi davranan, ancak denetim kaydının $ \demet{5} = \ayraç{101}$ durumunu temsil ettiği koşulda tür `(Int, ('T => Unit is Adj + Ctl)) => ((Qubit[], 'T) => Unit is Adj + Ctl)`sahiptir.
Bu nedenle, bir geliştirici `ControlledOnInt` girişlerinin en son dönüştürdüğünü ve sonuçta elde edilen işlemin, `Controlled` functor çıkışının ardından gelen giriş `(Qubit[], 'T)` olarak---olmasını bekler.

# <a name="guidancetabguidance"></a>[Rehber](#tab/guidance)

Şunları öneririz:

- Kısmi uygulama kullanımıyla tutarlı giriş sırası kullanın.
- Yerleşik komik ile tutarlı giriş sırası kullanın.
- Tüm klasik girişleri, tüm hisse girişlerinden önce yerleştirin.

# <a name="examplestabexamples"></a>[Örnekler](#tab/examples)

***

## <a name="documentation-conventions"></a>Belge kuralları ##

Q # dili, özel olarak biçimlendirilmiş belge açıklamalarını kullanarak işlemlere, işlevlere ve Kullanıcı tanımlı türlere belge iliştirmeye olanak tanır.
Üçlü eğik çizgi (`///`) ile belirtilen bu belge açıklamaları, her bir işlemin, işlevin ve Kullanıcı tanımlı türün amacını açıklamak için kullanılabilen küçük [Docfx-flavored markı](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html) belgeleriyle, her birinin hangi girişlerin beklediklerini açıklamak için kullanılabilir.
Hisse geliştirme seti ile sağlanan derleyici, bu açıklamaları ayıklar ve bu yorumları, https://docs.microsoft.com/quantum ' de olduğu gibi, karakterlik alan kaplamaları belgelerinin yardım 'ını kullanır.
Benzer şekilde, hisse geliştirme kiti ile birlikte sağlanan dil sunucusu, kullanıcılar için Q # kodundaki sembolleri üzerine getirdiğinde yardım sağlamak üzere bu açıklamaları kullanır.
Belge açıklamalarının kullanımı, bu belgedeki diğer kurallara göre kolayca ifade olmayan Ayrıntılar için yararlı bir başvuru sunarak kullanıcıların kod anlamlı olmasına yardımcı olabilir.

<div class="nextstepaction">
    [Belge açıklaması sözdizimi başvurusu](xref:microsoft.quantum.language.statements#documentation-comments)
</div>

Kullanıcılara yardımcı olmak üzere bu işlevselliği etkili bir şekilde kullanabilmek için, belge açıklamalarını yazarken göz önünde bulundurmanız önerilir.

# <a name="guidancetabguidance"></a>[Rehber](#tab/guidance)

Şunları öneririz:

- Her ortak işlev, işlem ve Kullanıcı tanımlı tür hemen öncesinde bir belge yorumu gelmelidir.
- En azından, her belge yorumu aşağıdaki bölümleri içermelidir:
    - Özet
    - Girdi
    - Çıkış (varsa)
- Tüm özetlerin iki cümle veya daha az olduğundan emin olun. Daha fazla oda gerekiyorsa, tüm ayrıntıların `# Summary` hemen ardından `# Description` bir bölüm sağlayın.
- Her türlü istemci, özetler içinde TeX gösterimini desteklemediği için, her ikisi de, özetler halinde matematik dahil değildir. Prose belgeleri yazarken (örn. TeX veya Markaşağı), daha uzun çizgi uzunluklarının kullanılması tercih edilebilir.
- `# Description` bölümünde tüm ilgili matematik ifadelerini sağlayın.
- Girişleri açıkladığınızda, derleyici tarafından çıkarsanabilecek ve tutarsızlık doğurabilecek şekilde her girişin türlerini tekrarlamayın.
- Her biri kendi `# Example` bölümünde örnekleri uygun şekilde girin.
- Kodu listelemeyi yapmadan önce her bir örneği kısaca açıklama yapın.
- `# References` bir bölümdeki tüm ilgili akademik yayınları (örn. incelemeler, uygulama, blog gönderileri ve alternatif uygulamalar) madde işaretli bağlantı listesi olarak belirtin.
- Mümkün olduğunda, tüm alıntı bağlantılarının kalıcı ve sabit tanımlayıcılar (Doın veya sürümlenmiş Arxıv numaraları) olduğundan emin olun.
- Bir işlem veya işlev, functor türevlerine göre diğer işlemlerle veya işlevlerle ilişkiliyse, `# See Also` bölümünde diğer çeşitleri madde işaretleri olarak listeleyin.
- Düzey 1 (`/// #`) bölümleri arasında boş bir yorum çizgisi bırakın, ancak düzey 2 (`/// ##`) bölümleri arasında boş bir satır bırakmayın.

# <a name="examplestabexamples"></a>[Örnekler](#tab/examples)

#### <a name=""></a>☑ ####

```
/// # Summary
/// Applies a rotation about the X-axis by a given angle.
///
///
/// # Description
/// This operation rotates a single qubit by the unitary operation
/// \begin{align}
///     R_x(\theta) \mathrel{:=} e^{-i \theta \sigma_x / 2}.
/// \end{align}
///
/// # Input
/// ## theta
/// Angle about which the qubit is to be rotated.
/// ## qubit
/// Qubit to which the gate should be applied.
///
/// # Remarks
/// Equivalent to:
/// ```qsharp
/// R(PauliX, theta, qubit);
/// ```
///
/// # See Also
/// - Ry
/// - Rz
operation Rx(theta : Double, qubit : Qubit) : Unit
is Adj + Ctl {
    body (...) { R(PauliX, theta, qubit); }
    adjoint (...) { R(PauliX, -theta, qubit); }
}
```

***

## <a name="formatting-conventions"></a>Biçimlendirme kuralları ##

Önceki önerilere ek olarak, tutarlı biçimlendirme kuralları kullanmak için kodun mümkün olduğunca okunabilir olmasını sağlamaya yardımcı olmak yararlı olur.
Doğası gereği bu tür biçimlendirme kuralları, kişisel aesmerkler için biraz rastgele ve kesin bir şekilde çalışır.
Nonetheless, bir ortak grup içinde tutarlı bir biçimlendirme kuralları kümesi ve özellikle de hisse geliştirme seti gibi büyük Q # projeleri için bakım yapmanızı öneririz.
Bu kurallar, Q # derleyicisi ile tümleştirilmiş biçimlendirme Aracı kullanılarak otomatik olarak uygulanabilir.

# <a name="guidancetabguidance"></a>[Rehber](#tab/guidance) 

Şunları öneririz:

- Taşınabilirlik için sekmeler yerine dört boşluk kullanın.
  Örneğin, VS Code:
  ```json
    "editor.insertSpaces": true,
    "editor.tabSize": 4
  ```
- Satır kaydırması, makul yerlerde 79 karakterden oluşmalıdır.
- İkili işleçler etrafında boşluklar kullanın.
- Tür ek açıklamaları için kullanılan iki nokta üst kısmında boşluk kullanın.
- Dizide ve tanımlama değerlerinde kullanılan virgüllerden sonra tek bir boşluk kullanın (örneğin, işlev ve işlemlere yönelik girişler).
- İşlev, işlem veya UDT adlarından sonra veya öznitelik bildirimlerinde `@` sonra boşluk kullanmayın.
- Her öznitelik bildirimi kendi satırında olmalıdır.

# <a name="examplestabexamples"></a>[Örnekler](#tab/examples)

|   | Gösterildiği | Açıklama |
|---|---------|-------------|
| ☒ | <s>`2+3`</s> | İkili işleçler etrafında boşluklar kullanın. |
| ☒ | <s>`target:Qubit`</s> | Tür ek açıklaması etrafında boşluklar kullanın. |
| ☑ | `Example(a, b, c)` | Giriş kayıt girişinde öğeler okunabilirlik için doğru aralıklıdır. |
| ☒ | <s>`Example (a, b, c)`</s> | Boşluklar, işlev, işlem veya UDT adlarından sonra bastırılmalıdır. |

***

