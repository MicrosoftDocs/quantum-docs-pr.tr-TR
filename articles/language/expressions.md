---
title: 'S # Ifadeleri'
description: Sabitleri, değişkenleri, işleçleri, işlemleri ve işlevleri soru-cevap olarak ifade olarak belirtme, başvurma ve birleştirme hakkında bilgi edinin.
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.language.expressions
ms.openlocfilehash: fbde873f220d737db17f889d00be33541e3eb59b
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907418"
---
# <a name="expressions"></a>İfadeler

## <a name="grouping"></a>Gruplandırma

Herhangi bir ifade verildiğinde, parantez içine alınmış aynı ifade aynı türde bir ifadedir.
Örneğin, `(7)` `Int` bir ifadedir, `([1,2,3])` `Int`s dizisi türünde bir ifadedir ve `((1,2))` türü `(Int, Int)`olan bir ifadedir.

[Tür modelinde](xref:microsoft.quantum.language.type-model#tuple-types) açıklanan basit değerler ve tek öğeli tanımlama grupları arasındaki denklik, grup olarak `(6)` ve tek öğeli tanımlama grubu olarak `(6)` arasındaki belirsizlik ortadan kaldırır.

## <a name="symbols"></a>Simgeleri

`'T` türünde bir değere atanan veya atanan bir simgenin adı `'T`türünde bir ifadedir.
Örneğin, sembol `count` `5`tamsayı değerine bağlıysa `count` bir tamsayı ifadesi olur.

## <a name="numeric-expressions"></a>Sayısal Ifadeler

Sayısal ifadeler `Int`, `BigInt`veya `Double`türündeki ifadelerdir.
Diğer bir deyişle, tamsayı veya kayan noktalı sayılardır.

`Int` değişmez değerleri, sonunda "l" veya "L C#" gerekli olmadığında (veya izin verilmeyen), içindeki tamsayı değişmez değerleri ile aynıdır.
Onaltılık ve ikili tamsayılar sırasıyla bir "0x" ve "0b" önekiyle desteklenir.

`BigInt` değişmez değerleri, "l" veya "L" ile birlikte .NET 'teki büyük tamsayı dizeleriyle aynıdır.
Onaltılık büyük tamsayılar bir "0x" öneki ile desteklenir.
Bu nedenle, `BigInt` değişmez değerlerin geçerli kullanımları aşağıda verilmiştir:

```qsharp
let bigZero = 0L;
let bigHex = 0x123456789abcdef123456789abcdefL;
let bigOne = bigZero + 1L;
```

`Double` değişmez değerler, sonunda "d" veya "D C#" gerekli olmadığında (veya izin verilmeyen), içindeki çift değişmez değerler ile aynıdır.

Herhangi bir öğe türünün dizi ifadesi verildiğinde, bir `Int` ifadesi, parantez, `(` ve `)`içine alınmış dizi ifadesi ile `Length` yerleşik işlevi kullanılarak oluşturulabilir.
Örneğin, `a` bir diziye bağlıysa `Length(a)` bir tamsayı ifadesidir.
`b` tamsayılar dizi diziyse `Int[][]`, `Length(b)` `b`içindeki alt dizilerin sayısıdır ve `Length(b[1])` `b`ikinci alt dizideki tamsayıların sayısıdır.

Aynı türde iki sayısal ifade verildiğinde, ikili işleçler `+`, `-`, `*`ve `/` yeni bir sayısal ifade oluşturmak için kullanılabilir.
Yeni ifadenin türü, bileşen ifadelerinin türleriyle aynı olacaktır.

İki tamsayı ifadesi verildiğinde, ikili işleç `^` (güç) yeni bir tamsayı ifadesi oluşturmak için kullanılabilir.
Benzer şekilde, `^` yeni bir Double ifadesi oluşturmak için iki Double ifadesiyle birlikte kullanılabilir.
Son olarak, `^` solda büyük bir tam sayı ile, yeni bir büyük tamsayı ifadesi oluşturmak için sağdaki bir tamsayı ile kullanılabilir.
Bu durumda, ikinci parametrenin 32 bite sığması gerekir; Aksi takdirde, bir çalışma zamanı hatası oluşur.

İki tamsayı veya büyük tamsayı ifadesi verildiğinde, yeni bir tamsayı veya büyük tamsayı ifadesi `%` (mod), `&&&` (bit düzeyinde ve), `|||` (bit düzeyinde OR) veya `^^^` (bit düzeyinde XOR) işleçleri kullanılarak oluşturulabilir.

Sol tarafta bir tamsayı veya büyük tamsayı ifadesi ve sağ taraftaki bir tamsayı ifadesi verildiğinde, `<<<` (aritmetik sol SHIFT) veya `>>>` (aritmetik sağa kaydırma) işleçleri, sol ifadeyle aynı türde yeni bir ifade oluşturmak için kullanılabilir.

Kaydırma işleminin ikinci parametresi (SHIFT miktarı) sıfırdan büyük veya sıfıra eşit olmalıdır; negatif kaydırma miktarları için davranış tanımsızdır.
Her iki vardiya işlemi için de SHIFT miktarı 32 bite uyum sağlamalıdır; Aksi takdirde, bir çalışma zamanı hatası oluşur.
Kaydırılan sayı bir tamsayı ise, kaydırma miktarı yorumlanır `mod 64`; Yani, 1 ' in bir vardiyası ve 65 vardiyası aynı etkiye sahiptir.

Hem tamsayı hem de büyük tamsayı değerleri için, vardiyalar aritmetik değerlerdir.
Negatif bir değeri sol veya sağ kaydırma, negatif bir sayı ile sonuçlanır.
Diğer bir deyişle, bir adım sola veya sağa kaydırma, sırasıyla 2 ile çarpılarak veya bölünerek tamamen aynıdır.

Tamsayı bölme ve tamsayı mod, negatif sayılar için aynı davranışı izler C#.
Diğer bir deyişle `a % b` her zaman `a`aynı işarete sahip olur ve `b * (a / b) + a % b` her zaman `a`eşit olur.
Örnek:

 `A` | `B` | `A / B` | `A % B`
---------|----------|---------|---------
 5 | 2 | 2 | 1
 5 | -2 | -2 | 1
 -5 | 2 | -2 | -1
 -5 | -2 | 2 | -1

Büyük tamsayı bölme ve mod aynı şekilde çalışmaktadır.

Herhangi bir sayısal ifade verildiğinde, yeni bir ifade `-` birli işleç kullanılarak oluşturulabilir.
Yeni ifade, anayent ifadesiyle aynı türde olacaktır.

Herhangi bir tamsayı veya büyük tamsayı ifadesi verildiğinde, aynı türde yeni bir ifade `~~~` (bit düzeyinde tamamlayıcı) birli işleç kullanılarak oluşturulabilir.

## <a name="boolean-expressions"></a>Boolean İfadeleri

İki `Bool` değişmez değer `true` ve `false`.

Aynı ilkel türün herhangi iki ifadesi verildiğinde, `==` ve `!=` ikili işleçleri `Bool` ifadesi oluşturmak için kullanılabilir.
İki ifade eşitse ifade true, değilse false olur.

Kullanıcı tanımlı türlerin değerleri karşılaştırılamayabilir, yalnızca sarmalanmamış değerler karşılaştırılabilir. Örneğin, "sarmalama" işlecinin `!` ( [Q # tür modeli sayfasında](xref:microsoft.quantum.language.type-model#user-defined-types)açıklanacaktır) kullanarak,

```qsharp
newtype WrappedInt = Int;     // Yes, this is a contrived example
let x = WrappedInt(1);
let y = WrappedInt(2);
let z = x! == y!;             // This will compile and yield z = false.
let t = x == y;               // This will cause a compiler error.
```

`Qubit` değerleri için eşitlik karşılaştırması, kimlik eşitliğini; diğer bir deyişle, iki ifadenin aynı qubit 'i tanımlamasına bakılmaksızın.
İki qubits 'in durumu karşılaştırılmaz, erişilmez, ölçülemez veya bu karşılaştırma tarafından değiştirilir.

`Double` değerleri için eşitlik karşılaştırması, yuvarlama etkileri nedeniyle yanıltıcı olabilir.
Örneğin, `49.0 * (1.0/49.0) != 1.0`.

İki sayısal ifade verildiğinde, `>`, `<`, `>=`ve `<=` ikili işleçleri, ilk ifade sırasıyla daha büyük, küçüktür, büyüktür veya eşittir veya ikinci ifadeden daha küçük veya eşit olduğunda doğru olan yeni bir Boole ifadesi oluşturmak için kullanılabilir.

İki Boolean ifade verildiğinde `and` ve `or` ikili işleçleri, iki ifadenin her ikisi de (her ikisi de veya her ikisi de) doğru olan yeni bir Boole ifadesi oluşturmak için kullanılabilir.

Herhangi bir Boole ifadesi verildiğinde, anayent ifadesi false olduğunda doğru olan yeni bir Boole ifadesi oluşturmak için `not` birli işleç kullanılabilir.

## <a name="string-expressions"></a>Dize Ifadeleri

Q # `fail` ifadesinde ve `Log` standart işlevinde dizelerin kullanılmasına izin verir.

Q # içindeki dizeler, değişmez değer veya enterpolasyonlu dizelerdir.
Dize sabit değerleri çoğu dilde basit dize sabit değerlerine benzer: çift tırnak içine alınmış bir Unicode karakter dizisi, `"`.
Bir dizenin içinde, ters eğik çizgi karakteri `\` bir çift tırnak karakteriyle çıkmak ve yeni satır `\n`, bir satır geri dönüş `\r`ve `\t`olarak bir sekme eklemek için kullanılabilir.
Örneğin:

```qsharp
"\"Hello world!\", she said.\n"
```

Dize enterpolasyonları için Q # sözdizimi, C# 7,0 sözdiziminin bir alt kümesidir; S #, tam (çok satırlı) enterpolasyonlu dizeleri desteklemez.
C# Sözdizimi için bkz. [*enterpolasyonlu dizeler*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings) .

Enterpolasyonlu bir dizenin içindeki ifadeler, sözdizimi değil C# , Q # söz dizimini izler.
Geçerli bir Q # ifadesi, enterpolasyonlu bir dizede görünebilir.

## <a name="qubit-expressions"></a>Qubit Ifadeleri

Tek `Qubit` ifadeleri, `Qubit` dizilerinin `Qubit` değerlerine veya dizi öğelerine bağlanan sembollerdir.
`Qubit` değişmez değer yok.

## <a name="pauli-expressions"></a>Pauli Ifadeleri

Dört `Pauli` değeri, `PauliI`, `PauliX`, `PauliY`ve `PauliZ`tüm geçerli `Pauli` ifadeleridir.

Bunun dışında, tek `Pauli` ifadeleri, `Pauli` dizilerinin `Pauli` değerlerine veya dizi öğelerine bağlanan sembollerdir.

## <a name="result-expressions"></a>Sonuç Ifadeleri

İki `Result` değeri `One` ve `Zero`geçerli `Result` ifadeleridir.

Bunun dışında, tek `Result` ifadeleri, `Result` dizilerinin `Result` değerlerine veya dizi öğelerine bağlanan sembollerdir.
Özellikle, `One` tamsayı `1`ile aynı değildir ve aralarında doğrudan dönüşüm yoktur.
`Zero` ve `0`için de aynı değer geçerlidir.

## <a name="range-expressions"></a>Aralık Ifadeleri

`start`, `step`ve `stop`olmak üzere üç `Int` ifade verildiğinde `start .. step .. stop`, ilk öğesi `start`, ikinci öğe ise `start+step`, üçüncü öğe ise `start+step+step`geçirilene kadar bir Aralık deyimidir.`stop`
Örneğin, `step` pozitif ve `stop < start`olduğunda bir Aralık boş olabilir.
Aralığın son öğesi, `start` ve `stop` arasındaki fark `step`bir tam sayı `stop` olur. diğer bir deyişle, Aralık her iki uçta da dahil olur.

`start` ve `stop`iki `Int` ifadesi verildiğinde `start .. stop`, `start .. 1 .. stop`eşit bir Aralık ifadesidir.
`stop` `start`'den az olsa bile, kapsanan `step` + 1 olduğunu unutmayın. Böyle bir durumda, Aralık boştur.

Bazı örnek aralıklar şunlardır:

- `1..3` 1, 2, 3 aralığıdır.
- `2..2..5` 2, 4 aralığıdır.
- `2..2..6`, 2, 4, 6 aralığıdır.
- `6..-2..2` 6, 4, 2 aralığıdır.
- boş Aralık `2..1`.
- `2..6..7` aralığı 2 ' dir.
- boş Aralık `2..2..1`.
- boş Aralık `1..-1..2`.

## <a name="callable-expressions"></a>Çağrılabilir Ifadeler

Çağrılabilir sabit değer, derleme kapsamında tanımlanan bir işlemin veya işlevin adıdır.
Örneğin, `X` standart kitaplık `X` işlemine başvuran bir işlem değişmez değeri ve `Message` standart kitaplık `Message` işlevine başvuran bir işlev sabit değeri.

Bir işlem `Adjoint` functor destekliyorsa, `Adjoint op` bir işlem ifadesi olur.
Benzer şekilde, işlem `Controlled` functor destekliyorsa, `Controlled op` bir işlem ifadesi olur.
Bu ifadelerin türleri, [Funörler](xref:microsoft.quantum.language.type-model#functors)içinde belirtilmiştir.

Funörler (`Adjoint` ve `Controlled`), sarmalama işleci olmayan `!` ve `[]`ile dizi dizini oluşturma dışında diğer işleçlerden daha yakından bağlanır.
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

Örneğin, `Fun` imza içeren bir işlevdir `'T1->Unit`:

```qsharp
let f = Fun<Int>;            // f is Int->Unit.
SomeOtherFun(Fun<Double>);   // A Double->Unit is passed to SomOtherFun.
let g = Fun;                 // This causes a compilation error.
SomeOtherFun(Fun);           // This also causes a compilation error.
```

## <a name="callable-invocation-expressions"></a>Çağrılabilir çağırma Ifadeleri

Çağrılabilir bir (işlem veya işlev) ifadesi ve çağrılabilir öğesinin giriş türünün bir tanımlama grubu ifadesi verildiğinde, çağrılabilir ifadeye kayıt kümesi ifadesi eklenerek bir çağırma ifadesi oluşturulabilir.
Çağırma ifadesinin türü, çağrılabilir olan imzanın çıkış türüdür.

Örneğin, `Op` imza `((Int, Qubit) => Double)`olan bir işlem ise, `Op(3, qubit1)` `Double`türünde bir ifadedir.
Benzer şekilde, `Sin` imza `(Double -> Double)`olan bir işlevdir, `Sin(0.1)` `Double`türünde bir ifadedir.
Son olarak, `Builder` imza `(Int -> (Int -> Int))`olan bir işlevdir, `Builder(3)` bir fonksiyondan Int 'e kadar olur.

Çağrılabilir değerli bir ifadenin sonucunu çağırmak, çağrılabilir ifade etrafında fazladan bir çift parantez gerektirir.
Bu nedenle, önceki paragraftan `Builder` çağırma sonucunu çağırmak için doğru sözdizimi şöyledir:

```qsharp
(Builder(3))(2)
```

Bir tür parametreli çağrılabilir çağrılırken, gerçek tür parametreleri açılı `<` ayraç içinde ve çağrılabilir ifadeden sonra `>` belirtilebilir.
Q # derleyicisi gerçek türleri çıkardığı için bu genellikle gereksizdir.
Bir tür parametreli bağımsız değişken belirtilmemişse, kısmi uygulama (aşağıya bakın) için gereklidir.
Ayrıca bazen farklı functor ile işlemleri bir çağrılabilir olarak geçirirken yararlı olur.

Örneğin, `Func` imza `('T1, 'T2, 'T1) -> 'T2`, `Op1` ve `Op2` imza `(Qubit[] => Unit is Adj)`sahipse ve `Op3`, ilk bağımsız değişken olarak `(Qubit[] => Unit)``Func` ve üçüncü olarak `Op1` çağırmak için imza `Op2` vardır:`Op3`

```qsharp
let combinedOp = Func<(Qubit[] => Unit), (Qubit[] => Unit is Adj)>(Op1, Op2, Op3);
```

Tür belirtimi gereklidir çünkü `Op3` ve `Op1` farklı türlere sahip olduğundan, derleyici bunu belirtim olmadan belirsiz olarak değerlendirir.

### <a name="partial-application"></a>Kısmi uygulama

Çağrılabilir bir ifade verildiğinde, çağrılabilir bir bağımsız değişkenlerin alt kümesini sağlayarak yeni bir çağrılabilir oluşturulabilir.
Buna _kısmi uygulama_denir.

Q # ' da, kısmen uygulanan çağrılabilir bir normal çağırma ifadesi yazılarak, ancak belirtilmemiş bağımsız değişkenler için `_`alt çizgi kullanılarak ifade edilir.
Elde edilen çağrılabilir taban çağrılabilir ile aynı sonuç türüne ve işlemler için aynı uzmanlıklarla aynı.
Kısmi uygulamanın giriş türü, yalnızca belirtilen bağımsız değişkenler kaldırılmış olan özgün türdür.

Kısmi uygulama oluştururken değişebilir bir değişken belirtilen bağımsız değişken olarak geçirilirse, değişkenin geçerli değeri kullanılır.
Değişkenin değerini daha sonra değiştirmek kısmi uygulamayı etkilemez.

Örneğin, `Op` türü `((Int, ((Qubit, Qubit), Double)) => Unit is Adj)`varsa:

- `Op(5,(_,_))` `(((Qubit,Qubit), Double) => Unit is Adj)`tür ve bu nedenle `Op(5,_)`.
- `Op(_,(_,1.0))` `((Int, (Qubit,Qubit)) => Unit is Adj)`türü vardır.
- `Op(_,((q1,q2),_))` `((Int,Double) => Unit is Adj)`türü vardır.
   Burada tek demet denklik 'i uyguladığımızda aklınızda olduğunu unutmayın.

Kısmen uygulanmış çağrılabilir, derleyici tarafından çıkarsanamayan tür parametrelerine sahipse, bunun çağırma sitesinde sağlanması gerekir.
Kısmi uygulama belirtilmeyen tür parametrelerine sahip olamaz.

Örneğin, `Op` türü `(('T1, Qubit, 'T1) => Unit : Adjoint)`varsa:

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

Tanımlama grubu sabit değeri, `(` ve `)`içine alınmış, virgülle ayrılmış, uygun türdeki öğe ifadelerinin dizelerdir.
Örneğin, `(1, One)` `(Int, Result)` bir ifadedir.

Değişmez değerler dışında, tek demet ifadeleri demet değerlerine, demet dizilerinin dizi öğelerine ve tanımlama grupları döndüren çağrılabilir çağırmaları olan sembollerdir.

## <a name="user-defined-type-expressions"></a>Kullanıcı tanımlı tür Ifadeleri

Kullanıcı tanımlı bir türün sabit değeri tür adından, ardından türün temel demet türünün bir tanımlama grubu değişmez değerinden oluşur.
Örneğin, `IntPair` `(Int, Int)`tabanlı kullanıcı tanımlı bir tür ise, `IntPair(2,3)` o türden geçerli bir sabit değer olacaktır.

Değişmez değerler dışında, Kullanıcı tanımlı bir türün tek ifadeleri, bu türün değerlerine, bu türden dizilerin dizi öğelerine ve bu türü döndüren çağrılabilir çağırmaları olan sembollerdir.

## <a name="unwrap-expressions"></a>Ifade kaydırmayı geri al

Q # içinde, Unwrap işleci sonda bir ünlem işaretiyle `!`.
Örneğin, `IntPair` temel alınan tür `(Int, Int)`sahip kullanıcı tanımlı bir tür ise ve `s` değeri `IntPair(2,3)`olan bir değişkense, `s!` `(2,3)`olur.

Diğer Kullanıcı tanımlı türler bakımından tanımlanan Kullanıcı tanımlı türler için. Unwrap işleci yinelenebilir olabilir; Örneğin, `s!!`, `s`doğru sarmalanmamış değeri gösterir.
Bu nedenle, `WrappedPair` temel alınan türe sahip kullanıcı tanımlı bir tür `IntPair`ve `t` değeri `WrappedPair(IntPair(1,2))`olan bir değişkense, `t!!` `(1,2)`olur.

`!` işleci, dizi dizini oluşturma ve dilimleme için `[]` dışındaki diğer işleçlerden daha yüksek önceliğe sahiptir.
`!` ve `[]` bağlama pozitif; diğer bir deyişle, `a[i]![3]` `((a[i])!)[3]`olarak okunmalıdır: `a``i`' th öğesini alın, sarmalayın ve sonra sarmalanmamış değerin 3. öğesini (bir dizi olması gerekir) alın.

`!` işlecinin önceliği, belirgin bir etkiye sahip olabilir.
Bir işlev veya işlem sarmalanmamış bir değer döndürürse, bağımsız değişken grubu, sarmalama yerine çağrıya bağlamak için işlev veya işlem çağrısının parantez içine alınması gerekir.
Örnek:

```qsharp
let f = (Foo(arg))!;    // Calls Foo(arg), then unwraps the result
let g = Foo(arg)!;      // Syntax error
```

## <a name="array-expressions"></a>Dizi Ifadeleri

Dizi sabit değeri, `[` ve `]`içine alınmış, virgülle ayrılmış bir veya daha fazla öğe ifadesi dizisidir.
Tüm öğeler aynı türle uyumlu olmalıdır.

Ortak öğe türü bir işlem ya da işlev türü ise, tüm öğeler aynı giriş ve çıkış türlerine sahip olmalıdır.
Dizinin öğe türü tüm öğeleri tarafından desteklenen tüm nesneleri destekleyecektir.
Örneğin, `Op1`, `Op2`ve `Op3` tümü `Qubit[] => Unit`, ancak `Op1` destekliyorsa `Adjoint`destekler ve `Op2` ikisini de destekler:`Controlled``Op3`

- `[Op1, Op2]`, `(Qubit[] => Unit)` işlemlerinin bir dizisidir.
- `[Op1, Op3]`, `(Qubit[] => Unit is Adj)` işlemlerinin bir dizisidir.
- `[Op2, Op3]`, `(Qubit[] => Unit is Ctl)` işlemlerinin bir dizisidir.

Boş dizi değişmez değerlerine, `[]`izin verilmez.
Bunun yerine, `★` uygun bir tür için yer tutucu olduğu `new ★[0]`kullanarak, istenen sıfır uzunluklu diziyi oluşturulmasına izin verir.

Aynı türde iki dizi verildiğinde, ikili `+` işleci iki dizinin birleşimi olan yeni bir dizi oluşturmak için kullanılabilir.
Örneğin, `[1,2,3] + [4,5,6]` `[1,2,3,4,5,6]`.

### <a name="array-creation"></a>Dizi oluşturma

Bir tür ve `Int` ifadesi verildiğinde, `new` işleci verilen boyutun yeni bir dizisini ayırmak için kullanılabilir.
Örneğin `new Int[i+1]`, `i+1` öğeleriyle yeni bir `Int` dizisi ayırır.

Yeni bir dizinin öğeleri, türe bağlı bir varsayılan değere başlatılır.
Çoğu durumda bu bazı sıfır çeşitlerinden oluşur.

Varlıklara başvurular olan qubits ve callables için makul bir varsayılan değer yoktur.
Bu nedenle, bu tür için varsayılan, çalışma zamanı hatasına neden olmadan kullanılamayan geçersiz bir başvurudur.
Bu, C# veya Java gibi dillerde null başvuruya benzer.
Qubits veya callables içeren diziler, öğeleri güvenle kullanılmadan önce varsayılan olmayan değerlerle düzgün başlatılmış olmalıdır. Uygun başlatma yordamları <xref:microsoft.quantum.arrays>bulunabilir.

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
 `Range` | Boş Aralık `1..1..0`
 `Callable` | _geçersiz çağrılabilir_
 `Array['T]` | `'T[0]`

Demet türleri, öğe öğesi tarafından başlatılmış.


### <a name="jagged-arrays"></a>Basit Diziler

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

Bir dizi ifadesi ve bir `Range` ifadesi verildiğinde, `[` ve `]` dizi dilimi işleci kullanılarak yeni bir ifade oluşturulabilir.
Yeni ifade, dizi ile aynı tür olur ve `Range`tarafından tanımlanan düzende `Range`öğeleri tarafından dizine alınmış dizi öğelerini içerir.
Örneğin, `a` bir `Double`s dizisine bağlıysa `a[3..-1..0]`, `a` ilk dört öğeyi içeren bir `Double[]` ifadedir ancak ters sırada `a`içinde görünürler.

`Range` boşsa, sonuçta elde edilen dizi dilimi sıfır uzunluğunda olur.

Dizi ifadesi basit bir tanımlayıcı değilse, dilimin dilimlemek için parantez içine alınması gerekir.
Örneğin, `a` ve `b` her ikisi de `Int`s dizilerinizde, birleştirme işleminden alınan bir dilim şöyle ifade edilir:

```qsharp
(a+b)[1..2..7]
```

Q # içindeki tüm diziler sıfır tabanlıdır.
Diğer bir deyişle, bir dizi `a` ilk öğesi her zaman `a[0]`.

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

Dizi ifadesi ve bir `Int` ifadesi verildiğinde, `[` ve `]` Array öğesi işleci kullanılarak yeni bir ifade oluşturulabilir.
Yeni ifade, dizinin öğe türüyle aynı türde olacaktır.
Örneğin, `a` bir `Double`s dizisine bağlıysa `a[4]` `Double` bir ifadedir.

Dizi ifadesi basit bir tanımlayıcı değilse, bir öğe seçmek için parantez içine alınmalıdır.
Örneğin, `a` ve `b` her iki dizi `Int`de varsa, birleştirilmeden bir öğe şöyle ifade edilir:

```qsharp
(a+b)[13]
```

Q # içindeki tüm diziler sıfır tabanlıdır.
Diğer bir deyişle, bir dizi `a` ilk öğesi her zaman `a[0]`.


## <a name="copy-and-update-expressions"></a>Kopyalama ve güncelleştirme Ifadeleri

Yeni diziler, kopyalama ve güncelleştirme ifadeleri aracılığıyla mevcut olanlardan oluşturulabilir.
Bir Copy-Update ifadesi, `expression1 w/ expression2 <- expression3``T`bir tür `T[]` `expression1` olması gereken form bir ifadedir. İkinci `expression2`, `expression1` dizi ile karşılaştırıldığında değiştirilecek öğe (ler) in dizinlerini tanımlar ve `Int` türünden ya da `Range`türünde olmalıdır. `expression2` `Int`tür ise `expression3` `T`türünde olması gerekir. `expression2` `Range`tür ise `expression3` `T[]`türünde olması gerekir.

Bir kopyalama ve güncelleştirme ifadesi `arr w/ idx <- value`, `idx`içindeki öğe (ler), `value`' de ayarlanan öğeler hariç, tüm öğeleri `arr`karşılık gelen öğeye ayarlanmış yeni bir dizi oluşturur. Örneğin, `arr` bir dizi `[0,1,2,3]`içeriyorsa, 
- `arr w/ 0 <- 10` dizi `[10,1,2,3]`.
- `arr w/ 2 <- 10` dizi `[0,1,10,3]`.
- `arr w/ 0..2..3 <- [10,12]` dizi `[10,1,12,3]`.

Kullanıcı tanımlı türlerde adlandırılmış öğeler için benzer ifadeler mevcuttur. Örneğin türü göz önünde bulundurun 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
`c`, `Complex(1.,-1.)`türünde değeri içeriyorsa `c w/ Re <- 0.`, `Complex(0.,-1.)`değerlendirilen `Complex` türünde bir ifadedir.

## <a name="conditional-expressions"></a>Koşullu Ifadeler

Aynı türde ve bir Boolean ifadesinin iki diğer ifadesi verildiğinde, koşullu ifade soru işareti `?` ve dikey çubuk `|`kullanılarak oluşturulmuş olabilir.
Örneğin, `a==b ? c | d`.
Bu örnekte, koşullu ifadenin değeri, `a==b` true ise ve false ise `d` `c` olacaktır.

İki ifade, aynı girişlere ve çıkışlara sahip olan ancak farklı komik desteği olan işlemlere göre değerlendirilemez.
Bu durumda, koşullu ifadenin türü, her iki ifade tarafından desteklenen tüm semantikleri destekleyen bu giriş ve çıkışlarla bir işlemdir.
Örneğin, `Op1`, `Op2`ve `Op3` tümü `Qubit[]=>Unit`, ancak `Op1` destekliyorsa `Adjoint`destekler ve `Op2` ikisini de destekler:`Controlled``Op3`

- `flag ? Op1 | Op2` `(Qubit[] => Unit)` bir işlemdir.
- `flag ? Op1 | Op3` `(Qubit[] => Unit is Adj)` bir işlemdir.
- `flag ? Op2 | Op3` `(Qubit[] => Unit is Ctl)` bir işlemdir.

Olası iki sonuç ifadesi varsa, bir işlev veya işlem çağrısı içeriyorsa, bu çağrı yalnızca çağrının değeri olacak şekilde gerçekleşdiğinde olur.
Örneğin, `a==b ? C(qs) | D(qs)`durumda, `a==b` true ise, `C` işlemi çağrılır ve false ise yalnızca `D` çağrılacaktır.
Bu, diğer dillerdeki kısa devre 'ya benzer.


## <a name="operator-precedence"></a>İşleç önceliği

Tüm ikili işleçler `^`dışında sağ ilişkilendirilebilir.

Parantez, `[` ve `]`, dizi Dilimleme ve dizin oluşturma için herhangi bir işleçten önce bağlayın.

Komik `Adjoint` ve `Controlled` dizi dizinledikten sonra, diğer tüm işleçlerden önce bağlanır.

İşlem ve işlev çağırma parantezleri aynı zamanda herhangi bir işleçten önce, ancak dizi dizinlemesi ve komik bir şekilde bağlanır.

En yüksekten en düşüğe göre öncelik sırasına göre işleçler:

İşleç | Sayısına | Açıklama | İşlenen türleri
---------|----------|---------|---------------
 Sondaki `!` | Li | Unwrap | Kullanıcı tanımlı herhangi bir tür
 `-`, `~~~`, `not` | Li | Sayısal negatif, bit düzeyinde tamamlama, mantıksal değilleme | `Int` için `BigInt` `-`, `~~~`veya `Bool` için `Int`, `BigInt` veya `Double` `not`
 `^` | İkili | Tamsayı güç | Taban için `Int` veya `BigInt` üs için `Int`
 `/`, `*`, `%` | İkili | Bölme, çarpma, tamsayı mod | `*`için `/` ve `Int`, `BigInt` veya `%` için `Int`, `BigInt` veya `Double`
 `+`, `-` | İkili | Ekleme veya dize ve dizi birleştirme, çıkarma | `Int`, `BigInt` veya `Double`, ayrıca `+` için `String` veya herhangi bir dizi türü
 `<<<`, `>>>` | İkili | Sol SHIFT, sağa kaydırma | `Int` veya `BigInt`
 `<`, `<=`, `>`, `>=` | İkili | Küçüktür, küçüktür veya eşittir, büyüktür, büyüktür veya eşittir karşılaştırmaları | `Int`, `BigInt` veya `Double`
 `==`, `!=` | İkili | eşit, eşit olmayan karşılaştırmalar | herhangi bir ilkel tür
 `&&&` | İkili | Bit düzeyinde AND | `Int` veya `BigInt`
 `^^^` | İkili | Bit düzeyinde XOR | `Int` veya `BigInt`
 <code>\|\|\|</code> | İkili | Bit düzeyinde OR | `Int` veya `BigInt`
 `and` | İkili | Mantıksal AND | `Bool`
 `or` | İkili | Mantıksal OR | `Bool`
 `..` | İkili/üçlü | Range işleci | `Int`
 `?` `|` | Üçlü | Koşullu | Sol taraftaki `Bool`
`w/` `<-` | Üçlü | Kopyala ve Güncelleştir | bkz. [kopyalama ve güncelleştirme ifadeleri](#copy-and-update-expressions)
