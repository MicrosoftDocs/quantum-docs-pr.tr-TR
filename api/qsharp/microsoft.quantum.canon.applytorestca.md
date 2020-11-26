---
uid: Microsoft.Quantum.Canon.ApplyToRestCA
title: ApplyToRestCA işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToRestCA
qsharp.summary: Applies an operation to all but the first element of an array.
ms.openlocfilehash: 3123c7f7b5e5c7f5cb17a34eedc81b3912109883
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208168"
---
# <a name="applytorestca-operation"></a>ApplyToRestCA işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir işlemi, bir dizinin ilk öğesi hariç tümüne uygular.

```qsharp
operation ApplyToRestCA<'T> (op : ('T[] => Unit is Adj + Ctl), targets : 'T[]) : Unit is Adj + Ctl
```


## <a name="description"></a>Açıklama

Bir işlem `op` ve bir hedef dizisi verildiğinde `targets` , geçerlidir `op(Rest(targets))` .

## <a name="input"></a>Giriş

### <a name="op--t--unit--is-adj--ctl"></a>Op: 'T [] => [birimi](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL

Uygulanacak bir işlem.


### <a name="targets--t"></a>hedefler: 'T []

Birincisi, ancak ilki uygulanacak bir dizi hedefi `op` .



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen

Uygulanacak işlemin giriş türü.

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Canon. ApplyToRest](xref:Microsoft.Quantum.Canon.ApplyToRest)
- [Microsoft. hisse. Canon. ApplyToRestA](xref:Microsoft.Quantum.Canon.ApplyToRestA)
- [Microsoft. hisse. Canon. ApplyToRestC](xref:Microsoft.Quantum.Canon.ApplyToRestC)