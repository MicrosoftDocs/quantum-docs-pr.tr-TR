---
uid: Microsoft.Quantum.Chemistry.IsNotZero
title: IsNotZero işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: IsNotZero
qsharp.summary: Checks whether a `Double` number is not approximately zero.
ms.openlocfilehash: 9384e5dafd4b5b7d44cb348c9537ebc2c621466d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839592"
---
# <a name="isnotzero-function"></a>IsNotZero işlevi

Ad alanı: [Microsoft. hisse. Chemistry](xref:Microsoft.Quantum.Chemistry)

Paket: [Microsoft. hisse. Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Bir `Double` sayının yaklaşık olarak sıfır olup olmadığını denetler.

```qsharp
function IsNotZero (number : Double) : Bool
```


## <a name="input"></a>Giriş

### <a name="number--double"></a>Sayı: [Double](xref:microsoft.quantum.lang-ref.double)

Denetlenecek numara



## <a name="output--bool"></a>Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)

Sıfırdan `number` büyük bir mutlak değere sahipse true değerini döndürür `1e-15` .