---
title: Numerics kitaplığını kullanma | Microsoft Docs
description: Numerics kitaplığını kullanma
author: thomashaener
ms.author: thhaner
ms.date: 5/14/2019
ms.topic: article
uid: microsoft.quantum.numerics.usage
ms.openlocfilehash: ca24ff60cd9ae5077c7f4bae0012fe1180d7e6d4
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76821040"
---
# <a name="using-the-numerics-library"></a>Numerics kitaplığını kullanma

## <a name="overview"></a>Genel Bakış

Numerics kitaplığı üç bileşenden oluşur

1. Tamsayı kurban ve Karşılaştırıcılar ile **temel tamsayı aritmetiği**
1. Temel işlevlerin üstünde oluşturulan **üst düzey tamsayı işlevselliği** ; çarpma, bölme, Inversion vb. içerir.  işaretli ve işaretsiz tamsayılar için.
1. Sabit noktalı başlatma, toplama, çarpma, karşılıklı, polinom değerlendirmesi ve ölçüyle **sabit noktalı aritmetik işlevsellik** .

Bu bileşenlere, tek bir `open` ekstresi kullanılarak erişilebilir:
```qsharp
open Microsoft.Quantum.Arithmetic;
```

## <a name="types"></a>Türler

Numerics kitaplığı aşağıdaki türleri destekler

1. **`LittleEndian`** : `qArr[0]` en az önemli biti gösterdiği bir tamsayıyı temsil eden bir qubit dizisi `qArr : Qubit[]`.
1. **`SignedLittleEndian`** : iki öğenin tamamlayıcısı içinde depolanan işaretli bir tamsayıyı temsil ettiğinden, `LittleEndian` aynı.
1. **`FixedPoint`** : bir qubit dizi `qArr2 : Qubit[]` ve ikili nokta `pos`konumundan oluşan gerçek bir sayıyı temsil eder. Bu, ikili noktanın solundaki ikili basamak sayısını sayar. `qArr2`, `SignedLittleEndian`ile aynı şekilde depolanır.

## <a name="operations"></a>Operations

Yukarıdaki üç türden her biri için çeşitli işlemler mevcuttur:

1. **`LittleEndian`**
    - Ek olarak
    - Karşılaştırma
    - Anda
    - Karelerini alıp
    - Bölme (geri kalan)

1. **`SignedLittleEndian`**
    - Ek olarak
    - Karşılaştırma
    - INVERSION modül 2 ' nin tamamlayıcı
    - Anda
    - Karelerini alıp

1. **`FixedPoint`**
    - Klasik değerlere hazırlık/başlatma
    - Toplama (klasik sabit veya diğer hisse sabit noktası)
    - Karşılaştırma
    - Anda
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
        x = LittleEndian(xQubits); // define bit order
        y = LittleEndian(yQubits);
        
        ApplyXorInPlace(xValue, x); // initialize values
        ApplyXorInPlace(yValue, y);
        
        AddI(x, y); // perform addition x+y into y
        
        // ... (use the result)
    }
}
```

## <a name="sample-evaluating-smooth-functions"></a>Örnek: Düzgünleştir işlevlerini değerlendirme

$ \Sin (x) $ gibi kesintisiz işlevleri bir hisse bilgisayarında değerlendirmek için, $x $ 'nin hisse `FixedPoint` numarası olduğu, hisse geliştirme seti Numerics kitaplığı, işlemler `EvaluatePolynomialFxP` ve `Evaluate[Even/Odd]PolynomialFxP`sağlar.

Birincisi, `EvaluatePolynomialFxP`, $ $ P (x) = a_0 + a_1x + a_2x ^ 2 + \cnoktalar + a_dx ^ d, $ $ biçiminde bir polinom değerini değerlendirmenize olanak tanır; burada $d $ *dereceyi*gösterir. Bunu yapmak için, gerekli olan polinom katsayıları `[a_0,..., a_d]` (`Double[]`türü), giriş `x : FixedPoint` ve çıkış `y : FixedPoint` (başlangıçta sıfır):
```qsharp
EvaluatePolynomialFxP([1.0, 2.0], x, y);
```
Sonuç, $P (x) = 1 + 2x $, `yFxP`depolanacak.

İkinci, `EvaluateEvenPolynomialFxP`ve üçüncü `EvaluateOddPolynomialFxP`, sırasıyla, hatta ve tek işlevler için özelleştirilmiş çalışmalardır. Diğer bir deyişle, Çift/tek işlevi için $f (x) $ ve $ $ P_ {çift} (x) = a_0 + a_1 x ^ 2 + a_2 x ^ 4 + \cnoktalar + a_d x ^ {2D}, $ $ $f (x) $, sırasıyla $P _ {çift} (x) $ veya $P _ {tek} (x): = x\cdot P_ {çift} (x) $.
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

Başlamak için depoyu kopyalayın ve `Numerics` alt klasörünü açın:

```bash
git clone https://github.com/Microsoft/Quantum.git
cd Quantum/Numerics
```

Ardından, örnek klasörlerden birine `cd` ve örneği kullanarak çalıştırın

```bash
dotnet run
```
