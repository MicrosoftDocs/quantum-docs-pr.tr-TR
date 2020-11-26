---
uid: Microsoft.Quantum.Canon.ApplyToHeadCA
title: ApplyToHeadCA işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHeadCA
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: f28cff599e06090145fac860dbaf8274c966f80a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208559"
---
# <a name="applytoheadca-operation"></a>ApplyToHeadCA işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir işlemi bir dizinin ilk öğesine uygular.

```qsharp
operation ApplyToHeadCA<'T> (op : ('T => Unit is Adj + Ctl), targets : 'T[]) : Unit is Adj + Ctl
```


## <a name="description"></a>Açıklama

Bir işlem `op` ve bir hedef dizisi verildiğinde `targets` , geçerlidir `op(Head(targets))` .

## <a name="input"></a>Giriş

### <a name="op--t--unit--is-adj--ctl"></a>Op: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL

Uygulanacak bir işlem.


### <a name="targets--t"></a>hedefler: 'T []

İlki uygulanacak bir dizi hedef `op` .



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen

Uygulanacak işlemin giriş türü.

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Canon. ApplyToHead](xref:Microsoft.Quantum.Canon.ApplyToHead)
- [Microsoft. hisse. Canon. ApplyToHeadA](xref:Microsoft.Quantum.Canon.ApplyToHeadA)
- [Microsoft. hisse. Canon. ApplyToHeadC](xref:Microsoft.Quantum.Canon.ApplyToHeadC)