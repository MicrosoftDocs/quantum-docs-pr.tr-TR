---
uid: Microsoft.Quantum.Random.DrawRandomDouble
title: DrawRandomDouble işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomDouble
qsharp.summary: Draws a random real number in a given inclusive interval.
ms.openlocfilehash: 6c0558ded2bd018afad84c42c2d15fc029ac0d44
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733210"
---
# <a name="drawrandomdouble-operation"></a>DrawRandomDouble işlemi

Ad alanı: [Microsoft. hisse. Random](xref:Microsoft.Quantum.Random)

Leyebilir [](https://nuget.org/packages/)


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