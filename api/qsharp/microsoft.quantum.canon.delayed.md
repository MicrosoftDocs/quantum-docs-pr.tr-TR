---
uid: Microsoft.Quantum.Canon.Delayed
title: Gecikmeli işlev
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Delayed
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: 820a38c2b4de2e0151d55bd88fb4f69567182f6b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728736"
---
# <a name="delayed-function"></a>Gecikmeli işlev

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Leyebilir [](https://nuget.org/packages/)


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