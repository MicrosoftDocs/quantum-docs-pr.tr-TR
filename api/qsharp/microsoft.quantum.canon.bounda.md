---
uid: Microsoft.Quantum.Canon.BoundA
title: Sını işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundA
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `A` indicates that all operations in the array are adjointable.
ms.openlocfilehash: 3132bf198e98dd1a2b433f36b000060e7e721865
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216957"
---
# <a name="bounda-function"></a>Sını işlevi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Tek bir girişte çalışan bir işlem dizisi verildiğinde, belirli bir işlemi sırayla gerçekleştiren yeni bir işlem oluşturur.
Değiştirici `A` dizideki tüm işlemlerin adjointable olduğunu gösterir.

```qsharp
function BoundA<'T> (operations : ('T => Unit is Adj)[]) : ('T => Unit is Adj)
```


## <a name="input"></a>Giriş

### <a name="operations--t--unit--is-adj"></a>işlemler: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)  sıfatı []

Belirli bir girişte gerçekleştirilecek işlemler dizisi.



## <a name="output--t--unit--is-adj"></a>Çıkış: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)  sıfatı

Belirli bir işlemi girişinde sırayla gerçekleştiren yeni bir işlem.

## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen

Dizideki her bir işlemin üzerinde işlem gören hedef.

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Canon. bağlanacak](xref:Microsoft.Quantum.Canon.Bound)