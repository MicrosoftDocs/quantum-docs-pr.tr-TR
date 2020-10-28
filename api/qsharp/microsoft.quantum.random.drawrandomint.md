---
uid: Microsoft.Quantum.Random.DrawRandomInt
title: DrawRandomInt işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomInt
qsharp.summary: Draws a random integer in a given inclusive range.
ms.openlocfilehash: d9d8d9fbb25587ac5ccbd4edf0e555649380375f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733594"
---
# <a name="drawrandomint-operation"></a>DrawRandomInt işlemi

Ad alanı: [Microsoft. hisse. Random](xref:Microsoft.Quantum.Random)

Leyebilir [](https://nuget.org/packages/)


Verili bir kapsayıcı aralığında rastgele bir tamsayı çizer.

```qsharp
operation DrawRandomInt (min : Int, max : Int) : Int
```


## <a name="input"></a>Giriş

### <a name="min--int"></a>Min: [Int](xref:microsoft.quantum.lang-ref.int)

Çizilecek en küçük tamsayı.


### <a name="max--int"></a>Max: [Int](xref:microsoft.quantum.lang-ref.int)

Çizilecek en büyük tamsayı.



## <a name="output--int"></a>Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)

İle arasında, tek bir tamsayı `min` `max` olasılığa sahip.

## <a name="remarks"></a>Açıklamalar

Başarısız olur `max <= min` .

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. DiscreteUniformDistribution](xref:Microsoft.Quantum.DiscreteUniformDistribution)