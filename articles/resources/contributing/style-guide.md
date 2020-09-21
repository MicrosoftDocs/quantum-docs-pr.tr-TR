---
title: Microsoft Q# Stil Kılavuzu
description: Programlar ve kitaplıklar için adlandırma, giriş, belge ve biçimlendirme kurallarını öğrenin Q# .
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.style
no-loc:
- Q#
- $$v
ms.openlocfilehash: fef3cea1c11e4fef49ddbf63adb34e07675049d2
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/21/2020
ms.locfileid: "90834202"
---
# <a name="no-locq-style-guide"></a>Q# Stil Kılavuzu #
## <a name="general-conventions"></a>Genel kurallar ##

Bu kılavuzda önerilen kurallar, Q# daha kolay okunmaları ve anlaşılması için program ve kitaplıkların yazıldığı konusunda yardımcı olmaya yöneliktir.

## <a name="guidance"></a>Rehber

Şunları öneririz:

- Kullanıcılarınız için daha okunaklı ve anlaşılır kod sağlamak üzere kasıtlı olarak yapmadığınız müddetçe hiçbir şekilde hiçbir kuralı yok saymayın.

## <a name="naming-conventions"></a>Adlandırma Kuralları ##

Hisse geliştirme setini sunan bölümünde, hisse geliştiricilerin kolayca okunabilen ve aniden en aza indirecek programlar yazmasına yardımcı olan işlev ve işlem adları için çaba duyuyoruz.
Bunun önemli bir bölümü, işlevler, işlemler ve türler için ad seçtiğimiz durumlarda, programcıların expressconcepts için kullandığı *sözlüğü* oluşturacağız; seçimlerimiz sayesinde, bunlara açık bir şekilde iletişim kurma çabalarına yardımcı olur veya bu işlemleri de destekliyoruz.
Bu, sunduğumuz adların Saklılığı yerine netlik sağlamalarını sağlamak için bize bir sorumluluk koyar.
Bu bölümde, geliştirme topluluğu tarafından en iyi şekilde buluşmamıza yardımcı olan açık yönergeler açısından bu yükümlülüğünüzü nasıl karşıladığımızdan ayrıntılıyoruz Q# .

### <a name="operations-and-functions"></a>İşlemler ve Işlevler ###

Bir adın oluşturulması gereken ilk şeylerden biri, belirli bir sembolün bir işlevi veya işlemi temsil ettiğini belirtir.
İşlevler ve işlemler arasındaki fark, bir kod bloğunun nasıl davranacağını anlamak açısından önemlidir.
İşlevler ve işlemler arasındaki ayrım ile kullanıcılara iletişim kurmak için, yan etkileri kullanılarak bu Q# modellerle eldeki işlemlere güveniyoruz.
Diğer bir deyişle, bir işlem bir işlem *yapar* .

Buna karşılık işlevler, veriler arasındaki matematik ilişkilerini tanımlar.
İfade `Sin(PI() / 2.0)` *olur* `1.0` ve bir programın veya qubits 'in durumu hakkında hiçbir şey anlamına gelir.

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
, `Apply` Ve ' de olduğu gibi fiili `ApplyIf` önerilir `ApplyToEach` `ApplyToFirst` .
Diğer fiiller, içinde olduğu gibi, bu durumda da yararlı olabilir `IterateThroughCartesianPower` .

| Fiil | Beklenen efekt |
| ---- | ------ |
| Uygula | Giriş olarak verilen bir işlem çağrılır |
| Assert | Olası bir hisse ölçüsünün sonucu hakkında bir varsayım simülatör tarafından denetlenir |
| Tahmin | Bir veya daha fazla ölçüden çizilen bir tahmini temsil eden klasik bir değer döndürüldü |
| Measure | Bir hisse ölçümü gerçekleştirilir ve sonucu kullanıcıya döndürülür |
| Hazırlama | Belirli bir qubits kaydı belirli bir duruma başlatılır |
| Örnek | Klasik bir değer, bazı dağılılardan rasgele döndürülür |

İşlevler için, fiillerin ortak isimler yerine kullanılmasını önletireceğiz (aşağıdaki doğru isimler üzerinde rehberlik) veya sıfatlar:

- `ConstantArray`
- `Head`
- `LookupFunction`

Özellikle, neredeyse her durumda, bir işlev adının bir işleme veya bir hisse senedine bağlı olarak bir eyleme bağlı olduğunu göstermek için uygun olan geçmiş participles kullanmayı öneririz.
Örneğin,  `ControlledOnInt` işlevin bağımsız değişkenini değiştirmek için bir sıfatlar olarak davrandığını göstermek için, "Control" fiilinin bölüm participle formunu kullanır.
Bu ad, `Controlled` aşağıda açıklandığı gibi yerleşik funın semantiğini eşleştirmesinin ek avantajına sahiptir.
Benzer şekilde, _Aracı isimleri_ , işlem adlarından Işlev ve udt adlarını oluşturmak için, `Encoder` kesin olarak ilişkili bir udt 'nin adı durumunda olduğu gibi kullanılabilir `Encode` .

# <a name="guidance"></a>[Rehber](#tab/guidance)

Şunları öneririz:

- İşlem adları için fiilleri kullanın.
- İşlev adları için isimleri veya sıfatları kullanın.
- Kullanıcı tanımlı türler ve öznitelikler için isimleri kullanın.
- Çağrılabilir tüm adlar için, `CamelCase` veya için güçlü bir tercih `pascalCase` kullanın `snake_case` `ANGRY_CASE` . Özellikle, çağrılabilir adların büyük harfle başlayıp başlamadiğinden emin olun.
- Tüm yerel değişkenler için, `pascalCase` veya için güçlü bir tercih `CamelCase` kullanın `snake_case` `ANGRY_CASE` . Özellikle, yerel değişkenlerin küçük harfle başlayıp başlamadiğinden emin olun.
- `_`İşlev ve işlem adlarında alt çizgi kullanmaktan kaçının; burada ek hiyerarşi düzeyleri gerekir, ad alanları ve ad alanı diğer adları kullanın.

# <a name="examples"></a>[Örnekler](#tab/examples)

| &nbsp;  | Ad | Açıklama |
|---|------|-------------|
| ☑ | `operation ReflectAboutStart` | İşlemin etkisini göstermek için bir fiil ("yansıtma") kullanımını temizleyin. |
| ☒ | <s>`operation XRotation`</s> | İsim ifadesi kullanımı, işlem yerine Function önerisinde bulunur. |
| ☒ | <s>`operation search_oracle`</s> | `snake_case`Değişken Venn Q# gösterimi kullanımı. |
| ☒ | <s>`operation Search_Oracle`</s> | Alt çizgiler iç işlem adı sınıfları Q# gösterimi kullanımı. |
| ☑ | `function StatePreparationOracle` | İsim ifadesinin kullanılması işlevin bir işlem döndürdüğünü önerir. |
| ☑ | `function EqualityFact` | Bu işlevin bir işlev olduğunu göstermek için ("olgu"), sıfatı seçimini temizleyin. |
| ☒ | <s>`function GetRotationAngles`</s> | Fiil ("Get") kullanılması bunun bir işlem olduğunu önerir. |
| ☑ | `newtype GeneratorTerm` | Ad ifadesinin kullanımı, UDT oluşturucusunun çağrılması sonucunu açıkça ifade eder. |
| ☒ | <s>`@Attribute() newtype RunOnce()`</s> | Fiil ifadesinin kullanımı, UDT oluşturucusunun bir işlem olduğunu önerir. |
| ☑ | `@Attribute() newtype Deprecated(Reason : String)` | İsim ifadesinin kullanılması özniteliğin kullanımını iletişim kurar. |

***

### <a name="entry-points"></a>Giriş Noktaları

Bir programa giriş noktası tanımlarken Q# , Q# derleyici, giriş noktalarının belirli bir ada sahip olması yerine [ `@EntryPoint()` özniteliği](xref:microsoft.quantum.core.entrypoint) tanır (ör.: `main` , `Main` , veya `__main__` ).
Diğer bir deyişle, bir Q# geliştiricinin perspektifinden giriş noktaları ile açıklanmış sıradan işlemlerdir `@EntryPoint()` .
Ayrıca, Q# giriş noktaları uygulamanın tamamı için giriş noktaları olabilir (örneğin, Q# tek başına çalıştırılabilir programlar) veya bir Q# uygulama için bir program ve ana bilgisayar programı ( Q# Python veya .NET ile kullanılırken) arasında bir arabirim olabilir. bu şekilde, "Main" adı bir giriş noktasına uygulandığında yanıltıcı olabilir Q# .

`@EntryPoint()`Yukarıda listelenen adlandırma işlemlerine yönelik genel tavsiyeler kullanılarak özniteliğin kullanımını yansıtmak için adlandırma giriş noktaları kullanmayı öneririz.


# <a name="guidance"></a>[Rehber](#tab/guidance)

Şunları öneririz:

- Giriş noktası işlemlerini "Main" olarak adlandırın.
- Giriş noktası işlemlerini sıradan işlemler olarak adlandırın.

# <a name="examples"></a>[Örnekler](#tab/examples)

| &nbsp;  | Ad | Açıklama |
|---|------|-------------|
| ☑ | `@EntryPoint() operation RunSimulation` | Giriş noktası amacını, işlem adı aracılığıyla açıkça iletir. |
| ☒ | <s>`@EntryPoint() operation Main`</s> | Kullanımı `Main` , giriş noktası amacını açıkça iletmez ve özniteliğiyle birlikte gereksizdir `@EntryPoint()` . |

***

### <a name="shorthand-and-abbreviations"></a>Özet ve kısaltmalar ###

Yukarıdaki önerinin, hisse yaramakta olan ortak ve kapsamlı kullanımı gösteren çok sayıda kısayol vardır.
Özellikle bir hedef makinenin işlemlerine iç işlemler için, var olan ve genel bir toplu işlemin bulunduğu yerde kullanmayı öneririz.
Örneğin, yerine ve yerine adını seçtik `X` `ApplyX` `Rz` `RotateAboutZ` .
Bu tür bir kısayol kullanırken, işlem adları tümü büyük harfle yazılmalıdır (ör.: `MAJ` ).

Bu kural, yaygın olarak kullanılan kısaltmalar ve başlangıçlar söz konusu olduğunda "hisse Fourier dönüştürmesi" için "QFT" gibi bazı durumlarda gereklidir.
Tam adlarda kısaltmalar ve ınitialisms 'lerin kullanılması için aşağıdaki genel .NET kurallarını öneririz:

- iki harfli kısaltmalar ve ınitialisms büyük harfle adlandırılır (örn. `BE` "Big-endian" için),
- daha uzun kısaltmalar ve ınitialisms 'ler içinde adlandırılır `CamelCase` (örn. `Qft` "hisse Fourier dönüştürmesi" için)

Bu nedenle, QFT 'yi uygulayan bir işlem `QFT` , toplu olarak çağrılabilir ya da olarak yazılabilir `ApplyQft` .

Özellikle yaygın olarak kullanılan işlemler ve işlevler için daha uzun bir form için bir _diğer_ ad olarak bir kısayol adı sağlanması istenebilir:

```qsharp
operation CCNOT(control0 : Qubit, control1 : Qubit, target : Qubit)
is Adj + Ctl {
    Controlled X([control0, control1], target);
}
```

# <a name="guidance"></a>[Rehber](#tab/guidance)

Şunları öneririz:

- Uygun olduğunda genellikle kabul edilen ve yaygın olarak kullanılan toplu adları göz önünde bulundurun.
- Toplu değer için büyük harf kullanın.
- Kısa (iki harfli) kısaltmalar ve ınitialisms için büyük harf kullanın.
- Daha `CamelCase` uzun (üç veya daha fazla harf) kısaltmalar ve ınitialisms için kullanın.

# <a name="examples"></a>[Örnekler](#tab/examples)

| &nbsp;   | Ad | Açıklama |
|---|------|-------------|
| ☑ | `X` | "Bir $X $ dönüşümü Uygula" için iyi anlaşılan toplu değer |
| ☑ | `CNOT` | "Denetimli-NOT" için iyi anlaşılan toplu değer |
| ☒ | <s>`Cnot`</s> | Kısayol içinde olmamalıdır `CamelCase` . |
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
Belirli bir örnek olarak, listedir denetimli takas ve yerleşik olmayan işlemler genellikle akademik belgelerinde "Fredkabağı" ve "Toffoli" işlemleri olarak adlandırılır, ancak Q# temelde ve olarak tanımlanmıştır `CSWAP` `CCNOT` .
Her iki durumda da, API belgesi açıklamaları uygun adlara göre eş anlamlı adlar sağlar ve tüm uygun alıntıları birlikte kapsar.

Bu tercih, bazı uygun isimler kullanımının her zaman gerekli olacağı bir Q# şekilde önemlidir. Örneğin, gelenek için birçok klasik dil tarafından ayarlanan (örneğin,) ve daha sonra `Bool` George Boole 'in içinde adı verilen Boolean mantığına başvuruda bulunan türlere başvurur.
Benzer şekilde, dilin yerleşik türü de dahil olmak üzere, benzer bir şekilde adlandırılmış birkaç hisse kavram kavramı `Pauli` Q# .
Bu kullanım açısından gerekli olan doğru isimler kullanımını en aza indirerek, doğru isimleri kabul etmeyeceğinden etkiyi azalttık.

# <a name="guidance"></a>[Rehber](#tab/guidance) 

Şunları öneririz:

- Adlarda doğru isimler kullanmaktan kaçının.

# <a name="examples"></a>[Örnekler](#tab/examples)

***

### <a name="type-conversions"></a>Tür Dönüştürmeleri ###

Q#Kesin ve statik olarak yazılmış bir dil olduğundan, bir tür değeri yalnızca bir tür dönüştürme işlevine açık bir çağrı kullanılarak başka bir türün değeri olarak kullanılabilir.
Bu, değerlerin örtük olarak (ör. tür promosyonu) veya atama yoluyla türlerin değiştirilmesini sağlayan dillere karşılık gelir.
Sonuç olarak, tür dönüştürme işlevleri kitaplık geliştirmede önemli bir rol oynar Q# ve adlandırma hakkında yaygın olarak karşılaşılan kararlardan birini içerir.
Ancak, tür dönüştürmeleri her zaman _belirleyici_olduğundan, bunlar işlev olarak yazılabilecekleri ve bu nedenle yukarıdaki önerinin altına düşecek.
Özellikle, tür dönüştürme işlevlerinin hiçbir şekilde fiiller (ör.: `ConvertToX` ) veya duyurusu b önceden konumsal tümceleri () olarak adlandırılmaması önerilir `ToX` , ancak kaynak ve hedef türlerini belirten sıfatıcı önceden konumsal ifadeler olarak adlandırılmalıdır ( `XAsY` ).
Tür dönüştürme işlevi adlarında dizi türleri listelenirken, Stenk önerilir `Arr` .
Tüm tür dönüştürme işlevlerinin, `As` hızlı bir şekilde tanımlanabilmesi için kullanılarak adlandırılması önerilir.

# <a name="guidance"></a>[Rehber](#tab/guidance)

Şunları öneririz:

- Bir işlev, türünde bir değeri `X` türünde bir değere dönüştürdüğünde `Y` , adını `AsY` veya kullanın `XAsY` .

# <a name="examples"></a>[Örnekler](#tab/examples)

| &nbsp;   | Ad | Açıklama |
|---|------|-------------|
| ☒ | <s>`ToDouble`</s> | "To" ön konumu, bir işlevi değil bir işlem belirten bir fiil ifadesi içinde sonuçlanır. |
| ☒ | <s>`AsDouble`</s> | Giriş türü, işlev adından net değildir. |
| ☒ | <s>`PauliArrFromBoolArr`</s> | Giriş ve çıkış türleri yanlış sırada görünüyor. |
| ☑ | `ResultArrAsBoolArr` | Hem giriş türleri hem de çıkış türleri net. |

***

### <a name="private-or-internal-names"></a>Özel veya Iç adlar ###

Çoğu durumda, bir ad bir kitaplık veya proje için dahili olarak kullanılmak üzere veya bir kitaplık tarafından sunulan API 'nin garantili bir parçası değildir.
Yalnızca iç kodda yanlışlıkla bağımlılıklara açık hale getirilmeleri için işlevleri ve işlemleri adlandırırken bu durumun büyük bir zaman olduğunu açıkça belirtmek faydalı olur.
Bir işlem veya işlev doğrudan kullanıma yönelik değildir, ancak bunun yerine kısmi uygulama tarafından davranan, eşleşen bir çağrılabilir tarafından kullanılması gerekiyorsa, `internal` kısmen uygulanan çağrılabilir anahtar sözcüğüyle başlayan bir ad kullanmayı düşünün.

# <a name="guidance"></a>[Rehber](#tab/guidance)

Şunları öneririz:

- Bir işlev, işlem veya Kullanıcı tanımlı tür bir kitaplık veya program için ortak API 'nin bir parçası olmadığında, Q# `internal` anahtar sözcüğünü `function` , `operation` veya bildiriminden önce yerleştirerek iç olarak işaretlendiğinden emin olun `newtype` .

# <a name="examples"></a>[Örnekler](#tab/examples)

| &nbsp;  | Ad | Açıklama |
|---|------|-------------|
| ☒ | <s>`operation _ApplyDecomposedOperation`</s> | `_`Bu işlemin yalnızca iç kullanım için olduğunu göstermek için alt çizgi kullanmayın. |
| ☑ | `internal operation ApplyDecomposedOperation` | `internal`Başındaki anahtar sözcük açıkça bu işlemin yalnızca iç kullanım için olduğunu gösterir. |

***
### <a name="variants"></a>Değişkenler ###

Bu sınırlama gelecekteki sürümlerinde kalmayabilir, ancak bu durum genellikle, kendilerine ait oldukları ve onların Q# bağımsız değişkenlerinin somut türleri tarafından kendilerine ait olan ilgili işlem veya işlev grupları olacaktır.
Bu gruplar, kendisini belirten bir veya iki harften sonra aynı kök adı kullanılarak ayırt edilebilir.

| Önekini | Anlamı |
|--------|---------|
| `A` | Destek için giriş bekleniyor `Adjoint` |
| `C` | Destek için giriş bekleniyor `Controlled` |
| `CA` | Destek için giriş bekleniyordu `Controlled` ve `Adjoint` |
| `I` | Giriş veya girişler tür `Int` |
| `D` | Giriş veya girişler tür `Double` |
| `L` | Giriş veya girişler tür `BigInt` |

# <a name="guidance"></a>[Rehber](#tab/guidance)

Şunları öneririz:

- Bir işlev veya işlem, girişlerinin türleri ve functor desteğiyle benzer işlevlerle veya işlemlerle ilişkili değilse, bir sonek kullanmayın.
- Bir işlev veya işlem, girişlerinin türleri ve functor desteğiyle benzer işlevlerle veya işlemlerle ilişkiliyse, sapmaları ayırt etmek için yukarıdaki tabloda olduğu gibi sonekleri kullanın.

# <a name="examples"></a>[Örnekler](#tab/examples)

***

### <a name="arguments-and-variables"></a>Bağımsız değişkenler ve değişkenler ###

Q#Bir işlev veya işlem için kodun önemli hedefi kolayca okunabilme ve anlaşılmalıdır.
Benzer şekilde, giriş ve tür bağımsız değişkenlerinin adları, bir işlev veya bağımsız değişkenin sağlandığı bir şekilde nasıl kullanılacağını iletmelidir.


# <a name="guidance"></a>[Rehber](#tab/guidance)

Şunları öneririz:

- Tüm değişken ve giriş adları için, `pascalCase` veya için güçlü bir tercih içinde kullanın `CamelCase` `snake_case` `ANGRY_CASE` .
- Giriş adları açıklayıcı olmalıdır; mümkün olduğunda bir veya iki harfli adlardan kaçının.
- Tam olarak bir tür bağımsız değişkeni kabul eden işlemler ve işlevler, rolü belirgin olduğunda bu tür bağımsız değişkenini göstermelidir `T` .
- Bir işlev veya işlem birden çok tür bağımsız değişkeni alırsa veya tek bir tür bağımsız değişkeninin rolü açık değilse, `T` her tür için (ör.:) kısa harfli bir sözcük kullanmayı düşünün `TOutput` .
- Bağımsız değişkene ve değişken adlarına tür adlarını eklemeyin; Bu bilgiler, geliştirme ortamınız tarafından sağlanmış ve sağlanmalıdır.
- Skalar türlerini, sabit adlarına ( `flagQubit` ) ve dizi türlerini bir plural () ile gösterir `measResults` .
  Belirli qubit dizileri için, bu tür türleri `Register` , adın bir şekilde daha yakından ilişkili bir qubit dizisine başvurduğu şekilde belirtmeyi düşünün.
- Dizilerde dizin olarak kullanılan değişkenler, ile başlamalı `idx` ve tekil olmalıdır (ör.: `things[idxThing]` ).
  Özellikle, tek harfli değişken adlarını dizin olarak kullanmaktan kesinlikle kaçının; En azından kullanmayı göz önünde bulundurun `idx` .
- Dizi uzunluklarını tutmak için kullanılan değişkenler, ile başlamalı `n` ve plurar (ör.: `nThings` ) olmalıdır.

# <a name="examples"></a>[Örnekler](#tab/examples)

***

### <a name="user-defined-type-named-items"></a>Kullanıcı tanımlı tür öğeleri ###

Kullanıcı tanımlı türlerdeki adlandırılmış öğeler `CamelCase` , udt oluşturucularının girişinde bile olarak adlandırılmalıdır.
Bu, erişimci gösterimini (ör.: `callable::Apply` ) veya kopyalama ve güncelleştirme gösterimini () kullanırken, adlandırılmış öğeleri yerel kapsamlı değişkenlere göre açıkça ayırmak için yardımcı olur `set arr w/= Data <- newData` .

# <a name="guidance"></a>[Rehber](#tab/guidance)

Şunları öneririz:

- UDT oluşturucularında adlandırılmış öğeler olarak adlandırılmalıdır `CamelCase` ; diğer bir deyişle, ilk büyük harfle başlamalıdır.
- İşlemlere çözüm veren adlandırılmış öğeler fiil aşamaları olarak adlandırılmalıdır.
- İşlemlere çözümlenmez adlandırılmış öğeler, ad ifadeleri olarak adlandırılmalıdır.
- Sarmalı işlemler için, adlı tek bir adlandırılmış öğe `Apply` tanımlanmalıdır.

# <a name="examples"></a>[Örnekler](#tab/examples)

| &nbsp;  | Kod Parçacığı | Açıklama |
|---|---------|-------------|
| ☑ | `newtype Oracle = (Apply : Qubit[] => Unit is Adj + Ctl)` | Ad, `Apply` `CamelCase` adlandırılmış öğenin bir işlem olmasını öneren, biçimli bir fiil tümceciktir. |
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
- ,, Ve için benzer bir şekilde çağrılabilir bağımsız değişkenlerle üzerinde işlem yapan koleksiyonlar `Map` `Iter` `Enumerate` `Fold` .
- Denetimler olarak kullanılan qubit bağımsız değişkenleri.
- Hedef olarak kullanılan qubit bağımsız değişkenleri.

Bir `ApplyPhaseEstimationIteration` açıyı, bir açı ve Oracle alan bir işlem tahminlerinde kullanmak için bir işlem düşünün, açıyı `Rz` farklı ölçekleme faktörleri dizisiyle geçirir ve sonra Oracle 'ın uygulamalarını denetler.
Girişleri `ApplyPhaseEstimationIteration` aşağıdaki biçimde sıraya ekleyeceğiz:

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
Bazı işlevler ve işlemler beklenmedik bir şekilde en aza indirildiği için, bazı işlevler ve işlemler yerleşik komik ve ' ın davranışını taklit ediyor `Adjoint` `Controlled` .
Örneğin, `ControlledOnInt<'T>` `(Int, ('T => Unit is Adj + Ctl)) => ((Qubit[], 'T) => Unit is Adj + Ctl)` `ControlledOnInt<Qubit[]>(5, _)` functor gibi davranan, `Controlled` ancak denetim kaydının $ \ket {5} = \ket $ durumunu temsil ettiği koşulda, türü vardır {101} .
Bu nedenle, bir geliştirici, `ControlledOnInt` çağrılabilir 'in, en son dönüştürülmüş değerini yerleştirmesini ve sonuçta elde edilen işlemin giriş---, diğer bir deyişle, `(Qubit[], 'T)` functor çıkışı tarafından aynı sırada sürdüğünü bekler `Controlled` .

# <a name="guidance"></a>[Rehber](#tab/guidance)

Şunları öneririz:

- Kısmi uygulama kullanımıyla tutarlı giriş sırası kullanın.
- Yerleşik komik ile tutarlı giriş sırası kullanın.
- Tüm klasik girişleri, tüm hisse girişlerinden önce yerleştirin.

# <a name="examples"></a>[Örnekler](#tab/examples)

***

## <a name="documentation-conventions"></a>Belge kuralları ##

Q#Dil, özel olarak biçimlendirilmiş belge açıklamalarını kullanarak işlemler, işlevler ve Kullanıcı tanımlı türlere belge iliştirmeye olanak tanır.
Üçlü eğik çizgi () tarafından belirtilen `///` Bu belge Yorumları, her bir işlemin, işlevin ve Kullanıcı tanımlı türün amacını açıklamak için kullanılabilen küçük [docfx-flavored](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html) , her beklediği girişi, vb..
Hisse geliştirme seti ile sağlanan derleyici, bu açıklamaları ayıklar ve bu yorumları, ' deki şuna benzer şekilde karakterlik alan kaplamaları belgelerine yardımcı olmak için kullanır https://docs.microsoft.com/quantum .
Benzer şekilde, hisse geliştirme kiti ile sağlanan dil sunucusu, kullanıcıların kodlarında sembolleri üzerine geldiğinde kullanıcılara yardım sağlamak için bu açıklamaları kullanır Q# .
Belge açıklamalarının kullanımı, bu belgedeki diğer kurallara göre kolayca ifade olmayan Ayrıntılar için yararlı bir başvuru sunarak kullanıcıların kod anlamlı olmasına yardımcı olabilir.

> [!div class="nextstepaction"]
> [Belge açıklaması sözdizimi başvurusu](xref:microsoft.quantum.guide.filestructure#documentation-comments).

Kullanıcılara yardımcı olmak üzere bu işlevselliği etkili bir şekilde kullanabilmek için, belge açıklamalarını yazarken göz önünde bulundurmanız önerilir.

# <a name="guidance"></a>[Rehber](#tab/guidance)

Şunları öneririz:

- Her ortak işlev, işlem ve Kullanıcı tanımlı tür hemen öncesinde bir belge yorumu gelmelidir.
- En azından, her belge yorumu aşağıdaki bölümleri içermelidir:
    - Özet
    - Giriş
    - Çıkış (varsa)
- Tüm özetlerin iki cümle veya daha az olduğundan emin olun. Daha fazla oda gerekiyorsa, `# Description` tüm ayrıntılarla hemen takip eden bir bölüm sağlayın `# Summary` .
- Her türlü istemci, özetler içinde TeX gösterimini desteklemediği için, her ikisi de, özetler halinde matematik dahil değildir. Prose belgeleri yazarken (örn. TeX veya Markaşağı), daha uzun çizgi uzunluklarının kullanılması tercih edilebilir.
- Bölümündeki tüm ilgili matematik ifadelerini belirtin `# Description` .
- Girişleri açıkladığınızda, derleyici tarafından çıkarsanabilecek ve tutarsızlık doğurabilecek şekilde her girişin türlerini tekrarlamayın.
- Her biri kendi bölümünde uygun şekilde örnekler sağlayın `# Example` .
- Kodu listelemeyi yapmadan önce her bir örneği kısaca açıklama yapın.
- Bir bölümdeki tüm ilgili akademik yayınları (örn. incelemeler, devam edimler, blog gönderileri ve alternatif uygulamalar) `# References` madde işaretli bağlantı listesi olarak belirtin.
- Mümkün olduğunda, tüm alıntı bağlantılarının kalıcı ve sabit tanımlayıcılar (Doın veya sürümlenmiş Arxıv numaraları) olduğundan emin olun.
- Bir işlem veya işlev, functor türevlerine göre diğer işlemlerle veya işlevlerle ilişkiliyse, diğer çeşitleri bölümünde madde işaretleri olarak listeleyin `# See Also` .
- Level-1 () bölümleri arasında boş bir yorum çizgisi bırakın `/// #` , ancak Level-2 () bölümleri arasında boş bir satır bırakmayın `/// ##` .

# <a name="examples"></a>[Örnekler](#tab/examples)

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
Nonetheless, bir ortak grup içinde tutarlı bir biçimlendirme kuralları kümesi ve özellikle de Q# hisse geliştirme setinin kendisi gibi büyük projeler için bakım yapmanızı öneririz.
Bu kurallar, derleyici ile tümleşik biçimlendirme Aracı kullanılarak otomatik olarak uygulanabilir Q# .

# <a name="guidance"></a>[Rehber](#tab/guidance) 

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
- İşlev, işlem veya UDT adlarından sonra veya `@` öznitelik bildirimlerinden sonra boşluk kullanmayın.
- Her öznitelik bildirimi kendi satırında olmalıdır.

# <a name="examples"></a>[Örnekler](#tab/examples)

| &nbsp; | Kod Parçacığı | Açıklama |
|---|---------|-------------|
| ☒ | <s>`2+3`</s> | İkili işleçler etrafında boşluklar kullanın. |
| ☒ | <s>`target:Qubit`</s> | Tür ek açıklaması etrafında boşluklar kullanın. |
| ☑ | `Example(a, b, c)` | Giriş kayıt girişinde öğeler okunabilirlik için doğru aralıklıdır. |
| ☒ | <s>`Example (a, b, c)`</s> | Boşluklar, işlev, işlem veya UDT adlarından sonra bastırılmalıdır. |

***
