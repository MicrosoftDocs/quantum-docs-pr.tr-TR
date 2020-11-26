---
uid: Microsoft.Quantum.Canon.BoundCA
title: BoundCA işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundCA
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `CA` indicates that all operations in the array are adjointable and controllable.
ms.openlocfilehash: 774a6f57566dce75b98290a7e81540b28afea1af
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216905"
---
# <a name="boundca-function"></a>BoundCA işlevi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Tek bir girişte çalışan bir işlem dizisi verildiğinde, belirli bir işlemi sırayla gerçekleştiren yeni bir işlem oluşturur.
Değiştirici `CA` dizideki tüm işlemlerin adjointable ve denetlenebilir olduğunu gösterir.

```qsharp
function BoundCA<'T> (operations : ('T => Unit is Adj + Ctl)[]) : ('T => Unit is Adj + Ctl)
```


## <a name="input"></a>Giriş

### <a name="operations--t--unit--is-adj--ctl"></a>işlemler: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL []

Belirli bir girişte gerçekleştirilecek işlemler dizisi.



## <a name="output--t--unit--is-adj--ctl"></a>Çıkış: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL

Belirli bir işlemi girişinde sırayla gerçekleştiren yeni bir işlem.

## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen

Dizideki her bir işlemin üzerinde işlem gören hedef.

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Canon. bağlanacak](xref:Microsoft.Quantum.Canon.Bound)