---
uid: Microsoft.Quantum.Canon.ApplyToEachIndexCA
title: Applytoeachındexca işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndexCA
qsharp.summary: Applies a single-qubit operation to each indexed element in a register. The modifier `CA` indicates that the single-qubit operation is adjointable and controllable.
ms.openlocfilehash: c5bb61aadbdaab9c74a3dcd418088c532b495ff5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729276"
---
# <a name="applytoeachindexca-operation"></a>Applytoeachındexca işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Leyebilir [](https://nuget.org/packages/)


Bir kayıttaki her dizinli öğeye bir tek qubit işlemi uygular.
Değiştirici, `CA` tek qubit işleminin adjointable ve denetlenebilir olduğunu gösterir.

```qsharp
operation ApplyToEachIndexCA<'T> (singleElementOperation : ((Int, 'T) => Unit is Adj + Ctl), register : 'T[]) : Unit
```


## <a name="input"></a>Giriş

### <a name="singleelementoperation--intt--unit-adj--ctl"></a>singleElementOperation: ([Int](xref:microsoft.quantum.lang-ref.int), 't) => [Unit](xref:microsoft.quantum.lang-ref.unit) ayarlaması + CTL

Her bir qubit için uygulanacak işlem.


### <a name="register--t"></a>kaydolun: 'T []

Verilen işlemin uygulanacağı qubit dizisi.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen

Her bir işlemin işlem gördüğü hedef.

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Canon. Applytoeachındex](xref:Microsoft.Quantum.Canon.ApplyToEachIndex)