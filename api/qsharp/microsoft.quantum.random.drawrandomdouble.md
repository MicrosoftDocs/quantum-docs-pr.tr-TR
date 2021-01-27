---
uid: Microsoft.Quantum.Random.DrawRandomDouble
title: DrawRandomDouble işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomDouble
qsharp.summary: Draws a random real number in a given inclusive interval.
ms.openlocfilehash: 792e9c714b761b48618aec2091e167a359c2b522
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847619"
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

## <a name="example"></a>Örnek

Aşağıdaki Q # kod parçacığı $0 $ ile $2 \pı $ arasında bir açı rastgele çizer:

```qsharp
let angle = DrawRandomDouble(0.0, 2.0 * PI());
```

## <a name="remarks"></a>Açıklamalar

Başarısız olur `max <= min` .

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. ContinuousUniformDistribution](xref:Microsoft.Quantum.ContinuousUniformDistribution)