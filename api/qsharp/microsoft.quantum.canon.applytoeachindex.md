---
uid: Microsoft.Quantum.Canon.ApplyToEachIndex
title: Applytoeachındex işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndex
qsharp.summary: Applies a single-qubit operation to each indexed element in a register.
ms.openlocfilehash: 8b34dc24580a3df7ae2c13ef87a6fa10c7afd3f8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844585"
---
# <a name="applytoeachindex-operation"></a>Applytoeachındex işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


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