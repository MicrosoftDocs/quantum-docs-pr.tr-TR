---
uid: Microsoft.Quantum.Chemistry.IsNotZero
title: IsNotZero işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: IsNotZero
qsharp.summary: Checks whether a `Double` number is not approximately zero.
ms.openlocfilehash: f80dbba6a51e62970e87c2782faba558340d2bd8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204071"
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