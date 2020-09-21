---
title: İçindeki denetim akışı Q#
description: Döngüler, koşullar, vb.
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.controlflow
no-loc:
- Q#
- $$v
ms.openlocfilehash: e8c873868d6f697fc90b23a38c11f35e46b40c4f
ms.sourcegitcommit: 8256ff463eb9319f1933820a36c0838cf1e024e8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2020
ms.locfileid: "90759671"
---
# <a name="control-flow-in-no-locq"></a>İçindeki denetim akışı Q#

Bir işlem veya işlev içinde, her bir ifade, diğer genel zorunlu klasik dillere benzer şekilde sırayla çalışır.
Ancak, denetim akışını üç farklı şekilde değiştirebilirsiniz:

* `if` deyimler
* `for` lerin
* `repeat-until-success` lerin

`if`Ve `for` Denetim akışı yapıları, çoğu klasik programlama diline tanıdık bir anlamda devam ediyor. [`Repeat-until-success`](#repeat-until-success-loop) döngüler Bu makalenin ilerleyen kısımlarında ele alınmıştır.

Daha önemlisi, `for` döngüler ve `if` deyimler, [özelleştirilmiş oluşturmaları](xref:microsoft.quantum.guide.operationsfunctions) otomatik olarak oluşturulan işlemlerde kullanılabilir. Bu senaryoda, bir döngünün adjoint `for` yönü tersine çevirir ve her yinelemenin adjoint değerini alır.
Bu eylem, "ayakkabılar-ve-SOCKS" ilkesini izler: SOCKS 'yi almayı geri almak istiyorsanız, sonra da sholer ' i ve sonra da 

## <a name="if-else-if-else"></a>If, else-if, Else

`if`İfade koşullu yürütmeyi destekler.
Anahtar sözcükten `if` , parantez içindeki bir Boole ifadesiyle ve bir deyim bloğundan ( _then_ bloğu) oluşur.
İsteğe bağlı olarak, her biri anahtar sözcüğü `elif` , parantez içindeki bir Boole ifadesini ve bir deyim bloğunu ( _Else-If_ bloğu) içeren herhangi bir sayıda Else-If yan tümcesi izleyebilir.
Son olarak, deyimi isteğe bağlı olarak `else` başka bir ifade bloğunun ( _Else_ bloğu) gelen anahtar sözcükten oluşan bir else yan tümcesi ile bitebileceğiniz anlamına gelir.

`if`Koşul değerlendirilir ve *true*ise blok çalıştırılır. *then*
Koşul *yanlışsa*, ilk else-if koşulu değerlendirilir; Bu doğruysa, *Else-If* bloğu çalıştırılır.
Aksi takdirde, ikinci Else-If bloğu değerlendirilir ve ardından, doğru bir koşula sahip bir yan tümce ile karşılaşılana ya da başka bir else-if yan tümcesi bulunmadığından, üçüncü ve bu şekilde devam eder.
*Eğer özgün If* koşulu ve tüm else-if yan tümceleri *yanlış*olarak değerlendirilmişse, varsa *Else* bloğu çalıştırılır.

Hangi bloğun çalıştığını, kendi kapsamında çalıştığını unutmayın.
Bir, veya bloğunun içinde yapılan bağlamalar, `if` `elif` `else` blok bittikten sonra görünür değildir.

Örneğin,

```qsharp
if (result == One) {
    X(target);
    let n = 1;
    // n is bound
} 
// n is not bound
```
veya
```qsharp
if (i == 1) {
    X(target);
    let n = 1;
} elif (i == 2) {
    Y(target);
    let m = n + 1; // would cause an error, because n is no longer bound
} else {
    Z(target);
}
```

## <a name="for-loop"></a>for döngüsü

`for`İfade, bir tamsayı aralığı veya dizi üzerinde yinelemeyi destekler.
Deyimi, anahtar sözcüğünden `for` , ardından bir sembol veya sembol tanımlama anahtarından, anahtar sözcükten `in` ve Type `Range` ya da Array, All parantez içinde ve bir deyim bloğundan oluşur.

İfade bloğu (Döngünün gövdesi), Aralık veya dizideki her bir değere bağlanacak şekilde, tanımlanmış sembol (döngü değişkeni) ile tekrar tekrar çalışır.
Aralık ifadesi boş bir aralığa veya diziye değerlendirilirse, gövdenin hiç çalıştırılmadığını unutmayın.
İfade, döngü girilmeden önce tam olarak değerlendirilir ve döngü yürütülürken değişmez.

Döngü değişkeni, döngü gövdesinin her girişinde bağlanır ve gövdenin sonunda ilişkisiz olur.
For döngüsü tamamlandıktan sonra döngü değişkeni bağlanmadı.
Döngü değişkeninin bağlaması sabittir ve diğer değişken bağlamalarıyla aynı kurallara uyar. 

Bu örneklerde, `qubits` qubits 'in bir yazmacı olur (örneğin, türü `Qubit[]` ), 

```qsharp
// ...
for (qubit in qubits) {  // iterate over each qubit value in the array qubits
    H(qubit);
}
// 'qubit' is no longer bound

mutable results = new (Int, Results)[Length(qubits)];
for (index in 0 .. Length(qubits) - 1) {  // iterates over the integers in the Range 0 .. (Length(qubits) - 1)
    set results w/= index <- (index, M(qubits[index])); // measure each qubit, updates the tuple value in the results array that at index 
}

mutable accumulated = 0;
for ((index, measured) in results) { // iterates over the tuple values in results
    if (measured == One) {
        set accumulated += 1 <<< index;
    }
}
```

Sonunda aritmetik-SHIFT-Left ikili işlecini kullandığımızda olduğunu unutmayın `<<<` . Daha fazla bilgi için bkz. [sayısal ifadeler](xref:microsoft.quantum.guide.expressions#numeric-expressions).

## <a name="repeat-until-success-loop"></a>Yineleme-Until-başarılı döngüsü

Q#Dil klasik denetim akışının, qubits 'in ölçüleriyle sonuçlanmasına bağlıdır.
Bu özellik, sırasıyla, birimlere uygulama için hesaplama maliyetini azaltabilecekleri güçlü dayalı araçları uygulamaya olanak tanıyor.
Bunun örnekleri, içindeki *yineleme-başarılı* (Rus) desenlerdir Q# .
Bu RUS desenleri, temel kapıların bakımından *beklenen* düşük maliyetli dayalı programlarıdır; tahakkuk eden maliyet, gerçek çalıştırmaya ve çoklu olası Branch'in araya yerleştirmesine bağlıdır.

Yinele-başarılı (RUS) desenleri kolaylaştırmak için Q# yapıları destekler

```qsharp
repeat {
    // do stuff
}
until (expression)
fixup {
    // do other stuff
}
```

`expression`, türünde bir değer değerlendirilen geçerli bir ifadedir `Bool` .
Döngü gövdesi çalışır ve ardından koşul değerlendirilir.
Koşul doğru ise, ifade tamamlanır; Aksi takdirde, düzeltme çalışır ve ifade, döngü gövdesiyle başlayarak yeniden çalışır.

Bir RUS döngüsünün üç bölümü (gövde, test ve düzeltme) *her yineleme için*tek bir kapsam olarak değerlendirilir, böylece gövdede bağlanan semboller hem testte hem de düzeltmede kullanılabilir.
Ancak, düzeltme yürütme işlemini tamamlamak, deyimin kapsamını sonlandırır, böylece gövde veya Düzeltme sırasında yapılan simge bağlamaları sonraki tekrarlarda kullanılamaz.

Ayrıca, `fixup` ifade genellikle yararlı olur ancak her zaman gerekli değildir.
Gerekli olmadığı durumlarda, yapı

```qsharp
repeat {
    // do stuff
}
until (expression);
```

aynı zamanda geçerli bir RUS örüntü.

Daha fazla örnek ve ayrıntı için, bu makaledeki [Yinele-Until-Success örneklerine](#repeat-until-success-examples) bakın.

> [!TIP]   
> İşlevler içinde yineleme-başarılı döngüleri kullanmaktan kaçının. İşlevler içinde karşılık gelen işlevleri sağlamak için *while* döngüleri kullanın. 

## <a name="while-loop"></a>while döngüsü

Yinele-Success desenlerinin çok hisse özgü bir connotation vardır. Bu değerler, ' de adanmış dil yapısı olan belirli hisse algoritmaları sınıflarında yaygın olarak kullanılırlar Q# . Bununla birlikte, bir koşula göre kesintiye uğratır ve derleme zamanında yürütme uzunluğu bilinmiyor olan döngüler, bir hisse çalışma zamanında belirli bir ilgiyle işlenir. Ancak, işlevleri içindeki kullanımları sorunlu değildir çünkü bu döngüler yalnızca geleneksel (hisse olmayan) donanımda çalışan bir kod içerir. 

Q#Bu nedenle, yalnızca işlevler içindeki while döngülerinin kullanımını destekler. Bir `while` deyim, anahtar sözcükten `while` , parantez içinde Boole ifadesiyle ve deyim bloğundan oluşur.
Koşul bloğu (Döngünün gövdesi), koşulun değerlendirildiği sürece çalışır `true` .

```qsharp
// ...
mutable (item, index) = (-1, 0);
while (index < Length(arr) && item < 0) { 
    set item = arr[index];
    set index += 1;
}
```

## <a name="return-statement"></a>Return Deyimi

Return ifadesinde bir işlemin veya işlevin çalışması sona erer ve çağırana bir değer döndürülür.
Anahtar sözcüğünden `return` , ardından uygun türdeki bir ifadeye ve bir sonlandırma noktalı virgülden oluşur.

Örneğin,
```qsharp
return 1;
```
veya
```qsharp
return (results, qubits);
```

* Boş bir tanımlama grubu döndüren çağrılabilir, `()` Return ifadesine gerek yoktur.
* İşlemden veya işlevden erken çıkış belirtmek için öğesini kullanın `return ();` .
Diğer herhangi bir tür döndüren callables, son Return ifadesine gerek duyar.
* Bir işlem içinde en fazla dönüş deyimi sayısı yoktur.
Deyimler bir blok içindeki Return deyimini izif ise derleyici bir uyarı verebilir.

   
## <a name="fail-statement"></a>Fail bildirisi

Fail deyimleri bir işlemin çalıştırılmasını sonlandırır ve çağırana bir hata değeri döndürür.
Anahtar sözcüğünden `fail` ve ardından bir dize ve Sonlandırıcı noktalı virgülden oluşur.
İfade, hata iletisi olarak, dizeyi klasik sürücüye döndürür.

İşlemdeki başarısızlık deyimlerinin sayısı üzerinde hiçbir kısıtlama yoktur.
Deyimler bir blok içindeki bir fail deyimini izif ise derleyici bir uyarı verebilir.

Örneğin,

```qsharp
fail $"Impossible state reached";
```
ya da, [enterpolasyonlu dizeleri](xref:microsoft.quantum.guide.expressions#interpolated-strings)kullanarak
```qsharp
fail $"Syndrome {syn} is incorrect";
```

## <a name="repeat-until-success-examples"></a>Yineleme-Until-Success örnekleri

### <a name="rus-pattern-for-single-qubit-rotation-about-an-irrational-axis"></a>Irrational Axis hakkında tek qubit döndürme için RUS stili 

Tipik bir kullanım durumunda aşağıdaki Q# işlem, {5} Bloch Sphere üzerinde $ (I + 2ı Z)/\sqrt $ bir ırrational ekseninin etrafında bir döndürme uygular. Uygulama, bilinen bir RUS modelini kullanır:

```qsharp
operation ApplyVRotationUsingRUS(qubit : Qubit) : Unit {
    using (controls = Qubit[2]) {
        ApplyToEachA(H, controls);
        mutable finished = false;
        repeat {
            Controlled X(controls, qubit);
            S(qubit);
            Controlled X(controls, qubit);
            Z(qubit);
        }
        until (finished)
        fixup {
            if (MeasureIfAllQubitsAreZero(controls, PauliX)) {
                set finished = true;
            }
        }
    }
}
```

### <a name="rus-loop-with-a-mutable-variable-in-scope"></a>Kapsam içinde kesilebilir değişkenle birlikte RUS döngüsü

Bu örnek, `finished` Tüm tekrarlama-Until-düzeltme döngüsünün kapsamı içinde olan ve düzeltme adımında güncelleştirildikten sonra başlatılan, kesilebilir değişken kullanımını gösterir.

```qsharp
mutable iter = 1;
repeat {
    ProbabilisticCircuit(qubits);
    let success = ComputeSuccessIndicator(qubits);
}
until (success || iter > maxIter)
fixup {
    iter += 1;
    ComputeCorrection(qubits);
}
```

### <a name="rus-without-fixup"></a>Şu olmadan RUS `fixup`

Bu örnekte, düzeltme adımı olmadan bir RUS döngüsü gösterilmektedir. Kod, {5} ve kapılarını kullanarak önemli bir döndürme kapısı uygulayan $V _3 = (\cıvalation+ 2 ı Z)/\sqrt $ olan bir dayalı devresi `H` `T` .
Döngü, ortalama $ \frac $ tekrarları içinde sona erer {8} {5} .
Daha fazla ayrıntı için bkz. [*yineleme-Until-başarılı: tek qubit unityalarının belirleyici olmayan ayrıştırma*](https://arxiv.org/abs/1311.1074) (paetznick ve svore, 2014).

```qsharp
using (qubit = Qubit()) {
    repeat {
        H(qubit);
        T(qubit);
        CNOT(target, qubit);
        H(qubit);
        Adjoint T(qubit);
        H(qubit);
        T(qubit);
        H(qubit);
        CNOT(target, qubit);
        T(qubit);
        Z(target);
        H(qubit);
        let result = M(qubit);
    } until (result == Zero);
}
```

### <a name="rus-to-prepare-a-quantum-state"></a>Ru bir hisse durumu hazırlamak için

Son olarak, {1} {3} {2} {0} $ \ket{+} $ durumundan başlayarak bir hisse durumu $ \frac {\sqrt} \left (\sqrt \ Tus+ {1} \tus\right) $ hazırlamak için bir Rus deseninin örneği aşağıda verilmiştir.

Bu işlemde gösterilen Notable programlama özellikleri şunlardır:

* Döngünün daha karmaşık bir `fixup` parçası olan ve bu da hisse işlemleri içerir. 
* `AssertMeasurementProbability`Programın belirtilen belirli noktalarda hisse miktarını ölçme olasılığını belirlemek için deyimlerin kullanılması.

Ve işlemleri hakkında daha fazla bilgi için [`AssertMeasurement`](xref:microsoft.quantum.diagnostics.assertmeasurement) [`AssertMeasurementProbability`](xref:microsoft.quantum.diagnostics.assertmeasurementprobability) bkz. [test ve hata ayıklama](xref:microsoft.quantum.guide.testingdebugging).

```qsharp
operation PrepareStateUsingRUS(target : Qubit) : Unit {
    using (auxiliary = Qubit()) {
        H(auxiliary);
        repeat {
            // We expect the target and auxiliary qubits to each be in
            // the |+> state.
            AssertMeasurementProbability(
                [PauliX], [target], Zero, 1.0,
                "target qubit should be in the |+> state", 1e-10 );
            AssertMeasurementProbability(
                [PauliX], [auxiliary], Zero, 1.0,
                "auxiliary qubit should be in the |+> state", 1e-10 );

            Adjoint T(auxiliary);
            CNOT(target, auxiliary);
            T(auxiliary);

            // The probability of measuring |+> state on the auxiliary qubit
            // is 3/4.
            AssertMeasurementProbability(
                [PauliX], [auxiliary], Zero, 3. / 4.,
                "Error: the probability to measure |+> in the first
                auxiliary must be 3/4",
                1e-10);

            // If we get the measurement outcome Zero, we prepare the
            // required state.
            let outcome = Measure([PauliX], [auxiliary]);
        }
        until (outcome == Zero)
        fixup {
            // Bring the auxiliary and target qubits back to |+> state.
            if (outcome == One) {
                Z(auxiliary);
                X(target);
                H(target);
            }
        }
        // Return the auxiliary qubit back to the Zero state.
        H(auxiliary);
    }
}
```

Daha fazla bilgi için bkz. [Standart kitaplıkla birlikte sunulan birim testi örneği](https://github.com/microsoft/Quantum/blob/main/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs):

## <a name="next-steps"></a>Sonraki adımlar

' De [test ve hata ayıklama](xref:microsoft.quantum.guide.testingdebugging) hakkında bilgi edinin Q# .
