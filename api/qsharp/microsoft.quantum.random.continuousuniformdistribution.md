---
uid: Microsoft.Quantum.Random.ContinuousUniformDistribution
title: ContinuousUniformDistribution işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: ContinuousUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive interval.
ms.openlocfilehash: c81eb433f50277c677756ee70d916f4856260c6d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842311"
---
# <a name="continuousuniformdistribution-function"></a>ContinuousUniformDistribution işlevi

Ad alanı: [Microsoft. hisse. Random](xref:Microsoft.Quantum.Random)

Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


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

## <a name="example"></a>Örnek

Aşağıdaki Q # kod parçacığı $0 $ ile $2 \pı $ arasında bir açı rastgele çizer:

```qsharp
let angleDistribution = ContinuousUniformDistribution(0.0, 2.0 * PI());
let angle = angleDistribution::Sample();
```

## <a name="remarks"></a>Açıklamalar

Başarısız olur `max <= min` .

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. DrawRandomDouble](xref:Microsoft.Quantum.DrawRandomDouble)