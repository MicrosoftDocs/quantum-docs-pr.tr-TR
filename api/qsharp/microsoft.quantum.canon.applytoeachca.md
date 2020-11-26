---
uid: Microsoft.Quantum.Canon.ApplyToEachCA
title: ApplyToEachCA işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachCA
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.
ms.openlocfilehash: dcfd4619a77413e71044e6a7d5fc19a9f22bbf94
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217756"
---
# <a name="applytoeachca-operation"></a>ApplyToEachCA işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir kayıttaki her öğeye bir tek qubit işlemi uygular.
Değiştirici, `CA` tek qubit işleminin denetlenebilir ve adjointable olduğunu gösterir.

```qsharp
operation ApplyToEachCA<'T> (singleElementOperation : ('T => Unit is Adj + Ctl), register : 'T[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Giriş

### <a name="singleelementoperation--t--unit--is-adj--ctl"></a>singleElementOperation: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL

Her bir qubit için uygulanacak işlem.


### <a name="register--t"></a>kaydolun: 'T []

Verilen işlemin uygulanacağı qubit dizisi.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen

İşlemin işlem gördüğü hedef.

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Canon. ApplyToEach](xref:Microsoft.Quantum.Canon.ApplyToEach)