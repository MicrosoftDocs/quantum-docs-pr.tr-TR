---
uid: Microsoft.Quantum.Random.DrawRandomInt
title: DrawRandomInt işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomInt
qsharp.summary: Draws a random integer in a given inclusive range.
ms.openlocfilehash: ebed7f52b7c4a8c538ed9d718c486b5aa94a0327
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851132"
---
# <a name="drawrandomint-operation"></a>DrawRandomInt işlemi

Ad alanı: [Microsoft. hisse. Random](xref:Microsoft.Quantum.Random)

Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


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

## <a name="example"></a>Örnek

Aşağıdaki Q # kod parçacığı rastgele altı taraflı bir zar kaydeder:

```qsharp
let roll = DrawRandomInt(1, 6);
```

## <a name="remarks"></a>Açıklamalar

Başarısız olur `max <= min` .

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. DiscreteUniformDistribution](xref:Microsoft.Quantum.DiscreteUniformDistribution)