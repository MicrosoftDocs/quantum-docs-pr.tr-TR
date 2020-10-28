---
uid: Microsoft.Quantum.Canon.DelayedC
title: DelayedC işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayedC
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: 7cfd77b0bb2d91c5a1c4bb5bc84e052421d733a9
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728718"
---
# <a name="delayedc-function"></a>DelayedC işlevi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Leyebilir [](https://nuget.org/packages/)


Verilen bağımsız değişkenle belirli bir işlem uygulayan bir işlem döndürür.

```qsharp
function DelayedC<'T> (op : ('T => Unit is Ctl), arg : 'T) : (Unit => Unit is Ctl)
```


## <a name="input"></a>Giriş

### <a name="op--t--unit-ctl"></a>Op: 'T => [birim](xref:microsoft.quantum.lang-ref.unit) CTL

Dönüş değeri uygulama sonucu olarak uygulanacak bir işlem


### <a name="arg--t"></a>bağımsız değişken: 'T

İşlemin `op` uygulandığı giriş.



## <a name="output--unit--unit-ctl"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit) => [birim](xref:microsoft.quantum.lang-ref.unit) CTL

Giriş ile uygulanan yeni bir işlem `op``arg`

## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen

Gecikecek işlemin giriş türü.

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Canon. Gecikmeli](xref:Microsoft.Quantum.Canon.Delayed)
- [Microsoft. hisse. Canon. Delay](xref:Microsoft.Quantum.Canon.Delay)