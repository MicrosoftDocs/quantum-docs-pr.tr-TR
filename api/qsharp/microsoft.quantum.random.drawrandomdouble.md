---
uid: Microsoft.Quantum.Random.DrawRandomDouble
title: DrawRandomDouble işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomDouble
qsharp.summary: Draws a random real number in a given inclusive interval.
ms.openlocfilehash: d62416f4a222716edb9393fe4f43731d0e8aa9d3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192953"
---
# <a name="drawrandomdouble-operation"></a>DrawRandomDouble işlemi

Ad alanı: [Microsoft. hisse. Random](xref:Microsoft.Quantum.Random)

Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Verili bir kapsayıcı aralığında rastgele bir gerçek sayı çizer.

```qsharp
operation DrawRandomDouble (min : Double, max : Double) : Double
```


## <a name="input"></a>Giriş

### <a name="min--double"></a>Min: [Double](xref:microsoft.quantum.lang-ref.double)

Çizilecek en küçük gerçek sayı.


### <a name="max--double"></a>Max: [Double](xref:microsoft.quantum.lang-ref.double)

Çizilecek en büyük gerçek sayı.



## <a name="output--double"></a>Çıkış: [Double](xref:microsoft.quantum.lang-ref.double)

Kapsamlı `min` olasılığa sahip olan ve arasında rastgele bir gerçek sayı `max` .

## <a name="remarks"></a>Açıklamalar

Başarısız olur `max <= min` .

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. ContinuousUniformDistribution](xref:Microsoft.Quantum.ContinuousUniformDistribution)