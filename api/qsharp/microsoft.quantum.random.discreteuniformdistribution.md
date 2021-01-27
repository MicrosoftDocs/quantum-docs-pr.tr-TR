---
uid: Microsoft.Quantum.Random.DiscreteUniformDistribution
title: DiscreteUniformDistribution işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DiscreteUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive range.
ms.openlocfilehash: f909e7def5439ec0feef4ca4dc0cf8ed12374dfe
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853716"
---
# <a name="discreteuniformdistribution-function"></a>DiscreteUniformDistribution işlevi

Ad alanı: [Microsoft. hisse. Random](xref:Microsoft.Quantum.Random)

Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


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

## <a name="example"></a>Örnek

Aşağıdaki Q # kod parçacığı rastgele altı taraflı bir zar kaydeder:

```qsharp
let dieDistribution = DiscreteUniformDistribution(1, 6);
let dieRoll = dieDistribution::Sample();
```

## <a name="remarks"></a>Açıklamalar

Başarısız olur `max <= min` .

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. DrawRandomDouble](xref:Microsoft.Quantum.DrawRandomDouble)