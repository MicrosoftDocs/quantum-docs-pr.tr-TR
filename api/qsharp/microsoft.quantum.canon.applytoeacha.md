---
uid: Microsoft.Quantum.Canon.ApplyToEachA
title: ApplyToEachA işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachA
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `A` indicates that the single-qubit operation is adjointable.
ms.openlocfilehash: 9819e78760caf6180edc5c2ca5e402060e3029a5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217807"
---
# <a name="applytoeacha-operation"></a>ApplyToEachA işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir kayıttaki her öğeye bir tek qubit işlemi uygular.
Değiştirici, `A` tek qubit işleminin adjointable olduğunu gösterir.

```qsharp
operation ApplyToEachA<'T> (singleElementOperation : ('T => Unit is Adj), register : 'T[]) : Unit is Adj
```


## <a name="input"></a>Giriş

### <a name="singleelementoperation--t--unit--is-adj"></a>singleElementOperation: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)  sıfatı

Her bir qubit için uygulanacak işlem.


### <a name="register--t"></a>kaydolun: 'T []

Verilen işlemin uygulanacağı qubit dizisi.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen

İşlemin işlem gördüğü hedef.

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Canon. ApplyToEach](xref:Microsoft.Quantum.Canon.ApplyToEach)