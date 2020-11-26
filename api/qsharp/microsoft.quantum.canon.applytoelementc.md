---
uid: Microsoft.Quantum.Canon.ApplyToElementC
title: ApplyToElementC işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElementC
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: c8d7841e3846ab435671f7959c724f987d8ad5a0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217586"
---
# <a name="applytoelementc-operation"></a>ApplyToElementC işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir dizinin belirli bir öğesine bir işlem uygular.

```qsharp
operation ApplyToElementC<'T> (op : ('T => Unit is Ctl), index : Int, targets : 'T[]) : Unit is Ctl
```


## <a name="description"></a>Açıklama

Bir işlem `op` , dizin ve bir `index` hedef dizisi verildiğinde `targets` , geçerlidir `op(targets[index])` .

## <a name="input"></a>Giriş

### <a name="op--t--unit--is-ctl"></a>Op: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)  CTL

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
- [Microsoft. hisse. Canon. ApplyToElementA](xref:Microsoft.Quantum.Canon.ApplyToElementA)
- [Microsoft. hisse. Canon. ApplyToElementCA](xref:Microsoft.Quantum.Canon.ApplyToElementCA)