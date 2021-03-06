---
uid: Microsoft.Quantum.Canon.ApplyToEachIndexA
title: Applytoeachındexa işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndexA
qsharp.summary: Applies a single-qubit operation to each indexed element in a register. The modifier `A` indicates that the single-qubit operation is adjointable.
ms.openlocfilehash: fb278f217ac450ab48aa37b0035cd1bdd295d3e5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850837"
---
# <a name="applytoeachindexa-operation"></a>Applytoeachındexa işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir kayıttaki her dizinli öğeye bir tek qubit işlemi uygular.
Değiştirici, `A` tek qubit işleminin adjointable olduğunu gösterir.

```qsharp
operation ApplyToEachIndexA<'T> (singleElementOperation : ((Int, 'T) => Unit is Adj), register : 'T[]) : Unit is Adj
```


## <a name="input"></a>Giriş

### <a name="singleelementoperation--intt--unit--is-adj"></a>singleElementOperation: ([Int](xref:microsoft.quantum.lang-ref.int), 't) => [birim](xref:microsoft.quantum.lang-ref.unit)  sıfatı

Her bir qubit için uygulanacak işlem.


### <a name="register--t"></a>kaydolun: 'T []

Verilen işlemin uygulanacağı qubit dizisi.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen

Her bir işlemin işlem gördüğü hedef.

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Canon. Applytoeachındex](xref:Microsoft.Quantum.Canon.ApplyToEachIndex)