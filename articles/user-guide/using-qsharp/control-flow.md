---
title: 'Q içindeki denetim akışı #'
description: Döngüler, koşullar, vb.
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.controlflow
ms.openlocfilehash: c534e016fcb8b50e66c11ca29c253ba0512acc6e
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/15/2020
ms.locfileid: "83430960"
---
# <a name="control-flow-in-q"></a>Q içindeki denetim akışı #

Bir işlem veya işlev içinde her bir ifade, en sık kullanılan zorunlu klasik dillere benzer şekilde sırayla yürütülür.
Bu denetim akışı, ancak üç farklı şekilde değiştirilebilir:

- `if`deyimler
- `for`lerin
- `repeat`-`until`lerin

Son tartışmayı [aşağıda](#repeat-until-success-loop)daha ileri erteliyoruz.
`if` `for` Ancak denetim akışı yapıları, klasik programlama dillerinin çoğu için tanıdık bir anlata devam ediyor.

Daha önemlisi, `for` döngüler ve `if` deyimler, özelleştirilmiş oluşturmaları otomatik olarak oluşturulan işlemlerde bile kullanılabilir. Bu durumda, bir döngünün adjoint `for` yönü tersine çevirir ve her yinelemenin adeklerini alır.
Bu, "ayakkabılar-ve-SOCKS" ilkesini izler: Socks ' yi almayı geri almak istiyorsanız, ve ardından
Bu işlem, siz de daha az bir işlem yapmaya çalışır.

## <a name="if-else-if-else"></a>If, else-if, Else

`if`İfade koşullu yürütmeyi destekler.
Anahtar sözcüğü `if` , açık parantez `(` , Boole ifadesi, kapatma parantezi `)` ve deyim bloğu ( _then_ bloğu) oluşur.
Bu, her biri anahtar sözcüğü `elif` , bir açık parantez `(` , Boole ifadesi, kapatma parantezi `)` ve deyim bloğu ( _Else-If_ bloğu) içeren herhangi bir sayıda Else-If yan tümcesi tarafından izlenebilir.
Son olarak, deyimi isteğe bağlı olarak `else` başka bir ifade bloğunun ( _Else_ bloğu) gelen anahtar sözcükten oluşan bir else yan tümcesi ile bitebileceğiniz anlamına gelir.

`if`Koşul değerlendirilir ve true ise blok yürütülür.
Koşul yanlışsa, ilk else-if koşulu değerlendirilir; true ise, Else-If bloğu yürütülür.
Aksi takdirde, ikinci Else-If bloğu test edilir ve ardından üçüncü, vb. doğru bir koşula sahip bir yan tümce ile karşılaşılana ya da başka bir else-if yan tümcesi içermeyecek şekilde devam eder.
Özgün If koşulu ve tüm else-if yan tümceleri yanlış olarak değerlendirilmişse, varsa Else bloğu yürütülür.

Hangi bloğun yürütüldüğü, kendi kapsamında yürütüleceğini unutmayın.
Bir `if` , veya bloğunun içinde yapılan bağlamalar, `elif` `else` sonunda görünür değildir.

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

## <a name="for-loop"></a>For döngüsü

İfade, bir `for` tamsayı aralığı veya dizi üzerinde yinelemeyi destekler.
Deyimi, anahtar sözcüğünden, bir `for` Açık parantezden `(` , ardından bir sembol veya sembol tanımlama anahtarından, anahtar sözcükten `in` , bir tür veya diziye, bir `Range` kapatma parantezine `)` ve bir deyim bloğuna sahip.

İfade bloğu (Döngünün gövdesi), her bir değere veya dizideki her bir değere bağlantılı tanımlanmış simgeler (döngü değişkenleri) ile tekrar tekrar yürütülür.
Aralık ifadesi boş bir aralığa veya diziye değerlendirilirse, gövdenin hiç yürütülmeyeceğini unutmayın.
İfade, döngü girilmeden önce tam olarak değerlendirilir ve döngü yürütülürken değişmeyecektir.

Döngü değişkeni, her giriş gövdesine bağlanır ve gövdenin sonunda ilişkisiz olur.
Özellikle, for döngüsü tamamlandıktan sonra döngü değişkeni bağlantılı değildir.
Belirtilen sembol (ler) in bağlaması sabittir ve diğer değişken bağlamalarıyla aynı kurallara uyar. 

Bazı örnekler için, `qubits` qubits 'in bir yazmacı olur (örneğin `Qubit[]` , türü), 

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
Sonunda, ' nin aritmetik ve sol ikili işlecini kullandığımızda, `<<<` ayrıntıları [sayısal ifadelerde](xref:microsoft.quantum.guide.expressions#numeric-expressions) nerede olabileceğini unutmayın


## <a name="repeat-until-success-loop"></a>Yineleme-Until-başarılı döngüsü

Q # dili, mebitleri ölçmeye yönelik sonuçlara bağlı olarak klasik denetim akışına izin verir.
Bu özellik sırasıyla, birimlere uygulama için hesaplama maliyetini azaltabilecekleri güçlü dayalı araçları uygulamaya olanak tanıyor.
Örnek olarak, Q # içinde *Yinele-başarılı* (ru) desenleri uygulamak çok kolaydır.
Bu RUS desenleri, temel kapıların bakımından *beklenen* düşük maliyetli dayalı programlarıdır, ancak gerçek maliyetten gerçek bir çalıştırmaya ve çeşitli olası branchlerin gerçek bir aramasına bağlı olarak değişir.

Yinele-başarılı (RUS) desenleri kolaylaştırmak için, Q # yapıları destekler

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
Döngü gövdesi yürütülür ve ardından koşul değerlendirilir.
Koşul doğru ise, ifade tamamlanır; Aksi takdirde, düzeltme yürütülür ve ifade, döngü gövdesiyle başlayarak yeniden yürütülür.

Yineleme/Until döngüsünün (gövde, test ve düzeltme) üç bölümü *her yineleme için*tek bir kapsam olarak değerlendirilir, bu nedenle gövdede bağlanan semboller testte ve düzeltmede kullanılabilir.
Ancak, düzeltme yürütme işlemini tamamlamak deyimin kapsamını sonlandırır, böylece gövde veya Düzeltme sırasında yapılan simge bağlamaları sonraki tekrarlarda kullanılamaz.

Ayrıca, `fixup` ifade genellikle yararlı olur ancak her zaman gerekli değildir.
Gerekli olmadığı durumlarda, yapı
```qsharp
repeat {
    // do stuff
}
until (expression);
```
aynı zamanda geçerli bir RUS örüntü.

Bu sayfanın en altında, [Rus döngülerinin bazı örneklerini](#repeat-until-success-examples)sunuyoruz.

> [!TIP]   
> İşlevler içinde yineleme-başarılı döngüleri kullanmaktan kaçının. Karşılık gelen işlevler, işlevlerde döngüler sırasında sağlanır. 

## <a name="while-loop"></a>While döngüsü

Yinele-Success desenlerinin çok hisse özgü bir connotation vardır. Bu diller, belirli hisse algoritmaları sınıflarında yaygın olarak kullanılır. bu nedenle, Q # içinde adanmış dil yapısı. Ancak, bir koşula göre kesintiye uğratır ve bu nedenle derleme sırasında yürütme uzunluğunun bilinmediği, bir hisse çalışma zamanında belirli bir ele alınabilmesi gerekir. Diğer yandan işlevleri içindeki kullanımları sorunlu değildir, çünkü bunlar yalnızca geleneksel (hisse olmayan) donanımda yürütülecek kodu içerir. 

Q # bu nedenle, yalnızca işlevler içindeki while döngülerinin kullanımını destekler. Deyim, bir `while` `while` açık parantez `(` , bir koşul (yani Boolean ifadesi), bir kapatma parantezi `)` ve deyim bloğu oluşur.
İfade bloğu (Döngünün gövdesi), koşulun değerlendirildiği sürece yürütülür `true` .

```qsharp
// ...
mutable (item, index) = (-1, 0);
while (index < Length(arr) && item < 0) { 
    set item = arr[index];
    set index += 1;
}
```


## <a name="return-statement"></a>Return Deyimi

Return deyimleri bir işlemin veya işlevin yürütmesini sonlandırır ve çağırana bir değer döndürür.
Anahtar sözcüğünden `return` , ardından uygun türdeki bir ifadeye ve bir sonlandırma noktalı virgülden oluşur.

Boş bir tanımlama grubu döndüren çağrılabilir, `()` Return ifadesine gerek yoktur.
Erken çıkış istenirse `return ()` Bu durumda kullanılabilir.
Diğer herhangi bir tür döndüren callables, son Return ifadesine gerek duyar.

Bir işlem içinde en fazla dönüş deyimi sayısı yoktur.
Deyimler bir blok içindeki Return deyimini izif ise derleyici bir uyarı verebilir.

Örneğin,
```qsharp
return 1;
```
veya
```qsharp
return ();
```
veya
```qsharp
return (results, qubits);
```

## <a name="fail-statement"></a>Fail bildirisi

Fail deyimleri bir işlemin yürütülmesini sonlandırır ve çağırana bir hata değeri döndürür.
Anahtar sözcüğünden `fail` ve ardından bir dize ve Sonlandırıcı noktalı virgülden oluşur.
Dize, hata iletisi olarak klasik sürücüye döndürülür.

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

Tipik bir kullanım durumunda, aşağıdaki Q # işlemi Bloch Sphere üzerinde $ (I + 2i Z)/\sqrt $ bir ırrational Axis etrafında bir döndürme uygular {5} . Bu, bilinen bir RUS kalıbı kullanılarak gerçekleştirilir:

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

### <a name="rus-loop-with-mutable-variable-in-scope"></a>Kapsam içinde kesilebilir değişkenle birlikte RUS döngüsü

Bu örnek, `finished` tüm yineleme-sonu-düzeltme döngüsü kapsamında olan ve düzeltme adımında kullanılmadan önce başlatılan bir kesilebilir değişkeninin kullanımını gösterir.

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

### <a name="rus-without-fixup"></a>Şu olmadan RUS`fixup`

Örneğin, aşağıdaki kod, ve kapılarını kullanarak önemli bir döndürme kapısı uygulayan bir dayalı devresi $V _3 = (\cıvalation+ 2 ı Z)/\sqrt {5} $ `H` `T` .
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

Son olarak, {1} {3} {2} {0} $ \ket{+} $ durumundan başlayarak bir hisse durumu $ \frac {\sqrt} \left (\sqrt \ Tus+ {1} \tus\right) $ hazırlamak için bir Rus deseninin örneğini gösteririz.
Ayrıca bkz. [Standart kitaplıkla birlikte sunulan birim testi örneği](https://github.com/microsoft/Quantum/blob/master/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs):

```qsharp
operation PrepareStateUsingRUS(target : Qubit) : Unit {
    using (auxiliary = Qubit()) {
        H(auxiliary);
        repeat {
            // We expect the target and auxiliary qubits to each be in
            // the |+> state.
            AssertProb(
                [PauliX], [target], Zero, 1.0,
                "target qubit should be in the |+> state", 1e-10 );
            AssertProb(
                [PauliX], [auxiliary], Zero, 1.0,
                "auxiliary qubit should be in the |+> state", 1e-10 );

            Adjoint T(auxiliary);
            CNOT(target, auxiliary);
            T(auxiliary);

            // The probability of measuring |+> state on the auxiliary qubit
            // is 3/4.
            AssertProb(
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

Bu işlemde gösterilen önemli programlı özellikler, bu döngünün daha karmaşık bir `fixup` parçasıdır ve bu da, hisse ve `AssertProb` programdaki belirli noktalarda hisse durumu ölçme olasılığını belirlemek için deyimleri kullanır.
Ve işlemleri hakkında daha fazla bilgi için bkz. [test ve hata ayıklama](xref:microsoft.quantum.guide.testingdebugging) [`Assert`](xref:microsoft.quantum.intrinsic.assert) [`AssertProb`](xref:microsoft.quantum.intrinsic.assertprob) .


## <a name="whats-next"></a>Sırada Ne Var?
Soru-cevap [Ile test ve hata ayıklama](xref:microsoft.quantum.guide.testingdebugging) hakkında bilgi edinin.