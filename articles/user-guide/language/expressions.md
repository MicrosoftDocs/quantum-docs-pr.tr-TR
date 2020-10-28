---
title: İçindeki ifadeler Q#
description: Sabitleri, değişkenleri, işleçleri, işlemleri ve işlevleri ' de ifade olarak belirtme, başvurma ve birleştirme işlemlerini anlayın Q# .
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.expressions
no-loc:
- Q#
- $$v
ms.openlocfilehash: e95a7cb9b74136ef9a6f51b4bbc32d1d93c43a0d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691596"
---
# <a name="expressions-in-no-locq"></a>İçindeki ifadeler Q#

## <a name="numeric-expressions"></a>Sayısal Ifadeler

Sayısal ifadeler `Int` , veya türündeki ifadelerdir `BigInt` `Double` .
Diğer bir deyişle, tamsayı veya kayan noktalı sayılardır.

`Int` içindeki değişmez değerler Q# , bir dizi basamak olarak yazılmıştır.
Onaltılık ve ikili tamsayılar desteklenir ve `0x` sırasıyla bir ve önekiyle yazılır `0b` .

`BigInt` içindeki değişmez değerler Q# sonunda `l` veya `L` soneke sahiptir.
Onaltılık büyük tamsayılar desteklenir ve "0x" önekiyle yazılır.
Bu nedenle, tüm geçerli sabit değer kullanımları aşağıda verilmiştir `BigInt` :

```qsharp
let bigZero = 0L;
let bigHex = 0x123456789abcdef123456789abcdefL;
let bigOne = bigZero + 1L;
```

`Double` içindeki değişmez değerler Q# , ondalık basamaklar kullanılarak yazılan kayan nokta sayılarıdır.
Bunlar ondalık bir nokta veya ya da ya da " `.` e" ya da "e" ya da bir üstel bölüm (yalnızca olası bir negatif işaret ve ondalık basamakların geçerli olması) ile yazılmış veya olmadan yazılabilir.
Aşağıdakiler geçerli `Double` değişmez değerler: `0.0` , `1.2e5` , `1e-5` .

Herhangi bir öğe türünün dizi ifadesi verildiğinde, `Int` [`Length`](xref:Microsoft.Quantum.Core.Length) yerleşik işlevini kullanarak, dizi ifadesi parantez içine alınmış bir ifade oluşturabilirsiniz.
Örneğin, `a` bir diziye bağlıysa, bir `Length(a)` tamsayı ifadesidir.
, `b` Tamsayıların dizilerindeki bir diziyse, `Int[][]` `Length(b)` içindeki alt dizilerin sayısıdır `b` ve `Length(b[1])` içindeki ikinci alt dizideki tamsayıların sayısıdır `b` .

Aynı türde iki sayısal ifade verildiğinde, ikili işleçler,,, `+` `-` `*` ve `/` Yeni bir sayısal ifade oluşturmak için kullanılabilir.
Yeni ifadenin türü, yapısal ifadelerin türleriyle aynıdır.

İki tamsayı ifadesi verildiğinde, `^` Yeni bir tamsayı ifadesi oluşturmak için ikili işleci (Power) kullanın.
Benzer şekilde, `^` Yeni bir Double ifadesi oluşturmak için iki Double ifadesiyle da kullanabilirsiniz.
Son olarak, sol taraftaki `^` büyük bir tamsayı ve sağ taraftaki bir tamsayı kullanarak yeni bir büyük tamsayı ifadesi oluşturabilirsiniz.
Bu durumda, ikinci parametrenin 32 bite sığması gerekir; Aksi takdirde, bir çalışma zamanı hatası oluşturur.

İki tamsayı veya büyük tamsayı ifadesi verildiğinde, `%` (mod), `&&&` (BIT düzeyinde and), `|||` (bit düzeyinde OR) veya `^^^` (bit düzeyinde xor) işleçlerini kullanarak yeni bir tamsayı veya büyük tamsayı ifadesi oluşturur.

Sol tarafta bir tamsayı veya büyük tamsayı ifadesi ve sağ taraftaki bir tamsayı ifadesi verildiğinde, `<<<` `>>>` sol ifadeyle aynı türde yeni bir ifade oluşturmak için (aritmetik sol SHIFT) veya (aritmetik sağa kaydırma) işleçlerini kullanın.

Kaydırma işleminin ikinci parametresi (SHIFT miktarı) sıfırdan büyük veya sıfıra eşit olmalıdır; negatif kaydırma miktarları için davranış tanımsızdır.
Her iki vardiya işlemi için de SHIFT miktarı 32 bite uyum sağlamalıdır; Aksi takdirde, bir çalışma zamanı hatası oluşturur.
Kaydırılan sayı bir tamsayı ise, kaydırma miktarı yorumlanır `mod 64` ; diğer bir deyişle, 1 vardiyası ve 65 vardiyası aynı etkiye sahiptir.

Hem tamsayı hem de büyük tamsayı değerleri için, vardiyalar aritmetik değerlerdir.
Negatif bir değeri sol veya sağ olarak değiştirme negatif bir sayı ile sonuçlanır.
Diğer bir deyişle, bir adım sola veya sağa kaydırma, sırasıyla 2 ile çarpılarak veya bölünerek aynıdır.

Tamsayı bölme ve tamsayı mod, negatif sayılar için C# olarak aynı davranışı izler. Yani, `a % b` her zaman aynı işarete sahiptir `a` ve `b * (a / b) + a % b` her zaman eşittir `a` . Örneğin:

|`A` | `B` | `A / B` | `A % B`|
|:---------:|:----------:|:---------:|:---------:|
| 5 | 2 | 2 | 1 |
| 5 | -2 | -2 | 1 |
| -5 | 2 | -2 | -1 |
| -5 | -2 | 2 | -1 |

Büyük tamsayı bölme ve mod işlemleri aynı şekilde çalışır.

Herhangi bir sayısal ifade verildiğinde birli işlecini kullanarak yeni bir ifade oluşturabilirsiniz `-` .
Yeni ifade, anayent ifadesiyle aynı türde.

Herhangi bir tamsayı veya büyük tamsayı ifadesi verildiğinde, `~~~` (bit düzeyinde tamamlayıcı) birli işlecini kullanarak aynı türde yeni bir ifade oluşturabilirsiniz.

## <a name="boolean-expressions"></a>Boole İfadeleri

İki `Bool` değişmez değer de `true` ve ' dir `false` .

Aynı ilkel türdeki iki ifade verildiğinde, `==` ve `!=` ikili işleçler bir ifade oluşturmak için kullanılabilir `Bool` .
İki ifade eşitse true, değilse false şeklindedir.

Kullanıcı tanımlı türlerin değerleri karşılaştırılamayabilir, yalnızca sarmalanmamış değerler karşılaştırılabilir. Örneğin, "sarmalama" işlecini kullanma `!` ( [içindeki Q# türlerde ](xref:microsoft.quantum.guide.types#access-anonymous-items-with-the-unwrap-operator)ayrıntılı olarak açıklanmıştır)

```qsharp
newtype WrappedInt = Int;     // Yes, this is a contrived example
let x = WrappedInt(1);
let y = WrappedInt(2);
let z = x! == y!;             // This will compile and yield z = false.
let t = x == y;               // This will cause a compiler error.
```

Değerler için eşitlik karşılaştırması `Qubit` kimlik eşitlik, yani iki ifadenin aynı qubit 'i tanımlamasına bakılmaksızın.
İki qubits 'in durumları karşılaştırılmaz, erişilmez, ölçülemez veya bu karşılaştırma tarafından değiştirilmez.

Değerler için eşitlik karşılaştırması `Double` , yuvarlama etkileri nedeniyle yanıltıcı olabilir.
Örneğin, `49.0 * (1.0/49.0) != 1.0`.

Herhangi iki sayısal ifade verildiğinde,,, ve ikili işleçleri,,, `>` `<` `>=` ve `<=` ilk ifade sırasıyla sıfırdan büyük, küçüktür, büyüktür veya eşittir veya ikinci ifadeden daha küçük veya eşit olduğunda doğru olan yeni bir Boole ifadesi oluşturmak için kullanılabilir.

Herhangi iki Boolean ifadesi verildiğinde, `and` iki ifadenin her ikisi de doğru olduğunda doğru olan yeni bir Boole ifadesi oluşturmak için ikili işleci kullanın. Benzer şekilde, işleci kullanıldığında, `or` iki deyimden biri true olduğunda true olan bir ifade oluşturulur.

Herhangi bir Boole ifadesi verildiğinde, `not` birli işleç yanlış olduğunda, doğru olan yeni bir Boole ifadesi oluşturmak için birli işleç kullanılabilir.

## <a name="string-expressions"></a>Dize ifadeleri

Q#`fail`deyimde ( [Denetim akışında](xref:microsoft.quantum.guide.controlflow#fail-statement)açıklanmıştır) ve standart işlevde dizelerin kullanılmasına izin verir [`Message`](xref:Microsoft.Quantum.Intrinsic.Message) . İkinci öğesinin belirli davranışı kullanılan simülatöre bağlıdır, ancak genellikle bir program sırasında çağrıldığında ana bilgisayar konsoluna bir ileti yazar Q# .

İçindeki dizeler Q# değişmez değerler ya da enterpolasyonlardır.

Dize sabit değerleri çoğu dilde basit dize sabit değerlerine benzer: çift tırnak içine alınmış bir Unicode karakter dizisi `" "` .
Bir dizenin içinde, `\` çift tırnak karakterini ( `\"` ) kaçış veya New-Line ( `\n` ), bir satır başı ( `\r` ) veya Tab ( `\t` ) eklemek için ters eğik çizgi karakterini kullanın.
Örneğin:

```qsharp
"\"Hello world!\", she said.\n"
```
### <a name="interpolated-strings"></a>Ara değerli dizeler

Q#Dize enterpolasyonları için sözdizimi, C# sözdiziminin bir alt kümesidir. Aşağıdakiler ile ilgili önemli noktaları aşağıda verilmiştir Q# :

* Bir dize sabit değerini, enterpolasyonlu bir dize olarak tanımlamak için, `$` simgeyi simgesiyle önüne ekleyin. `$`Ve arasında `"` bir dize sabiti Başlatan boşluk olamaz.

* Aşağıdaki örnek, [`Message`](xref:Microsoft.Quantum.Intrinsic.Message) diğer ifadelerle birlikte, bir ölçünün sonucunu konsola yazmak için fonksiyonunu kullanan temel bir örnektir Q# .

```qsharp
    let num = 8;       // some Q# expression
    let res = M(q);
    Message($"Number: {num}, Result: {res}");
```

* Geçerli Q# bir ifade, enterpolasyonlu bir dizede görünebilir.

* Bir enterpolasyonlu dize içindeki ifadeler Q# C# söz dizimini değil söz dizimini izler. En önemli ayrım, tam Q# (çok satırlı) enterpolasyonlu dizeleri desteklemedir.

C# sözdizimi hakkında daha fazla bilgi için bkz. [*enterpolasyonlu dizeler*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings).

## <a name="range-expressions"></a>Aralık Ifadeleri

, Ve olmak üzere üç ifade verildiğinde, `Int` `start` `step` `stop` ifadesi `start .. step .. stop` ilk öğesi olan bir Aralık ifadesi, `start` ikinci öğe ise, üçüncü öğe, vb., `start+step` `start+step+step` geçene kadar `stop` .
Örneğin, pozitif ve olduğunda bir Aralık boş olabilir `step` `stop < start` .

Aralık her iki ucu da dahil değildir. Diğer bir deyişle, ve arasındaki fark `start` `stop` bir tamsayı ise `step` , aralığın son öğesi olacaktır `stop` .

Her iki `Int` ifade de `start` ve `stop` ifade verilen `start .. stop` bir Aralık ifadesi `start .. 1 .. stop` .
Önünde ve `step` ' den küçük olsa bile, örtük ' ın + 1 olduğunu unutmayın `stop` `start` . böyle bir durumda, Aralık boş olur.

Bazı örnek aralıklar şunlardır:

- `1..3` 1, 2, 3 aralığıdır.
- `2..2..5` 2, 4 aralığındadır.
- `2..2..6` 2, 4, 6 aralığıdır.
- `6..-2..2` 6, 4, 2 aralığıdır.
- `2..1` boş aralıktır.
- `2..6..7` Aralık 2 ' dir.
- `2..2..1` boş aralıktır.
- `1..-1..2` boş aralıktır.

## <a name="qubit-expressions"></a>Qubit Ifadeleri

Tek `Qubit` ifadeler, `Qubit` dizilerin değerlerine veya dizi öğelerine bağlanan sembollerdir `Qubit` .
Değişmez değer yok `Qubit` .

## <a name="pauli-expressions"></a>Pauli Ifadeleri

Dört değeri,,, `Pauli` `PauliI` `PauliX` `PauliY` ve `PauliZ` , tüm geçerli `Pauli` ifadelerdir.

Bunun dışında, tek ifadeler, `Pauli` `Pauli` dizilere ait değerlere veya dizi öğelerine bağlanan sembollerdir `Pauli` .

## <a name="result-expressions"></a>Sonuç Ifadeleri

İki `Result` değer `One` ve `Zero` , geçerli `Result` ifadelerdir.

Bunun dışında, tek ifadeler, `Result` `Result` dizilere ait değerlere veya dizi öğelerine bağlanan sembollerdir `Result` .
Özellikle, `One` tamsayıyla aynı olmadığını ve aralarında doğrudan dönüşüm olmadığını unutmayın `1` .
Aynı, ve için de `Zero` geçerlidir `0` .

## <a name="tuple-expressions"></a>Demet Ifadeleri

Tanımlama grubu sabit değeri, virgülle ayrılmış şekilde, uygun türdeki öğe ifadelerinin dizelerdir.
Örneğin, `(1, One)` bir `(Int, Result)` ifadedir.

Değişmez değerler dışında, tek demet ifadeleri demet değerlerine, demet dizilerinin dizi öğelerine ve tanımlama grupları döndüren çağrılabilir çağırmaları olan sembollerdir.

## <a name="user-defined-type-expressions"></a>User-Defined tür Ifadeleri

Kullanıcı tanımlı bir türün sabit değeri tür adından, ardından türün temel demet türünün bir tanımlama grubu değişmez değerinden oluşur.
Örneğin, `IntPair` temelli Kullanıcı tanımlı bir tür ise `(Int, Int)` , `IntPair(2, 3)` Bu türün geçerli bir sabit değeri olur.

Değişmez değerler dışında, Kullanıcı tanımlı bir türün tek ifadeleri, bu türün değerlerine, bu türden dizilerin dizi öğelerine ve bu türü döndüren çağrılabilir çağırmaları olan sembollerdir.

## <a name="unwrap-expressions"></a>Ifade kaydırmayı geri al

Q#' De, geri sarım işleci sondaki bir ünlem işaretidir `!` .
Örneğin, `IntPair` temel alınan türe sahip kullanıcı tanımlı bir türdür `(Int, Int)` ve `s` değeri olan bir değişkense, `IntPair(2, 3)` `s!` olur `(2, 3)` .

Diğer Kullanıcı tanımlı türler bakımından tanımlanan Kullanıcı tanımlı türler için, Unwrap işlecini yineleyebilirsiniz. Örneğin, `s!!` paketlenmiş ve sarmalanmamış değeri gösterir `s` .
Bu nedenle, `WrappedPair` temel alınan türe sahip kullanıcı tanımlı bir türdür `IntPair` ve `t` değeri olan bir değişkense, `WrappedPair(IntPair(1,2))` `t!!` olur `(1,2)` .

`!`İşleç, `[]` dizi dizini oluşturma ve dilimleme için dışındaki diğer işleçlerden daha yüksek önceliğe sahiptir.
`!` ve, `[]` pozitif bir deyişle, `a[i]![3]` şöyle okunurdur `((a[i])!)[3]` : `i` . öğesini alın `a` , sarmalayın ve sarmalanmamış değerin 3. öğesini (bir dizi olması gerekir) alın.

`!`İşlecin önceliği belirgin olmayan bir etkiye sahip olabilir.
Bir işlev veya işlem sarmalanmamış bir değer döndürürse, bağımsız değişken grubu, sarmalama yerine çağrıya bağlamak için işlev veya işlem çağrısının parantez içine alınması gerekir.
Örneğin:

```qsharp
let f = (Foo(arg))!;    // Calls Foo(arg), then unwraps the result
let g = Foo(arg)!;      // Syntax error
```

## <a name="array-expressions"></a>Dizi Ifadeleri

Dizi sabit değeri, virgülle ayrılmış bir veya daha fazla öğe ifadesi dizisi parantez içine alınmıştır `[]` .
Tüm öğeler aynı türle uyumlu olmalıdır.

Aynı türde iki dizi verildiğinde, `+` iki dizinin birleşimi olan yeni bir dizi oluşturmak için ikili işlecini kullanın.
Örneğin, `[1,2,3] + [4,5,6]` = `[1,2,3,4,5,6]`.

### <a name="array-creation"></a>Dizi oluşturma

Bir tür ve ifade verildiğinde `Int` , `new` verilen boyutun yeni bir dizisini ayırmak için işlecini kullanın.
Örneğin, `new Int[i + 1]` öğeleri içeren yeni bir `Int` dizi ayırır `i + 1` .

Boş dizi değişmez değerlerine (gibi) `[]` izin verilmez.
Bunun yerine, `new T[0]` `T` uygun bir tür için yer tutucu olan öğesini kullanarak sıfır uzunluğunda bir dizi oluşturabilirsiniz.

Yeni bir dizinin öğeleri, türe bağlı bir varsayılan değere başlatırlar.
Çoğu durumda, bu bazı sıfır çeşitlerinden oluşur.

Varlıklara başvurular olan qubits ve callables için makul bir varsayılan değer yoktur.
Bu nedenle, varsayılan olarak, bir çalışma zamanı hatasına neden olmadan, C# veya Java gibi dillerdeki bir null başvuruya benzer şekilde kullanamazsınız.
, Öğelerini güvenli bir şekilde kullanabilmeniz için qubits veya callables içeren diziler varsayılan olmayan değerlerle başlatılmalıdır. Uygun başlatma yordamları için bkz <xref:Microsoft.Quantum.Arrays> ..

Her türün varsayılan değerleri şunlardır:

Tür | Varsayılan
---------|----------
 `Int` | `0`
 `BigInt` | `0L`
 `Double` | `0.0`
 `Bool` | `false`
 `String` | `""`
 `Qubit` | _geçersiz qubit_
 `Pauli` | `PauliI`
 `Result` | `Zero`
 `Range` | Boş Aralık, `1..1..0`
 `Callable` | _geçersiz çağrılabilir_
 `Array['T]` | `'T[0]`

Demet türleri öğeyi by öğesi olarak başlatır.


### <a name="array-elements"></a>Dizi öğeleri

Dizi ifadesi ve bir ifade verildiğinde `Int` , Array öğesi işlecini kullanarak yeni bir ifade oluşturur `[]` .
Yeni ifade, dizinin öğe türüyle aynı türde.
Örneğin, türünde bir `a` diziye bağlanmışsa `Double` , `a[4]` bir `Double` ifadedir.

Dizi ifadesi basit bir tanımlayıcı değilse, bir öğeyi seçmek için ayraçları parantez içine almalısınız.
Örneğin, `a` ve `b` her iki dizi dizisise `Int` , birleştirme işleminden bir öğe şöyle ifade edilir:

```qsharp
(a + b)[13]
```

İçindeki tüm diziler Q# sıfır tabanlıdır.
Diğer bir deyişle, bir dizinin ilk öğesi `a` her zaman olur `a[0]` .


### <a name="array-slices"></a>Dizi dilimleri

Dizi ifadesi ve bir ifade verildiğinde `Range` , dizi dilimi işlecini kullanarak yeni bir ifade oluşturur `[ ]` .
Yeni ifade, dizisiyle aynı türdür ve tarafından tanımlanan sırada öğesi tarafından dizin oluşturulan dizi öğelerini içerir `Range` `Range` .
Örneğin, `a` türünde bir diziye bağlıysa `Double` ,, `a[3..-1..0]` `Double[]` `a` ancak içinde göründükleri şekilde ters sırada olan ilk dört öğeyi içeren bir ifadedir `a` .

`Range`Boşsa, sonuçta elde edilen dizi dilimi sıfır uzunluktadır.

Başvuran dizi öğelerinde olduğu gibi, dizi ifadesi basit bir tanımlayıcı değilse, onu dilimlemek için parantez içine almalısınız.
Örneğin, `a` ve `b` her iki dizi dizisise `Int` , birleştirme işleminden alınan bir dilim şöyle ifade edilir:

```qsharp
(a+b)[1..2..7]
```

#### <a name="inferred-startend-values"></a>Çıkarılan başlangıç/bitiş değerleri

[0,8 sürümümüzden](xref:microsoft.quantum.relnotes)başlayarak, Aralık Dilimleme için bağlamsal ifadeleri destekliyoruz. Özellikle bir Aralık Dilimleme ifadesi bağlamında Aralık başlangıcı ve bitiş değerlerini atlayabilirsiniz. Bu durumda, derleyici aralığa yönelik istenen sınırlayıcıları çıkarması için aşağıdaki kuralları uygular:

* Aralık *başlangıcı* değeri atlanırsa, çıkarılan başlangıç değeri
  * bir adım belirtilmemişse veya belirtilen adım pozitif ise sıfır olur.  
  * , belirtilen adım negatifse, dilimli dizinin uzunluğu eksi bir değer.

* Aralık *bitiş* değeri atlanırsa, çıkarılan bitiş değeri
  * , hiçbir adım belirtilmediyse veya belirtilen adım pozitifse dilimli dizinin uzunluğu eksi bir değer.
  * , belirtilen adım negatifse sıfırdır.

Bazı örnekler şunlardır:

```qsharp
let arr = [1,2,3,4,5,6];
let slice1  = arr[3...];      // slice1 is [4,5,6];
let slice2  = arr[0..2...];   // slice2 is [1,3,5];
let slice3  = arr[...2];      // slice3 is [1,2,3];
let slice4  = arr[...2..3];   // slice4 is [1,3];
let slice5  = arr[...2...];   // slice5 is [1,3,5];
let slice7  = arr[4..-2...];  // slice7 is [5,3,1];
let slice8  = arr[...-1..3];  // slice8 is [6,5,4];
let slice9  = arr[...-1...];  // slice9 is [6,5,4,3,2,1];
let slice10 = arr[...];       // slice10 is [1,2,3,4,5,6];
```

### <a name="copy-and-update-expressions"></a>Kopyalama ve güncelleştirme Ifadeleri

Tüm Q# türler değer türleri olduğundan (biraz özel bir rol alan qubits ile), bir değer bir simgeye bağlandığında veya bir sembol yeniden bağlandığında bir "kopya" oluşturulur. Şöyle ki, davranışı Q# atama işleci kullanılarak oluşturulmuş bir kopya ile aynı olur. 

Tabii ki, pratikte yalnızca ilgili parçalar gerektiği şekilde yeniden oluşturulur. Bu, dizi öğelerini güncelleştirmek mümkün olmadığından dizileri kopyalamayı etkiler. Var olan bir diziyi değiştirmek için bir *kopyalama ve güncelleştirme* mekanizmasının kullanılmasını gerekir.

Var olan bir diziden, işleçlerini ve işlecini kullanan *kopyalama ve güncelleştirme* ifadeleri aracılığıyla yeni bir dizi oluşturabilirsiniz `w/` `<-` .
Bir kopya ve güncelleştirme ifadesi formun bir ifadesidir `expression1 w/ expression2 <- expression3` , burada

* `expression1``T[]`bir tür için tür olmalıdır `T` .
* `expression2` ' de belirtilen dizide hangi dizinlerin değiştirileceğini tanımlar `expression1` . `expression2` tür `Int` ya da tür olmalıdır `Range` .
* `expression3``expression1`, içinde belirtilen indeksler temelinde içindeki öğeleri güncelleştirmek için kullanılan değerdir `expression2` . `expression2`Tür ise `Int` , tür olmalıdır `expression3` `T` . `expression2`Tür ise `Range` , tür olmalıdır `expression3` `T[]` .

Örneğin, Copy ve Update ifadesi, ' `arr w/ idx <- value` `arr` `idx` deki değer (ler) e ayarlanan tarafından belirtilen öğe (ler) hariç, içindeki karşılık gelen öğelere ayarlanmış tüm öğeleri içeren yeni bir dizi oluşturur `value` . 

Verilen `arr` diziyi içeriyorsa `[0,1,2,3]` , 

- `arr w/ 0 <- 10` dizi `[10,1,2,3]` .
- `arr w/ 2 <- 10` dizi `[0,1,10,3]` .
- `arr w/ 0..2..3 <- [10,12]` dizi `[10,1,12,3]` .

#### <a name="copy-and-update-expressions-for-named-items"></a>Adlandırılmış öğeler için kopyalama ve güncelleştirme ifadeleri

Kullanıcı tanımlı türlerde adlandırılmış öğeler için benzer ifadeler mevcuttur. 

Örneğin, türü göz önünde bulundurun 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
`c`Türü değerini içeriyorsa `Complex(1., -1.)` ,, `c w/ Re <- 0.` olarak değerlendirilen türünde bir ifadedir `Complex` `Complex(0., -1.)` .

### <a name="jagged-arrays"></a>Düzensiz Diziler

Bazen "dizi dizisi" olarak adlandırılan pürüzlü bir dizi, öğeleri dizi dizileri olan bir dizidir.
Pürüzlü bir dizinin öğeleri farklı boyutlarda olabilir.
Aşağıdaki örnek, çarpma tablosunu temsil eden pürüzlü bir dizinin nasıl bildirilemeyeceğini ve başlatılacağını gösterir.

```qsharp
let N = 4;
mutable multiplicationTable = new Int[][N];
for (i in 1..N) {
    mutable row = new Int[i];
    for (j in 1..i) {
        set row w/= j-1 <- i * j;
    }
    set multiplicationTable w/= i-1 <- row;
}
```

### <a name="arrays-of-callables"></a>Callables dizileri 

Ayrıca, callables dizisi de oluşturabilirsiniz.

* Ortak öğe türü bir işlem ya da işlev türü ise, tüm öğeler aynı giriş ve çıkış türlerine sahip olmalıdır.
* Dizinin öğe türü tüm öğeleri tarafından [desteklenen tüm unsurları](xref:microsoft.quantum.guide.operationsfunctions) destekler.
Örneğin,, `Op1` `Op2` ve `Op3` hepsi `Qubit[] => Unit` operasyonlardır, ancak `Op1` `Adjoint` `Op2` her ikisini de destekler, destekler `Controlled` ve `Op3` destekler:
  * `[Op1, Op2]` , bir dizi `(Qubit[] => Unit)` işlemden oluşur.
  * `[Op1, Op3]` , bir dizi `(Qubit[] => Unit is Adj)` işlemden oluşur.
  * `[Op2, Op3]` , bir dizi `(Qubit[] => Unit is Ctl)` işlemden oluşur.

Ancak, işlemler `(Qubit[] => Unit is Adj)` ve  `(Qubit[] => Unit is Ctl)` ortak temel türüne sahip olmakla birlikte `(Qubit[] => Unit)` , bu işlemlerin *dizileri* ortak bir temel türü paylaşmazlar.

Örneğin, `[[Op1], [Op2]]` Şu anda iki uyumsuz dizi türünden oluşan bir dizi oluşturmayı denediğinde bir hata oluşturur `(Qubit[] => Unit is Adj)[]` `(Qubit[] => Unit is Ctl)[]` .

Callables hakkında daha fazla bilgi için bu sayfadaki veya [işlemler ve Q# işlevlerde ](xref:microsoft.quantum.guide.operationsfunctions) [çağrılabilir ifadeler](#callable-expressions) bölümüne bakın.

## <a name="conditional-expressions"></a>Koşullu Ifadeler

Aynı türde ve bir Boolean ifadesinin iki ifadesi verildiğinde, soru işaretini, ve dikey çubuğu kullanarak koşullu bir ifade oluşturur `?` `|` . Verildiğinde `a==b ? c | d` , koşullu ifadenin değeri `c` `a==b` true ise ve false ise `d` .

### <a name="conditional-expressions-with-callables"></a>Callables ile koşullu ifadeler

Koşullu ifadeler, aynı girişlere ve çıkışlara sahip olan ancak farklı komik desteği olan işlemleri değerlendirebilir. Bu durumda, koşullu ifadenin türü, her iki ifade tarafından desteklenen tüm semantikleri destekleyen giriş ve çıkışlarla bir işlemdir.
Örneğin,, ve hepsi ise,, `Op1` `Op2` ve `Op3` `Qubit[]=>Unit` `Op1` `Adjoint` `Op2` `Controlled` her ikisini de destekler, destekler ve `Op3` destekler:

- `flag ? Op1 | Op2` bir `(Qubit[] => Unit)` işlemdir.
- `flag ? Op1 | Op3` bir `(Qubit[] => Unit is Adj)` işlemdir.
- `flag ? Op2 | Op3` bir `(Qubit[] => Unit is Ctl)` işlemdir.

Olası iki sonuç ifadesinin herhangi biri bir işlev veya işlem çağrısını içeriyorsa, bu çağrı yalnızca çağrının değeri olan bir sonuç olduğunda gerçekleşir. Örneğin, bu durumda, `a==b ? C(qs) | D(qs)` `a==b` true ise `C` işlem çağrılır ve yanlış ise yalnızca `D` işlem çağrılır. Bu yaklaşım, diğer dillerdeki *kısa* devre 'ya benzer.

## <a name="callable-expressions"></a>Çağrılabilir Ifadeler

Çağrılabilir sabit değer, derleme kapsamında tanımlanan bir işlemin veya işlevin adıdır. Örneğin, `X` standart kitaplık işlemine başvuran bir işlem sabit değeri `X` ve `Message` standart kitaplık işlevine başvuran bir işlev sabit değeri `Message` .

Bir işlem `Adjoint` functor destekliyorsa, `Adjoint op` bir işlem ifadesi olur.
Benzer şekilde, işlem `Controlled` functor 'ı destekliyorsa, `Controlled op` bir işlem ifadesi olur.
Bu ifadelerin türleri hakkında daha fazla bilgi için bkz. [işlem uzmanlıklarını çağırma](xref:microsoft.quantum.guide.operationsfunctions#calling-operation-specializations).

Funörler ( `Adjoint` ve `Controlled` ), ile geri sarım operatörü `!` ve dizi dizini oluşturma dışında diğer işleçlerden daha yakından bağlanır `[ ]` .
Bu nedenle, işlemlerin kullanılan funları destekledikleri varsayılarak aşağıdakiler geçerlidir:

```qsharp
Adjoint Op(qs)
Controlled Op(controls, targets)
Controlled Adjoint Op(controls, targets)
Adjoint WrappedOp!(qs)
```

### <a name="type-parameterized-callable-expressions"></a>Tür parametreli çağrılabilir ifadeler

Çağrılabilir bir sabit değeri, örneğin, bir değişkene atamak veya başka bir çağrılabilir öğesine geçirmek için değer olarak kullanabilirsiniz. Bu durumda, çağrılabilir [tür parametrelerine](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables)sahipse, çağrılabilir değerin parçası olarak parametreleri sağlamanız gerekir.

Çağrılabilir bir değer belirtilmeyen tür parametrelerine sahip olamaz. Örneğin, `Fun` imzaya sahip bir işlevdir `'T1->Unit` :

```qsharp
let f = Fun<Int>;            // f is (Int->Unit).
let g = Fun;                 // This causes a compilation error.
SomeOtherFun(Fun<Double>);   // A (Double->Unit) is passed to SomeOtherFun.
SomeOtherFun(Fun);           // This also causes a compilation error.
```

## <a name="callable-invocation-expressions"></a>Çağrılabilir çağırma Ifadeleri

Çağrılabilir bir ifade (işlem veya işlev) ve çağrılabilir öğesinin giriş türünün bir tanımlama grubu ifadesi verildiğinde, çağrılabilir ifadeye demet ifadesini ekleyerek bir *çağırma ifadesi* oluşturabilirsiniz.
Çağırma ifadesinin türü, çağrılabilir olan imzanın çıkış türüdür.

Örneğin, `Op` imzaya sahip bir işlem ise `((Int, Qubit) => Double)` , `Op(3, qubit1)` türünde bir ifadedir `Double` .
Benzer şekilde, `Sin` imzaya sahip bir `(Double -> Double)` `Sin(0.1)` işlevsiyse, türünde bir ifadedir `Double` .
Son olarak, `Builder` imzaya sahip bir işlevle `(Int -> (Int -> Int))` , ' `Builder(3)` den ' a bir işlevdir `Int` `Int` .

Çağrılabilir değerli bir ifadenin sonucunu çağırmak, çağrılabilir ifade etrafında fazladan bir çift parantez gerektirir.
Bu nedenle, önceki paragraftan çağırma sonucunu çağırmak için `Builder` doğru sözdizimi şöyledir:

```qsharp
(Builder(3))(2)
```

Bir [tür parametreli](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables) çağrılabilir çağırılırken, çağrılabilir ifadeden sonra, açılı ayraç içinde gerçek tür parametrelerini belirtebilirsiniz `< >` .
Derleyici gerçek türleri olduğu için bu eylem genellikle gereksizdir Q# .
Ancak, tür parametreli bir bağımsız değişken belirtilmemişse, [kısmi uygulama](xref:microsoft.quantum.guide.operationsfunctions#partial-application) *için gereklidir.*
Aynı zamanda farklı bir functor ile işlemleri bir çağrılabilir hale geçirilerek de yararlıdır.

Örneğin, imzası varsa `Func` `('T1, 'T2, 'T1) -> 'T2` `Op1` ve `Op2` imza içeriyorsa `(Qubit[] => Unit is Adj)` ve `Op3` `(Qubit[] => Unit)` `Func` `Op1` ilk bağımsız değişken olarak, `Op2` ikinci olarak ve `Op3` Üçüncü olarak çağırmak için imza varsa:

```qsharp
let combinedOp = Func<(Qubit[] => Unit), (Qubit[] => Unit is Adj)>(Op1, Op2, Op3);
```

Tür belirtimi gereklidir çünkü `Op3` ve `Op1` farklı türlere sahip olur, bu nedenle derleyici bunu belirtim olmadan belirsiz olarak değerlendirir.


## <a name="operator-precedence"></a>İşleç Önceliği

* Tüm ikili işleçler, hariç olmak üzere, doğru ilişkilendirilebilir `^` .

* Parantez, `[ ]` dizi Dilimleme ve dizin oluşturma için herhangi bir işleçten önce bağlayın.

* `Adjoint`Ve `Controlled` diğer tüm işleçlerden önce, dizi dizinlemesi ve sonra bağlama.

* İşlem ve işlev çağırma parantezleri aynı zamanda herhangi bir işleçten önce, ancak dizi dizinlemesi ve komik bir şekilde bağlanır.

Q# en yüksekten en düşüğe göre öncelik sırasına göre işleçler:

İşleç | Sayısına | Açıklama | İşlenen türleri
---------|----------|---------|---------------
 arkasında `!` | Birli | Unwrap | Kullanıcı tanımlı herhangi bir tür
 `-`, `~~~`, `not` | Birli | Sayısal negatif, bit düzeyinde tamamlama, mantıksal değilleme | `Int`, için `BigInt` veya için `Double` `-` `Int` veya `BigInt` `~~~` `Bool` için `not`
 `^` | İkili | Tamsayı güç | `Int`üs için veya `BigInt` taban için `Int`
 `/`, `*`, `%` | İkili | Bölme, çarpma, tamsayı mod | `Int`, `BigInt` veya `Double` için `/` `*` `Int` veya `BigInt` için `%`
 `+`, `-` | İkili | Ekleme veya dize ve dizi birleştirme, çıkarma | `Int``BigInt`veya `Double` `String` için bir dizi türü veya`+`
 `<<<`, `>>>` | İkili | Sol SHIFT, sağa kaydırma | `Int` veya `BigInt`
 `<`, `<=`, `>`, `>=` | İkili | Küçüktür, küçüktür veya eşittir, büyüktür, büyüktür veya eşittir karşılaştırmaları | `Int``BigInt`veya`Double`
 `==`, `!=` | İkili | eşit, eşit olmayan karşılaştırmalar | herhangi bir ilkel tür
 `&&&` | İkili | Bit düzeyinde AND | `Int` veya `BigInt`
 `^^^` | İkili | Bit düzeyinde XOR | `Int` veya `BigInt`
 <code>\|\|\|</code> | İkili | Bit düzeyinde OR | `Int` veya `BigInt`
 `and` | İkili | Mantıksal VE | `Bool`
 `or` | İkili | Mantıksal EĞER | `Bool`
 `..` | İkili/üçlü | Range işleci | `Int`
 `?` `|` | Üçlü | Koşullu | `Bool` Sol taraftaki
`w/` `<-` | Üçlü | Kopyala ve Güncelleştir | Bkz. [kopyalama ve güncelleştirme ifadeleri](#copy-and-update-expressions)

## <a name="next-steps"></a>Sonraki adımlar

Artık içindeki ifadelerle Q# çalışacağınızı, işlemler ve işlevlerin nasıl tanımlanacağını ve çağrılacağını öğrenmek için [içindeki Q# işlemlere ve işlevlerine](xref:microsoft.quantum.guide.operationsfunctions) geçebilirsiniz.
