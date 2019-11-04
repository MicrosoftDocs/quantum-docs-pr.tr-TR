---
title: 'S # deyimleri | Microsoft Docs'
description: 'Q # deyimleri'
author: QuantumWriter
uid: microsoft.quantum.language.statements
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 5bcbee868c76aaf53d0b7969e6e634da62689aaa
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2019
ms.locfileid: "73184874"
---
# <a name="statements-and-other-constructs"></a>Deyimler ve diğer yapılar

## <a name="comments"></a>Yorumlar

Açıklamalar iki eğik çizgi ile başlar, `//`ve satır sonuna kadar devam eder.
Bir soru, Q # kaynak dosyasında herhangi bir yerde görünebilir.

### <a name="documentation-comments"></a>Belge açıklamaları

Üç eğik çizgi ile başlayan açıklamalar, `///`, bir ad alanı, işlem, özelleştirme, işlev veya tür tanımından hemen önce görüntülendiklerinde derleyici tarafından özellikle işlenir.
Bu durumda, içeriği diğer .NET dilleri gibi tanımlanmış çağrılabilir veya Kullanıcı tanımlı tür için belgeler olarak alınır.

`///` açıklamaları içinde, API belgelerinin bir parçası olarak görünen metin, özel olarak adlandırılan üstbilgiler tarafından belirtilen belgelerin farklı bölümleriyle [Markaşağı](https://daringfireball.net/projects/markdown/syntax)olarak biçimlendirilir.
Markı 'nin bir uzantısı olarak, Q # içindeki işlemlere, işlevlere ve Kullanıcı tanımlı türlere çapraz başvurular `@"<ref target>"`kullanılarak dahil edilebilir. burada `<ref target>`, başvurulan kod nesnesinin tam adı ile değiştirilmiştir.
İsteğe bağlı olarak, bir belge altyapısı ek markı uzantılarını da destekleyebilir.

Örnek:

```qsharp
/// # Summary
/// Given an operation and a target for that operation,
/// applies the given operation twice.
///
/// # Input
/// ## op
/// The operation to be applied.
/// ## target
/// The target to which the operation is to be applied.
///
/// # Type Parameters
/// ## 'T
/// The type expected by the given operation as its input.
///
/// # Example
/// ```Q#
/// // Should be equivalent to the identity.
/// ApplyTwice(H, qubit);
/// ```
///
/// # See Also
/// - Microsoft.Quantum.Intrinsic.H
operation ApplyTwice<'T>(op : ('T => Unit), target : 'T) : Unit
{
    op(target);
    op(target);
}
```

Aşağıdaki adlar belge açıklama üstbilgileri olarak tanınır.

- **Özet**: bir işlev veya işlemin davranışının veya bir tür amacının kısa özeti. Özetin ilk paragrafı, üzerine gelme bilgileri için kullanılır. Düz metin olmalıdır.
- **Açıklama**: bir işlevin veya işlemin davranışının veya bir türün amacının açıklaması. Özet ve açıklama, işlev, işlem veya tür için üretilen belge dosyasını oluşturacak şekilde birleştirilir.
  Açıklama, satır içi LaTeX biçimli sembolleri ve denklemleri içerebilir.
- **Giriş**: bir işlemin veya işlevin giriş kayıt düzeninin açıklaması.
  Giriş kayıt düzeni öğelerinin her birini belirten ek Markup alt bölümleri içerebilir.
- **Output**: bir işlem veya işlev tarafından döndürülen tanımlama grubunun açıklaması.
- **Tür parametreleri**: her genel tür parametresi için bir ek alt bölüm içeren boş bir bölüm.
- **Örnek**: işlemin, işlevin veya tür kullanılan kısa bir örnek.
- **Açıklamalar**: işlemin, işlevin veya türün bazı yönlerini açıklayan çeşitli işlemler.
- **Ayrıca bkz**: ilgili işlevleri, işlemleri veya Kullanıcı tanımlı türleri gösteren tam nitelikli adların listesi.
- **Başvurular**: belgelendirilmekte olan öğe için başvuruların ve alıntıların listesi.

## <a name="namespaces"></a>Ad Alanları

Her Q # işlem, işlev ve Kullanıcı tanımlı tür bir ad alanı içinde tanımlanır.
Q #, diğer .NET dilleri olarak adlandırmayla aynı kuralları izler.
Ancak, Q # ad alanlarına göreli başvuruları desteklemez.
Diğer bir deyişle, ad alanı `a.b` açıldıysa, `c.d` bir işlem adları başvurusu, tam adı `a.b.c.d`olan bir işleme çözümlenmeyecektir.

Bir ad alanı bloğunda, belirli bir ad alanında belirtilen tüm türleri ve callabları içeri aktarmak için `open` yönergesi kullanılabilir ve bunlara nitelenmemiş adlarıyla başvurabilirler. İsteğe bağlı olarak, açık ad alanı için bir kısa ad, bu ad alanındaki tüm öğelerin tanımlanmış kısa ad ile nitelendirilerek (ve gerek olması) tanımlanabilir. `open` yönergesi, bir dosya içindeki tüm ad alanı bloğunun tamamına uygulanır.

Geçerli ad alanında açılmamış başka bir ad alanında tanımlanan bir tür veya çağrılabilir, tam nitelikli ad tarafından başvurulmalıdır.
Örneğin, `X.Y` ad alanındaki `Op` adlı bir işleme, `X.Y` ad alanı geçerli blokta daha önce açılmadığı müddetçe, tam adı `X.Y.Op`tarafından başvurulmalıdır. Yukarıda belirtildiği gibi, `X` ad alanı açılmış olsa bile, işleme `Y.Op`olarak başvurulmayabilir.
`X.Y` için `Z` kısa bir ad, bu ad alanında ve dosyada tanımlanmışsa, `Op` `Z.Op`olarak başvurulduğu gerekir. 

```qsharp
namespace NS {

    open Microsoft.Quantum.Intrinsic; // opens the namespace
    open Microsoft.Quantum.Math as Math; // defines a short name for the namespace
}
```

`open` yönergesini kullanarak bir ad alanı eklemek genellikle daha iyidir.
İki ad alanı aynı ada sahip yapıları tanımladıysa ve geçerli kaynak yapıları her ikisiyle kullanıyorsa, tam nitelikli ad kullanılması gerekir.

## <a name="formatting"></a>Biçimlendirme

Çoğu Q # deyimi ve yönergeleri sonlandırma noktalı virgülle biter `;`.
Bir deyim bloğu ile biten `for` ve `operation` gibi deyimler ve bildirimler sonlandırma noktalı virgül gerektirmez.
Her bir ifade açıklaması, Sonlandırıcı noktalı virgülden gerekli olup olmadığını not edin.

İfadeler, bildirimler ve yönergeler gibi deyimler birden çok satıra ayrılabilir.
Tek bir satırda birden çok deyimin olması kaçınılmalıdır.

## <a name="statement-blocks"></a>Ekstre blokları

Q # deyimleri deyim blokları halinde gruplandırılır.
Bir ifade bloğu, açma `{` başlar ve bir kapanış `}`ile biter.

Başka bir blok içinde Sözcüksel olarak bulunan bir ifade bloğu, kapsayan bloğun bir alt bloğu olarak kabul edilir; içerilen ve alt bloklara dış ve iç bloklar de denir.

## <a name="symbol-binding-and-assignment"></a>Sembol bağlama ve atama

S # kesilebilir ve değişmez semboller arasında ayrım yapar.
Genellikle, derleyicinin daha iyi iyileştirmeler gerçekleştirmesini sağladığından, değişmez sembollerin kullanılması önerilir.

Bağlamanın sol tarafı bir sembol tanımlama grubu ve bir ifadenin sağ tarafından oluşur.

Tüm Q # türleri değer türleri olduğundan ve bir özel rol alan qubits ile, bir değer bir simgeye bağlandığında veya bir sembol yeniden bağlandığında bir "kopya" oluşturulur. Yani, Q # davranışı atamadaki bir kopyanın oluşturulmasıyla aynı olur. Bu özellikle de diziler içerir. Pratikte yalnızca ilgili parçalar gerektiği şekilde yeniden oluşturulur. 

### <a name="tuple-deconstruction"></a>Demet oluşturmayı kaldırma

Bağlamanın sağ tarafı bir tanımlama grubu ise, bu kayıt düzeni atama sonrasında oluşturulabilir.
Bu tür ayrıştırmaları iç içe geçmiş tanımlama gruplarını içerebilir ve sağ taraftaki tanımlama grubunun şekli sembol tanımlama grubu şekli ile uyumlu olduğu sürece herhangi bir tam veya kısmi kaldırma geçerli olur.
Kayıt düzeni, `=` sağ tarafı bir demet değerli ifade olduğunda da kullanılabilir.

```qsharp
let (i, f) = (5, 0.1); // i is bound to 5 and f to 0.1
mutable (a, (_, b)) = (1, (2, 3)); // a is bound to 1, b is bound to 3
mutable (x, y) = ((1, 2), [3, 4]); // x is bound to (1,2), y is bound to [3,4]
set (x, _, y) = ((5, 6), 7, [8]);  // x is rebound to (5,6), y is rebound to [8]
let (r1, r2) = MeasureTwice(q1, PauliX, q2, PauliY);
```

### <a name="immutable-symbols"></a>Sabit semboller

Değişmez semboller `let` ifadesiyle ilişkilidir.
Bu, her ne kadar C#soru-cevap, bu, örneğin, bir kez bağlantılı olan Q # sembolleri değiştirilmedikçe, değişken bildirimine ve başlatmaya eşittir. `let` bağlamaları sabittir.

Değişmez bir bağlama, bir sembol veya sembol kümesi, eşittir işareti `=`, sembolleri bağlamak için bir ifade ve sondaki noktalı virgülden oluşan `let`anahtar sözcükten oluşur.
Bağlı sembol (ler) in türü sağ taraftaki ifadeye göre belirlenir.

### <a name="mutable-symbols"></a>Değişebilir semboller

Kesilebilir semboller `mutable` ifadesiyle tanımlanır ve başlatılır.
`mutable` deyimin bir parçası olarak belirtilen ve bağlantılı semboller kodun ilerleyen kısımlarında farklı bir değere yeniden bağlanabilir. 

Kesilebilir bağlama deyimi, bir sembol veya sembol kümesi, eşittir işareti `=`, sembolleri bağlamak için bir ifade ve sondaki noktalı virgülden oluşan `mutable`anahtar sözcükten oluşur.
Bağlı sembol (ler) in türü sağ taraftaki ifadeye göre belirlenir. Bir sembol kodun ilerleyen kısımlarında yeniden bağlanmışsa, türü değişmez ve bağlanan değerin bu türle uyumlu olması gerekir.

### <a name="rebinding-of-mutable-symbols"></a>Kesilebilir sembolleri yeniden bağlama

Kesilebilir değişken, bir `set` ifadesiyle yeniden bağlanabilir.
Bu tür bir yeniden bağlama, arkasından bir sembol veya sembol kümesi, eşittir işareti `=`, sembolleri yeniden bağlamak için bir ifade ve bir sonlandırma noktalı virgülle oluşur `set`.
Değer, bağlandığı sembolün (ler) türüyle uyumlu olmalıdır.

#### <a name="apply-and-reassign-statement"></a>Apply ve-yeniden atama ekstresi

Bir Apply ve-reassıgn olarak adlandırdığımız belirli bir set-deyimin türü, sağ taraftaki bir ikili işleç uygulamasından oluşuyorsa ve sonuç işlecin sol bağımsız değişkenine yeniden bağlanılacağından, birleştirme işlemi için uygun bir yol sağlar. Örneğin,
```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter += 1;
    // ...
}
```
`for` döngüsünün her yinelemesinde sayaç `counter` değerini artırır. Yukarıdaki kod şu şekilde eşdeğerdir 
```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter = counter + 1;
    // ...
}
```
Benzer deyimler, sol taraftaki türün ifade türüyle eşleştiği tüm ikili işleçler için kullanılabilir. Bu, örneğin değerleri biriktirmek için kullanışlı bir yol sağlar:
```qsharp
mutable results = new Result[0];
for (q in qubits) {
    set results += [M(q)];
    // ...
}
```
#### <a name="update-and-reassign-statement"></a>Update-ve-yeniden atama ekstresi

Sağ taraftaki kopyalama ve güncelleştirme ifadeleri için benzer bir birleştirme bulunur. Kullanıcı tanımlı türlerde ve dizi öğelerinde adlandırılmış öğeler için birlikte, Update-ve-yeniden ata deyimleri mevcuttur.  

```qsharp
newtype Complex = (Re : Double, Im : Double);

function AddAll (reals : Double[], ims : Double[]) : Complex[] {
    mutable res = Complex(0.,0.);

    for (r in reals) {
        set res w/= Re <- res::Re + r; // update-and-reassign statement
    }
    for (i in ims) {
        set res w/= Im <- res::Im + i; // update-and-reassign statement
    }
    return res;
}
```

Diziler söz konusu olduğunda standart kitaplıklarımız birçok yaygın dizi başlatma ve işleme ihtiyacı için gerekli araçları içerir ve bu nedenle dizi öğelerini ilk yerde güncelleştirmek zorunda kalmamak için yardımcı olur. Update-ve-yeniden ata deyimleri gerekirse bir alternatif sağlar:

```qsharp
operation RandomInts(maxInt : Int, nrSamples : Int) : Int[] {

    mutable samples = new Double[0];
    for (i in 1 .. nrSamples) {
        set samples += [RandomInt(maxInt)];
    }
    return samples;
}

operation SampleUniformDistr(nrSamples : Int, prec : Int) : Double[] {

    let normalization = 1. / IntAsDouble(prec);
    mutable samples = RandomInts(prec, nrSamples);
    
    for (i in IndexRange(samples) {
        let value = IntAsDouble(samples[i]);
        set samples w/= i <- normalization * value; // update-and-reassign statement
    }
}

```

> [!TIP]   
> <xref:microsoft.quantum.arrays>' de sunulan araçlardan yararlanarak Update ve-yeniden atama deyimlerinin gereksiz bir şekilde kullanılmasını önleyin.

İşlevi
```qsharp
function EmbedPauli (pauli : Pauli, location : Int, n : Int) : Pauli[]
{
    mutable pauliArray = new Pauli[n];
    for (index in 0 .. n - 1) {
        set pauliArray w/= index <- 
            index == location ? pauli | PauliI;
    }    
    return pauliArray;
}
```
Örneğin, `Microsoft.Quantum.Arrays``ConstantArray` işlevini kullanarak basit bir şekilde basitleştirilebilir ve bir kopya ve güncelleştirme ifadesi getirebilirsiniz:

```qsharp
function EmbedPauli (pauli : Pauli, i : Int, n : Int) : Pauli[] {
    return ConstantArray(n, PauliI) w/ i <- pauli;
}
```

### <a name="binding-scopes"></a>Kapsamları bağlama

Genel olarak, sembol bağlamaları kapsam dışına çıkar ve içinde oluştuğu deyim bloğunun sonunda çalışır duruma gelir.
Bu kuralın iki özel durumu vardır:

- Bir `for` döngüsünün döngü değişkeninin bağlaması, for döngüsünün gövdesinden, ancak döngünün sonundan sonra değil.
- Bir `repeat`/`until` döngüsünün üç bölümü (gövde, test ve düzeltme) tek bir kapsam olarak değerlendirilir, bu nedenle gövdede bağlanan semboller testte ve düzeltmede kullanılabilir.

Her iki döngü türü için, döngüden geçen her bir geçiş kendi kapsamında yürütülür, bu nedenle önceki bir geçişte bağlamalar daha sonraki bir geçişte kullanılamaz.

Dış bloklarında sembol bağlamaları iç bloklar tarafından devralınır.
Bir sembol, blok başına yalnızca bir kez bağlanabilir; kapsam içindeki başka bir sembolle aynı ada sahip bir sembol tanımlamak geçersizdir ("gölgeleme" yoktur).
Aşağıdaki diziler geçerli olacaktır:

```qsharp
if (a == b) {
    ...
    let n = 5;
    ...             // n is 5
}
let n = 8;
...                 // n is 8
```

'nı ve

```qsharp
if (a == b) {
    ...
    let n = 5;
    ...             // n is 5
} else {
    ...
    let n = 8;
    ...             // n is 8
}
```

Ancak bu geçersiz olabilir:

```qsharp
let n = 5;
...                 // n is 5
let n = 8;          // Error!!
...
```

şöyle olacaktır:

```qsharp
let n = 8;
if (a == b) {
    ...             // n is 8
    let n = 5;      // Error!
    ...
}
...
```

## <a name="control-flow"></a>Denetim Akışı

### <a name="for-loop"></a>For döngüsü

`for` ifade, bir tamsayı aralığı veya dizi üzerinde yinelemeyi destekler.
Deyimi `for`, bir açık parantez `(`ve ardından bir sembol veya sembol kümesi, anahtar sözcük `in`, `Range` veya dizi türünde bir ifade, bir kapatma parantezi `)`ve bir deyim bloğunu içerir.

İfade bloğu (Döngünün gövdesi), her bir değere veya dizideki her bir değere bağlantılı tanımlanmış simgeler (döngü değişkenleri) ile tekrar tekrar yürütülür.
Aralık ifadesi boş bir aralığa veya diziye değerlendirilirse, gövdenin hiç yürütülmeyeceğini unutmayın.
İfade, döngü girilmeden önce tam olarak değerlendirilir ve döngü yürütülürken değişmeyecektir.

Belirtilen sembol (ler) in bağlaması sabittir ve diğer değişken bağlamalarıyla aynı kurallara uyar. Özellikle, döngü değişkenlerine atama yapıldığında dizi üzerinde bir yineleme için örneğin dizi öğeleri için bir dizi öğe oluşturulabilir.

Örneğin,

```qsharp
// ...
for (qb in qubits) { // qubits contains a Qubit[]
    H(qb);
}

mutable results = new (Int, Results)[Length(qubits)];
for (index in 0 .. Length(qubits) - 1) {
    set results w/= index <- (index, M(qubits[index]));
}

mutable accumulated = 0;
for ((index, measured) in results) {
    if (measured == One) {
        set accumulated += 1 <<< index;
    }
}
```

Döngü değişkeni, her giriş gövdesine bağlanır ve gövdenin sonunda ilişkisiz olur.
Özellikle, for döngüsü tamamlandıktan sonra döngü değişkeni bağlantılı değildir.

### <a name="repeat-until-success-loop"></a>Yineleme-Until-başarılı döngüsü

`repeat` bildiri, hisse "başarılı olana kadar Yinele" deseninin modelini destekler.
Anahtar sözcüğünden `repeat`, ardından bir deyim bloğu ( _döngü_ gövdesi), anahtar sözcük `until`, bir Boole ifadesi ve bir Sonlandırıcı noktalı virgül veya anahtar sözcüğü `fixup` ve ardından başka bir deyim bloğu ( _Düzeltme_) gelir.
Döngü gövdesi, koşulu ve düzeltme tek bir kapsam olarak kabul edilir, bu nedenle gövdedeki semboller, koşul ve düzeltme içinde kullanılabilir.

```qsharp
mutable iter = 1;
repeat {
    ProbabilisticCircuit(qs);
    let success = ComputeSuccessIndicator(qs);
}
until (success || iter > maxIter)
fixup {
    iter += 1;
    ComputeCorrection(qs);
}
```

Döngü gövdesi yürütülür ve ardından koşul değerlendirilir.
Koşul doğru ise, ifade tamamlanır; Aksi takdirde, düzeltme yürütülür ve ifade, döngü gövdesiyle başlayarak yeniden yürütülür.
Düzeltme yürütme işlemini tamamlamak deyimin kapsamını sonlandırır, böylece gövde veya Düzeltme sırasında yapılan simge bağlamaları sonraki oturumlarda kullanılamaz.

Örneğin, aşağıdaki kod, Hadamard ve T kapılarını kullanarak önemli bir dönüş geçidi $V _3 = (\cıvalation+ 2 ı Z)/\sqrt{5}$ uygulayan bir dayalı devresi.
Döngü, ortalama 8/5 tekrarda sona erer.
Ayrıntılar için bkz. [*yineleme-Until-başarılı: tek qubit unityalarının belirleyici olmayan ayrıştırma*](https://arxiv.org/abs/1311.1074) (paetznick ve svore, 2014).

```qsharp
using (anc = Qubit()) {
    repeat {
        H(anc);
        T(anc);
        CNOT(target,anc);
        H(anc);
        Adjoint T(anc);
        H(anc);
        T(anc);
        H(anc);
        CNOT(target,anc);
        T(anc);
        Z(target);
        H(anc);
        let result = M(anc);
    } until (result == Zero);
}
```

> [!TIP]   
> İşlevler içinde yineleme-başarılı döngüleri kullanmaktan kaçının. Karşılık gelen işlevler, işlevlerde döngüler sırasında sağlanır. 

### <a name="while-loop"></a>While döngüsü

Yinele-Success desenlerinin çok hisse özgü bir connotation vardır. Bu diller, belirli hisse algoritmaları sınıflarında yaygın olarak kullanılır. bu nedenle, Q # içinde adanmış dil yapısı. Ancak, bir koşula göre kesintiye uğratır ve bu nedenle derleme sırasında yürütme uzunluğunun bilinmediği, bir hisse çalışma zamanında belirli bir ele alınabilmesi gerekir. Diğer yandan işlevleri içindeki kullanımları sorunlu değildir, çünkü bunlar yalnızca geleneksel (hisse olmayan) donanımda yürütülecek kodu içerir. 

Q # bu nedenle, yalnızca işlevler içindeki while döngülerinin kullanımını destekler. `while` deyimi, bir açık parantez `(`, bir koşul (yani Boolean ifadesi), bir kapatma parantezi `)`ve bir deyim bloğunu `while`içerir.
Koşul bloğu (Döngünün gövdesi) `true`olarak değerlendirilen sürece yürütülür.

```qsharp
// ...
mutable (item, index) = (-1, 0);
while (index < Length(arr) && item < 0) { 
    set item = arr[index];
    set index += 1;
}
```

### <a name="conditional-statement"></a>Koşul ekstresi

`if` deyimleri koşullu yürütmeyi destekler.
Anahtar sözcüğünden `if`, açık bir parantez `(`, Boole ifadesi, kapatma parantezi `)`ve deyim bloğu ( _then_ bloğu) oluşur.
Bu, her biri anahtar sözcük `elif`, bir açık parantez `(`, bir Boole ifadesi, kapatma parantezi `)`ve bir deyim bloğu ( _Else-If_ bloğu) içeren herhangi bir sayıda Else-If yan tümcesi gelebilir.
Son olarak, deyimi isteğe bağlı olarak bir else yan tümcesi ile bitebileceği gibi, daha sonra başka bir ifade bloğunun ( _Else_ bloğu) tarafından izlenen `else` anahtar sözcükten oluşur.
Koşul değerlendirilir ve true ise blok yürütülür.
Koşul yanlışsa, ilk else-if koşulu değerlendirilir; true ise, Else-If bloğu yürütülür.
Aksi takdirde, ikinci Else-If bloğu test edilir ve ardından üçüncü, vb. doğru bir koşula sahip bir yan tümce ile karşılaşılana ya da başka bir else-if yan tümcesi içermeyecek şekilde devam eder.
Özgün If koşulu ve tüm else-if yan tümceleri yanlış olarak değerlendirilmişse, varsa Else bloğu yürütülür.

Hangi bloğun yürütüldüğü, kendi kapsamında yürütüleceğini unutmayın.
Daha sonra, else-if veya else bloğunun içinde yapılan bağlamalar, IF ifadesinin sonundan sonra görünmez.

Örneğin,

```qsharp
if (result == One) {
    X(target);
} 
```

or

```qsharp
if (i == 1) {
    X(target);
} elif (i == 2) {
    Y(target);
} else {
    Z(target);
}
```

### <a name="return"></a>döndürülmesini

Return deyimleri bir işlemin veya işlevin yürütmesini sonlandırır ve çağırana bir değer döndürür.
Anahtar sözcüğünden `return`, ardından uygun türdeki bir ifade ve sonlandırma noktalı virgülünden oluşur.

Boş bir tanımlama grubu döndüren çağrılabilir, `()`, return ifadesine gerek yoktur.
Erken çıkış isteniyorsa, bu durumda `return ()` kullanılabilir.
Diğer herhangi bir tür döndüren callables, son Return ifadesine gerek duyar.

Bir işlem içinde en fazla dönüş deyimi sayısı yoktur.
Deyimler bir blok içindeki Return deyimini izif ise derleyici bir uyarı verebilir.

Örneğin,

```qsharp
return 1;
```

or

```qsharp
return ();
```

or

```qsharp
return (results, qubits);
```

### <a name="fail"></a>Neden

Fail deyimleri bir işlemin yürütülmesini sonlandırır ve çağırana bir hata değeri döndürür.
Anahtar sözcüğünden `fail`, ardından bir dize ve Sonlandırıcı noktalı virgülden oluşur.
Dize, hata iletisi olarak klasik sürücüye döndürülür.

İşlemdeki başarısızlık deyimlerinin sayısı üzerinde hiçbir kısıtlama yoktur.
Deyimler bir blok içindeki bir fail deyimini izif ise derleyici bir uyarı verebilir.

Örneğin,

```qsharp
fail $"Impossible state reached";
```

or

```qsharp
fail $"Syndrome {syn} is incorrect";
```

## <a name="qubit-management"></a>Qubit yönetimi

Bir işlevin gövdesinde bu deyimlerden hiçbirine izin verilmediğini unutmayın.
Bunlar yalnızca işlemler içinde geçerlidir.

### <a name="clean-qubits"></a>Qubit Temizleme

`using` deyimleri, bir bildirim bloğu sırasında kullanılmak üzere yeni qubit almak için kullanılır.
Qubits 'in hesaplama `Zero` durumuna başlatılması garanti edilir.
Qubits, bildiri bloğunun sonundaki hesaplama `Zero` durumunda olmalıdır; simülatörleri bunu zorunlu tutmaları önerilir.

İfade, anahtar sözcüğünden `using`, ardından bir açık parantez `(`, bir bağlama, bir kapatma parantezi `)`ve qubits 'in kullanılabileceği bildiri bloğunu içerir.
Bağlama `let` deyimleriyle aynı düzeni izler: tek bir sembol veya sembol tanımlama grubu, ardından eşittir işareti `=`ve tek bir değer ya da eşleşen bir başlatıcı grubu.
Başlatıcılar, `Qubit()`olarak belirtilen tek bir qubit için veya `Qubit[`, `Int` ifadesi ve `]`belirtilen bir qubit dizisi için kullanılabilir.

Örneğin,

```qsharp
using (q = Qubit()) {
    // ...
}
using ((ancilla, qubits) = (Qubit(), Qubit[bits * 2 + 3])) {
    // ...
}
```

### <a name="dirty-qubits"></a>Kirli qubits

`borrowing` deyimleri, geçici kullanım için qubits almak için kullanılır. İfade, anahtar sözcüğünden `borrowing`, ardından bir açık parantez `(`, bir bağlama, bir kapatma parantezi `)`ve qubits 'in kullanılabileceği bildiri bloğunu içerir.
Bağlama, bir `using` bildirimiyle aynı model ve kurallara uyar.

Örneğin,

```qsharp
borrowing (q = Qubit()) {
    // ...
}
borrowing ((ancilla, qubits) = (Qubit(), Qubit[bits * 2 + 3])) {
    // ...
}
```

Ödünç alınan qubits, bilinmeyen bir durumda ve bildiri bloğunun sonundaki kapsam dışına çıkar.
Ödünç alma, qubits 'i ödünç aldıkları aynı durumda bırakır, yani deyimin başındaki ve sonundaki durumları aynı olmalıdır. bu durum, ifade bloğunun başındaki ve sonundaki durumunun aynı olması beklenir.
Özellikle bu durum klasik bir durum değildir; çoğu durumda, ödünç alınan kapsamlar ölçüm içermemelidir. 

Bu tür qugeler genellikle "kirli anyenla" olarak bilinir.
Düzenleme, bir kirli kullanımı örneği için Toffoli tabanlı modüler çarpma (haner, Roetteler ve Svore 2017) [*ile 2n + 2 qubit kullanarak*](https://arxiv.org/abs/1611.07995) bkz.

Qubits 'i ödünç alırken, sistem önce kullanımda olan ancak `borrowing` ifadesinin gövdesi sırasında erişilemeyen qubits 'ten gelen isteği doldurmaya çalışacaktır.
Bu tür qubit yoksa, isteği tamamlayacak yeni qubit ayırabilirsiniz.

## <a name="conjugations"></a>Conjugations

Klasik bitlerin aksine, qubits 'in hala bir daha açık olması durumunda qubits 'in kalan hesaplamada istenmeyen etkileri olabildiğinden, hisse bitlerinin serbest bırakılması biraz daha karmaşıktır. Bu, belleğin serbest bırakılmasından önce düzgün bir şekilde "geri alma" sırasında gerçekleştirilen hesaplamaları önlenebilir. Bu nedenle, hisse kullanımı için genel bir model aşağıda verilmiştir: 

```qsharp
operation ApplyWith<'T>(
    outerOperation : ('T => Unit is Adj), 
    innerOperation : ('T => Unit), 
    target : 'T) 
: Unit {

    outerOperation(target);
    innerOperation(target);
    Adjoint outerOperation(target);
}
```

: yeni: 0,9 sürümümüzden başlayarak, yukarıdaki dönüşümü uygulayan bir Birleşik bildirim bildirisini destekliyoruz. Bu ifadeyi kullanarak, işlem `ApplyWith` aşağıdaki şekilde uygulanabilir:

```qsharp
operation ApplyWith<'T>(
    outerOperation : ('T => Unit is Adj), 
    innerOperation : ('T => Unit), 
    target : 'T) 
: Unit {

    within{ 
        outerOperation(target);
    }
    apply {
        innerOperation(target);
    }
}
```
Bu tür bir birleşim deyimi, dış ve iç dönüşüm işlem olarak hazır değilse ancak birkaç deyimden oluşan bir blok tarafından tanımlanmakla daha kullanışlı hale gelirse çok daha yararlıdır. 

İçindeki blok içinde tanımlanan deyimler için ters dönüşüm, derleyici tarafından otomatik olarak oluşturulur ve Apply-Block tamamlandıktan sonra yürütülür. İçindeki blok içinde kullanılan herhangi bir değişebilir değişken, Apply-Block içinde yeniden bağlanamaz, oluşturulan dönüşümün, hesaplamanın içindeki adeklik olduğu garanti edilir. 

## <a name="expression-evaluation-statements"></a>İfade değerlendirme deyimleri

`Unit` türündeki herhangi bir çağrı ifadesi bir deyim olarak kullanılabilir.
Bu, deyimin amacı örtülü hisse durumu ' nu değiştirecek olduğundan, bu, öncelikle `Unit` döndüren qubits üzerinde işlemler çağrılırken kullanılır.
İfade değerlendirme deyimleri, sonlandırma noktalı virgül gerektirir.

Örneğin,

```qsharp
X(q);
CNOT(control, target);
Adjoint T(q);
```
