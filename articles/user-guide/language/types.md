---
title: "Q 'daki türler #"
description: 'Q # programlama dilinde kullanılan farklı türler hakkında bilgi edinin.'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.types
ms.openlocfilehash: 58370193bd62e306197a9e07c28f8611f043e55c
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/15/2020
ms.locfileid: "83431147"
---
# <a name="types-in-q"></a>Q 'daki türler #

Bu sayfa, Q # tür modelini yerleştirir ve türleri belirtmek ve bunlarla çalışmak için sözdizimini açıklar.
Sonraki sayfa, [tür ifadeleri](xref:microsoft.quantum.guide.expressions), bu türlerin ifadeleri oluşturma ve üzerinde işlem yapma ayrıntıları.

Bu tür dikkatle kullanılması derleyicinin, derleme zamanında Q # programları hakkında güçlü garantiler sağlamasına yardımcı olabileceğini belirten, *kesin olarak yazılmış* bir dil olduğunu unutmayın.
Mümkün olan en güçlü garantiyi sağlamak için, Q # içindeki türler arasındaki dönüştürmeler, bu dönüştürmeyi ifade eden işlevlere yapılan çağrılar kullanılarak açık olmalıdır. Bu gibi çeşitli işlevler, ad alanının bir parçası olarak sağlanır <xref:microsoft.quantum.convert> .
Diğer yandan uyumlu türlere yapılan yayınlar örtülü olarak gerçekleşir. 

Q #, doğrudan kullanılabilen basit türler ve diğer türlerden yeni türler oluşturmak için çeşitli yollar sağlar.
Bu bölümün geri kalanında her birini açıklıyoruz.

## <a name="primitive-types"></a>İlkel Türler

Q # dili, diğer türlerin oluşturulabileceği çeşitli *temel türler*sağlar:

- `Int`Tür, 64 bitlik işaretli bir tamsayıyı temsil eder, örneğin: `2` , `107` , `-5` .
- `BigInt`Tür, rastgele boyutun işaretli bir tamsayı temsil eder, örneğin, `2L` `107L` `-5L` .
   Bu tür .NET tabanlıdır<xref:System.Numerics.BigInteger>
   türüyle.
- `Double`Tür çift duyarlıklı kayan noktalı sayıyı temsil eder, örneğin: `0.0` , `-1.3` , `4e-7` .
- `Bool`Tür ya da olabilecek bir Boolean değeri temsil eder `true` `false` .
- `Range`Türü, ile belirtilen ve adım seçenekleri gösteren bir tamsayılar dizisini temsil eder `start..step..stop` . 
   Bu `start .. stop` öğesine karşılık gelir `start..1..stop` ve örn. `1..2..7` $ \{ 1, 3, 5, 7 $ dizisini temsil eder \} .
- `String`Tür, bir kez oluşturulduktan sonra kullanıcıya donuk olan Unicode karakterlerinden oluşan bir dizidir.
  Bu tür, bir hata veya tanılama olayı durumunda iletileri klasik bir konağa raporlamak için kullanılır.
- `Unit`Tür yalnızca bir değere izin veren türdür `()` . 
  Bu tür, Q # işlevinin veya işleminin hiçbir bilgi döndürdüğünü göstermek için kullanılır. 
- `Qubit`Tür bir hisse bitini veya qubit 'i temsil eder.
   `Qubit`, kullanıcının opaktır; Bunlar ile mümkün olan tek işlem, başka bir işleme geçirilmekten farklı kimlik (eşitlik) için test amaçlıdır.
   Sonuç olarak, içindeki eylemler `Qubit` bir hisse işlemcisi (veya bir simülasyonu) üzerinde iç yönergeler çağırarak uygulanır.
- `Pauli`Tür, dört adet tek qubit Pauli işleçlerinden birini temsil eder.
   Bu tür, döndürmeler için temel işlemi göstermek ve ölçülecek observable 'ı belirtmek için kullanılır.
   Bu, dört olası değeri olan numaralandırılmış bir türdür: `PauliI` ,, `PauliX` `PauliY` , ve `PauliZ` , türünde sabitler `Pauli` .
- `Result`Tür, ölçümün sonucunu temsil eder.
   Bu, iki olası değeri olan `One` ve türünde sabitler olan numaralandırılmış bir türdür `Zero` `Result` .
   `Zero`+ 1 eigenvalue değerinin ölçüldüğünü belirtir; `One`-1 eigenvalue değerini gösterir.

,,,,,, Ve sabitleri, `true` `false` `PauliI` `PauliX` `PauliY` `PauliZ` `One` `Zero` Q # içinde tüm ayrılmış sembollerdir.

## <a name="array-types"></a>Dizi türleri

Geçerli bir Q # türü verildiğinde `'T` , türünde bir değer dizisini temsil eden bir tür vardır `'T` .
Bu dizi türü olarak temsil edilir `'T[]` ; Örneğin, `Qubit[]` veya `Int[][]` .
Örneğin, bir tamsayılar koleksiyonu gösterilir `Int[]` , ancak değer dizileri dizisi `(Bool, Pauli)` gösterilir `(Bool, Pauli)[][]` .

İkinci örnekte bunun, dikdörtgen iki boyutlu bir dizi değil, potansiyel olarak pürüzlü dizi dizileri temsil ettiğini unutmayın.
Q #, dikdörtgen çok boyutlu diziler için destek sağlamaz.

Bir dizi değeri, içinde olduğu gibi bir dizinin öğeleri etrafında köşeli parantezler kullanılarak Q # kaynak kodunda yazılabilir `[PauliI, PauliX, PauliY, PauliZ]` .
Dizi sabit değerinin türü dizideki tüm öğelerin ortak temel türüne göre belirlenir. 

> [!WARNING]
> Dizinin öğeleri, dizi oluşturulduktan sonra değiştirilemez.
> [Güncelleştirme ve yeniden atama deyimleri](xref:microsoft.quantum.guide.variables#update-and-reassign-statements) ve/veya [kopyalama ve güncelleştirme ifadeleri](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions) , değiştirilmiş bir diziyi oluşturmak için kullanılabilir.

Alternatif olarak, bir dizi boyutundan `new` anahtar sözcüğü kullanılarak oluşturulabilir:

```qsharp
let zeros = new Int[13];
// new also allows for creating empty arrays:
let emptyRegister = new Qubit[0];
```

Her iki durumda da, bir dizi oluşturulduktan sonra, temel işlev `Length` öğe sayısını bir olarak almak için kullanılabilir `Int` .
Diziler, `Int` `Range` bir dizinin öğelerinin bir alt kümesini içeren tek öğe veya yeni diziler elde etmek için tür veya tür içeren alt simgeler ile köşeli ayraç kullanılarak alt simge olabilir.
Dizilerin alt simgeleri sıfır tabanlıdır:

```qsharp
let arr = [10, 11, 36, 49];
let ten = arr[0]; // 10
let odds = arr[1..2..4]; // [11, 49]
```

## <a name="tuple-types"></a>Demet türleri

Sıfır veya daha fazla farklı tür (, `T0` `T1` ...) verildiğinde `Tn` Yeni bir *demet türü* olarak belirtilebilir `(T0, T1, ..., Tn)` .
Yeni bir demet türü oluşturmak için kullanılan türler, içinde olduğu gibi kendi tanımlama grupları olabilir `(Int, (Qubit, Qubit))` .
Bu iç içe geçme her zaman sınırlıdır, ancak demet türleri hiçbir koşulda kendilerini içeremez.

Yeni demet türünün değerleri, kayıt düzeni içindeki her türden değer dizileri tarafından oluşturulan dizileridir.
Örneğin, `(3, false)` türü demet türünde olan bir kayıt türüdür `(Int, Bool)` .
Tanımlama dizileri, dizi dizilerindeki diziler, alt tanımlama grupları, vb. öğeleri oluşturmak mümkündür.

Q # 0,3 itibariyle, boş kayıt düzeni `Unit` *türünün* adı, boş demet `()` *değeri*için kullanılır.

Demet örnekleri sabittir.
S #, oluşturulduktan sonra bir kayıt düzeninin içeriğini değiştirme mekanizması sağlamaz.

Tanımlama grupları, her bir değer toplamak için Q # boyunca kullanılan güçlü bir kavramdır; bu da, daha kolay bir şekilde geçiş yapmayı kolaylaştırır.
Özellikle, tanımlama grubu gösterimini kullanarak her işlemin ve çağrılabilir şekilde tam olarak bir giriş aldığını ve tam olarak bir çıkış döndürdüğünü ifade edebilirsiniz.

### <a name="singleton-tuple-equivalence"></a>Tek kayıt düzeni denklik

Veya gibi tek bir (tek öğeli) tanımlama grubu oluşturmak mümkündür `('T1)` `(5)` `([1,2,3])` .
Ancak, Q #, tek bir kayıt kümesini, iliştirilmiş türdeki bir değere tamamen eşdeğer olarak değerlendirir.
Diğer bir deyişle, ve arasında ya da ile arasında ya da arasında bir fark yoktur `5` `(5)` `5` `(((5)))` `(5, (6))` `(5, 6)` .
Yazmak üzere yazmak için geçerli olduğu gibi `(5)+3` `5+3` , her iki ifade de olarak değerlendirilir `8` .

Bu denklik, atama ve ifadeler dahil tüm amaçlar için geçerlidir.
Herhangi bir ifade verildiğinde, parantez içine alınmış aynı ifade aynı türde bir ifadedir.
Örneğin, `(7)` bir ifadedir, `Int` `([1,2,3])` dizi türünde bir ifadedir `Int` ve `((1,2))` türünde bir ifadedir `(Int, Int)` .

Özellikle, bu, giriş kümesi veya çıkış grubu türü olan bir işlemin veya işlevin tek bir bağımsız değişken alan veya tek bir değer döndüren bir alana sahip olabileceği anlamına gelir.

Bu özelliğe, _tek demet denklik_olarak başvurduk.


## <a name="user-defined-types"></a>Kullanıcı tanımlı türler

Kullanıcı tanımlı tür bildirimi, anahtar sözcükten `newtype` , ardından Kullanıcı tanımlı türün adı, bir `=` , geçerli bir tür belirtimi ve sonlandırma noktalı virgülünden oluşur.

Örneğin:

```qsharp
newtype PairOfInts = (Int, Int);
```

Her Q # kaynak dosyası herhangi bir sayıda kullanıcı tanımlı tür bildirebilir.
Tür adları ad alanı içinde benzersiz olmalıdır ve işlem ve işlev adlarıyla çakışmayabilir.

Temel türler özdeş olsa bile Kullanıcı tanımlı türler farklıdır.
Özellikle, temeldeki türler özdeş olsa bile, iki Kullanıcı tanımlı türün değerleri arasında otomatik dönüşüm yoktur.

### <a name="named-vs-anonymous-items"></a>Adlandırılmış vs. Anonymous öğeleri

Bir Q # dosyası, geçerli bir türden tek bir değer içeren yeni bir adlandırılmış tür tanımlayabilir.
Herhangi bir demet türü için `T` , ifadesiyle birlikte bir alt türü olan yeni bir Kullanıcı tanımlı tür bildirebiliriz `T` `newtype` .
@"microsoft.quantum.math"Ad alanında, örneğin, karmaşık sayılar Kullanıcı tanımlı bir tür olarak tanımlanmıştır:

```qsharp
newtype Complex = (Double, Double);
```
Bu ifade, türünde iki anonim öğe içeren yeni bir tür oluşturur `Double` .   

Anonim öğeler dışında, Kullanıcı tanımlı türler Ayrıca, Q # sürüm 0,7 veya üzeri olarak *adlandırılmış öğeleri* de destekler. Örneğin, `Re` bir karmaşık sayının gerçek bölümünü ve sanal parçayı temsil eden Double için öğeleri olarak adlandırdık `Im` . 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
Kullanıcı tanımlı bir türdeki bir öğenin adlandırılması, tüm öğelerin adlandırılması gerektiğini göstermez; adlandırılmış ve adlandırılmamış öğelerin herhangi bir birleşimi desteklenir. Ayrıca, iç öğeler de adlandırılmış olabilir.
`Nested`Aşağıda tanımlanan türün temel bir türü vardır `(Double, (Int, String))` ; yalnızca türü öğe `Int` ve diğer tüm öğeler anonim olarak adlandırılır. 

```qsharp
newtype Nested = (Double, (ItemName : Int, String)); 
```

Adlandırılmış öğeler, *erişim operatörü* aracılığıyla doğrudan erişilebilecekleri avantajına sahiptir `::` . 

```qsharp
function ComplexAddition(c1 : Complex, c2 : Complex) : Complex {
    return Complex(c1::Re + c2::Re, c1::Im + c2::Im);
}
```

Karmaşık tanımlama grubu türleri için kısa diğer adlar sağlamaya ek olarak, bu tür türler tanımlamanın önemli bir avantajı, belirli bir değerin amacını belgelememelerdir.
Örneğe dönerek `Complex` , bir Kullanıcı tanımlı tür olarak 2B kutupsal koordinatları de tanımlanabilir:

```qsharp
newtype Polar = (Radius : Double, Phase : Double);
```

Hem hem de her ikisi de temel bir türe sahip olsa da, iki tür, her ikisi de, her ikisi de `Complex` `Polar` aynı şekilde soru-cevap olarak `(Double, Double)` bir karmaşık matematik işlevini çağırma riskini en aza indirir.
Bu şekilde, Kullanıcı tanımlı türlerin F # ' ta kayıt olarak benzer bir rolü vardır. 


#### <a name="access-anonymous-items-with-the-unwrap-operator"></a>Unwrap işleci ile anonim öğelere erişme

Diğer yandan anonim öğelere erişmek için, Sarmalanan değerin ilk olarak sonek işleci kullanılarak ayıklanabilmesi gerekir `!` .
"Unwrap" işleci, `!` Kullanıcı tanımlı bir türde bulunan değeri ayıklamasına izin verir.
Böyle bir "sarmalama" ifadesinin türü, Kullanıcı tanımlı türün temel türüdür. 

```qsharp
function PrintedMessage(value : Nested) : Unit {
    let (d, (_, str)) = value!;
    Message ($"{str}, value: {d}");
}
```

Unwrap işleci, tam olarak bir sarmalama katmanını sarmalanmış olarak kaldırır.
Çarpma sarmalanmış bir değere erişmek için birden çok sarmalama işleci kullanılabilir.

Örneğin:

```qsharp
newtype WrappedInt = Int;
newtype DoublyWrappedInt = WrappedInt;

...
    let x = DoublyWrappedInt(WrappedInt(6));
    let y = x!;       // y is WrappedInt(6)
    let z = x!!;      // z is 6
    let a = x + 5;    // This is an error, a DoublyWrappedInt isn't an Int
    let b = x! + 5;   // Also an error
    let c = x!! + 5;  // This is valid, c will be 11
...
```

Unwrap işleci hakkında daha fazla ayrıntı, [Q # Içindeki tür ifadelerinde](xref:microsoft.quantum.guide.expressions)bulunabilir.

### <a name="creating-values-of-user-defined-types"></a>Kullanıcı tanımlı türlerin değerlerini oluşturma

Kullanıcı tanımlı bir türün değerleri, karşılık gelen tür Oluşturucusu çağırarak oluşturulabilir:

```
let realUnit = Complex(1.0, 0.0);
let imaginaryUnit = Complex(0.0, 1.0);
```

Alternatif olarak, [kopyalama ve güncelleştirme ifadeleri](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions)kullanılarak mevcut olanlardan yeni değerler oluşturulabilir. Diziler gibi ifadeler, özgün ifadenin tüm öğe değerlerini, belirtilen adlandırılmış öğelerin özel durumuyla birlikte kopyalar. Bu değerler için, ifadenin sağ tarafında tanımlananlara ayarlanır. Aynı zamanda, Kullanıcı tanımlı türlerde adlandırılmış öğeler için kullanılabilen, örneğin [Update-ve-yeniden atama deyimleri](xref:microsoft.quantum.guide.variables#update-and-reassign-statements)gibi diğer dil yapıları de mevcuttur.

```qsharp
newtype ComplexArray = (Count : Int, Data : Complex[]);

function AsComplexArray (data : Double[]) : ComplexArray {

    mutable res = ComplexArray(0, new Complex[0]);
    for (item in data) {
        set res w/= Data <- res::Data + [Complex(item, 0.)]; // update-and-reassign statement
    }
    return res w/ Count <- Length(res::Data); // returning a copy-and-update expression
}
```

Kullanıcı tanımlı türler, diğer herhangi bir tür kullanılabilir her yerde kullanılabilir.
Özellikle, Kullanıcı tanımlı bir türün dizisini tanımlamak ve Kullanıcı tanımlı bir türü bir demet türünün öğesi olarak eklemek mümkündür.

Özyinelemeli tür yapıları oluşturmak için Not mümkün değildir.
Diğer bir deyişle, Kullanıcı tanımlı bir türü tanımlayan tür, Kullanıcı tanımlı türdeki bir öğe içeren bir demet türü olamaz.
Daha genel olarak, Kullanıcı tanımlı türlerin birbirlerine döngüsel bağımlılıkları olmayabilir, bu nedenle aşağıdaki tür tanımları kümesi geçersizdir:

```qsharp
newtype TypeA = (Int, TypeB);
newtype TypeB = (Double, TypeC);
newtype TypeC = (TypeA, Range);
```


## <a name="operation-and-function-types"></a>İşlem ve Işlev türleri

Çağrılabilir her ikisi için temel tür veya olarak yazılır `('Tinput => 'Tresult)` ; `('Tinput -> 'Tresult)` burada `'Tinput` ve `'Tresult` türleri.
Bunlara çağrılabilir *imzası* denir.

Tüm Q # callables, giriş olarak tek bir değer alıp çıkış olarak tek bir değer döndürecek şekilde değerlendirilir.
Hem giriş hem de çıkış değerleri tanımlama grupları olabilir.
Sonuç dönüşü olmayan callables `Unit` .
Girişi olmayan callables, boş kayıt grubunu giriş olarak alır.

> [!NOTE]
> İle ilk form, `=>` işlemler için kullanılır; ikinci form, ile, `->` işlevleri için.
> Örneğin, `((Qubit, Pauli) => Result)` olası bir tek qubit ölçüm işleminin imzasını temsil eder.
*İşlev* türleri kendi imzasıyla tamamen belirtilir.
Örneğin, bir açının sinüsünü hesaplayan bir işlev türünde olabilir `(Double -> Double)` .

*İşlemler*---, ancak işlevleri---, işlem türünün bir parçası olarak ifade edilen bazı ek özelliklere sahiptir. Bu tür özellikler, işlemin desteklediği *komik* ilgili bilgileri içerir.
Örneğin, işlemin yürütülmesi diğer qubit durumlarına göre koşullu olarak kullanılıyorsa, bu, `Controlled` functor 'ı desteklemelidir; işlemin bir ters olması halinde, `Adjoint` functor desteği gerekir. Funörler ve işlemler, [Q # ' daki işlemler ve işlevlerde](xref:microsoft.quantum.guide.operationsfunctions)ayrıntılı olarak ele alınmıştır, ancak burada bunun işlem imzasını nasıl değiştiren açıklanmıştır.

`Controlled`Bir işlem türünde ve/veya functor desteğinin gerekli olması için `Adjoint` , karşılık gelen özellikleri belirten bir ek açıklama eklememiz gerekir.
Ek açıklama `is Ctl` (örn. `(Qubit => Unit is Ctl)` ), işlemin denetlenebilir olduğunu---, yani yürütmenin başka bir qubit veya qubits durumunda olduğunu gösterir. Benzer şekilde, `is Adj` işlemin bir adjoint olduğunu veya yalnızca bir işlemi tamamen uygulayan ve bu durumda adjoint, durumu değişmeden bırakan bir "ters" olabilir. 

Bu tür bir işlemin hem hem de `Adjoint` `Controlled` functor desteklediğinden, bunu olarak ifade etmek istiyoruz `(Qubit => Unit is Adj + Ctl)` . Örneğin, yerleşik Pauli <xref:microsoft.quantum.intrinsic.x> işleminin türü vardır `(Qubit => Unit is Adj + Ctl)` . 

Herhangi bir belirtiyi desteklemeyen bir işlem türü, giriş ve çıkış türü ile tek başına, ek açıklama olmadan belirtilir.

### <a name="type-parameterized-functions-and-operations"></a>Tür parametreli Işlevler ve Işlemler

Çağrılabilir türler tür parametreleri içerebilir.
Tür parametreleri, tek bir teklifin önekli simgesiyle belirtilir; Örneğin, `'A` yasal bir tür parametresidir.
Türü tanımlama hakkında ayrıntılar-parametreli callables, [Q # sayfasındaki işlemler ve işlevler](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables) için verilmiştir.

Bir tür parametresi, tek bir imzada birden çok kez görünebilir.
Örneğin, bir dizinin her öğesine başka bir işlev uygulayan ve toplanan sonuçların geri döndürdüğü bir işlev imzaya sahip olur `(('A[], 'A->'A) -> 'A[])` .
Benzer şekilde, iki işlemin birleşimini döndüren bir işlev imzaya sahip olabilir `((('A=>'B), ('B=>'C)) -> ('A=>'C))` .

Bir tür parametreli çağrılabilir çağrılırken, aynı tür parametresine sahip tüm bağımsız değişkenler aynı türde olmalıdır.

S #, bir tür parametresi için yerine gelebilecek olası türleri kısıtlayan bir mekanizma sağlamaz.

## <a name="whats-next"></a>Sırada Ne Var?
Artık, Q # dilini oluşturan tüm türleri gördüğünüze göre, bu çeşitli türlerin ifadelerini oluşturma ve değiştirme hakkında bilgi almak için, [q # Içinde Ifade türüne](xref:microsoft.quantum.guide.expressions) gidebilirsiniz.


