---
uid: Microsoft.Quantum.Canon.DelayedC
title: DelayedC işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayedC
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: d8036397559b1587b806f701d89e892eea2da8f9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207028"
---
# <a name="delayedc-function"></a>DelayedC işlevi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Verilen bağımsız değişkenle belirli bir işlem uygulayan bir işlem döndürür.

```qsharp
function DelayedC<'T> (op : ('T => Unit is Ctl), arg : 'T) : (Unit => Unit is Ctl)
```


## <a name="input"></a>Giriş

### <a name="op--t--unit--is-ctl"></a>Op: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)  CTL

Dönüş değeri uygulama sonucu olarak uygulanacak bir işlem


### <a name="arg--t"></a>bağımsız değişken: 'T

İşlemin `op` uygulandığı giriş.



## <a name="output--unit--unit--is-ctl"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit) => [birimi](xref:microsoft.quantum.lang-ref.unit)  CTL 'dir

Giriş ile uygulanan yeni bir işlem `op``arg`

## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen

Gecikecek işlemin giriş türü.

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Canon. Gecikmeli](xref:Microsoft.Quantum.Canon.Delayed)
- [Microsoft. hisse. Canon. Delay](xref:Microsoft.Quantum.Canon.Delay)