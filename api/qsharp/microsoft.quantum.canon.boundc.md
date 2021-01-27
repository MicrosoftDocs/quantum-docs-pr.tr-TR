---
uid: Microsoft.Quantum.Canon.BoundC
title: BoundC işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundC
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `C` indicates that all operations in the array are controllable.
ms.openlocfilehash: 6b640c0dab14778336f42098e699e7e68cc726df
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841037"
---
# <a name="boundc-function"></a>BoundC işlevi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Tek bir girişte çalışan bir işlem dizisi verildiğinde, belirli bir işlemi sırayla gerçekleştiren yeni bir işlem oluşturur.
Değiştirici `C` dizideki tüm işlemlerin denetlenebilir olduğunu gösterir.

```qsharp
function BoundC<'T> (operations : ('T => Unit is Ctl)[]) : ('T => Unit is Ctl)
```


## <a name="input"></a>Giriş

### <a name="operations--t--unit--is-ctl"></a>işlemler: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)  CTL []

Belirli bir girişte gerçekleştirilecek işlemler dizisi.



## <a name="output--t--unit--is-ctl"></a>Çıkış: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)  CTL

Belirli bir işlemi girişinde sırayla gerçekleştiren yeni bir işlem.

## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen

Dizideki her bir işlemin üzerinde işlem gören hedef.

## <a name="example"></a>Örnek

Aşağıdakiler eşdeğerdir:

```qsharp
let bound = BoundC([U, V]);
bound(x);
```

ve

```qsharp
U(x); V(x);
```

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Canon. bağlanacak](xref:Microsoft.Quantum.Canon.Bound)