---
uid: Microsoft.Quantum.Canon.Delayed
title: Gecikmeli işlev
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Delayed
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: 40fcc7d0a178fdb18437b4d6c96542db593347b4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840579"
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