---
uid: Microsoft.Quantum.Canon.ApplyIfOneC
title: ApplyIfOneC işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfOneC
qsharp.summary: Applies a controllable operation conditioned on a classical result value being one.
ms.openlocfilehash: ebeec5b46567892ad30f194ababb42876ba08bcb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841748"
---
# <a name="applyifonec-operation"></a>ApplyIfOneC işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Klasik sonuç değeri bir olan denetlenebilir bir işlem uygular.

```qsharp
operation ApplyIfOneC<'T> (result : Result, (op : ('T => Unit is Ctl), target : 'T)) : Unit is Ctl
```


## <a name="description"></a>Description

Bir işlem `op` ve sonuç değeri verildiğinde, `result` if ise `op` için geçerlidir `target` `result` `One` . Varsa, `Zero` hiçbir şey olmaz `target` .
Sonek, `C` uygulanacak işlemin denetlenebilir olduğunu gösterir.

## <a name="input"></a>Giriş

### <a name="result--__invalidresult__"></a>Sonuç: __geçersiz <Result>__

Op 'ın uygulanıp uygulanmadığını denetleyen ölçüm sonucu.


### <a name="op--t--unit--is-ctl"></a>Op: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)  CTL

Koşullu olarak uygulanacak bir işlem.


### <a name="target--t"></a>Hedef: 'T

İşlemin uygulandığı giriş.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen

Koşullu olarak uygulanacak işlemin giriş türü.

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Canon. ApplyIfOneC](xref:Microsoft.Quantum.Canon.ApplyIfOneC)
- [Microsoft. hisse. Canon. ApplyIfOneA](xref:Microsoft.Quantum.Canon.ApplyIfOneA)
- [Microsoft. hisse. Canon. ApplyIfOneCA](xref:Microsoft.Quantum.Canon.ApplyIfOneCA)