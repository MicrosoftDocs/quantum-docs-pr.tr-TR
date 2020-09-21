---
title: İçindeki türler Q#
description: Programlama dilinde kullanılan farklı türler hakkında bilgi edinin Q# .
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.types
no-loc:
- Q#
- $$v
ms.openlocfilehash: c4a3e6563b8cabee87d1db6b9cb1c1f1c1a7131b
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835834"
---
# <a name="types-in-no-locq"></a>İçindeki türler Q#

Bu makalede Q# tür modeli ve türleri belirtmek ve bunlarla çalışmak için sözdizimi açıklanır. Bu türlerin ifadelerinde oluşturma ve üzerinde işlem yapma hakkında ayrıntılı bilgi için bkz. [tür ifadeleri](xref:microsoft.quantum.guide.expressions).

Q#Bu tür dikkatle kullanılması derleyicinin derleme zamanında programlar hakkında güçlü garantiler sağlamasına yardımcı olabileceğini belirten, *kesin olarak belirlenmiş* bir dil olduğunu unutmayın Q# .
Mümkün olan en güçlü garantiyi sağlamak için, içindeki türler arasındaki dönüştürmeler, Q# bu dönüştürmeyi ifade eden işlevlere yapılan çağrılar kullanılarak açık olmalıdır. 
Q# ad alanının bir parçası olarak çeşitli işlevler sağlar <xref:microsoft.quantum.convert> .
Diğer yandan, uyumlu türlere yönelik olarak yapılan yayınlar örtülü olarak gerçekleşir. 

Q# , doğrudan kullanılan ilkel türler ve diğer türlerden yeni türler oluşturmak için çeşitli yollar sağlar.
Bu makalenin geri kalanında anlatılmaktadır.

## <a name="primitive-types"></a>İlkel Türler

Q#Dil, hepsi doğrudan programlarda kullanabileceğiniz aşağıdaki *temel türleri*sağlar Q# . Bu temel türleri yeni türler oluşturmak için de kullanabilirsiniz.

- `Int`Tür, 64 bitlik işaretli bir tamsayıyı temsil eder, örneğin,, `2` , `107` `-5` .
- `BigInt`Türü, rastgele boyutun işaretli bir tamsayı temsil eder, örneğin,, `2L` , `107L` `-5L` .
   Bu tür .NET tabanlıdır <xref:System.Numerics.BigInteger>
   türüyle.

- `Double`Tür, bir çift duyarlıklı kayan noktalı sayıyı temsil eder, örneğin,,, `0.0` `-1.3` `4e-7` .
- `Bool`Tür ya da bir Boolean değerini temsil eder `true` `false` .
- `Range`Türü, tarafından belirtilen, `start..step..stop` adımın isteğe bağlı olduğunu gösteren bir tamsayılar dizisini temsil eder. 
   Örneğin, `start .. stop` öğesine karşılık gelir `start..1..stop` ve `1..2..7` $ \{ 1, 3, 5, 7 $ dizisini temsil eder \} .
- `String`Tür, bir kez oluşturulduktan sonra kullanıcıya donuk olan Unicode karakterlerinden oluşan bir dizidir.
  `string`Bir hata veya tanılama olayı durumunda iletileri klasik bir konağa raporlamak için türünü kullanın.
- `Unit`Tür yalnızca bir değere sahip olabilir `()` . 
  Bir Q# işlev veya işlemin hiçbir bilgi döndürdüğünü belirtmek için bu türü kullanın. 
- `Qubit`Tür bir hisse bitini veya qubit 'i temsil eder.
   `Qubit`, kullanıcının opaktır. Bunlar ile mümkün olan tek işlem, başka bir işleme geçirilmekten farklı kimlik (eşitlik) için test amaçlıdır.
   Sonuç olarak, `Qubit` bir hisse işlemcisi (veya hisse Benzetici simülatörü) üzerinde iç yönergeleri çağırarak öğeleri ' de uygulayabilirsiniz.
- `Pauli`Tür, dört adet tek qubit Pauli işleçlerinden birini temsil eder.
   Bu türü, döndürmeler için temel işlemi göstermek ve ölçülecek observable 'ı belirtmek için kullanın.
   Dört olası değeri olan numaralandırılmış bir türdür: `PauliI` ,, `PauliX` `PauliY` , ve `PauliZ` , türünde sabitler `Pauli` .
- `Result`Tür, ölçümün sonucunu temsil eder.
   Bu, iki olası değeri olan `One` ve türünde sabitler olan numaralandırılmış bir türdür `Zero` `Result` .
   `Zero` + 1 eigenvalue değerinin ölçüldüğünü belirtir; `One` -1 eigenvalue değerinin ölçüldüğünü gösterir.

,,,,,, `true` `false` Ve sabitleri `PauliI` `PauliX` `PauliY` `PauliZ` `One` `Zero` içindeki tüm ayrılmış semboller Q# .

## <a name="array-types"></a>Dizi türleri

* Geçerli herhangi bir Q# tür için, bu türdeki bir değer dizisini temsil eden bir tür vardır.
    Örneğin, `Qubit[]` ve `(Bool, Pauli)[]` `Qubit` değerlerin dizilerini ve `(Bool, Pauli)` demet değerlerini temsil edin.

* Dizi dizisi de geçerlidir. Önceki örnekte genişletilen dizi dizisi `(Bool, Pauli)` gösterilir `(Bool, Pauli)[][]` .

> [!NOTE] 
> Bu örnek, `(Bool, Pauli)[][]` dikdörtgen bir iki boyutlu diziyi değil, potansiyel olarak pürüzlü dizi dizileri temsil eder. Q# dikdörtgen çok boyutlu dizileri desteklemez.

* Bir dizi değeri Q# , içinde olduğu gibi bir dizinin öğeleri etrafında köşeli parantezler kullanılarak kaynak kodunda yazılabilir `[PauliI, PauliX, PauliY, PauliZ]` .
Dizideki tüm öğelerin ortak temel türü bir dizi sabit değerinin türünü belirler. Bu nedenle, ortak temel türü olmayan öğelerle bir dizi oluşturmak bir hata oluşturur.  
Bir örnek için bkz. [callables dizileri](xref:microsoft.quantum.guide.expressions#arrays-of-callables).

    > [!WARNING]
    > Oluşturulduktan sonra bir dizinin öğeleri değiştirilemez.
    > Değiştirilmiş bir dizi oluşturmak için, [Update-and-reassıgn deyimlerini](xref:microsoft.quantum.guide.variables#update-and-reassign-statements) veya [kopyalama ve güncelleştirme ifadelerini](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions)kullanın.

* Alternatif olarak, bir dizi boyutundan `new` anahtar sözcüğü kullanılarak oluşturulabilir:

    ```qsharp
    let zeros = new Int[13];
    // you can also use new for creating empty arrays:
    let emptyRegister = new Qubit[0];
    ```

* Bir `Length` diziden öğe sayısını bir olarak almak için çekirdek işlevini kullanın `Int` .
* Diziler, bir dizinin öğelerinin bir alt kümesini içeren tek öğe veya yeni diziler elde etmek için erişilebilir.
Dizilerin alt simgeleri sıfır tabanlıdır ve tür `Int` ya da tür olmalıdır `Range` :

    ```qsharp
    let arr = [10, 11, 36, 49];
    let ten = arr[0]; // 10
    let odds = arr[1..2..4]; // [11, 49]
    ```

## <a name="tuple-types"></a>Demet türleri

Tanımlama grupları Q# , değerleri tek bir değer toplamak için kullanılan güçlü bir kavramdır, bu da bunları bir araya getirmek daha kolay hale getirir.
Özellikle, tanımlama grubu gösterimini kullanarak her işlemin ve çağrılabilir şekilde tam olarak bir giriş aldığını ve tam olarak bir çıkış döndürdüğünü ifade edebilirsiniz.

* Sıfır veya daha fazla farklı tür (, `T0` `T1` ...) verildiğinde, `Tn` Yeni bir  *demet türünü* olarak belirtebilirsiniz `(T0, T1, ..., Tn)` .
Yeni bir demet türü oluşturmak için kullanılan türler, içinde olduğu gibi kendi tanımlama grupları olabilir `(Int, (Qubit, Qubit))` .
Bu iç içe geçme her zaman sınırlıdır, ancak demet türleri hiçbir koşulda kendilerini içeremez.

* Yeni demet türünün değerleri, kayıt düzeni içindeki her türden değer dizileri tarafından oluşturulan dizileridir.
Örneğin, `(3, false)` türü demet türünde olan bir kayıt türüdür `(Int, Bool)` .
Tanımlama dizileri, dizi dizileri, alt tanımlama grupları ve benzeri diziler oluşturmak mümkündür.

* 0,3 itibariyle Q# , boş tanımlama grubunun `Unit` *türünün* adı, `()` boş tanımlama grubunun *değeri* için kullanılır.

* Demet örnekleri sabittir.
Q# , oluşturulduktan sonra bir kayıt düzeninin içeriğini değiştirme mekanizması sağlamaz.



### <a name="singleton-tuple-equivalence"></a>Tek kayıt düzeni denklik

Ya da gibi tek bir (tek öğeli) tanımlama grubu oluşturmak mümkündür `('T1)` `(5)` `([1,2,3])` .
Ancak, Q# tek bir kayıt kümesini, iliştirilmiş türdeki bir değere eşdeğer olarak değerlendirir.
Diğer bir deyişle, ve arasında ya da ile arasında ya da arasında bir fark yoktur `5` `(5)` `5` `(((5)))` `(5, (6))` `(5, 6)` .
Yazmak üzere yazmak için geçerli olduğu gibi, `(5)+3` `5+3` her iki ifade de olarak değerlendirilir `8` .

Bu denklik, atama ve ifadeler dahil tüm amaçlar için geçerlidir.
Herhangi bir ifade verildiğinde, parantez içine alınmış aynı ifade aynı türde bir ifadedir.
Örneğin, türünde bir ifadedir, türünde bir ifadedir `(7)` `Int` `([1,2,3])` `Int[]` ve `((1,2))` türünde bir ifadedir `(Int, Int)` .

Özellikle, bu, giriş tanımlama grubu veya çıktı kayıt türü türünde tek bir bağımsız değişken alan veya tek bir değer döndüren bir işlem veya işlevi görüntüleyebileceðiniz anlamına gelir.

Bu özelliğe, _tek demet denklik_olarak başvurduk.


## <a name="user-defined-types"></a>Kullanıcı tanımlı türler

Kullanıcı tanımlı tür bildirimi, anahtar sözcükten `newtype` , ardından Kullanıcı tanımlı türün adı, bir `=` , geçerli bir tür belirtimi ve sonlandırma noktalı virgülünden oluşur.

Örnek:

```qsharp
newtype PairOfInts = (Int, Int);
```
    
* Her Q# kaynak dosya, Kullanıcı tanımlı herhangi bir sayıda tür bildirebilir.
* Tür adları ad alanı içinde benzersiz olmalıdır ve işlem ve işlev adlarıyla çakışmayabilir.
* Temel türler özdeş olsa bile Kullanıcı tanımlı türler farklıdır.
Özellikle, temel alınan türler özdeş olsa bile, iki Kullanıcı tanımlı türün değerleri arasında otomatik dönüşüm yoktur.

### <a name="named-vs-anonymous-items"></a>Adlandırılmış vs. Anonymous öğeleri

Bir Q# Dosya, geçerli bir türden tek bir değer içeren yeni bir adlandırılmış tür tanımlayabilir.
Herhangi bir demet türü için `T` , ifadesiyle birlikte bir alt türü olan yeni bir Kullanıcı tanımlı tür bildirebilirsiniz `T` `newtype` .
@"microsoft.quantum.math"Ad alanında, örneğin, karmaşık sayılar Kullanıcı tanımlı bir tür olarak tanımlanmıştır:

```qsharp
newtype Complex = (Double, Double);
```
Bu ifade, türünde iki anonim öğe içeren yeni bir tür oluşturur `Double` .   

Anonim öğeler dışında, Kullanıcı tanımlı türler Ayrıca sürüm 0,7 veya üzeri olarak *adlandırılmış öğeleri* destekler Q# . Örneğin, `Real` bir karmaşık sayının gerçek bölümünü ve sanal parçayı temsil eden Double için öğeleri olarak adlandırın `Imag` : 

```qsharp
newtype Complex = (Real : Double, Imag : Double);
```
Kullanıcı tanımlı bir türdeki bir öğenin adlandırılması, tüm öğelerin adlandırılması gerektiğini göstermez; adlandırılmış ve adlandırılmamış öğelerin herhangi bir birleşimi desteklenir. Ayrıca, iç öğeler de adlandırılmış olabilir.
`Nested`Örneğin, aşağıda tanımlandığı gibi türü, temel bir tür içerir `(Double, (Int, String))` ve yalnızca türü öğe olarak `Int` adlandırılır ve diğer tüm öğeler anonimdir. 

```qsharp
newtype Nested = (Double, (ItemName : Int, String)); 
```

Adlandırılmış öğeler, *erişim operatörü* aracılığıyla doğrudan erişilebilecekleri avantajına sahiptir `::` . 

```qsharp
function ComplexAddition(c1 : Complex, c2 : Complex) : Complex {
    return Complex(c1::Real + c2::Real, c1::Imag + c2::Imag);
}
```

Karmaşık tanımlama grubu türleri için kısa diğer adlar sağlamaya ek olarak, böyle türler tanımlamanın önemli bir avantajı, belirli bir değerin amacını belgelememelerdir.
Örneğe dönerek `Complex` , bir tane, Kullanıcı tanımlı tür olarak bir kutupsal koordinat gösterilemeyen de tanımlanabilir:

```qsharp
newtype ComplexPolar = (Magnitude : Double, Argument : Double);
```

Hem hem de `Complex` `ComplexPolar` her ikisi de temel bir türe sahip olsa da `(Double, Double)` , iki tür ' de tamamen uyumsuz Q# , yanlışlıkla bir karmaşık matematik işlevini kutupsal koordinatlarla çağırma riskini en aza indirir ve tam tersi de geçerlidir.

#### <a name="access-anonymous-items-with-the-unwrap-operator"></a>Unwrap işleci ile anonim öğelere erişme

Anonim öğelere erişmek için önce sonek işlecini kullanarak sarmalanmış değeri ayıklayın `!` .
"Sarmalama" işleci ile, `!` Kullanıcı tanımlı bir türde bulunan değeri ayıklayabilirsiniz.
Böyle bir "sarmalama" ifadesinin türü, Kullanıcı tanımlı türün temel türüdür. 

```qsharp
function PrintedMessage(value : Nested) : Unit {
    let (d, (_, str)) = value!;
    Message ($"{str}, value: {d}");
}
```

Tek sarmalama işleci bir sarmalama katmanının sarmalanmasını kaldırır. Çarpmadan kaydırılmış bir değere erişmek için birden çok sarmalama işleci kullanın.

Örnek:

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

Unwrap işleci hakkında daha fazla bilgi için bkz. [Içindeki Q# tür ifadeleri ](xref:microsoft.quantum.guide.expressions).

### <a name="creating-values-of-user-defined-types"></a>Kullanıcı tanımlı türlerin değerlerini oluşturma

Karşılık gelen tür oluşturucusunu çağırarak Kullanıcı tanımlı bir türün değerlerini oluşturun:

```qsharp
let realUnit = Complex(1.0, 0.0);
let imaginaryUnit = Complex(0.0, 1.0);
```

Alternatif olarak, [kopyalama ve güncelleştirme ifadelerini](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions)kullanarak var olan olanlardan yeni değerler oluşturabilirsiniz. Diziler ile yaptığı gibi, kopyalama ve güncelleştirme ifadeleri, belirtilen adlandırılmış öğeler hariç özgün ifadenin tüm öğe değerlerini kopyalar. Bu özel durumlar için, bu öğelerin değerleri, ifadenin sağ tarafında tanımlanan değerlerdir. Dizi öğeleri için kullanılabilen diğer dil yapıları (örneğin, [Update ve-yeniden atama deyimleri](xref:microsoft.quantum.guide.variables#update-and-reassign-statements)), Kullanıcı tanımlı türlerde adlandırılmış öğeler için de mevcuttur.

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

* Kullanıcı tanımlı türleri başka herhangi bir türü kullandığınız her yerde kullanabilirsiniz.
Özellikle, Kullanıcı tanımlı bir türün dizisini tanımlamak ve Kullanıcı tanımlı bir türü bir demet türünün öğesi olarak eklemek mümkündür.

* Özyinelemeli tür yapıları oluşturmak mümkün değildir.
Diğer bir deyişle, Kullanıcı tanımlı bir türü tanımlayan tür, Kullanıcı tanımlı türdeki bir öğeyi içeren bir demet türü olamaz.
Daha genel olarak, Kullanıcı tanımlı türlerin birbirlerine döngüsel bağımlılıkları olmayabilir, bu nedenle aşağıdaki tür tanımları kümesi geçersizdir:

    ```qsharp
    newtype TypeA = (Int, TypeB);
    newtype TypeB = (Double, TypeC);
    newtype TypeC = (TypeA, Range);
    ```


## <a name="operation-and-function-types"></a>İşlem ve Işlev türleri

Türler `'Tinput` ve `'Tresult` :

* `('Tinput => 'Tresult)` , örneğin, her bir *işlemin*temel türüdür `((Qubit, Pauli) => Result)` .
* `('Tinput -> 'Tresult)` , örneğin, herhangi bir *işlevin*temel türüdür `(Int -> Int)` . 

Bunlara çağrılabilir *imzası* denir.

* Tüm Q# callables, girdi olarak tek bir değer alır ve çıkış olarak tek bir değer döndürür.
* Hem giriş hem de çıkış değerleri için tanımlama grupları kullanabilirsiniz.
* Sonuç içermeyen callables, döndürün `Unit` .
* Girişi olmayan callables, boş kayıt grubunu giriş olarak alır.

### <a name="functors"></a>Functorları

*İşlev* türleri kendi imzasıyla tamamen belirtilir. Örneğin, bir açının sinüsünü hesaplayan bir işlev türünde olabilir `(Double -> Double)` . 

*İşlemler* , işlem türünün bir parçası olarak ifade edilen bazı ek özelliklere sahiptir. Bu tür özellikler, işlemin desteklediği *komik* ilgili bilgileri içerir.
Örneğin, işlemin çalıştırılması diğer qubits 'in durumuna dayanıyorsa, bu durumda `Controlled` functor 'ı desteklemelidir; işlemin bir ters olması halinde, functor 'ı desteklemesi gerekir `Adjoint` .

> [!NOTE]
> Bu makalede, yalnızca funörler işlem imzasını nasıl değiştirtiğiyle tartışılmaz. Komik ve işlemler hakkında daha fazla bilgi için bkz. [Içindeki Q# Işlemler ve işlevler ](xref:microsoft.quantum.guide.operationsfunctions). 

`Controlled`Bir işlem türünde ve/veya functor desteğinin gerekli olmasını sağlamak için `Adjoint` , karşılık gelen özellikleri belirten bir ek açıklama eklemeniz gerekir.
Ek açıklama `is Ctl` (örneğin, `(Qubit => Unit is Ctl)` ), işlemin denetlenebilir olduğunu gösterir. Diğer bir deyişle, çalıştırması başka bir qubit veya qubits 'in durumuna bağlıdır. Benzer şekilde, ek açıklama `is Adj` işlemin bir adeklem olduğunu, yani "ters" (bir işlem) ve ardından adjoint değerini bir durum olduğu gibi bırakır. 

Bu tür bir işlemin hem hem de functor desteklediğinden emin olmak istiyorsanız `Adjoint` `Controlled` bunu olarak ifade edebilirsiniz `(Qubit => Unit is Adj + Ctl)` . Örneğin, yerleşik Pauli <xref:microsoft.quantum.intrinsic.x> işleminin türü vardır `(Qubit => Unit is Adj + Ctl)` . 

Herhangi bir belirtiyi desteklemeyen bir işlem türü, giriş ve çıkış türü ile tek başına, ek açıklama olmadan belirtilir.

### <a name="type-parameterized-functions-and-operations"></a>Tür parametreli Işlevler ve Işlemler

Çağrılabilir türler *tür parametreleri*içerebilir.
Bir tür parametresi belirtilen tek tırnak tarafından önekli bir sembol kullanın; Örneğin, `'A` yasal bir tür parametresidir.
Tür parametreli callables tanımlama hakkında daha fazla bilgi ve Ayrıntılar için bkz. [Içindeki Q# Işlemler ve işlevler ](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables).

Bir tür parametresi, tek bir imzada birden çok kez görünebilir.
Örneğin, bir dizinin her öğesine başka bir işlev uygulayan ve toplanan sonuçların imzasını döndüren bir işlev `(('A[], 'A->'A) -> 'A[])` .
Benzer şekilde, iki işlemin birleşimini döndüren bir işlev imzaya sahiptir `((('A=>'B), ('B=>'C)) -> ('A=>'C))` .

Parametreli bir tür türü çağırdığınızda, aynı tür parametresine sahip olan tüm bağımsız değişkenler aynı türde olmalıdır.

Q# , bir kullanıcının bir tür parametresi için yerine geçecek olası türleri kısıtlayan bir mekanizma sağlamaz.

## <a name="next-steps"></a>Sonraki adımlar

Dili oluşturan tüm türleri gördüğünüze Q# göre, bu çeşitli türlerin ifadelerini oluşturmayı ve işlemeyi öğrenmek için [Içindeki Q# tür ifadeleri](xref:microsoft.quantum.guide.expressions) bölümüne bakın.
