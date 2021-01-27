---
uid: Microsoft.Quantum.Random.DrawCategorical
title: DrawCategorical işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawCategorical
qsharp.summary: Draws a random sample from a categorical distribution specified by a list of probablities.
ms.openlocfilehash: a9fe1b08e80abc65a5c4b803f0cb8a5e7a62759c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851162"
---
# <a name="drawcategorical-operation"></a>DrawCategorical işlemi

Ad alanı: [Microsoft. hisse. Random](xref:Microsoft.Quantum.Random)

Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Bir olasılık listesi tarafından belirtilen kategorik bir dağılıdan rastgele bir örnek çizer.

```qsharp
operation DrawCategorical (probs : Double[]) : Int
```


## <a name="description"></a>Description

Belirli bir dizini seçme olasılığı, bu dizindeki dizi öğesinin değeri ile orantılıdır.
Sıfıra eşit dizi öğeleri yok sayılır ve bunların dizinleri hiçbir şekilde döndürülmez. Herhangi bir dizi öğesi sıfırdan küçükse veya hiçbir dizi öğesi sıfırdan büyükse, işlem başarısız olur.

## <a name="input"></a>Giriş

### <a name="probs--double"></a>probs: [Double](xref:microsoft.quantum.lang-ref.double)[]

Kayan noktalı sayıların dizisi her bir dizini seçme olasılığa göre orantılıdır.



## <a name="output--int"></a>Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)

Olasılık $ \Pr (i) = p_i/\ sum_i p_i $ olan bir tamsayı $i $, burada $p _i $, $i $ TH öğesidir `probs` .

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Random. CategoricalDistribution](xref:Microsoft.Quantum.Random.CategoricalDistribution)