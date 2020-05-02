---
title: 'Microsoft Q # Numerics kitaplığını kullanma'
description: Microsoft hisse türü kitaplığı 'nda bulunan türler ve işlemler hakkında bilgi edinin.
author: thomashaener
ms.author: thhaner
ms.date: 5/14/2019
ms.topic: article
uid: microsoft.quantum.numerics.usage
ms.openlocfilehash: 10d5675e0ef182211a38db4d09347b05afe109c3
ms.sourcegitcommit: db23885adb7ff76cbf8bd1160d401a4f0471e549
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/01/2020
ms.locfileid: "82677103"
---
# <a name="using-the-numerics-library"></a>Numerics kitaplığını kullanma

## <a name="overview"></a>Genel Bakış

Numerics kitaplığı üç bileşenden oluşur

1. Tamsayı kurban ve Karşılaştırıcılar ile **temel tamsayı aritmetiği**
1. Temel işlevlerin üstünde oluşturulan **üst düzey tamsayı işlevselliği** ; çarpma, bölme, Inversion vb. içerir.  işaretli ve işaretsiz tamsayılar için.
1. Sabit noktalı başlatma, toplama, çarpma, karşılıklı, polinom değerlendirmesi ve ölçüyle **sabit noktalı aritmetik işlevsellik** .

Bu bileşenlere tek `open` bir ifade kullanılarak erişilebilir:
```qsharp
open Microsoft.Quantum.Arithmetic;
```

## <a name="types"></a>Türler

Numerics kitaplığı aşağıdaki türleri destekler

1. **`LittleEndian`**: En az önemli bir `qArr : Qubit[]` bit belirten bir tamsayıyı `qArr[0]` temsil eden bir qubit dizisi.
1. **`SignedLittleEndian`**: İki öğesinin `LittleEndian` tamamlayıcısı içinde depolanan işaretli bir tamsayıyı temsil ettiğinden olduğu gibi.
1. **`FixedPoint`**: Bir qubit dizisi `qArr2 : Qubit[]` ve ikili nokta konumundan `pos`oluşan gerçek bir sayıyı temsil eder. Bu, ikili noktanın solundaki ikili basamak sayısını sayar. `qArr2`, ile `SignedLittleEndian`aynı şekilde depolanır.

## <a name="operations"></a>İşlemler

Yukarıdaki üç türden her biri için çeşitli işlemler mevcuttur:

1. **`LittleEndian`**
    - Toplama
    - Karşılaştırma
    - Çarpma
    - Karelerini alıp
    - Bölme (geri kalan)

1. **`SignedLittleEndian`**
    - Toplama
    - Karşılaştırma
    - INVERSION modül 2 ' nin tamamlayıcı
    - Çarpma
    - Karelerini alıp

1. **`FixedPoint`**
    - Klasik değerlere hazırlık/başlatma
    - Toplama (klasik sabit veya diğer hisse sabit noktası)
    - Karşılaştırma
    - Çarpma
    - Karelerini alıp
    - Çift ve tek işlevler için özelleşmede polinom değerlendirmesi
    - Karşılıklı (1/x)
    - Ölçüm (Klasik Çift)

Bu işlemlerin her biri için daha fazla bilgi ve ayrıntılı belgeler için [docs.Microsoft.com](https://docs.microsoft.com/quantum) adresindeki Q # kitaplığı başvuru belgelerine bakın.

## <a name="sample-integer-addition"></a>Örnek: tamsayı ekleme

Temel bir örnek olarak, $ $ \ ayraç x\tusi\mapsto \tusx\ket {x + y} $ $ işlemini, yani n-qubit Integer $x $ ve n-veya (n + 1)-qubit, $ (x + y) $ toplamına eşlendiği bir giriş olarak $y $ olduğunu bir işlem. $Y $ bir $n $-bit kasada depolanıyorsa, Sum 'un hesaplanmış mod $2 ^ n $ olduğunu unutmayın.

Bu işlem, hisse geliştirme setini kullanarak aşağıdaki gibi uygulanabilir:
```qsharp
operation TestMyAddition(xValue : Int, yValue : Int, n : Int) : Unit {
    using ((xQubits, yQubits) = (Qubit[n], Qubit[n]))
    {
        let x = LittleEndian(xQubits); // define bit order
        let y = LittleEndian(yQubits);
        
        ApplyXorInPlace(xValue, x); // initialize values
        ApplyXorInPlace(yValue, y);
        
        AddI(x, y); // perform addition x+y into y
        
        // ... (use the result)
    }
}
```

## <a name="sample-evaluating-smooth-functions"></a>Örnek: Düzgünleştir işlevlerini değerlendirme

$ \Sin (x) $ gibi kesintisiz işlevleri bir hisse bilgisayarında değerlendirmek için, $x $ 'nin hisse `FixedPoint` numarası olduğu, hisse geliştirme seti Numerics kitaplığı, işlemleri `EvaluatePolynomialFxP` ve `Evaluate[Even/Odd]PolynomialFxP`sunar.

Birincisi, `EvaluatePolynomialFxP`, $ $ P (x) = a_0 + a_1x + a_2x ^ 2 + \cnoktalar + a_dx ^ d, $ $ ($d $ *derecesini*gösterir) biçiminde bir polinom değerini değerlendirebilmenizi sağlar. Bunu yapmak `[a_0,..., a_d]` için, gerekli olan polinom katsayıları (türü `Double[]`), giriş `x : FixedPoint` ve çıkış `y : FixedPoint` (başlangıçta sıfır):
```qsharp
EvaluatePolynomialFxP([1.0, 2.0], x, y);
```
Sonuç, $P (x) = 1 + 2x $, içinde `yFxP`depolanacak.

İkinci, `EvaluateEvenPolynomialFxP`ve üçüncü, `EvaluateOddPolynomialFxP`sırasıyla, hatta ve tek işlevler için özelleştirilmiş çalışmalardır. Diğer bir deyişle, Çift/tek işlevi için $f (x) $ ve $ $ P_ {çift} (x) = a_0 + a_1 x ^ 2 + a_2 x ^ 4 + \cnoktalar + a_d x ^ {2D}, $ $ $f (x) $, sırasıyla $P _ {çift} (x) $ veya $P _ {tek} (x): = x\cdot P_ {çift} (x) $.
Q # içinde, bu iki durum şu şekilde işlenebilir:
```qsharp
EvaluateEvenPolynomialFxP([1.0, 2.0], x, y);
```
$P _ {çift} (x) = 1 + 2x ^ 2 $ olduğunu değerlendirir ve
```qsharp
EvaluateOddPolynomialFxP([1.0, 2.0], x, y);
```
$P _ {tek} (x) = x + 2x ^ 3 $ öğesini değerlendirir.

## <a name="more-samples"></a>Daha fazla örnek

[Ana örnekler deposunda](https://github.com/Microsoft/Quantum)daha fazla örnek bulabilirsiniz.

Başlamak için depoyu kopyalayın ve `Numerics` alt klasörü açın:

```bash
git clone https://github.com/Microsoft/Quantum.git
cd Quantum/Numerics
```

Ardından, `cd` örnek klasörlerden birine ve örneği ile çalıştırın

```bash
dotnet run
```
