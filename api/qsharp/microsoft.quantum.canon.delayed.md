---
uid: Microsoft.Quantum.Canon.Delayed
title: Gecikmeli işlev
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Delayed
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: 863c63d0c1a50339e9d5b9fbe4729932b2706f32
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216464"
---
# <a name="delayed-function"></a>Gecikmeli işlev

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Verilen bağımsız değişkenle belirli bir işlem uygulayan bir işlem döndürür.

```qsharp
function Delayed<'T, 'U> (op : ('T => 'U), arg : 'T) : (Unit => 'U)
```


## <a name="input"></a>Giriş

### <a name="op--t--u"></a>Op: 'T => ' U 

Uygulanacak bir işlem.


### <a name="arg--t"></a>bağımsız değişken: 'T

İşlemin uygulandığı giriş.



## <a name="output--unit--u"></a>Çıkış: [Unit](xref:microsoft.quantum.lang-ref.unit) => ' U 

Giriş ile uygulanan yeni bir işlem `op``arg`

## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen

Gecikecek işlemin giriş türü.
### <a name="u"></a>' U

Gecikecek işlemin dönüş türü.

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Canon. DelayedC](xref:Microsoft.Quantum.Canon.DelayedC)
- [Microsoft. hisse. Canon. DelayedA](xref:Microsoft.Quantum.Canon.DelayedA)
- [Microsoft. hisse. Canon. DelayedCA](xref:Microsoft.Quantum.Canon.DelayedCA)
- [Microsoft. hisse. Canon. Delay](xref:Microsoft.Quantum.Canon.Delay)