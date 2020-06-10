---
title: 'Q içindeki tür Ifadeleri #'
description: Sabitleri, değişkenleri, işleçleri, işlemleri ve işlevleri soru-cevap olarak ifade olarak belirtme, başvurma ve birleştirme hakkında bilgi edinin.
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.expressions
ms.openlocfilehash: b32644382bb88fb11da00d0d7d78bbd797a0eaaa
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84629991"
---
# <a name="type-expressions-in-q"></a>Q içindeki tür Ifadeleri #

## <a name="numeric-expressions"></a>Sayısal Ifadeler

Sayısal ifadeler `Int` , veya türündeki ifadelerdir `BigInt` `Double` .
Diğer bir deyişle, tamsayı veya kayan noktalı sayılardır.

`Int`Q # içindeki sabit değerler yalnızca bir dizi basamakla yazılır.
Onaltılık ve ikili tamsayılar `0x` `0b` sırasıyla ve önekiyle desteklenir.

`BigInt`Q # içindeki sabit değerler, sondaki `l` veya `L` son ek ile yazılır.
Onaltılık büyük tamsayılar bir "0x" öneki ile desteklenir.
Bu nedenle, tüm geçerli sabit değer kullanımları aşağıda verilmiştir `BigInt` :

```qsharp
let bigZero = 0L;
let bigHex = 0x123456789abcdef123456789abcdefL;
let bigOne = bigZero + 1L;
```

`Double`Q # içindeki sabit değerler, ondalık basamaklar kullanılarak yazılan kayan nokta sayılarıdır.
Bunlar, bir ondalık noktayla, `.` ve/veya ' e ' veya ' e ' ile belirtilen üstel bir bölüm (yalnızca olası bir negatif işaret ve ondalık basamakların geçerli olması) ile yazılabilir.
Aşağıdakiler geçerli `Double` değişmez değerler: `0.0` , `1.2e5` , `1e-5` .

Herhangi bir öğe türünün dizi ifadesi verildiğinde, bir `Int` ifade [`Length`](xref:microsoft.quantum.core.length) yerleşik işlev kullanılarak, dizi ifadesi parantez içine alınmış ve ile oluşturulmuş olabilir `(` `)` .
Örneğin, `a` bir diziye bağlıysa, bir `Length(a)` tamsayı ifadesidir.
, `b` Tamsayıların dizilerindeki bir diziyse, `Int[][]` `Length(b)` içindeki alt dizilerin sayısıdır `b` ve `Length(b[1])` içindeki ikinci alt dizideki tamsayıların sayısıdır `b` .

Aynı türde iki sayısal ifade verildiğinde, ikili işleçler,,, `+` `-` `*` ve `/` Yeni bir sayısal ifade oluşturmak için kullanılabilir.
Yeni ifadenin türü, bileşen ifadelerinin türleriyle aynı olacaktır.

İki tamsayı ifadesi verildiğinde, ikili işleç `^` (güç) yeni bir tamsayı ifadesi oluşturmak için kullanılabilir.
Benzer şekilde, `^` Yeni bir Double ifadesi oluşturmak için iki çift ifade ile birlikte kullanılabilir.
Son olarak, `^` solda büyük bir tamsayı ve yeni bir büyük tamsayı ifadesi oluşturmak için sağdaki bir tamsayı ile birlikte kullanılabilir.
Bu durumda, ikinci parametrenin 32 bite sığması gerekir; Aksi takdirde, bir çalışma zamanı hatası oluşur.

İki tamsayı veya büyük tamsayı ifadesi verildiğinde, `%` (mod), `&&&` (BIT düzeyinde and), `|||` (bit düzeyinde OR) veya `^^^` (bit düzeyinde xor) işleçleri kullanılarak yeni bir tamsayı veya büyük tamsayı ifadesi oluşturulabilir.

Sol tarafta bir tamsayı veya büyük tamsayı ifadesi ve sağ taraftaki bir tamsayı ifadesi verildiğinde, `<<<` (aritmetik sol SHIFT) veya `>>>` (aritmetik sağa kaydırma) işleçleri, sol ifadeyle aynı türde yeni bir ifade oluşturmak için kullanılabilir.

Kaydırma işleminin ikinci parametresi (SHIFT miktarı) sıfırdan büyük veya sıfıra eşit olmalıdır; negatif kaydırma miktarları için davranış tanımsızdır.
Her iki vardiya işlemi için de SHIFT miktarı 32 bite uyum sağlamalıdır; Aksi takdirde, bir çalışma zamanı hatası oluşur.
Kaydırılan sayı bir tamsayı ise, SHIFT miktarı yorumlanır `mod 64` ; Yani, 1 vardiyası ve 65 vardiyası aynı etkiye sahiptir.

Hem tamsayı hem de büyük tamsayı değerleri için, vardiyalar aritmetik değerlerdir.
Negatif bir değeri sol veya sağ kaydırma, negatif bir sayı ile sonuçlanır.
Diğer bir deyişle, bir adım sola veya sağa kaydırma, sırasıyla 2 ile çarpılarak veya bölünerek tamamen aynıdır.

Tamsayı bölme ve tamsayı mod, negatif sayılar için C# olarak aynı davranışı izler.
Diğer bir deyişle, `a % b` her zaman aynı işarete sahip olur `a` ve `b * (a / b) + a % b` her zaman eşit olur `a` .
Örnek:

 `A` | `B` | `A / B` | `A % B`
---------|----------|---------|---------
 5 | 2 | 2 | 1
 5 | -2 | -2 | 1
 -5 | 2 | -2 | -1
 -5 | -2 | 2 | -1

Büyük tamsayı bölme ve mod aynı şekilde çalışmaktadır.

Herhangi bir sayısal ifade verildiğinde, birli işleç kullanılarak yeni bir ifade oluşturulmuş olabilir `-` .
Yeni ifade, anayent ifadesiyle aynı türde olacaktır.

Herhangi bir tamsayı veya büyük tamsayı ifadesi verildiğinde, aynı türde yeni bir ifade `~~~` (bit düzeyinde tamamlayıcı) birli işleç kullanılarak oluşturulabilir.

## <a name="boolean-expressions"></a>Boole İfadeleri

İki `Bool` değişmez değer de `true` ve ' dir `false` .

Aynı ilkel türdeki iki ifade verildiğinde, `==` ve `!=` ikili işleçler bir ifade oluşturmak için kullanılabilir `Bool` .
İki ifade eşitse ifade true, değilse false olur.

Kullanıcı tanımlı türlerin değerleri karşılaştırılamayabilir, yalnızca sarmalanmamış değerler karşılaştırılabilir. Örneğin, "sarmalama" işlecini kullanma `!` ( [Q # türlerinde](xref:microsoft.quantum.guide.types#access-anonymous-items-with-the-unwrap-operator)ayrıntılı olarak açıklanmıştır),

```qsharp
newtype WrappedInt = Int;     // Yes, this is a contrived example
let x = WrappedInt(1);
let y = WrappedInt(2);
let z = x! == y!;             // This will compile and yield z = false.
let t = x == y;               // This will cause a compiler error.
```

Değerler için eşitlik karşılaştırması `Qubit` kimlik eşitlik, yani iki ifadenin aynı qubit 'i tanımlamasına bakılmaksızın.
İki qubits 'in durumu karşılaştırılmaz, erişilmez, ölçülemez veya bu karşılaştırma tarafından değiştirilir.

Değerler için eşitlik karşılaştırması `Double` , yuvarlama etkileri nedeniyle yanıltıcı olabilir.
Örneğin, `49.0 * (1.0/49.0) != 1.0` .

Herhangi iki sayısal ifade verildiğinde,,, ve ikili işleçleri,,, `>` `<` `>=` ve `<=` ilk ifade sırasıyla sıfırdan büyük, küçüktür, büyüktür veya eşittir veya ikinci ifadeden daha küçük veya eşit olduğunda doğru olan yeni bir Boole ifadesi oluşturmak için kullanılabilir.

İki Boolean ifade verildiğinde, `and` ve `or` ikili işleçler, iki ifadenin her ikisi de (her ikisi de veya her ikisi de) doğru olduğunda doğru olan yeni bir Boole ifadesi oluşturmak için kullanılabilir.

Herhangi bir Boole ifadesi verildiğinde, `not` birli işleç yanlış olduğunda, doğru olan yeni bir Boole ifadesi oluşturmak için birli işleç kullanılabilir.

## <a name="string-expressions"></a>Dize Ifadeleri

Q #, `fail` deyimde ( [Denetim akışında](xref:microsoft.quantum.guide.controlflow#fail-statement)açıklanmıştır) ve standart işlevde dizelerin kullanılmasına izin verir [`Message`](xref:microsoft.quantum.intrinsic.message) .
İkinci öğesinin belirli davranışı kullanılan simülatmaya bağlıdır, ancak genellikle bir Q # programı sırasında çağrıldığında ana bilgisayar konsoluna bir ileti yazar.

Q # içindeki dizeler, değişmez değer veya enterpolasyonlu dizelerdir.

Dize sabit değerleri çoğu dilde basit dize sabit değerlerine benzer: çift tırnak içine alınmış bir Unicode karakter dizisi `"` .
Bir dizenin içinde, arka eğik çizgi karakteri `\` bir çift tırnak karakteriyle çıkmak ve yeni satır `\n` , satır başı olarak `\r` ve bir sekme olarak eklemek için kullanılabilir `\t` .
Örneğin:

```qsharp
"\"Hello world!\", she said.\n"
```
### <a name="interpolated-strings"></a>Ara değerli dizeler

Dize enterpolasyonları için Q # sözdizimi, C# sözdiziminin bir alt kümesidir, ancak burada soru-cevap ' a ait olan anahtar noktalarını özetliyoruz.
Ana farklılıklar aşağıda ele alınmıştır.

Bir dize sabit değerini, enterpolasyonlu bir dize olarak tanımlamak için, `$` simgeyi simgesiyle önüne ekleyin.
`$`Ve arasında `"` bir dize sabiti Başlatan boşluk olamaz.

Aşağıdaki, [`Message`](xref:microsoft.quantum.intrinsic.message) diğer Q # ifadeleriyle birlikte, bir ölçünün sonucunu konsola yazmak için işlevi kullanan temel bir örnektir.

```qsharp
    let num = 8;       // some Q# expression
    let res = M(q);
    Message($"Number: {num}, Result: {res}");
```
Geçerli bir Q # ifadesi, enterpolasyonlu bir dizede görünebilir.

C# sözdizimi hakkında daha fazla ayrıntı, [*enterpolasyonlu dizelerde*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings)bulunabilir.
En önemli ayrım, Q # ' ın tam (çok satırlı) enterpolasyonlu dizeleri desteklemedir.
Enterpolasyonlu dize içindeki ifadeler, C# söz dizimini değil, Q # söz dizimini izler.

## <a name="range-expressions"></a>Aralık Ifadeleri

, Ve olmak üzere üç ifade verildiğinde, `Int` `start` `step` `stop` `start .. step .. stop` birinci öğesi olan bir Aralık ifadesi, `start` ikinci öğe ise, `start+step` üçüncü öğe, `start+step+step` vb. olur `stop` .
Örneğin, pozitif ve olduğunda bir Aralık boş olabilir `step` `stop < start` .
Aralığın son öğesi, `stop` ve arasındaki fark, ve arasındaki fark olur `start` `stop` `step` ; diğer bir deyişle, Aralık her iki uçta da dahil olur.

Her iki ifade de verildiğinde `Int` `start` `stop` , ve `start .. stop` değerine eşit bir Aralık deyimidir `start .. 1 .. stop` .
Önünde ve `step` ' den küçük olsa bile, örtük ' ın + 1 olduğunu unutmayın `stop` `start` . böyle bir durumda, Aralık boş olur.

Bazı örnek aralıklar şunlardır:

- `1..3`1, 2, 3 aralığıdır.
- `2..2..5`2, 4 aralığındadır.
- `2..2..6`2, 4, 6 aralığıdır.
- `6..-2..2`6, 4, 2 aralığıdır.
- `2..1`boş aralıktır.
- `2..6..7`Aralık 2 ' dir.
- `2..2..1`boş aralıktır.
- `1..-1..2`boş aralıktır.

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

Tanımlama grubu değişmez değeri, ve ' de bulunan, virgülle ayrılmış şekilde, uygun türdeki öğe ifadelerinin dizelerdir `(` `)` .
Örneğin, `(1, One)` bir `(Int, Result)` ifadedir.

Değişmez değerler dışında, tek demet ifadeleri demet değerlerine, demet dizilerinin dizi öğelerine ve tanımlama grupları döndüren çağrılabilir çağırmaları olan sembollerdir.

## <a name="user-defined-type-expressions"></a>Kullanıcı tanımlı tür Ifadeleri

Kullanıcı tanımlı bir türün sabit değeri tür adından, ardından türün temel demet türünün bir tanımlama grubu değişmez değerinden oluşur.
Örneğin, `IntPair` temelli Kullanıcı tanımlı bir tür ise `(Int, Int)` , `IntPair(2, 3)` Bu türün geçerli bir sabit değeri olur.

Değişmez değerler dışında, Kullanıcı tanımlı bir türün tek ifadeleri, bu türün değerlerine, bu türden dizilerin dizi öğelerine ve bu türü döndüren çağrılabilir çağırmaları olan sembollerdir.

## <a name="unwrap-expressions"></a>Ifade kaydırmayı geri al

Q # içinde, Unwrap işleci sondaki bir ünlem işaretidir `!` .
Örneğin, `IntPair` temel alınan türe sahip kullanıcı tanımlı bir türdür `(Int, Int)` ve `s` değeri olan bir değişkense, `IntPair(2, 3)` daha sonra `s!` olur `(2, 3)` .

Diğer Kullanıcı tanımlı türler bakımından tanımlanan Kullanıcı tanımlı türler için, Unwrap işleci yinelenebilir. Örneğin, `s!!` paketlenmiş, sarmalanmamış değeri gösterir `s` .
Bu nedenle, `WrappedPair` temel alınan türe sahip kullanıcı tanımlı bir türdür `IntPair` ve `t` değeri olan bir değişkense, `WrappedPair(IntPair(1,2))` `t!!` olur `(1,2)` .

`!`İşleç, `[]` dizi dizini oluşturma ve dilimleme için dışındaki diğer işleçlerden daha yüksek önceliğe sahiptir.
`!``[]`, pozitif bir değer; yani, `a[i]![3]` şöyle okunmalıdır `((a[i])!)[3]` : `i` ' th öğesini al `a` , sarmalama kaldır ve sonra sarmalanmamış değerin 3. öğesini (bir dizi olması gerekir) alın.

`!`İşlecin önceliği belirgin olmayan bir etkiye sahip olabilir.
Bir işlev veya işlem sarmalanmamış bir değer döndürürse, bağımsız değişken grubu, sarmalama yerine çağrıya bağlamak için işlev veya işlem çağrısının parantez içine alınması gerekir.
Örnek:

```qsharp
let f = (Foo(arg))!;    // Calls Foo(arg), then unwraps the result
let g = Foo(arg)!;      // Syntax error
```

## <a name="array-expressions"></a>Dizi Ifadeleri

Dizi değişmez değeri, virgülle ayrılmış bir veya daha fazla öğe ifadesinin sırasıdır `[` ve `]` .
Tüm öğeler aynı türle uyumlu olmalıdır.

Aynı türde iki dizi verildiğinde, ikili `+` işleç iki dizinin birleşimi olan yeni bir dizi oluşturmak için kullanılabilir.
Örneğin, `[1,2,3] + [4,5,6]` `[1,2,3,4,5,6]` .

### <a name="array-creation"></a>Dizi oluşturma

Bir tür ve ifade verildiğinde `Int` , `new` işleç verilen boyutun yeni bir dizisini ayırmak için kullanılabilir.
Örneğin, `new Int[i + 1]` `Int` öğeleri içeren yeni bir dizi ayırır `i + 1` .

Boş dizi değişmez `[]` değerlerine izin verilmez.
Bunun yerine `new ★[0]` ,, `★` uygun bir tür için yer tutucu olarak olduğu gibi, istenen sıfır uzunluklu diziyi oluşturulmasına izin verir.

Yeni bir dizinin öğeleri, türe bağlı bir varsayılan değere başlatılır.
Çoğu durumda bu bazı sıfır çeşitlerinden oluşur.

Varlıklara başvurular olan qubits ve callables için makul bir varsayılan değer yoktur.
Bu nedenle, bu tür için varsayılan, çalışma zamanı hatasına neden olmadan kullanılamayan geçersiz bir başvurudur.
Bu, C# veya Java gibi dillerde null başvuruya benzer.
Qubits veya callables içeren diziler, öğeleri güvenle kullanılmadan önce varsayılan olmayan değerlerle düzgün başlatılmış olmalıdır. İçin uygun başlatma yordamları bulunabilir <xref:microsoft.quantum.arrays> .

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
 `Range` | Boş Aralık,`1..1..0`
 `Callable` | _geçersiz çağrılabilir_
 `Array['T]` | `'T[0]`

Demet türleri, öğe öğesi tarafından başlatılmış.


### <a name="array-elements"></a>Dizi öğeleri

Bir dizi ifadesi ve bir `Int` ifade verildiğinde, `[` ve dizi öğesi işleci kullanılarak yeni bir ifade oluşturulabilir `]` .
Yeni ifade, dizinin öğe türüyle aynı türde olacaktır.
Örneğin, bir `a` dizi s öğesine bağlıysa, `Double` `a[4]` bir `Double` ifadedir.

Dizi ifadesi basit bir tanımlayıcı değilse, bir öğe seçmek için parantez içine alınmalıdır.
Örneğin, `a` ve `b` öğelerinin her ikisi de varsa `Int` , birleştirilmeden bir öğe şöyle ifade edilir:

```qsharp
(a + b)[13]
```

Q # içindeki tüm diziler sıfır tabanlıdır.
Diğer bir deyişle, bir dizinin ilk öğesi `a` her zaman olur `a[0]` .


### <a name="array-slices"></a>Dizi dilimleri

Bir dizi ifadesi ve bir `Range` ifade verildiğinde, `[` ve dizi dilimi işleci kullanılarak yeni bir ifade oluşturulabilir `]` .
Yeni ifade, dizisiyle aynı türde olur ve tarafından tanımlanan sırada öğesi tarafından dizin oluşturulan dizi öğelerini içerir `Range` `Range` .
Örneğin, `a` bir dizi bir diziyle ilişkiliyse, ' ın `Double` `a[3..-1..0]` `Double[]` ilk dört öğesini, `a` ancak içinde göründükleri şekilde ters sırada içeren bir ifadedir `a` .

`Range`Boşsa, sonuçta elde edilen dizi dilimi sıfır uzunluğunda olur.

Başvuran dizi öğelerinde olduğu gibi, dizi ifadesi basit bir tanımlayıcı değilse, dilimin dilimlemek için parantez içine alınması gerekir.
`a`Ve `b` dizilerinin her ikisi de varsa `Int` , birleştirme işleminden alınan bir dilim şöyle ifade edilir:

```qsharp
(a+b)[1..2..7]
```

#### <a name="inferred-startend-values"></a>Çıkarılan başlangıç/bitiş değerleri

0,8 sürümümüzden başlayarak, Aralık Dilimleme için bağlamsal ifadeleri destekliyoruz. Özellikle, Aralık başlangıç ve bitiş değerleri bir Aralık Dilimleme ifadesi bağlamında atlanabilir. Bu durumda, derleyici aralığa yönelik istenen sınırlayıcıları çıkarması için aşağıdaki kuralları uygular. 

Örneğin, Aralık başlangıç değeri atlanırsa, çıkarılan başlangıç değeri 
- bir adım belirtilmemişse veya belirtilen adım pozitifse sıfır ve 
- , belirtilen adım negatifse, dilimli dizinin uzunluğu eksi bir değer. 

Aralık bitiş değeri atlanırsa, çıkarılan bitiş değeri 
- , bir adım belirtilmediyse veya belirtilen adım pozitif ise ve 
- , belirtilen adım negatifse sıfırdır. 

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

Tüm Q # türleri değer türleri olduğundan ve biraz özel bir rol alan qubits ile, bir değer bir simgeye bağlandığında veya bir sembol yeniden bağlandığında bir "kopya" oluşturulur. Yani, Q # davranışı atamadaki bir kopyanın oluşturulmasıyla aynı olur.
Pratikte yalnızca ilgili parçalar gerektiği şekilde yeniden oluşturulur. 

Bu özellikle de diziler içerir.
Özellikle, dizi öğelerini güncelleştirmek mümkün değildir. Var olan bir diziyi değiştirmek için bir *kopyalama ve güncelleştirme* mekanizmasının kullanılmasını gerekir.

Yeni diziler, *kopyalama ve güncelleştirme* ifadeleri aracılığıyla mevcut olanlardan oluşturulabilir.
Bir Copy-Update ifadesi formun bir ifadesidir `expression1 w/ expression2 <- expression3` , burada bir `expression1` tür için tür olması gerekir `T[]` `T` .
İkincisi, `expression2` içindeki diziye kıyasla değiştirilecek öğe dizinlerini tanımlar `expression1` ve türünden ya da `Int` türünde olmalıdır `Range` .
`expression2`Türünde ise `Int` , `expression3` türünde olması gerekir `T` . `expression2`Türünde ise `Range` , `expression3` türünde olması gerekir `T[]` .

Bir Copy-Update ifadesi, ' deki `arr w/ idx <- value` öğe (ler) i olarak ayarlanan öğeler hariç, içindeki öğesine karşılık gelen öğeye ayarlanmış olan yeni bir dizi oluşturur `arr` `idx` `value` . Örneğin, `arr` bir dizi içeriyorsa `[0,1,2,3]` , 
- `arr w/ 0 <- 10`dizi `[10,1,2,3]` .
- `arr w/ 2 <- 10`dizi `[0,1,10,3]` .
- `arr w/ 0..2..3 <- [10,12]`dizi `[10,1,12,3]` .

#### <a name="copy-and-update-expressions-for-named-items"></a>Adlandırılmış öğeler için kopyalama ve güncelleştirme ifadeleri

Kullanıcı tanımlı türlerde adlandırılmış öğeler için benzer ifadeler mevcuttur. 

Örneğin türü göz önünde bulundurun 

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

Çağrılabilir türlerle ilgili daha fazla ayrıntıyı aşağıda ve bir sonraki sayfada, [işlemler ve Q #](xref:microsoft.quantum.guide.operationsfunctions)' da işlevlerde bulabilirsiniz.

Ortak öğe türü bir işlem ya da işlev türü ise, tüm öğeler aynı giriş ve çıkış türlerine sahip olmalıdır.
Dizinin öğe türü tüm öğeleri tarafından desteklenen tüm nesneleri destekleyecektir.
Örneğin,, ve hepsi ise,, `Op1` `Op2` ve `Op3` `Qubit[] => Unit` `Op1` `Adjoint` `Op2` `Controlled` her ikisini de destekler, destekler ve `Op3` destekler:

- `[Op1, Op2]`, bir dizi `(Qubit[] => Unit)` işlemden oluşur.
- `[Op1, Op3]`, bir dizi `(Qubit[] => Unit is Adj)` işlemden oluşur.
- `[Op2, Op3]`, bir dizi `(Qubit[] => Unit is Ctl)` işlemden oluşur.

Ancak, `(Qubit[] => Unit is Adj)` ve `(Qubit[] => Unit is Ctl)` işlemleri ortak temel türüne sahip olsa `(Qubit[] => Unit)` da, bu işleçlerin dizilerinin ortak *of* bir temel türü paylaşmadığını unutmayın. Örneğin, `[[Op1], [Op2]]` Şu anda, uyumsuz dizi türlerinin bir dizisini oluşturmaya çalıştığı için bir hata oluşturur `(Qubit[] => Unit is Adj)[]` `(Qubit[] => Unit is Ctl)[]` .


## <a name="conditional-expressions"></a>Koşullu Ifadeler

Aynı türde ve bir Boolean ifadesinin iki diğer ifadesi verildiğinde, koşullu ifade soru işareti `?` ve dikey çubuk kullanılarak oluşturulmuş olabilir `|` .
Örneğin, `a==b ? c | d` .
Bu örnekte, koşullu ifadenin değeri `c` `a==b` true, ise false ise olur `d` .

### <a name="conditional-expressions-with-callables"></a>Callables ile koşullu ifadeler

İki ifade, aynı girişlere ve çıkışlara sahip olan ancak farklı komik desteği olan işlemlere göre değerlendirilemez.
Bu durumda, koşullu ifadenin türü, her iki ifade tarafından desteklenen tüm semantikleri destekleyen bu giriş ve çıkışlarla bir işlemdir.
Örneğin,, ve hepsi ise,, `Op1` `Op2` ve `Op3` `Qubit[]=>Unit` `Op1` `Adjoint` `Op2` `Controlled` her ikisini de destekler, destekler ve `Op3` destekler:

- `flag ? Op1 | Op2`bir `(Qubit[] => Unit)` işlemdir.
- `flag ? Op1 | Op3`bir `(Qubit[] => Unit is Adj)` işlemdir.
- `flag ? Op2 | Op3`bir `(Qubit[] => Unit is Ctl)` işlemdir.

Olası iki sonuç ifadesi varsa, bir işlev veya işlem çağrısı içeriyorsa, bu çağrı yalnızca çağrının değeri olacak şekilde gerçekleşdiğinde olur.
Örneğin, bu durumda, `a==b ? C(qs) | D(qs)` `a==b` true ise `C` işlem çağrılacaktır ve false ise yalnızca `D` çağrılacaktır.
Bu, diğer dillerdeki kısa devre 'ya benzer.

## <a name="callable-expressions"></a>Çağrılabilir Ifadeler

Çağrılabilir sabit değer, derleme kapsamında tanımlanan bir işlemin veya işlevin adıdır.
Örneğin, `X` standart kitaplık işlemine başvuran bir işlem sabit değeri `X` ve `Message` standart kitaplık işlevine başvuran bir işlev sabit değeri `Message` .

Bir işlem `Adjoint` functor destekliyorsa, `Adjoint op` bir işlem ifadesi olur.
Benzer şekilde, işlem `Controlled` functor 'ı destekliyorsa, `Controlled op` bir işlem ifadesi olur.
Bu ifadelerin türleri [çağıran işlem özelleştirmeleri](xref:microsoft.quantum.guide.operationsfunctions#calling-operation-specializations)sırasında belirtilmiştir.

Funörler ( `Adjoint` ve `Controlled` ), Unwrap operatörü `!` ve [] ' ile dizi dizini oluşturma dışında diğer işleçlerden daha yakından bağlanır.
Bu nedenle, işlemlerin kullanılan funları destekledikleri varsayılarak şunlar geçerlidir:

```qsharp
Adjoint Op(qs)
Controlled Op(controls, targets)
Controlled Adjoint Op(controls, targets)
Adjoint WrappedOp!(qs)
```

### <a name="type-parameterized-callable-expressions"></a>Tür parametreli çağrılabilir ifadeler

Çağrılabilir bir sabit değer olarak kullanılabilir, bir değişkene atamak veya başka bir çağrılabilir öğesine geçirmek için deyin.
Bu durumda, çağrılabilir [tür parametrelerine](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables)sahipse, çağrılabilir değerin bir parçası olarak sağlanması gerekir.
Çağrılabilir bir değer belirtilmeyen tür parametrelerine sahip olamaz.

Örneğin, `Fun` imzasına sahip bir işlevdir `'T1->Unit` :

```qsharp
let f = Fun<Int>;            // f is (Int->Unit).
let g = Fun;                 // This causes a compilation error.
SomeOtherFun(Fun<Double>);   // A (Double->Unit) is passed to SomOtherFun.
SomeOtherFun(Fun);           // This also causes a compilation error.
```

## <a name="callable-invocation-expressions"></a>Çağrılabilir çağırma Ifadeleri

Çağrılabilir bir (işlem veya işlev) ifadesi ve çağrılabilir öğesinin giriş türünün bir tanımlama grubu ifadesi verildiğinde, çağrılabilir ifadeye kayıt kümesi ifadesi eklenerek bir çağırma ifadesi oluşturulabilir.
Çağırma ifadesinin türü, çağrılabilir olan imzanın çıkış türüdür.

Örneğin, `Op` imzaya sahip bir işlem ise `((Int, Qubit) => Double)` , `Op(3, qubit1)` türünde bir ifadedir `Double` .
Benzer şekilde, `Sin` imzaya sahip bir `(Double -> Double)` `Sin(0.1)` işlevsiyse, türünde bir ifadedir `Double` .
Son olarak, `Builder` imza içeren bir işlevdir `(Int -> (Int -> Int))` ,, `Builder(3)` öğesinden Int 'e kadar bir işlevdir.

Çağrılabilir değerli bir ifadenin sonucunu çağırmak, çağrılabilir ifade etrafında fazladan bir çift parantez gerektirir.
Bu nedenle, önceki paragraftan çağırma sonucunu çağırmak için `Builder` doğru sözdizimi şöyledir:

```qsharp
(Builder(3))(2)
```

Bir [tür parametreli](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables) çağrılabilir çağırılırken, gerçek tür parametreleri açılı ayraç içinde `<` ve `>` çağrılabilir ifadeden sonra belirtilebilir.
Q # derleyicisi gerçek türleri çıkardığı için bu genellikle gereksizdir.
Ancak, tür parametreli bir bağımsız değişken belirtilmemişse, [kısmi uygulama](xref:microsoft.quantum.guide.operationsfunctions#partial-application) *için gereklidir.*
Ayrıca bazen farklı functor ile işlemleri bir çağrılabilir olarak geçirirken yararlı olur.

Örneğin, imzası varsa `Func` ve imza `('T1, 'T2, 'T1) -> 'T2` içeriyorsa `Op1` `Op2` `(Qubit[] => Unit is Adj)` ve `Op3` `(Qubit[] => Unit)` `Func` `Op1` ilk bağımsız değişken olarak, `Op2` ikinci olarak ve üçüncü olarak çağırmak için imza varsa `Op3` :

```qsharp
let combinedOp = Func<(Qubit[] => Unit), (Qubit[] => Unit is Adj)>(Op1, Op2, Op3);
```

Tür belirtimi gereklidir çünkü `Op3` ve `Op1` farklı türlere sahip olur, bu nedenle derleyici bunu belirtim olmadan belirsiz olarak değerlendirir.


## <a name="operator-precedence"></a>İşleç Önceliği

Tüm ikili işleçler, hariç olmak üzere, doğru ilişkilendirilebilir `^` .

Parantez ve `[` `]` dizi Dilimleme ve dizin oluşturma için herhangi bir işleçten önce bağlayın.

`Adjoint`Ve `Controlled` diğer tüm işleçlerden önce, dizi dizinlemesi ve sonra bağlama.

İşlem ve işlev çağırma parantezleri aynı zamanda herhangi bir işleçten önce, ancak dizi dizinlemesi ve komik bir şekilde bağlanır.

En yüksekten en düşüğe göre öncelik sırasına göre işleçler:

Operatör | Sayısına | Description | İşlenen türleri
---------|----------|---------|---------------
 arkasında`!` | Birli | Unwrap | Kullanıcı tanımlı herhangi bir tür
 `-`, `~~~`, `not` | Birli | Sayısal negatif, bit düzeyinde tamamlama, mantıksal değilleme | `Int`, için `BigInt` veya için `Double` `-` `Int` veya `BigInt` `~~~` `Bool` için`not`
 `^` | İkili | Tamsayı güç | `Int`üs için veya `BigInt` taban için `Int`
 `/`, `*`, `%` | İkili | Bölme, çarpma, tamsayı mod | `Int`, `BigInt` veya `Double` için `/` `*` `Int` veya `BigInt` için`%`
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
 `?` `|` | Üçlü | Koşullu | `Bool`Sol taraftaki
`w/` `<-` | Üçlü | Kopyala ve Güncelleştir | bkz. [kopyalama ve güncelleştirme ifadeleri](#copy-and-update-expressions)

## <a name="next-steps"></a>Sonraki adımlar

Artık Q # ' da ifadelerle çalışdığınıza göre, işlem ve işlevlerin nasıl tanımlanacağını ve çağrılacağını öğrenmek için [q # Içindeki işlemlere ve işlevlere](xref:microsoft.quantum.guide.operationsfunctions) gidebilirsiniz.
