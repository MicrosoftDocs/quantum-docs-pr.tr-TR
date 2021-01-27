---
uid: Microsoft.Quantum.Canon.ApplyToElementCA
title: ApplyToElementCA işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElementCA
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: 420a92ae10d2fc260024968b1846e669c4b62d73
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841463"
---
# <a name="applytoelementca-operation"></a>ApplyToElementCA işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir dizinin belirli bir öğesine bir işlem uygular.

```qsharp
operation ApplyToElementCA<'T> (op : ('T => Unit is Adj + Ctl), index : Int, targets : 'T[]) : Unit is Adj + Ctl
```


## <a name="description"></a>Description

Bir işlem `op` , dizin ve bir `index` hedef dizisi verildiğinde `targets` , geçerlidir `op(targets[index])` .

## <a name="input"></a>Giriş

### <a name="op--t--unit--is-adj--ctl"></a>Op: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL

Uygulanacak bir işlem.


### <a name="index--int"></a>Dizin: [Int](xref:microsoft.quantum.lang-ref.int)

Hedef dizisine bir dizin.


### <a name="targets--t"></a>hedefler: 'T []

İçin olası hedeflerin bir dizisi `op` .



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen

Uygulanacak işlemin giriş türü.

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Canon. ApplyToElement](xref:Microsoft.Quantum.Canon.ApplyToElement)
- [Microsoft. hisse. Canon. ApplyToElementC](xref:Microsoft.Quantum.Canon.ApplyToElementC)
- [Microsoft. hisse. Canon. ApplyToElementA](xref:Microsoft.Quantum.Canon.ApplyToElementA)