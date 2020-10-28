---
uid: Microsoft.Quantum.Random.ContinuousUniformDistribution
title: ContinuousUniformDistribution işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: ContinuousUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive interval.
ms.openlocfilehash: 74300efb10ba7b5aa006f0b1b6aafde0da840f00
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725813"
---
# <a name="continuousuniformdistribution-function"></a>ContinuousUniformDistribution işlevi

Ad alanı: [Microsoft. hisse. Random](xref:Microsoft.Quantum.Random)

Leyebilir [](https://nuget.org/packages/)


Verilen bir kapsayıcı aralığı üzerinde Tekdüzen dağılımı döndürür.

```qsharp
function ContinuousUniformDistribution (min : Double, max : Double) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a>Giriş

### <a name="min--double"></a>Min: [Double](xref:microsoft.quantum.lang-ref.double)

Çizilecek en küçük gerçek sayı.


### <a name="max--double"></a>Max: [Double](xref:microsoft.quantum.lang-ref.double)

Çizilecek en büyük gerçek sayı.



## <a name="output--continuousdistribution"></a>Çıkış: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)

Rastgele `min` bultteklerini, kapsamlı olasılığa sahip olan bağımsız aralıkta gerçek sayı olan bir dağıtım `max` .

## <a name="remarks"></a>Açıklamalar

Başarısız olur `max <= min` .

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. DrawRandomDouble](xref:Microsoft.Quantum.DrawRandomDouble)