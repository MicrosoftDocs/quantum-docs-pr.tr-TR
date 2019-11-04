---
title: 'Q # tür modeli | Microsoft Docs'
description: 'Q # tür modeli'
author: QuantumWriter
uid: microsoft.quantum.language.type-model
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 4e251053d1b8306bf8956314d8099e95c56bce55
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/28/2019
ms.locfileid: "73184755"
---
# <a name="the-type-model"></a>Tür modeli

Bu bölüm, Q # tür modelini düzenler ve türleri belirtmek ve bunlarla çalışmak için sözdizimini açıklar.
Bu tür dikkatle kullanılması derleyicinin, derleme zamanında Q # programları hakkında güçlü garantiler sağlamasına yardımcı olabileceğini belirten, *kesin olarak yazılmış* bir dil olduğunu unutmayın.

Mümkün olan en güçlü garantiyi sağlamak için, Q # içindeki türler arasındaki dönüştürmeler, bu dönüştürmeyi ifade eden işlevlere yapılan çağrılar kullanılarak açık olmalıdır. <xref:microsoft.quantum.convert> ad alanının bir parçası olarak çeşitli işlevler sağlanır.
Diğer yandan uyumlu türlere yapılan yayınlar örtülü olarak gerçekleşir. 

Q #, doğrudan kullanılabilen basit türler ve diğer türlerden yeni türler oluşturmak için çeşitli yollar sağlar.
Bu bölümün geri kalanında her birini açıklıyoruz.

## <a name="primitive-types"></a>İlkel türler

Q # dili, diğer türlerin oluşturulabileceği çeşitli *temel türler*sağlar:

- `Int` türü, 64 bitlik işaretli bir tamsayıyı temsil eder, örneğin: `2`, `107`, `-5`.
- `BigInt` türü, rastgele boyutun işaretli bir tamsayı (örn. `2L`, `107L`, `-5L`) temsil eder.
   Bu tür .NET <xref:System.Numerics.BigInteger> tabanlıdır
   türüyle.
- `Double` türü çift duyarlıklı kayan noktalı sayıyı temsil eder, örneğin: `0.0`, `-1.3`, `4e-7`.
- `Bool` türü `true` veya `false`olabilen bir Boolean değeri temsil eder.
- `Qubit` türü bir hisse bitini veya qubit 'i temsil eder.
   `Qubit`s, kullanıcının opaktır; Bunlar ile mümkün olan tek işlem, başka bir işleme geçirilmekten farklı kimlik (eşitlik) için test amaçlıdır.
   Sonuç olarak, `Qubit`s üzerindeki eylemler bir hisse işlemcisi (veya bir simülasyonu) üzerinde iç yönergeler çağırarak uygulanır.
- `Pauli` türü, dört adet tek qubit Pauli işleçlerinden birini temsil eder.
   Bu tür, döndürmeler için temel işlemi göstermek ve ölçülecek observable 'ı belirtmek için kullanılır.
   Bu, dört olası değeri olan numaralandırılmış bir türdür: `PauliI`, `PauliX`, `PauliY`ve `PauliZ`, `Pauli`türünde sabitler.
- `Result` türü bir ölçünün sonucunu temsil eder.
   Bu, iki olası değeri olan numaralandırılmış bir türdür: `One` ve `Zero`, `Result`türünde sabitler.
   `Zero` + 1 eigenvalue değerinin ölçüldüğünü belirtir; `One`-1 eigenvalue değerini gösterir.
- `Range` türü, `start..step..stop`tarafından belirtilen ve adım seçeneklerini gösteren bir tamsayılar dizisini temsil eder. 
   Bu `start .. stop` `start..1..stop`karşılık gelir ve örn. `1..2..7` $\{1, 3, 5, 7\}$ dizisini temsil eder.
- `String` türü, bir kez oluşturulduktan sonra kullanıcıya donuk olan Unicode karakterlerinden oluşan bir dizidir.
  Bu tür, bir hata veya tanılama olayı durumunda iletileri klasik bir konağa raporlamak için kullanılır.
- `Unit` türü yalnızca bir değer `()`izin veren türdür. 
  Bu tür, Q # işlevinin veya işleminin hiçbir bilgi döndürdüğünü göstermek için kullanılır. 

`true`, `false`, `PauliI`, `PauliX`, `PauliY`, `PauliZ`, `One`ve `Zero` sabitleri, Q # içindeki tüm ayrılmış sembollerdir.

## <a name="array-types"></a>Dizi türleri

Geçerli bir Q # tür `'T`verildiğinde, `'T`türünde bir değer dizisini temsil eden bir tür vardır.
Bu dizi türü `'T[]`olarak temsil edilir; Örneğin, `Qubit[]` veya `Int[][]`.
Örneğin, bir tamsayılar koleksiyonu `Int[]`gösterilir, ancak `(Bool, Pauli)` değerlerinin dizi dizileri `(Bool, Pauli)[][]`olarak gösterilir.

İkinci örnekte bunun, dikdörtgen iki boyutlu bir dizi değil, potansiyel olarak pürüzlü dizi dizileri temsil ettiğini unutmayın.
Q #, dikdörtgen çok boyutlu diziler için destek sağlamaz.

Dizi değeri, `[PauliI, PauliX, PauliY, PauliZ]`içinde olduğu gibi, bir dizinin öğeleri etrafında köşeli ayraçlar kullanılarak Q # kaynak kodunda yazılabilir.
Dizi sabit değerinin türü dizideki tüm öğelerin ortak temel türüne göre belirlenir. 

> [!WARNING]
> Dizinin öğeleri, dizi oluşturulduktan sonra değiştirilemez.
> Güncelleştirme ve yeniden atama deyimleri ve/veya kopyalama ve güncelleştirme ifadeleri, değiştirilmiş bir diziyi oluşturmak için kullanılabilir.

Alternatif olarak, bir dizi `new` anahtar sözcüğü kullanılarak boyutundan oluşturulabilir:

```qsharp
let zeros = new Int[13];
// new also allows for creating empty arrays:
let emptyRegister = new Qubit[0];
```

Her iki durumda da, bir dizi oluşturulduktan sonra `Length` çekirdek işlevi, öğe sayısını `Int`olarak elde etmek için kullanılabilir.
Diziler, bir dizinin öğelerinin bir alt kümesini içeren tek öğe veya yeni diziler elde etmek için tür `Int` ya da `Range`tür olan alt simgeler ile köşeli ayraç kullanılarak alt simge olabilir.
Dizilerin alt simgeleri sıfır tabanlıdır:

```qsharp
let arr = [10, 11, 36, 49];
let ten = arr[0]; // 10
let odds = arr[1..2..4]; // [11, 49]
```

## <a name="tuple-types"></a>Demet türleri

Sıfır veya daha fazla farklı tür `T0`, `T1`,... `Tn`, yeni bir *tanımlama grubu türünü* `(T0, T1, ..., Tn)`olarak gösteremez.
Yeni bir demet türü oluşturmak için kullanılan türler, `(Int, (Qubit, Qubit))`gibi kendi tanımlama grupları olabilir.
Bu iç içe geçme her zaman sınırlıdır, ancak demet türleri hiçbir koşulda kendilerini içeremez.

Yeni demet türünün değerleri, kayıt düzeni içindeki her türden değer dizileri tarafından oluşturulan dizileridir.
Örneğin, `(3, false)` türü `(Int, Bool)`demet türü olan bir kayıt türüdür.
Tanımlama dizileri, dizi dizilerindeki diziler, alt tanımlama grupları, vb. öğeleri oluşturmak mümkündür.

Q # 0,3 itibariyle `Unit`, boş tanımlama grubunun *türünün* adıdır; `()`, boş demet *değeri*için kullanılır.

Demet örnekleri sabittir.
S #, oluşturulduktan sonra bir kayıt düzeninin içeriğini değiştirme mekanizması sağlamaz.

Tanımlama grupları, her bir değer toplamak için Q # boyunca kullanılan güçlü bir kavramdır; bu da, daha kolay bir şekilde geçiş yapmayı kolaylaştırır.
Özellikle, tanımlama grubu gösterimini kullanarak her işlemin ve çağrılabilir şekilde tam olarak bir giriş aldığını ve tam olarak bir çıkış döndürdüğünü ifade edebilirsiniz.

### <a name="singleton-tuple-equivalence"></a>Tek kayıt düzeni denklik

`('T1)`, `(5)` veya `([1,2,3])`gibi tek öğeli bir tanımlama grubu oluşturmak mümkündür.
Ancak, Q #, tek bir kayıt kümesini, iliştirilmiş türdeki bir değere tamamen eşdeğer olarak değerlendirir.
Diğer bir deyişle, `5` ile `(5)`arasında veya `5` ile `(((5)))`arasında ya da `(5, (6))` ile `(5, 6)`arasında bir fark yoktur.

Bu denklik, atama ve ifadeler dahil tüm amaçlar için geçerlidir.
`5+3`yazmak için `(5)+3` yazmak için geçerli olduğu gibi, her iki ifade de `8`olarak değerlendirilir.
Özellikle, bu, giriş kümesi veya çıkış grubu türü olan bir işlemin veya işlevin tek bir bağımsız değişken alan veya tek bir değer döndüren bir alana sahip olabileceği anlamına gelir.

Bu özelliğe, _tek demet denklik_olarak başvurduk.

## <a name="user-defined-types"></a>Kullanıcı tanımlı türler

Bir Q # dosyası, geçerli bir türden tek bir değer içeren yeni bir adlandırılmış tür tanımlayabilir.
`T`tanımlama grubu türü için, `newtype` ifadesiyle `T` alt türü olan yeni bir Kullanıcı tanımlı tür bildirebiliriz.
@"microsoft.quantum.canon" ad alanında, örneğin, karmaşık sayılar Kullanıcı tanımlı bir tür olarak tanımlanmıştır:

```qsharp
newtype Complex = (Double, Double);
```

Bu ifade `Double`türünde iki anonim öğe içeren yeni bir tür oluşturur.   
Anonim öğelerden biri dışında, Kullanıcı tanımlı türler de Q # sürüm 0,7 veya üzeri olarak adlandırılmış öğeleri destekler. Örneğin, bir karmaşık sayının gerçek parçasını temsil eden Double için `Re` ve sanal bölüm için `Im` olarak adlandırdık: 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
Kullanıcı tanımlı tür içindeki bir öğenin adlandırılması, tüm öğelerin adlandırılması gerektiğini göstermez; adlandırılmış ve adlandırılmamış öğelerin herhangi bir birleşimi desteklenir. Ayrıca, iç öğeler de adlandırılmış olabilir.
Aşağıda tanımlanan `Nested` türü, temel alınan bir tür `(Double, (Int, String))`vardır ve yalnızca `Int` türü öğe ve diğer tüm öğeler anonimdir. 

```qsharp
newtype Nested = (Double, (ItemName : Int, String)); 
```
Adlandırılmış öğeler, erişim operatörü `::`aracılığıyla doğrudan erişilebilecekleri avantajına sahiptir. 

```qsharp
function Addition (c1 : Complex, c2 : Complex) : Complex {
    return Complex(c1::Re + c2::Re, c1::Im + c2::Im);
}
```

Diğer yandan anonim öğelere erişmek için, sarmalanmış değerin ilk olarak `!`sonek işleci kullanılarak ayıklanması gerekir.
`!`, bir Kullanıcı tanımlı türde bulunan değeri ayıklamaya izin veren "Unwrap" işleci.
Böyle bir "sarmalama" ifadesinin türü, Kullanıcı tanımlı türün temel türüdür. 

```qsharp
function PrintMsg (value : Nested) : Unit {
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

Daha fazla ayrıntı için [sarmalama ifadelerinin](xref:microsoft.quantum.language.expressions#unwrap-expressions) ve [operatör önceliğinde](xref:microsoft.quantum.language.expressions#operator-precedence) bölüme göz atın.

Kullanıcı tanımlı türün değerleri, karşılık gelen tür Oluşturucusu çağırarak oluşturulabilir:

```
let realUnit = Complex(1.0, 0.0);
let imaginaryUnit = Complex(0.0, 1.0);
```

Alternatif olarak, [kopyalama ve güncelleştirme ifadeleri](xref:microsoft.quantum.language.expressions#copy-and-update-expressions)kullanılarak mevcut olanlardan yeni değerler oluşturulabilir. Diziler gibi ifadeler, özgün ifadenin tüm öğe değerlerini, belirtilen adlandırılmış öğelerin özel durumuyla birlikte kopyalar. Bu değerler için, ifadenin sağ tarafında tanımlananlara ayarlanır. Aynı zamanda Kullanıcı tanımlı türlerde adlandırılmış öğeler için kullanılabilen, örneğin [Update-ve-yeniden atama deyimleri](xref:microsoft.quantum.language.statements#update-and-reassign-statement)gibi diğer dil yapıları de mevcuttur.

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

Özyinelemeli tür yapıları oluşturmak mümkün değildir.
Diğer bir deyişle, Kullanıcı tanımlı bir türü tanımlayan tür, Kullanıcı tanımlı türdeki bir öğe içeren bir demet türü olamaz.
Daha genel olarak, Kullanıcı tanımlı türlerin birbirlerine döngüsel bağımlılıkları olmayabilir, bu nedenle aşağıdaki tür tanımları kümesi geçersizdir:

```qsharp
newtype TypeA = (Int, TypeB);
newtype TypeB = (Double, TypeC);
newtype TypeC = (TypeA, Range);
```

Karmaşık tanımlama grubu türleri için kısa diğer adlar sağlamaya ek olarak, bu tür türler tanımlamanın önemli bir avantajı, belirli bir değerin amacını belgelememelerdir.
`Complex`örneğine dönerek, bir Kullanıcı tanımlı tür olarak 2B kutupsal koordinatları de tanımlanabilir:

```qsharp
newtype Polar = (Radius : Double, Phase : Double);
```

Hem `Complex` hem de `Polar` hem temel alınan bir tür `(Double, Double)`olsa da, iki tür de her ikisi de, her ikisi de aynı şekilde, bir karmaşık matematik işlevini kutupsal koordinatlarla çağırma riskini en aza indirir ve tam tersi de geçerlidir.
Bu şekilde, Kullanıcı tanımlı türlerin, örneğin kayıtları F# olarak benzer bir rolü vardır. 


## <a name="operation-and-function-types"></a>İşlem ve Işlev türleri

Bir Q # _işlemi_ bir hisse alt yordamı.
Diğer bir deyişle, bu, hisse işleme içeren çağrılabilir bir yordamdır.

Bir Q # _işlevi_ , bir hisse algoritması içinde kullanılan klasik bir alt yordam.
Klasik kod içerebilir, ancak hisse işlem işlemleri yoktur.
Özellikle, işlevler qubit ayıramayabilir veya bu işlemleri çağırabilir.
Bununla birlikte, işlemleri veya işleme için qubits 'i geçirmek mümkündür.
Bu nedenle işlevler, aynı bağımsız değişkenlerle çağrı yapan her zaman aynı sonucu üreten anlamda tamamen belirleyici olur. 

Birlikte, işlemler ve işlevler _callables_olarak adlandırılır.  Aşağıda bunların bazı [örneklerini](#examples) görebilirsiniz.

Tüm Q # callables, giriş olarak tek bir değer alıp çıkış olarak tek bir değer döndürecek şekilde değerlendirilir.
Hem giriş hem de çıkış değerleri tanımlama grupları olabilir.
Sonuç döndüren `Unit`callables.
Girişi olmayan callables, boş kayıt grubunu giriş olarak alır.

Çağrılabilir için temel tür, hem `'Tinput` hem de `'Tresult` türler olan `('Tinput => 'Tresult)` veya `('Tinput -> 'Tresult)`olarak yazılır.
`=>`olan ilk form, işlemler için kullanılır; ikinci form, işlevleri için `->`.
Örneğin `((Qubit, Pauli) => Result)`, olası bir tek qubit ölçüm işleminin imzasını temsil eder.

İşlev türleri kendi imzasıyla tamamen belirtilir.
Örneğin, bir açının sinüsünü hesaplayan bir işlevin türü `(Double -> Double)`olacaktır.

İşlemler (ancak işlevleri değil), işlem türünün bir parçası olarak ifade edilen bazı ek _özelliklere_ sahiptir. Bu tür özellikler, işlemin desteklediği komik ilgili bilgileri içerir.
Funörler, temel bir işlemin bir özelleştirmesi üreten meta işlemlerdir; Aşağıdaki bkz. [Funörler](#functors).

İşlem türleri, giriş türü, çıkış türü ve özellikleri tarafından belirtilir.    
Bir işlem türünde `Controlled` ve/veya `Adjoint` functor desteğinin gerekli olması için, karşılık gelen özellikleri belirten bir ek açıklama eklememiz gerekir.
Örneğin bir ek açıklama `is Ctl`, işlemin denetlenebilir olduğunu gösterir. Bu tür bir işlemin hem `Adjoint` hem de `Controlled` functor desteklemesini istiyorsanız bunu `(Qubit => Unit is Adj + Ctl)`olarak ifade edebilirsiniz. Kullanılan işlem özellikleri `Adj` ve `Ctl` kesinlikle konuşurken, her etiketin, örneğin belirli bir functor desteği gibi belirli bir işlem özelliklerini gösterdiği, önceden tanımlanmış iki etiket kümesi vardır.
Bu nedenle `+`, bu iki kümenin birleşimini belirtmek için kullanılır ve `*` kesişimini belirtmek için kullanılır. her iki küme için de ortak olan Etiketler.  

Örneğin, Pauli `X` işleminin türü `(Qubit => Unit is Adj + Ctl)`vardır.
Herhangi bir belirtiyi desteklemeyen bir işlem türü, giriş ve çıkış türü ile tek başına, ek açıklama olmadan belirtilir.


### <a name="type-parameterized-functions-and-operations"></a>Tür parametreli Işlevler ve Işlemler

Çağrılabilir türler tür parametreleri içerebilir.
Tür parametreleri, tek bir teklifin önekli simgesiyle belirtilir; Örneğin, `'A` yasal bir tür parametresidir.

Bir tür parametresi, tek bir imzada birden çok kez görünebilir.
Örneğin, bir dizinin her öğesine başka bir işlev uygulayan ve toplanan sonuçların döndüren bir işlev imza `(('A[], 'A->'A) -> 'A[])`olacaktır.
Benzer şekilde, iki işlemin birleşimini döndüren bir işlev imzaya `((('A=>'B), ('B=>'C)) -> ('A=>'C))`sahip olabilir.

Bir tür parametreli çağrılabilir çağrılırken, aynı tür parametresine sahip tüm bağımsız değişkenler aynı türde olmalıdır.

S #, bir tür parametresi için yerine gelebilecek olası türleri kısıtlayan bir mekanizma sağlamaz.

### <a name="type-compatibility"></a>Tür uyumluluğu

Desteklenen ek bir işlem, daha az komik olan bir işlemin her yerde kullanılabilir, ancak aynı imza beklenmektedir.
Örneğin, `(Qubit => Unit is Adj)` türünde bir işlem, `(Qubit => Unit)` türünde bir işlemin beklendiği her yerde kullanılabilir.

Q #, çağrılabilir dönüş türlerine göre değişkenle birlikte bulunur: `'A` bir türü döndüren çağrılabilir, aynı giriş türüne ve `'A` uyumlu olan bir sonuç türüne sahip çağrılabilir ile uyumludur.

S #, giriş türlerine göre değişken karşıtı: giriş, aynı sonuç türü ve `'A`ile uyumlu bir giriş türü olan çağrılabilir ile uyumlu olduğundan `'A` bir türü alan çağrılabilir.

Diğer bir deyişle, aşağıdaki tanımlar verilir:

```qsharp
operation Invertible (qs : Qubit[]) : Unit 
is Adj {...} 
operation Unitary (qs : Qubit[]) : Unit 
is Adj + Ctl {...} 

function ConjugateInvertibleWith (
   inner: (Qubit[] => Unit is Adj),
   outer : (Qubit[] => Unit is Adj))
: (Qubit[] => Unit is Adj) {...}

function ConjugateUnitaryWith (
   inner: (Qubit[] => Unit is Adj + Ctl),
   outer : (Qubit[] => Unit is Adj))
: (Qubit[] => Unit is Adj + Ctl) {...}
```

aşağıdakiler doğrudur:

- İşlem `ConjugateInvertibleWith`, `Invertible` veya `Unitary`bir `inner` bağımsız değişkeniyle çağrılabilir.
- İşlem `ConjugateUnitaryWith`, `Unitary``inner` bağımsız değişkeniyle çağrılabilir, ancak `Invertible`.
- `(Qubit[] => Unit is Adj + Ctl)` türünde bir değer `ConjugateInvertibleWith`döndürebilir.

> [!IMPORTANT]
> Q # 0,3, Kullanıcı tanımlı türlerin davranışında önemli bir farklılık sunar.

Kullanıcı tanımlı türler, alt tür yerine temel alınan türün Sarmalanan bir sürümü olarak değerlendirilir.
Bu, Kullanıcı tanımlı türün bir değerinin, temel alınan türden bir değerin beklenildiği durumlarda kullanılamaz olduğu anlamına gelir.

### <a name="functors"></a>Functorları

Q # ' daki bir functor, başka bir işlemden yeni bir işlem tanımlayan bir fabrikadır.
Funörler, yeni işlemin uygulamasını tanımlarken temel işlemin uygulamasına erişebilir.
Bu nedenle, funörler geleneksel daha yüksek düzey işlevlerden daha karmaşık işlevler gerçekleştirebilir.

Funörler, Q # tür sisteminde bir gösterimine sahip değildir. Bu nedenle, şu anda bunları bir değişkene bağlamak veya bağımsız değişken olarak geçirmek mümkün değildir. 

Komik bir ctor, bir işleme uygulanarak yeni bir işlem döndürerek kullanılır.
Örneğin, `Adjoint` functor `Y` işlemine uygulamanın sonucu olan işlem `Adjoint Y`olarak yazılmıştır.
Yeni işlem daha sonra başka bir işlem gibi çağrılabilir.
Bu nedenle, `Adjoint Y(q1)` yeni bir işlem oluşturmak için adjoint functor `Y` işlemine uygular ve bu yeni işlemi `q1`uygular.

Benzer şekilde, `Controlled X(controls, target)` yeni bir işlem oluşturmak için denetlenen functor `X` işlemine uygular ve bu yeni işlemi `controls` ve `target`uygular.

Q # içindeki iki standart komik `Adjoint` ve `Controlled`.

#### <a name="adjoint"></a>Adjoint

Hisse bilgi işlem ortamında, bir işlemin adjoint işlemi, işlemin karmaşık eşleniği olarak devrik bir işlemdir.
Bir Unitary işleci uygulayan işlemler için, adjoint işlemin tersidir.
Bir qubits kümesi üzerinde diğer Unitary işlemlerini bir dizi olarak çağıran basit bir işlem için, bu, ters sırada alt işlemlerin aynı qubits 'ler üzerinde bir arada uygulanarak, adjoint hesaplanmayabilir.

İşlem ifadesi verildiğinde, yeni bir işlem ifadesi `Adjoint` functor kullanılarak oluşturulabilir.
Örneğin, `Adjoint QFT` `QFT` işleminin adjoint değerini belirtir.
Yeni işlem, temel işlemle aynı imzaya ve türe sahip.
Özellikle de yeni işlem `Adjoint`sağlar ve yalnızca temel işlem olduysa `Controlled` izin verir.

Adjoint functor kendi tersidir; Yani, `Adjoint Adjoint Op` `Op`her zaman aynıdır.

#### <a name="controlled"></a>Tarafından

Bir işlemin denetlenen sürümü, yalnızca tüm denetim qubits 'in belirtilen durumda olması durumunda temel işlemi etkili bir şekilde uygulayan yeni bir işlemdir.
Denetim qubitleri üst konumundayken, temel işlem üst konumun uygun bölümüne doğru şekilde uygulanır.
Bu nedenle, denetimli işlemler genellikle entanglement oluşturmak için kullanılır.

Q # ' da, denetimli sürümler her zaman bir denetim qubit dizisi alır ve belirtilen durum her zaman denetim qubits 'in işlem (`PauliZ`) `One` durumunda $ \gre{1}$ ' a kadar olur.
Diğer durumlara dayalı olarak denetlemek, denetimli işlemden önce denetim qubits 'e uygun Unitary işlemini uygulayarak ve sonra, denetimli işlemden sonra Unitary işleminin evirimini uygulayarak elde edilebilir.
Örneğin, denetimli bir işlemden önce ve sonra bir denetim qubit 'e `X` işlemi uygulamak, bu qubit için `Zero` durumunda ($ \tus{0}$), işlemin denetimine neden olur; `H` işlemi ve sonrasında önce ve sonra,{0}{1}durum yerine-1 eigenvalue of Pauli X, $ \ket{-} \mathrel{: =} (\demet{2}-\tus`PauliZ`)/\sqrt `One` $ olan `PauliX` `One` durumunda bir denetim uygulayın.

İşlem ifadesi verildiğinde, yeni bir işlem ifadesi `Controlled` functor kullanılarak oluşturulabilir.
Yeni işlemin imzası, özgün işlemin imzasını temel alır.
Sonuç türü aynıdır, ancak giriş türü, ilk öğe olarak denetim qubit dizisini ve ikinci öğe olarak orijinal işlemin bağımsız değişkenlerini tutan bir qubit dizisi olan iki kayıt türüdür.
Yeni işlem `Controlled`destekler ve yalnızca özgün işlem olduysa `Adjoint` destekleyecektir.

Özgün işlem yalnızca tek bir bağımsız değişken alıyorsa, bu durumda tek demet denklik, burada yürütmeye gelir.
Örneğin, `Controlled X` `X` işleminin denetlenen sürümüdür.
`X` `(Qubit => Unit is Adj + Ctl)`türüne sahip `Controlled X` türü `((Qubit[], (Qubit)) => Unit is Adj + Ctl)`; tek kayıt düzeni denkliği nedeniyle bu `((Qubit[], Qubit) => Unit is Adj + Ctl)`aynıdır.

Temel işlem birkaç bağımsız değişken alıyorsa, bu işlemin denetlenen sürümünün ilgili bağımsız değişkenlerini, bir tanımlama grubu içine dönüştürmek için parantez içine almayı unutmayın.
Örneğin, `Controlled Rz` `Rz` işleminin denetlenen sürümüdür.
`Rz` `((Double, Qubit) => Unit is Adj + Ctl)`türüne sahip `Controlled Rz` `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)`türüne sahip.
Bu nedenle, `Controlled Rz(controls, (0.1, target))` geçerli bir `Controlled Rz` çağrısı olacaktır (`0.1, target`etrafında ayraçları aklınızda).

Başka bir örnek olarak, `CNOT(control, target)` `Controlled X([control], target)`olarak uygulanabilir. Bir hedefin 2 denetim qubits (CCNOT) ile denetlenmesi gerekiyorsa `Controlled X([control1, control2], target)` deyiminizi kullanabiliriz.

### <a name="examples"></a>Örnekler

Bir Q # işleminin bu örneği, [ölçüm](https://github.com/microsoft/Quantum/tree/master/samples/getting-started/measurement) örneğinden gelir. İşlemler içinde, `H` ve `X`gibi bu qubits üzerinde qubits ayırabiliriz ve hisse alma işlemleri kullanabilirsiniz:

```qsharp
/// # Summary
/// Prepares a state and measures it in the Pauli-Z basis.
operation MeasureOneQubit () : Result {
        mutable result = Zero;

        using (qubit = Qubit()) { // Allocate a qubit
            H(qubit);               // Use a quantum operation on that qubit

            set result = M(qubit);      // Measure the qubit

            if (result == One) {    // Reset the qubit so that it can be released
                X(qubit);
            }

            return result;
        }
 }
```

Bir işlevin bu örneği, [Phasetahmin](https://github.com/microsoft/Quantum/tree/master/samples/characterization/phase-estimation) örneğinden gelir. Yalnızca klasik kod içerir. Yukarıdaki örneğin aksine, qubits ayrılmadığından ve hisse alma işlemleri kullanılmamış olduğunu görebilirsiniz.


```qsharp
/// # Summary
/// Given two arrays, returns a new array that is the pointwise product
/// of each of the given arrays.
function MultiplyPointwise (left : Double[], right : Double[]) : Double[] {
    mutable product = new Double[Length(left)];

    for (idxElement in IndexRange(left)) {
        set product w/= idxElement <- left[idxElement] * right[idxElement];
    }
    return product;
}
```

Ayrıca, [Reversıblelogicsensıs](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/reversible-logic-synthesis) örneğinden Bu örnekte olduğu gibi, bir işlevin işleme için qubits 'e geçirilmesi de mümkündür. Qubits işlevine geçirilir ve işlemek için kullanılır, ancak hiç bir nokta, hiçbir noktadan böyle bir şekilde değiştirilir.

```qsharp
/// # Summary
/// Translate MCT masks into multiple-controlled Toffoli gates (with single
/// targets).
function GateMasksToToffoliGates (qubits : Qubit[], masks : MCMTMask[]) : MCTGate[] {

    mutable result = new MCTGate[0];
    let n = Length(qubits);

    for (i in 0 .. Length(masks) - 1) {
        let (controls, targets) = (masks[i])!;
        let controlBits = IntegerBits(controls, n);
        let targetBits = IntegerBits(targets, n);
        let cQubits = Subarray(controlBits, qubits);
        let tQubits = Subarray(targetBits, qubits);

        for (target in tQubits) {
            set result += [MCTGate(cQubits, target)];
        }
    }

    return result;
}
```
