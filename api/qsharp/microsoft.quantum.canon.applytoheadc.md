---
uid: Microsoft.Quantum.Canon.ApplyToHeadC
title: ApplyToHeadC işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHeadC
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: 3a65ad52e0b2f8b3a921fc549c35311f24d0e189
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850622"
---
# <a name="applytoheadc-operation"></a>ApplyToHeadC işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir işlemi bir dizinin ilk öğesine uygular.

```qsharp
operation ApplyToHeadC<'T> (op : ('T => Unit is Ctl), targets : 'T[]) : Unit is Ctl
```


## <a name="description"></a>Description

Bir işlem `op` ve bir hedef dizisi verildiğinde `targets` , geçerlidir `op(Head(targets))` .

## <a name="input"></a>Giriş

### <a name="op--t--unit--is-ctl"></a>Op: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)  CTL

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
- [Microsoft. hisse. Canon. ApplyToHeadCA](xref:Microsoft.Quantum.Canon.ApplyToHeadCA)