---
uid: Microsoft.Quantum.Canon.ApplyToEachIndex
title: Applytoeachındex işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndex
qsharp.summary: Applies a single-qubit operation to each indexed element in a register.
ms.openlocfilehash: 4ce184b34add9238e26f9b35b40ec0bddb23ccf9
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729288"
---
# <a name="applytoeachindex-operation"></a>Applytoeachındex işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Leyebilir [](https://nuget.org/packages/)


Bir kayıttaki her dizinli öğeye bir tek qubit işlemi uygular.

```qsharp
operation ApplyToEachIndex<'T> (singleElementOperation : ((Int, 'T) => Unit), register : 'T[]) : Unit
```


## <a name="input"></a>Giriş

### <a name="singleelementoperation--intt--unit"></a>singleElementOperation: ([Int](xref:microsoft.quantum.lang-ref.int), 't) => [Unit](xref:microsoft.quantum.lang-ref.unit) 

Her bir qubit için uygulanacak işlem.


### <a name="register--t"></a>kaydolun: 'T []

Verilen işlemin uygulanacağı qubit dizisi.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen

Her bir işlemin işlem gördüğü hedef.

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Canon. ApplyToEach](xref:Microsoft.Quantum.Canon.ApplyToEach)
- [Microsoft. hisse. Canon. Applytoeachındexa](xref:Microsoft.Quantum.Canon.ApplyToEachIndexA)
- [Microsoft. hisse. Canon. Applytoeachındexc](xref:Microsoft.Quantum.Canon.ApplyToEachIndexC)
- [Microsoft. hisse. Canon. Applytoeachındexca](xref:Microsoft.Quantum.Canon.ApplyToEachIndexCA)