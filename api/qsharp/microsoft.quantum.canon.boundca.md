---
uid: Microsoft.Quantum.Canon.BoundCA
title: BoundCA işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundCA
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `CA` indicates that all operations in the array are adjointable and controllable.
ms.openlocfilehash: 391183829a3cc8b7aa8051767dcfc6bec9638223
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844524"
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

## <a name="example"></a>Örnek

Aşağıdakiler eşdeğerdir:

```qsharp
let bound = BoundCA([U, V]);
bound(x);
```

ve

```qsharp
U(x); V(x);
```

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Canon. bağlanacak](xref:Microsoft.Quantum.Canon.Bound)