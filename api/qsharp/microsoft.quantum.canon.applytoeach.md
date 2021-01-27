---
uid: Microsoft.Quantum.Canon.ApplyToEach
title: ApplyToEach işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEach
qsharp.summary: Applies a single-qubit operation to each element in a register.
ms.openlocfilehash: 61dda69751989ef8a98fa8fb01d832014ec4ad35
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844633"
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

## <a name="example"></a>Örnek

Üç-qubit $ \ket{+} $ durumu hazırlayın:

```qsharp
using (register = Qubit[3]) {
    ApplyToEach(H, register);
}
```

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Canon. ApplyToEachC](xref:Microsoft.Quantum.Canon.ApplyToEachC)
- [Microsoft. hisse. Canon. ApplyToEachA](xref:Microsoft.Quantum.Canon.ApplyToEachA)
- [Microsoft. hisse. Canon. ApplyToEachCA](xref:Microsoft.Quantum.Canon.ApplyToEachCA)