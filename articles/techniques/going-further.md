---
title: 'S # teknik-daha fazla | Microsoft Docs'
description: 'S # teknik-daha fazla'
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: c079364f8808304e0132fa2a4226cd6400e81339
ms.sourcegitcommit: 27c9bf1aae923527aa5adeaee073cb27d35c0ca1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74863155"
---
# <a name="going-further"></a>Daha fazla #

Artık soru-cevap programlarının soru-cevap olarak nasıl yazılacağını gördüğünüze göre, bu bölüm ileride yararlı olması için daha fazla gelişmiş konu sunarak daha fazla bilgi edinilerek devam ediyor.


## <a name="generic-operations-and-functions"></a>Genel Işlemler ve Işlevler ##

> [!TIP]
> Bu bölümde, diğer dillerdeki [genel C#türler ](https://docs.microsoft.com/dotnet/csharp/programming-guide/generics/introduction-to-generics) [, F# ](https://docs.microsoft.com/dotnet/fsharp/language-reference/generics/) [ C++ şablonlarda, şablonlar](https://docs.microsoft.com/cpp/cpp/templates-cpp)veya diğer dillerde metaprogramlamaya benzer yaklaşımlar içeren bazı temel benzerlik varsayılmaktadır.

Tanımlamak isteyebileceğiniz birçok işlev ve işlem, kendi giriş türlerine gerçekten büyük ölçüde güvenmiyor, ancak bunun yerine yalnızca başka bir işlev veya işlem aracılığıyla türlerini örtülü olarak kullanın.
Örneğin, yaygın olarak kullanılan *harita* kavramını birçok işlevsel dilde değerlendirin. $f (x) $ işlevi ve $\{x_1, x_2, \noktalar, x_n\}$, Map bir değer koleksiyonu verildiğinde, <\{f (x_1), f (x_2), \noktalar, f (x_n)\}$ gibi yeni bir koleksiyon döndürür.
Bunu Q # ' da uygulamak için, bu işlevlerden faydalanabilir.
İhtiyaç duyduğumuz türleri anlarken, bir yer tutucu olarak ★ kullanarak `Map`hızlı bir örneğini yazalım.

```qsharp
function Map(fn : ★ -> ★, values : ★[]) : ★[] {
    mutable mappedValues = new ★[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

Bu işlev, yaptığımız gerçek türler dikkate alınmaz.
Örneğin, tamsayılardan Paulis 'e yapılan bir harita, kayan noktalı sayıların dizelerdeki eşlemesiyle çok benzer şekilde görünür:

```qsharp
function MapIntsToPaulis(fn : Int -> Pauli, values : Int[]) : Pauli[] {
    mutable mappedValues = new Pauli[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}

function MapDoublesToStrings(fn : Double -> String, values : Double[]) : String[] {
    mutable mappedValues = new String[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

Prensibi, karşılaştiğimiz her tür çifti için `Map` bir sürümünü yazalım, ancak bu çok sayıda zorluklar sunarız.
Örneğin, `Map`bir hata bulduk, bu durumda düzeltilmesinin tüm `Map`sürümlerinde tek bir şekilde uygulandığından emin olunması gerekir.
Ayrıca, yeni bir tanımlama grubu veya UDT oluşturuyoruz, yeni tür ile birlikte çalışmak için yeni bir `Map` de oluşturmanız gerekir.
Bu, az sayıda işlev için daha fazla ve daha fazla `Map`işlev topladığımızda, bu tür bir izleme tablosu olsa da, yeni türleri tanıtma maliyeti oldukça kısa bir süre boyunca makul bir şekilde büyük hale gelir.

Bununla birlikte, bu zorluklar, derleyicinin farklı `Map` sürümlerinin birbirleriyle ilgili olduğunu tanıması için ihtiyaç duymadığımızda oluşur.
Etkin olarak, derleyicinin `Map` bir tür matematik işlevini Q # *türünden* q # işlevlerine kadar görmesini istiyoruz.
Bu kavram, işlevlerin ve işlemlerin *tür parametrelerine*ve bunların normal demet parametrelerine sahip olmasını sağlayarak şekillendirililir.
Yukarıdaki örneklerde, ilk durumda `Int, Pauli` tür parametrelerine sahip olarak `Map` düşünmek istiyoruz ve ikinci durumda `Double, String`.
Çoğu bölüm için, bu tür parametreleri normal türlermiş gibi kullanılabilir: dizileri ve tanımlama grupları oluşturmak, işlevleri ve işlemleri çağırmak ve sıradan ya da kesilebilir değişkenlere atamak için parametre türü değerlerini kullanıyoruz.

> [!NOTE]
> Dolaylı bağımlıların en büyük olması, bir Q # programının `Qubit` türünün yapısına doğrudan güvenebileceği, ancak bu tür türleri diğer işlemlere ve işlevlere geçirmesi **gereken** qubitlerdir.

Yukarıdaki örneğe dönerek, bir tane olmak üzere tür parametrelerine sahip olmak için `Map` gerektiğini ve bir diğeri de `fn`çıktıyı temsil edecek şekilde `fn`.
Q # dilinde, bu, bildiriminde bir işlev veya işlemin adından sonra ve her tür parametresini listeleyerek açılı ayraç (brakets $ \bratus{}$! değil `<>`) eklenerek yazılır.
Her tür parametresinin adı, bir tür parametresi olduğunu ve sıradan bir tür ( *somut* tür olarak da bilinir) olmadığını belirten bir Tick `'`ile başlamalıdır.
`Map`için şunu yazın:

```qsharp
function Map<'Input, 'Output>(fn : 'Input -> 'Output, values : 'Input[]) : 'Output {
    mutable mappedValues = new 'Output[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

`Map<'Input, 'Output>` tanımının, daha önce yazdığımız sürümlere çok benzediğini unutmayın.
Tek fark, derleyicinin `Map` `'Input` ve `'Output` ne olduğunu doğrudan belirtmediğimiz, ancak bunları `fn`aracılığıyla dolaylı olarak kullanarak herhangi iki tür için nasıl çalıştığına dair kesin olarak bilgi sahibi veriyoruz.
Bu şekilde `Map<'Input, 'Output>` tanımladıktan sonra, bu işlemi sıradan bir fonksiyonmuş gibi çağırabiliriz:

```qsharp
// Represent Z₀ Z₁ X₂ Y₃ as a list of ints.
let ints = [3, 3, 1, 2];
// Here, we assume IntToPauli : Int -> Pauli
// looks up PauliI by 0, PauliX by 1, so forth.
let paulis = Map(IntToPauli, ints);
```

> [!TIP]
> Genel işlevler ve işlemler yazmak, "kayıt düzeni-Out" ın Q # işlevleri ve işlemlerini düşünmek için çok faydalı bir yoldur.
> Her işlev tam olarak bir giriş yaptığından ve tam olarak bir çıkış döndürdüğünden, `'T -> 'U` türünde bir giriş *herhangi* bir Q # işleviyle eşleşir.
> Benzer şekilde, herhangi bir işlem `'T => 'U`türünde bir girişe geçirilebilir.

İkinci bir örnek olarak, iki diğer işlevin birleşimini döndüren bir işlev yazma sınamasını göz önünde bulundurun:

```qsharp
function ComposeImpl(outerFn : (B -> C), innerFn : (A -> B), input : A) : C {
    return outerFn(innerFn(input));
}

function Compose(outerFn : (B -> C), innerFn : (A -> B)) : (A -> C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

Burada, tam olarak hangi `A`, `B`ve `C` olduğunu belirtmemiz gerekir. bu nedenle, yeni `Compose` işlevimizin yardımcı programını ciddi ölçüde kısıtlar.
Tüm `Compose`, yalnızca `A`, `B`ve `C` `innerFn` ve `outerFn`*aracılığıyla* bağlıdır.
Alternatif olarak *, `A`,* `B`ve `C`için çalıştığını belirten `Compose` tür parametreleri ekleyebiliyoruz, böylece bu parametreler `innerFn` ve `outerFn`tarafından beklenen olanlarla eşleşir.

```qsharp
function ComposeImpl<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B), input : 'A) : 'C {
    return outerFn(innerFn(input));
}

function Compose<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B)) : ('A -> 'C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

Q # standart kitaplıkları, daha yüksek sıralı denetim akışı hızlı bir şekilde daha kolay hale getirmek için tür parametreli işlem ve işlev aralığı sağlar.
Bunlar, [Q # standart kitaplığı kılavuzunda](xref:microsoft.quantum.libraries.standard.intro)daha ayrıntılı olarak ele alınmıştır.

## <a name="borrowing-qubits"></a>Ödünç alma qubit ##

Ödünç alma mekanizması, bir hesaplama sırasında karalama alanı olarak kullanılabilecek qubits ayrılmasına izin verir. Bu qubits genellikle temiz bir durumda değildir, yani $ \ket{0}$ gibi bilinen bir durumda başlatılmazlar. Ayrıca, durumu bilinmediği için "kirli" qubit "de konuşur ve hatta hisse bilgisayar belleğinin diğer bölümleriyle de bir arada olabilir. Kirli qubits 'in bilinen kullanım durumları arasında, yalnızca çok az sayıda qubit ve incrementers uygulaması gerektiren çok kontrollü CNOT kapıları olan uygulamalardır.

Canon 'de, aşağıda tanımlanan işlev `MultiControlledXBorrow` gibi `borrowing` anahtar sözcüğünü kullanan örnekler vardır.
`controls`, bir `X` işlemine eklenmesi gereken denetim qubits ' i alıyorsa, bu uygulama tarafından `Length(controls)-2` çok sayıda kirli ve bu şekilde bir genel bakış eklenir.

```qsharp
operation MultiControlledXBorrow ( controls : Qubit[] , target : Qubit ) : Unit
is Adj + Ctl {

    body (...) {
        ... // skipping some case handling here
        let numberOfDirtyQubits = numberOfControls - 2;
        borrowing( dirtyQubits = Qubit[ numberOfDirtyQubits ] ) {

            let allQubits = [ target ] + dirtyQubits + controls;
            let lastDirtyQubit = numberOfDirtyQubits;
            let totalNumberOfQubits = Length(allQubits);

            let outerOperation1 = 
                CCNOTByIndexLadder(
                    numberOfDirtyQubits + 1, 1, 0, numberOfDirtyQubits , _ );
            
            let innerOperation = 
                CCNOTByIndex(
                    totalNumberOfQubits - 1, totalNumberOfQubits - 2, lastDirtyQubit, _ );
            
            WithA(outerOperation1, innerOperation, allQubits);
            
            let outerOperation2 = 
                CCNOTByIndexLadder(
                    numberOfDirtyQubits + 2, 2, 1, numberOfDirtyQubits - 1 , _ );
            
            WithA(outerOperation2, innerOperation, allQubits);
        }
    }

    controlled(extraControls, ...) {
        MultiControlledXBorrow( extraControls + controls, target );
    }
}
```

`With`---Combinator ' nin, adjoint 'i destekleyen işlemler için geçerli olan `WithA`---, bu örnekte, `With` içeren yapılara denetim ekleme ve yalnızca denetimi iç işleme yayar. İşlemin `body` ek olarak, işlemin `controlled` gövdesinin bir `controlled auto` bildirimine yeniden eklemek yerine açıkça sağlandığını daha fazla unutmayın. Bunun nedeni, her bir ve `body`her bir kapıya denetim eklemeye kıyasla yararlı olan daha fazla denetimi nasıl kolayca ekleyebileceğinizi biliyoruz. 

Bu kodu, `using` mekanizması kullanılarak birkaç temiz qubit kullanan, çarpma denetimli `X` işlemi uygulama amacını elde eden başka bir Canon işlevi `MultiControlledXClean` karşılaştırmak için kullanılır. 
