---
uid: Microsoft.Quantum.Random.DrawCategorical
title: DrawCategorical işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawCategorical
qsharp.summary: Draws a random sample from a categorical distribution specified by a list of probablities.
ms.openlocfilehash: fdc5ae3a9341cb11e8fda129bdd030289b6c99c2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730959"
---
# <a name="drawcategorical-operation"></a>DrawCategorical işlemi

Ad alanı: [Microsoft. hisse. Random](xref:Microsoft.Quantum.Random)

Leyebilir [](https://nuget.org/packages/)


Bir olasılık listesi tarafından belirtilen kategorik bir dağılıdan rastgele bir örnek çizer.

```qsharp
operation DrawCategorical (probs : Double[]) : Int
```


## <a name="description"></a>Açıklama

Belirli bir dizini seçme olasılığı, bu dizindeki dizi öğesinin değeri ile orantılıdır.
Sıfıra eşit dizi öğeleri yok sayılır ve bunların dizinleri hiçbir şekilde döndürülmez. Herhangi bir dizi öğesi sıfırdan küçükse veya hiçbir dizi öğesi sıfırdan büyükse, işlem başarısız olur.

## <a name="input"></a>Giriş

### <a name="probs--double"></a>probs: [Double](xref:microsoft.quantum.lang-ref.double)[]

Kayan noktalı sayıların dizisi her bir dizini seçme olasılığa göre orantılıdır.



## <a name="output--int"></a>Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)

Olasılık $ \Pr (i) = p_i/\ sum_i p_i $ olan bir tamsayı $i $, burada $p _i $, $i $ TH öğesidir `probs` .

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Random. CategoricalDistribution](xref:Microsoft.Quantum.Random.CategoricalDistribution)