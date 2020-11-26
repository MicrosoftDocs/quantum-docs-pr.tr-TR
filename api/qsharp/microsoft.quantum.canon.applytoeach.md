---
uid: Microsoft.Quantum.Canon.ApplyToEach
title: ApplyToEach işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEach
qsharp.summary: Applies a single-qubit operation to each element in a register.
ms.openlocfilehash: 11f9363feb38676df3f805496c74036aa96160c1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217875"
---
# <a name="applytoeach-operation"></a>ApplyToEach işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir kayıttaki her öğeye bir tek qubit işlemi uygular.

```qsharp
operation ApplyToEach<'T> (singleElementOperation : ('T => Unit), register : 'T[]) : Unit
```


## <a name="input"></a>Giriş

### <a name="singleelementoperation--t--unit"></a>singleElementOperation: 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) 

Her bir qubit için uygulanacak işlem.


### <a name="register--t"></a>kaydolun: 'T []

Verilen işlemin uygulanacağı qubit dizisi.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen

İşlemin işlem gördüğü hedef.

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Canon. ApplyToEachC](xref:Microsoft.Quantum.Canon.ApplyToEachC)
- [Microsoft. hisse. Canon. ApplyToEachA](xref:Microsoft.Quantum.Canon.ApplyToEachA)
- [Microsoft. hisse. Canon. ApplyToEachCA](xref:Microsoft.Quantum.Canon.ApplyToEachCA)