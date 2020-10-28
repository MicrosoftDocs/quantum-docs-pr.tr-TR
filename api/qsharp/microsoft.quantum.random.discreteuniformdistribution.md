---
uid: Microsoft.Quantum.Random.DiscreteUniformDistribution
title: DiscreteUniformDistribution işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DiscreteUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive range.
ms.openlocfilehash: 5e93c66d891d9b6aec548c0cf266df35e6090c92
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730967"
---
# <a name="discreteuniformdistribution-function"></a>DiscreteUniformDistribution işlevi

Ad alanı: [Microsoft. hisse. Random](xref:Microsoft.Quantum.Random)

Leyebilir [](https://nuget.org/packages/)


Verili bir kapsayıcı aralığı üzerinde Tekdüzen dağılımı döndürür.

```qsharp
function DiscreteUniformDistribution (min : Int, max : Int) : Microsoft.Quantum.Random.DiscreteDistribution
```


## <a name="input"></a>Giriş

### <a name="min--int"></a>Min: [Int](xref:microsoft.quantum.lang-ref.int)

Çizilecek en küçük tamsayı.


### <a name="max--int"></a>Max: [Int](xref:microsoft.quantum.lang-ref.int)

Çizilecek en büyük tamsayı.



## <a name="output--discretedistribution"></a>Çıkış: [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)

Rastgele değiştireni, kapsamlı `min` olasılığa sahip olan ve arasında bir tamsayı olan bir dağıtım `max` .

## <a name="remarks"></a>Açıklamalar

Başarısız olur `max <= min` .

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. DrawRandomDouble](xref:Microsoft.Quantum.DrawRandomDouble)