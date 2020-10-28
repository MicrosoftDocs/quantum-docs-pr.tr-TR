---
uid: Microsoft.Quantum.Canon.ApplyToElementCA
title: ApplyToElementCA işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElementCA
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: 599a8afe1ab97b0ab0d6621cabd7707faaeddda3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729246"
---
# <a name="applytoelementca-operation"></a>ApplyToElementCA işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Leyebilir [](https://nuget.org/packages/)


Bir dizinin belirli bir öğesine bir işlem uygular.

```qsharp
operation ApplyToElementCA<'T> (op : ('T => Unit is Adj + Ctl), index : Int, targets : 'T[]) : Unit
```


## <a name="description"></a>Açıklama

Bir işlem `op` , dizin ve bir `index` hedef dizisi verildiğinde `targets` , geçerlidir `op(targets[index])` .

## <a name="input"></a>Giriş

### <a name="op--t--unit-adj--ctl"></a>Op: 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) ayarlaması + CTL

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