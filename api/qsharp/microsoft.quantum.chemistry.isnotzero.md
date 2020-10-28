---
uid: Microsoft.Quantum.Chemistry.IsNotZero
title: IsNotZero işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: IsNotZero
qsharp.summary: Checks whether a `Double` number is not approximately zero.
ms.openlocfilehash: 3c0f9c6695e8c9ec4a0953d5217c28c512ac7de1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728124"
---
# <a name="isnotzero-function"></a>IsNotZero işlevi

Ad alanı: [Microsoft. hisse. Chemistry](xref:Microsoft.Quantum.Chemistry)

Leyebilir [](https://nuget.org/packages/)


Bir `Double` sayının yaklaşık olarak sıfır olup olmadığını denetler.

```qsharp
function IsNotZero (number : Double) : Bool
```


## <a name="input"></a>Giriş

### <a name="number--double"></a>Sayı: [Double](xref:microsoft.quantum.lang-ref.double)

Denetlenecek numara



## <a name="output--bool"></a>Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)

Sıfırdan `number` büyük bir mutlak değere sahipse true değerini döndürür `1e-15` .