---
title: 'S # Ifadeleri'
description: Sabitleri, değişkenleri, işleçleri, işlemleri ve işlevleri soru-cevap olarak ifade olarak belirtme, başvurma ve birleştirme hakkında bilgi edinin.
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.language.expressions
ms.openlocfilehash: 095be52af27f827f3e52d39a70702f50d6d59ee8
ms.sourcegitcommit: db23885adb7ff76cbf8bd1160d401a4f0471e549
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/01/2020
ms.locfileid: "82683921"
---
# <a name="expressions"></a>İfadeler

## <a name="grouping"></a>Gruplandırma

Herhangi bir ifade verildiğinde, parantez içine alınmış aynı ifade aynı türde bir ifadedir.
`(7)` Örneğin, bir `Int` ifadedir `([1,2,3])` , dizi `Int`türünde bir ifadedir ve `((1,2))` türünde `(Int, Int)`bir ifadedir.

[Tür modelinde](xref:microsoft.quantum.language.type-model#tuple-types) açıklanan basit değerler ve tek öğeli tanımlama grupları arasındaki denklik, Grup olarak ve `(6)` `(6)` tek öğeli tanımlama grubu arasındaki belirsizlik ortadan kaldırır.

## <a name="symbols"></a>Simgeleri

Türünde `'T` bir değere göre veya atanan bir simgenin adı, türünde `'T`bir ifadedir.
Örneğin, sembol `count` tamsayı değerine `5` `count` bağlıysa bir tamsayı ifadesidir.

## <a name="numeric-expressions"></a>Sayısal Ifadeler

Sayısal ifadeler, `Int` `BigInt`veya `Double`türündeki ifadelerdir.
Diğer bir deyişle, tamsayı veya kayan noktalı sayılardır.

`Int`Soru-cevap "l" veya "L" gerekli olmadığında (veya izin verilmeyen), Q # içindeki değişmez değerler C# ' deki tamsayı değişmez değerler ile aynıdır.
Onaltılık ve ikili tamsayılar sırasıyla bir "0x" ve "0b" önekiyle desteklenir.

`BigInt`Soru-cevap "l" veya "L" ile, Q # içindeki sabit değerler .NET 'teki büyük tamsayı dizeleriyle aynıdır.
Onaltılık büyük tamsayılar bir "0x" öneki ile desteklenir.
Bu nedenle, tüm geçerli `BigInt` sabit değer kullanımları aşağıda verilmiştir:

```qsharp
let bigZero = 0L;
let bigHex = 0x123456789abcdef123456789abcdefL;
let bigOne = bigZero + 1L;
```

`Double`Soru-cevap "d" veya "D" gerekli olmadığında (veya izin verilmeyen), Q # içindeki sabit değerler C# içindeki Double değişmez değerler ile aynıdır.

Herhangi bir öğe türünün dizi ifadesi verildiğinde, `Int` bir ifade `Length` yerleşik işlev kullanılarak, dizi ifadesi parantez içine alınmış `(` ve `)`ile oluşturulmuş olabilir.
Örneğin, `a` bir diziye `Length(a)` bağlıysa, bir tamsayı ifadesidir.
`b` , Tamsayıların `Int[][]` `Length(b)` dizilerindeki bir diziyse, içindeki `b`alt dizilerin sayısıdır ve `Length(b[1])` içindeki `b`ikinci alt dizideki tamsayıların sayısıdır.

Aynı türde iki sayısal ifade verildiğinde, ikili `+`işleçler, `-` `*`,, ve `/` yeni bir sayısal ifade oluşturmak için kullanılabilir.
Yeni ifadenin türü, bileşen ifadelerinin türleriyle aynı olacaktır.

İki tamsayı ifadesi verildiğinde, ikili işleç `^` (güç) yeni bir tamsayı ifadesi oluşturmak için kullanılabilir.
Benzer şekilde `^` , yeni bir Double ifadesi oluşturmak için iki çift ifade ile birlikte kullanılabilir.
Son olarak `^` , solda büyük bir tamsayı ve yeni bir büyük tamsayı ifadesi oluşturmak için sağdaki bir tamsayı ile birlikte kullanılabilir.
Bu durumda, ikinci parametrenin 32 bite sığması gerekir; Aksi takdirde, bir çalışma zamanı hatası oluşur.

İki tamsayı veya büyük tamsayı ifadesi verildiğinde `%` , (mod), `&&&` (bit düzeyinde and), `|||` (bit düzeyinde OR) veya `^^^` (bit düzeyinde xor) işleçleri kullanılarak yeni bir tamsayı veya büyük tamsayı ifadesi oluşturulabilir.

Sol tarafta bir tamsayı veya büyük tamsayı ifadesi ve sağ taraftaki bir tamsayı ifadesi verildiğinde, `<<<` (aritmetik sol SHIFT) veya `>>>` (aritmetik sağa kaydırma) işleçleri, sol ifadeyle aynı türde yeni bir ifade oluşturmak için kullanılabilir.

Kaydırma işleminin ikinci parametresi (SHIFT miktarı) sıfırdan büyük veya sıfıra eşit olmalıdır; negatif kaydırma miktarları için davranış tanımsızdır.
Her iki vardiya işlemi için de SHIFT miktarı 32 bite uyum sağlamalıdır; Aksi takdirde, bir çalışma zamanı hatası oluşur.
Kaydırılan sayı bir tamsayı ise, kaydırma miktarı yorumlanır `mod 64`; Yani, 1 ' in bir vardiyası ve 65 vardiyası aynı etkiye sahiptir.

Hem tamsayı hem de büyük tamsayı değerleri için, vardiyalar aritmetik değerlerdir.
Negatif bir değeri sol veya sağ kaydırma, negatif bir sayı ile sonuçlanır.
Diğer bir deyişle, bir adım sola veya sağa kaydırma, sırasıyla 2 ile çarpılarak veya bölünerek tamamen aynıdır.

Tamsayı bölme ve tamsayı mod, negatif sayılar için C# olarak aynı davranışı izler.
Diğer bir deyişle `a % b` , her zaman aynı işarete `a`sahip olur ve `b * (a / b) + a % b` her zaman eşit `a`olur.
Örneğin:

 `A` | `B` | `A / B` | `A % B`
---------|----------|---------|---------
 5 | 2 | 2 | 1
 5 | -2 | -2 | 1
 -5 | 2 | -2 | -1
 -5 | -2 | 2 | -1

Büyük tamsayı bölme ve mod aynı şekilde çalışmaktadır.

Herhangi bir sayısal ifade verildiğinde, `-` birli işleç kullanılarak yeni bir ifade oluşturulmuş olabilir.
Yeni ifade, anayent ifadesiyle aynı türde olacaktır.

Herhangi bir tamsayı veya büyük tamsayı ifadesi verildiğinde, aynı türde yeni bir ifade `~~~` (bit düzeyinde tamamlayıcı) birli işleç kullanılarak oluşturulabilir.

## <a name="boolean-expressions"></a>Boole İfadeleri

İki `Bool` değişmez değer de ve `true` ' `false`dir.

Aynı ilkel türdeki iki ifade verildiğinde, `==` ve `!=` ikili işleçler bir `Bool` ifade oluşturmak için kullanılabilir.
İki ifade eşitse ifade true, değilse false olur.

Kullanıcı tanımlı türlerin değerleri karşılaştırılamayabilir, yalnızca sarmalanmamış değerler karşılaştırılabilir. Örneğin, "sarmalama" işlecini `!` kullanarak ( [Q # tür modeli sayfasında](xref:microsoft.quantum.language.type-model#user-defined-types)açıklanmıştır),

```qsharp
newtype WrappedInt = Int;     // Yes, this is a contrived example
let x = WrappedInt(1);
let y = WrappedInt(2);
let z = x! == y!;             // This will compile and yield z = false.
let t = x == y;               // This will cause a compiler error.
```

Değerler için `Qubit` eşitlik karşılaştırması kimlik eşitliğini; diğer bir deyişle, iki ifadenin aynı qubit 'i tanımlamasına bakılmaksızın.
İki qubits 'in durumu karşılaştırılmaz, erişilmez, ölçülemez veya bu karşılaştırma tarafından değiştirilir.

Değerler için `Double` eşitlik karşılaştırması, yuvarlama etkileri nedeniyle yanıltıcı olabilir.
Örneğin, `49.0 * (1.0/49.0) != 1.0`.

Herhangi iki sayısal ifade verildiğinde,,, ve `>`ikili `<`işleçleri `>=`,, `<=` , ve ilk ifade sırasıyla sıfırdan büyük, küçüktür, büyüktür veya eşittir veya ikinci ifadeden daha küçük veya eşit olduğunda doğru olan yeni bir Boole ifadesi oluşturmak için kullanılabilir.

İki Boolean ifade verildiğinde, `and` ve `or` ikili işleçler, iki ifadenin her ikisi de (her ikisi de veya her ikisi de) doğru olduğunda doğru olan yeni bir Boole ifadesi oluşturmak için kullanılabilir.

Herhangi bir Boole ifadesi verildiğinde, `not` birli işleç yanlış olduğunda, doğru olan yeni bir Boole ifadesi oluşturmak için birli işleç kullanılabilir.

## <a name="string-expressions"></a>Dize Ifadeleri

Q #, `fail` deyimde ve `Log` standart işlevde dizelerin kullanılmasına izin verir.

Q # içindeki dizeler, değişmez değer veya enterpolasyonlu dizelerdir.
Dize sabit değerleri çoğu dilde basit dize sabit değerlerine benzer: çift tırnak içine alınmış bir Unicode karakter dizisi `"`.
Bir dizenin `\` içinde, arka eğik çizgi karakteri bir çift tırnak karakteriyle çıkmak ve yeni satır `\n`, satır başı olarak `\r`ve bir sekme olarak `\t`eklemek için kullanılabilir.
Örneğin:

```qsharp
"\"Hello world!\", she said.\n"
```

Dize enterpolasyonları için Q # sözdizimi, C# 7,0 sözdiziminin bir alt kümesidir; S #, tam (çok satırlı) enterpolasyonlu dizeleri desteklemez.
C# sözdizimi için bkz. [*enterpolasyonlu dizeler*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings) .

Enterpolasyonlu dize içindeki ifadeler, C# söz dizimini değil, Q # söz dizimini izler.
Geçerli bir Q # ifadesi, enterpolasyonlu bir dizede görünebilir.

## <a name="qubit-expressions"></a>Qubit Ifadeleri

Tek `Qubit` ifadeler, `Qubit` `Qubit` dizilerin değerlerine veya dizi öğelerine bağlanan sembollerdir.
`Qubit` Değişmez değer yok.

## <a name="pauli-expressions"></a>Pauli Ifadeleri

Dört `Pauli` değeri `PauliI` `PauliX` `PauliZ` `Pauli` ,,, ve, tüm geçerli ifadelerdir. `PauliY`

Bunun dışında, tek `Pauli` ifadeler, dizilere ait `Pauli` `Pauli` değerlere veya dizi öğelerine bağlanan sembollerdir.

## <a name="result-expressions"></a>Sonuç Ifadeleri

İki `Result` değer `One` ve `Zero`, geçerli `Result` ifadelerdir.

Bunun dışında, tek `Result` ifadeler, dizilere ait `Result` `Result` değerlere veya dizi öğelerine bağlanan sembollerdir.
Özellikle, tamsayıyla `1`aynı `One` olmadığını ve aralarında doğrudan dönüşüm olmadığını unutmayın.
Aynı, ve `Zero` `0`için de geçerlidir.

## <a name="range-expressions"></a>Aralık Ifadeleri

, Ve `Int` `start` `step` `start` `start+step` `start+step+step` `stop` olmak üzere üç ifade verildiğinde, birinci öğesi olan bir Aralık ifadesi, ikinci öğe ise, üçüncü öğe, vb. olur. `stop` `start .. step .. stop`
Örneğin, pozitif ve `step` `stop < start`olduğunda bir Aralık boş olabilir.
Aralığın son öğesi, ve arasındaki fark, `stop` ve `start` `stop` arasında bir tamsayı `step`ise, diğer bir deyişle, Aralık her iki uçta da dahil olur.

`Int` Her iki ifade `start` de verildiğinde `stop`, `start .. stop` ve değerine eşit bir Aralık deyimidir `start .. 1 .. stop`.
Yukarıda, ' den `step` `stop` `start`küçük olsa bile, zımni + 1 olduğunu unutmayın. Böyle bir durumda, Aralık boştur.

Bazı örnek aralıklar şunlardır:

- `1..3`1, 2, 3 aralığıdır.
- `2..2..5`2, 4 aralığındadır.
- `2..2..6`2, 4, 6 aralığıdır.
- `6..-2..2`6, 4, 2 aralığıdır.
- `2..1`boş aralıktır.
- `2..6..7`Aralık 2 ' dir.
- `2..2..1`boş aralıktır.
- `1..-1..2`boş aralıktır.

## <a name="callable-expressions"></a>Çağrılabilir Ifadeler

Çağrılabilir sabit değer, derleme kapsamında tanımlanan bir işlemin veya işlevin adıdır.
Örneğin, `X` standart kitaplık `X` işlemine başvuran bir işlem sabit değeri ve `Message` standart kitaplık `Message` işlevine başvuran bir işlev sabit değeri.

Bir işlem `Adjoint` functor destekliyorsa, bir işlem ifadesi `Adjoint op` olur.
Benzer şekilde, işlem `Controlled` functor 'ı destekliyorsa, bir işlem `Controlled op` ifadesi olur.
Bu ifadelerin türleri, [Funörler](xref:microsoft.quantum.language.type-model#functors)içinde belirtilmiştir.

Funörler (`Adjoint` ve `Controlled`), ile `!` `[]`geri sarım operatörü ve dizi dizini oluşturma dışında diğer işleçlerden daha yakından bağlanır.
Bu nedenle, işlemlerin kullanılan funları destekledikleri varsayılarak şunlar geçerlidir:

```qsharp
Adjoint Op(qs)
Controlled Op(controls, targets)
Controlled Adjoint Op(controls, targets)
Adjoint WrappedOp!(qs)
```

Çağrılabilir bir sabit değer olarak kullanılabilir, bir değişkene atamak veya başka bir çağrılabilir öğesine geçirmek için deyin.
Bu durumda, çağrılabilir tür parametrelerine sahipse, çağrılabilir değerin bir parçası olarak sağlanması gerekir.
Çağrılabilir bir değer belirtilmeyen tür parametrelerine sahip olamaz.

Örneğin, imzasına `'T1->Unit`sahip `Fun` bir işlevdir:

```qsharp
let f = Fun<Int>;            // f is Int->Unit.
SomeOtherFun(Fun<Double>);   // A Double->Unit is passed to SomeOtherFun.
let g = Fun;                 // This causes a compilation error.
SomeOtherFun(Fun);           // This also causes a compilation error.
```

## <a name="callable-invocation-expressions"></a>Çağrılabilir çağırma Ifadeleri

Çağrılabilir bir (işlem veya işlev) ifadesi ve çağrılabilir öğesinin giriş türünün bir tanımlama grubu ifadesi verildiğinde, çağrılabilir ifadeye kayıt kümesi ifadesi eklenerek bir çağırma ifadesi oluşturulabilir.
Çağırma ifadesinin türü, çağrılabilir olan imzanın çıkış türüdür.

Örneğin, `Op` imzaya `((Int, Qubit) => Double)`sahip bir işlem ise, `Op(3, qubit1)` türünde `Double`bir ifadedir.
Benzer şekilde, `Sin` imzaya `(Double -> Double)`sahip bir işlevsiyse, `Sin(0.1)` türünde `Double`bir ifadedir.
Son olarak, `Builder` imza `(Int -> (Int -> Int))`içeren bir Işlevdir,, `Builder(3)` öğesinden Int 'e kadar bir işlevdir.

Çağrılabilir değerli bir ifadenin sonucunu çağırmak, çağrılabilir ifade etrafında fazladan bir çift parantez gerektirir.
Bu nedenle, önceki paragraftan çağırma `Builder` sonucunu çağırmak için doğru sözdizimi şöyledir:

```qsharp
(Builder(3))(2)
```

Bir tür parametreli çağrılabilir çağırılırken, gerçek tür parametreleri açılı ayraç `<` içinde ve `>` çağrılabilir ifadeden sonra belirtilebilir.
Q # derleyicisi gerçek türleri çıkardığı için bu genellikle gereksizdir.
Bir tür parametreli bağımsız değişken belirtilmemişse, kısmi uygulama (aşağıya bakın) için gereklidir.
Ayrıca bazen farklı functor ile işlemleri bir çağrılabilir olarak geçirirken yararlı olur.

Örneğin, imzası `Func` `('T1, 'T2, 'T1) -> 'T2`varsa `Op1` `Op2` ve `(Qubit[] => Unit is Adj)`imza içeriyorsa ve `Op3` ilk bağımsız değişken `(Qubit[] => Unit)` `Func` `Op1` `Op2` olarak, ikinci olarak ve `Op3` üçüncü olarak çağırmak için imza varsa:

```qsharp
let combinedOp = Func<(Qubit[] => Unit), (Qubit[] => Unit is Adj)>(Op1, Op2, Op3);
```

Tür belirtimi gereklidir çünkü `Op3` ve `Op1` farklı türlere sahip olur, bu nedenle derleyici bunu belirtim olmadan belirsiz olarak değerlendirir.

### <a name="partial-application"></a>Kısmi uygulama

Çağrılabilir bir ifade verildiğinde, çağrılabilir bir bağımsız değişkenlerin alt kümesini sağlayarak yeni bir çağrılabilir oluşturulabilir.
Buna _kısmi uygulama_denir.

Q # ' da, kısmen uygulanan çağrılabilir bir normal çağırma ifadesi yazılarak, ancak belirtilmeyen bağımsız değişkenler için alt çizgi `_`kullanılarak ifade edilir.
Elde edilen çağrılabilir taban çağrılabilir ile aynı sonuç türüne ve işlemler için aynı uzmanlıklarla aynı.
Kısmi uygulamanın giriş türü, yalnızca belirtilen bağımsız değişkenler kaldırılmış olan özgün türdür.

Kısmi uygulama oluştururken değişebilir bir değişken belirtilen bağımsız değişken olarak geçirilirse, değişkenin geçerli değeri kullanılır.
Değişkenin değerini daha sonra değiştirmek kısmi uygulamayı etkilemez.

Örneğin, şunu `((Int, ((Qubit, Qubit), Double)) => Unit is Adj)`içeriyorsa `Op` :

- `Op(5,(_,_))`türüne `(((Qubit,Qubit), Double) => Unit is Adj)`sahiptir ve bu nedenle `Op(5,_)`.
- `Op(_,(_,1.0))`türü `((Int, (Qubit,Qubit)) => Unit is Adj)`.
- `Op(_,((q1,q2),_))`türü `((Int,Double) => Unit is Adj)`.
   Burada tek demet denklik 'i uyguladığımızda aklınızda olduğunu unutmayın.

Kısmen uygulanmış çağrılabilir, derleyici tarafından çıkarsanamayan tür parametrelerine sahipse, bunun çağırma sitesinde sağlanması gerekir.
Kısmi uygulama belirtilmeyen tür parametrelerine sahip olamaz.

Örneğin, şunu `(('T1, Qubit, 'T1) => Unit : Adjoint)`içeriyorsa `Op` :

```qsharp
let f1 = Op<Int>(_, qb, _); // f1 has type ((Int,Int) => Unit is Adj)
let f2 = Op(5, qb, _);      // f2 has type (Int => Unit is Adj)
let f3 = Op(_,qb, _);       // f3 generates a compilation error
```

### <a name="recursion"></a>Özyineleme

Q # callables 'in doğrudan veya dolaylı olarak özyinelemeli olmasına izin verilir.
Diğer bir deyişle, bir işlem veya işlev kendisini çağırabilir veya çağrılabilir işlemi doğrudan veya dolaylı olarak çağıran başka bir çağrılabilir çağrısı sağlayabilir.

Ancak özyineleme kullanımı hakkında iki önemli yorum vardır:

- İşlemlerde özyineleme kullanımı, bazı iyileştirmelere engel olabilir.
  Bu, algoritmanın yürütme süresi üzerinde önemli bir etkiye sahip olabilir.
- Gerçek bir hisse cihazında yürütme yaparken, yığın alanı sınırlı olabilir ve bu nedenle derin özyineleme bir çalışma zamanı hatasına neden olabilir.
  Özellikle, Q # derleyicisi ve çalışma zamanı, kuyruk özyinelemeyi tanımlamaz ve iyileştirmez.

## <a name="tuple-expressions"></a>Demet Ifadeleri

Tanımlama grubu değişmez değeri, ve `(` `)`' de bulunan, virgülle ayrılmış şekilde, uygun türdeki öğe ifadelerinin dizelerdir.
Örneğin, `(1, One)` bir `(Int, Result)` ifadedir.

Değişmez değerler dışında, tek demet ifadeleri demet değerlerine, demet dizilerinin dizi öğelerine ve tanımlama grupları döndüren çağrılabilir çağırmaları olan sembollerdir.

## <a name="user-defined-type-expressions"></a>Kullanıcı tanımlı tür Ifadeleri

Kullanıcı tanımlı bir türün sabit değeri tür adından, ardından türün temel demet türünün bir tanımlama grubu değişmez değerinden oluşur.
Örneğin, `IntPair` temelli Kullanıcı tanımlı bir tür ise `(Int, Int)`, `IntPair(2,3)` bu türün geçerli bir sabit değeri olur.

Değişmez değerler dışında, Kullanıcı tanımlı bir türün tek ifadeleri, bu türün değerlerine, bu türden dizilerin dizi öğelerine ve bu türü döndüren çağrılabilir çağırmaları olan sembollerdir.

## <a name="unwrap-expressions"></a>Ifade kaydırmayı geri al

Q # içinde, Unwrap işleci sondaki bir ünlem işaretidir `!`.
Örneğin `IntPair` , temel alınan `(Int, Int)`türe sahip kullanıcı tanımlı bir türdür ve `s` değeri `IntPair(2,3)`olan bir değişkense, daha sonra `s!` olur. `(2,3)`

Diğer Kullanıcı tanımlı türler bakımından tanımlanan Kullanıcı tanımlı türler için. Unwrap işleci yinelenebilir olabilir; Örneğin, `s!!` paketlenmiş, sarmalanmamış değeri gösterir `s`.
Bu nedenle, `WrappedPair` temel `IntPair`alınan türe sahip kullanıcı tanımlı bir türdür ve `t` değeri `WrappedPair(IntPair(1,2))` `t!!` olan bir değişkense, olur. `(1,2)`

İşleç `!` , dizi dizini oluşturma ve dilimleme `[]` için dışındaki diğer işleçlerden daha yüksek önceliğe sahiptir.
`!`ve `[]` , pozitif bağlama; diğer bir deyişle `a[i]![3]` , şöyle `((a[i])!)[3]`okunmalıdır: `i`' th öğesini alın `a`, sarmalayın ve sonra sarmalanmamış değerin 3. öğesini (bir dizi olması gerekir) alın.

`!` İşlecin önceliği belirgin olmayan bir etkiye sahip olabilir.
Bir işlev veya işlem sarmalanmamış bir değer döndürürse, bağımsız değişken grubu, sarmalama yerine çağrıya bağlamak için işlev veya işlem çağrısının parantez içine alınması gerekir.
Örneğin:

```qsharp
let f = (Foo(arg))!;    // Calls Foo(arg), then unwraps the result
let g = Foo(arg)!;      // Syntax error
```

## <a name="array-expressions"></a>Dizi Ifadeleri

Dizi değişmez değeri, virgülle ayrılmış bir veya daha fazla öğe ifadesinin sırasıdır `[` ve. `]`
Tüm öğeler aynı türle uyumlu olmalıdır.

Ortak öğe türü bir işlem ya da işlev türü ise, tüm öğeler aynı giriş ve çıkış türlerine sahip olmalıdır.
Dizinin öğe türü tüm öğeleri tarafından desteklenen tüm nesneleri destekleyecektir.
Örneğin,, ve `Op1`hepsi `Op2` `Op3` `Qubit[] => Unit` `Op1` ise,, ve her ikisini de `Adjoint`destekler `Op2` , `Controlled`destekler ve `Op3` destekler:

- `[Op1, Op2]`, bir dizi `(Qubit[] => Unit)` işlemden oluşur.
- `[Op1, Op3]`, bir dizi `(Qubit[] => Unit is Adj)` işlemden oluşur.
- `[Op2, Op3]`, bir dizi `(Qubit[] => Unit is Ctl)` işlemden oluşur.

Boş dizi değişmez `[]`değerlerine izin verilmez.
Bunun yerine `new ★[0]`,, `★` uygun bir tür için yer tutucu olarak olduğu gibi, istenen sıfır uzunluklu diziyi oluşturulmasına izin verir.

Aynı türde iki dizi verildiğinde, ikili `+` işleç iki dizinin birleşimi olan yeni bir dizi oluşturmak için kullanılabilir.
Örneğin, `[1,2,3] + [4,5,6]` `[1,2,3,4,5,6]`.

### <a name="array-creation"></a>Dizi oluşturma

Bir tür ve `Int` ifade verildiğinde, `new` işleç verilen boyutun yeni bir dizisini ayırmak için kullanılabilir.
Örneğin, `new Int[i+1]` öğeleri içeren `Int` `i+1` yeni bir dizi ayırır.

Yeni bir dizinin öğeleri, türe bağlı bir varsayılan değere başlatılır.
Çoğu durumda bu bazı sıfır çeşitlerinden oluşur.

Varlıklara başvurular olan qubits ve callables için makul bir varsayılan değer yoktur.
Bu nedenle, bu tür için varsayılan, çalışma zamanı hatasına neden olmadan kullanılamayan geçersiz bir başvurudur.
Bu, C# veya Java gibi dillerde null başvuruya benzer.
Qubits veya callables içeren diziler, öğeleri güvenle kullanılmadan önce varsayılan olmayan değerlerle düzgün başlatılmış olmalıdır. İçin uygun başlatma yordamları bulunabilir <xref:microsoft.quantum.arrays>.

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


### <a name="jagged-arrays"></a>Düzensiz Diziler

Bazen "dizi dizisi" olarak adlandırılan pürüzlü bir dizi, öğeleri dizi olan bir dizidir. Pürüzlü bir dizinin öğeleri farklı boyutlarda olabilir. Aşağıdaki örnek, çarpma tablosunu temsil eden pürüzlü bir dizinin nasıl bildirilemeyeceğini ve başlatılacağını gösterir.

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


### <a name="array-slices"></a>Dizi dilimleri

Bir dizi ifadesi ve bir `Range` ifade verildiğinde, `[` ve `]` dizi dilimi işleci kullanılarak yeni bir ifade oluşturulabilir.
Yeni ifade, dizisiyle aynı türde olur ve tarafından tanımlanan sırada öğesi `Range`tarafından dizin oluşturulan dizi öğelerini içerir. `Range`
Örneğin, `a` bir dizi bir diziyle `Double`ilişkiliyse, `a[3..-1..0]` ' ın ilk dört öğesini, `Double[]` `a` ancak içinde `a`göründükleri şekilde ters sırada içeren bir ifadedir.

`Range` Boşsa, sonuçta elde edilen dizi dilimi sıfır uzunluğunda olur.

Dizi ifadesi basit bir tanımlayıcı değilse, dilimin dilimlemek için parantez içine alınması gerekir.
Örneğin, ve `a` `b` her iki dizisise `Int`, birleştirilmeden bir dilim şöyle ifade edilir:

```qsharp
(a+b)[1..2..7]
```

Q # içindeki tüm diziler sıfır tabanlıdır.
Diğer bir deyişle, bir dizinin `a` ilk öğesi her zaman `a[0]`olur.

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

## <a name="array-element-expressions"></a>Dizi öğesi Ifadeleri

Bir dizi ifadesi ve bir `Int` ifade verildiğinde, `[` ve `]` dizi öğesi işleci kullanılarak yeni bir ifade oluşturulabilir.
Yeni ifade, dizinin öğe türüyle aynı türde olacaktır.
Örneğin, `a` bir dizi `Double`s `a[4]` öğesine bağlıysa, bir `Double` ifadedir.

Dizi ifadesi basit bir tanımlayıcı değilse, bir öğe seçmek için parantez içine alınmalıdır.
Örneğin, ve `a` `b` öğelerinin her ikisi de `Int`varsa, birleştirilmeden bir öğe şöyle ifade edilir:

```qsharp
(a+b)[13]
```

Q # içindeki tüm diziler sıfır tabanlıdır.
Diğer bir deyişle, bir dizinin `a` ilk öğesi her zaman `a[0]`olur.


## <a name="copy-and-update-expressions"></a>Kopyalama ve güncelleştirme Ifadeleri

Yeni diziler, kopyalama ve güncelleştirme ifadeleri aracılığıyla mevcut olanlardan oluşturulabilir.
Bir Copy-Update ifadesi `expression1 w/ expression2 <- expression3`formun bir ifadesidir, burada `expression1` bir tür `T[]` `T`için tür olması gerekir. İkincisi `expression2` , içindeki `expression1` diziye kıyasla değiştirilecek öğe dizinlerini tanımlar ve türünden `Int` ya da türünde `Range`olmalıdır. `expression2` Türünde `Int`ise, `expression3` türünde `T`olması gerekir. `expression2` Türünde `Range`ise, `expression3` türünde `T[]`olması gerekir.

Bir Copy-Update `arr w/ idx <- value` ifadesi, ' deki öğe (ler) `arr` `idx`i olarak ayarlanan öğeler hariç, içindeki öğesine karşılık gelen öğeye ayarlanmış olan yeni bir dizi oluşturur. `value` Örneğin, bir dizi `arr` `[0,1,2,3]`içeriyorsa, 
- `arr w/ 0 <- 10`dizi `[10,1,2,3]`.
- `arr w/ 2 <- 10`dizi `[0,1,10,3]`.
- `arr w/ 0..2..3 <- [10,12]`dizi `[10,1,12,3]`.

Kullanıcı tanımlı türlerde adlandırılmış öğeler için benzer ifadeler mevcuttur. Örneğin türü göz önünde bulundurun 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
Türü `c` `Complex(1.,-1.)`değerini içeriyorsa,, `c w/ Re <- 0.` olarak `Complex` `Complex(0.,-1.)`değerlendirilen türünde bir ifadedir.

## <a name="conditional-expressions"></a>Koşullu Ifadeler

Aynı türde ve bir Boolean ifadesinin iki diğer ifadesi verildiğinde, koşullu ifade soru işareti `?` ve dikey çubuk `|`kullanılarak oluşturulmuş olabilir.
Örneğin, `a==b ? c | d`.
Bu örnekte, koşullu ifadenin değeri true `c` `a==b` `d` , ise false ise olur.

İki ifade, aynı girişlere ve çıkışlara sahip olan ancak farklı komik desteği olan işlemlere göre değerlendirilemez.
Bu durumda, koşullu ifadenin türü, her iki ifade tarafından desteklenen tüm semantikleri destekleyen bu giriş ve çıkışlarla bir işlemdir.
Örneğin,, ve `Op1`hepsi `Op2` `Op3` `Qubit[]=>Unit` `Op1` ise,, ve her ikisini de `Adjoint`destekler `Op2` , `Controlled`destekler ve `Op3` destekler:

- `flag ? Op1 | Op2`bir `(Qubit[] => Unit)` işlemdir.
- `flag ? Op1 | Op3`bir `(Qubit[] => Unit is Adj)` işlemdir.
- `flag ? Op2 | Op3`bir `(Qubit[] => Unit is Ctl)` işlemdir.

Olası iki sonuç ifadesi varsa, bir işlev veya işlem çağrısı içeriyorsa, bu çağrı yalnızca çağrının değeri olacak şekilde gerçekleşdiğinde olur.
Örneğin `a==b ? C(qs) | D(qs)`, bu durumda `a==b` , true ise `C` işlem çağrılacaktır ve false ise yalnızca `D` çağrılacaktır.
Bu, diğer dillerdeki kısa devre 'ya benzer.


## <a name="operator-precedence"></a>İşleç Önceliği

Tüm ikili işleçler, hariç olmak üzere `^`, doğru ilişkilendirilebilir.

`[` Parantez ve dizi Dilimleme ve dizin oluşturma için herhangi bir işleçten önce `]`bağlayın.

`Adjoint` Ve diğer tüm işleçlerden önce, dizi dizinlemesi ve `Controlled` sonra bağlama.

İşlem ve işlev çağırma parantezleri aynı zamanda herhangi bir işleçten önce, ancak dizi dizinlemesi ve komik bir şekilde bağlanır.

En yüksekten en düşüğe göre öncelik sırasına göre işleçler:

İşleç | Sayısına | Açıklama | İşlenen türleri
---------|----------|---------|---------------
 arkasında`!` | Li | Unwrap | Kullanıcı tanımlı herhangi bir tür
 `-`, `~~~`, `not` | Li | Sayısal negatif, bit düzeyinde tamamlama, mantıksal değilleme | `Int`, `BigInt` için `Double` veya `-`için `Int` veya `BigInt` `~~~`için `Bool``not`
 `^` | İkili | Tamsayı güç | `Int`üs `BigInt` için veya taban `Int` için
 `/`, `*`, `%` | İkili | Bölme, çarpma, tamsayı mod | `Int`, `BigInt` veya `Double` `/` `Int` için veya `BigInt` için `*``%`
 `+`, `-` | İkili | Ekleme veya dize ve dizi birleştirme, çıkarma | `Int``BigInt` `Double`veya `String` için bir dizi türü veya`+`
 `<<<`, `>>>` | İkili | Sol SHIFT, sağa kaydırma | `Int` veya `BigInt`
 `<`, `<=`, `>`, `>=` | İkili | Küçüktür, küçüktür veya eşittir, büyüktür, büyüktür veya eşittir karşılaştırmaları | `Int``BigInt` veya`Double`
 `==`, `!=` | İkili | eşit, eşit olmayan karşılaştırmalar | herhangi bir ilkel tür
 `&&&` | İkili | Bit düzeyinde AND | `Int` veya `BigInt`
 `^^^` | İkili | Bit düzeyinde XOR | `Int` veya `BigInt`
 <code>\|\|\|</code> | İkili | Bit düzeyinde OR | `Int` veya `BigInt`
 `and` | İkili | Mantıksal VE | `Bool`
 `or` | İkili | Mantıksal VEYA | `Bool`
 `..` | İkili/üçlü | Range işleci | `Int`
 `?` `|` | Üçlü | Koşullu | `Bool`Sol taraftaki
`w/` `<-` | Üçlü | Kopyala ve Güncelleştir | bkz. [kopyalama ve güncelleştirme ifadeleri](#copy-and-update-expressions)
