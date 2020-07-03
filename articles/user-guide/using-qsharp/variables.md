---
title: 'Soru-cevap #'
description: Fill açıklaması
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.variables
ms.openlocfilehash: 08301f408dcb2211ba25c582a5e5aa43310b714a
ms.sourcegitcommit: a3775921db1dc5c653c97b8fa8fe2c0ddd5261ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/02/2020
ms.locfileid: "85885281"
---
# <a name="variables-in-q"></a>Soru-cevap #

S #, değişebilir ve değişmez semboller ya da ifadelerle sınırlanan/atanan *değişkenler*arasında ayrım yapar.
Genellikle, derleyicinin daha iyi iyileştirmeler gerçekleştirmesini sağladığından, değişmez sembollerin kullanılması önerilir.

Bir bağlamanın sol tarafı bir sembol tanımlama grubu ve bir ifadenin sağ tarafından oluşur.

## <a name="immutable-variables"></a>Sabit değişkenler

Anahtar sözcüğünü kullanarak bir işlem veya işlev içinde yeniden kullanmak üzere Q # içinde herhangi bir türün değerini bir değişkene atayabilirsiniz `let` . 

Değişmez bir bağlama anahtar sözcükten `let` , ardından bir sembol veya sembol kümesi, eşittir işareti `=` , sembolleri bağlamak için bir ifade ve sondaki noktalı virgülden oluşur.

Örneğin:

```qsharp
let measurementOperator = [PauliX, PauliZ, PauliZ, PauliX, PauliI];
```

Bu, belirli bir Pauli işleçleri dizisini değişken adına (veya "Symbol") atar `measurementOperator` .

> [!NOTE]
> Önceki örnekte, deyimin sağ tarafındaki ifade `let` belirsiz olduğundan ve derleyici doğru türü kodcıdığı için, yeni değişkenin türünü açıkça belirtmeniz gerekmez. 

Kullanılarak tanımlanan değişkenler `let` *sabittir*, yani tanımladıktan sonra herhangi bir şekilde artık değiştiremezsiniz.
Bu, bir işlemin türevini uygulamak için değişkenlerin yeniden sıralanmasında davranan klasik mantığın iyileştirmesi dahil olmak üzere birkaç yararlı iyileştirmede izin verir `Adjoint` .

## <a name="mutable-variables"></a>Değişebilir değişkenler

İle bir değişken oluşturulmasına alternatif olarak `let` , anahtar sözcüğü, `mutable` anahtar sözcüğü kullanılarak ilk oluşturulduktan sonra *can* yeniden bağlanabilen kesilebilir bir değişken oluşturur `set` .

Bir deyimin parçası olarak belirtilen ve bağlantılı sembolleri `mutable` kodun ilerleyen kısımlarında bulunan farklı bir değere yeniden bağlayabilirsiniz. Bir sembol kodun ilerleyen kısımlarında yeniden bağlanmışsa, türü değişmez ve yeni bağlanan değer bu türle uyumlu olmalıdır.

### <a name="rebinding-of-mutable-symbols"></a>Kesilebilir sembolleri yeniden bağlama

Bir ifadeyi kullanarak kesilebilir bir değişkeni yeniden bağlayabilirsiniz `set` .
Bu tür bir yeniden bağlama anahtar sözcüğünden `set` , ardından bir sembol veya sembol tanımlama grubu, eşittir işareti `=` , sembolleri yeniden bağlamak için bir ifade ve sondaki noktalı virgülden oluşur.

Aşağıda, yeniden bağlama deyimleri tekniklerinin bazı örnekleri verilmiştir.

#### <a name="apply-and-reassign-statements"></a>Uygula ve yeniden ata deyimleri

Belirli bir tür `set` ifade, *Uygula ve-yeniden ata* deyimleri, sağ taraf bir ikili işlecin uygulamasından oluşuyorsa ve sonuç işlecin sol bağımsız değişkenine yeniden bağlanılacağından, birleştirme için kullanışlı bir yol sağlar. Örneğin,

```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter += 1;
    // ...
}
```
`counter`döngünün her yinelemesinde sayacın değerini artırır `for` . Önceki kod şu şekilde eşdeğerdir 

```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter = counter + 1;
    // ...
}
```

Benzer deyimler, sol taraftaki türün ifade türüyle eşleştiği tüm ikili işleçler için kullanılabilir. Bu deyimler, değerleri biriktirmek için kullanışlı bir yol sağlar.

Örneğin, `qubits` bir qubits 'in bir kaydı vardır:
```qsharp
mutable results = new Result[0];   // results is an empty array of type Result[]
for (q in qubits) {
    set results += [M(q)];         // concatenate the outcome from measuring q to the existing array
    // ...
}
...                                // results contains the measurement outcomes from the whole register
```

#### <a name="update-and-reassign-statements"></a>Güncelleştirme ve yeniden atama deyimleri

Sağ taraftaki [kopyalama ve güncelleştirme ifadeleri](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions) için benzer bir birleştirme bulunur.
Kullanıcı tanımlı türlerde ve *dizi öğelerinde* *adlandırılmış öğeler* için birlikte, *Update-ve-yeniden ata* deyimleri mevcuttur.  

```qsharp
newtype Complex = (Re : Double, Im : Double);

function ComplexSum(reals : Double[], ims : Double[]) : Complex[] {
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

Diziler söz konusu olduğunda, [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) Q # standart kitaplığı 'nda birçok yaygın dizi başlatma ve işleme ihtiyacı için gerekli araçlar sağlanır ve bu sayede dizi öğelerini ilk yerde güncelleştirmek zorunda kalmamak için yardımcı olur. 

Update-ve-yeniden ata deyimleri gerekirse bir alternatif sağlar:

```qsharp
operation GenerateRandomInts(max : Int, nSamples : Int) : Int[] {
    mutable samples = new Double[0];
    for (i in 1 .. nSamples) {
        set samples += [RandomInt(max)];
    }
    return samples;
}

operation SampleUniformDistrbution(nSamples : Int, nSteps : Int) : Double[] {
    let normalization = 1. / IntAsDouble(nSteps);
    mutable samples = GenerateRandomInts(nSteps, nSamples);
    
    for (i in IndexRange(samples) {
        let value = IntAsDouble(samples[i]);
        set samples w/= i <- normalization * value; // update-and-reassign statement
    }
}

```

' De sağlanan diziler için kitaplık araçlarını kullanarak, [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) Örneğin, `Pauli` dizindeki öğenin belirli bir değeri aldığı bir tür dizisi döndüren bir işlevi kolayca tanımlayabilir `i` `Pauli` ve diğer tüm girişler kimlik () olarak verilebilir `PauliI` .

Bu tür bir işlevin, elden çıkarmada araçların avantajlarından faydalanarak iki tanımı vardır.

```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    mutable pauliArray = new Pauli[length];             // initialize pauliArray of given length
    for (index in 0 .. length - 1) {                    // iterate over the integers in the length range
        set pauliArray w/= index <-                     // change the value at index to input pauli or PauliI
            index == location ? pauli | PauliI;         // cond. expression evaluating to pauli if index==location and PauliI if not
    }    
    return pauliArray;
}
```

Dizideki her dizin üzerinde yineleme yapmak ve bunu olarak veya verilen olarak ayarlamak yerine ' `PauliI` den ' ı `pauli` kullanarak `ConstantArray` [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) bir tür dizisi oluşturabilir `PauliI` ve sonra dizinde belirli bir değeri değiştirdiğiniz bir kopya ve güncelleştirme ifadesi döndürebilirsiniz `location` :

```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    return ConstantArray(length, PauliI) w/ location <- pauli;
}
```

## <a name="tuple-deconstruction"></a>Demet oluşturmayı kaldırma

Tek bir değişken atamaya ek olarak, `let` `mutable` `set` bir [demet türünün](xref:microsoft.quantum.guide.types#tuple-types)içeriğini açmak için ve anahtar sözcüklerini ya da gibi başka herhangi bir bağlama yapısını kullanabilirsiniz.
Bu formun bir ataması, bu kayıt düzeninin öğelerini *parçalara ayırmayı* kabul edilir.

Bağlamanın sağ tarafı bir tanımlama grubu ise, bu kayıt kümesini atama sırasında oluşturabilirsiniz.
Bu tür ayrıştırmaları iç içe diziler içerebilir ve sağ taraftaki tanımlama grubunun şekli sembol tanımlama grubu şekli ile uyumlu olduğu sürece herhangi bir tam veya kısmi ayrıştırma geçerlidir.

Örneğin:

```qsharp
let (i, f) = (5, 0.1); // i is bound to 5 and f to 0.1
mutable (a, (_, b)) = (1, (2, 3)); // a is bound to 1, b is bound to 3
mutable (x, y) = ((1, 2), [3, 4]); // x is bound to (1,2), y is bound to [3,4]
set (x, _, y) = ((5, 6), 7, [8]);  // x is rebound to (5,6), y is rebound to [8]
let (r1, r2) = MeasureTwice(q1, PauliX, q2, PauliY);
```

## <a name="binding-scopes"></a>Kapsamları bağlama

Genel olarak, sembol bağlamaları kapsam dışına çıkar ve içinde oluştuğu deyim bloğunun sonunda çalışır duruma gelir.
Bu kuralın iki özel durumu vardır:

- Bir döngünün döngü değişkeninin bağlaması, `for` for döngüsünün gövdesinden, ancak döngünün sonundan sonra değil.
- Bir döngünün üç bölümü `repeat` / `until` (gövde, test ve düzeltme) tek bir kapsam gibi davranır, bu nedenle gövdede bağlanan semboller testte ve düzeltmede kullanılabilir.

Her iki döngü türü için, döngüden geçen her bir geçiş kendi kapsamında çalışır, bu nedenle önceki bir geçişte bağlamalar daha sonraki bir geçişte kullanılamaz.
Bu döngüler hakkında daha fazla bilgi için bkz. [Denetim akışı](xref:microsoft.quantum.guide.controlflow).

İç bloklar, dış bloklarında sembol bağlamalarını miras alır.
Her blok için yalnızca bir sembol bağlayabilirsiniz; kapsam içindeki başka bir sembolle aynı ada sahip bir sembol tanımlamak geçersizdir ("gölgeleme" yoktur).
Aşağıdaki diziler geçerlidir:

```qsharp
if (a == b) {
    ...
    let n = 5;
    ...             // n is 5
}
let n = 8;
...                 // n is 8
```

ve

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
...                 // n is not bound to a value
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

## <a name="next-steps"></a>Sonraki adımlar

Q # içinde [qubits Ile çalışma](xref:microsoft.quantum.guide.qubits) hakkında bilgi edinin.