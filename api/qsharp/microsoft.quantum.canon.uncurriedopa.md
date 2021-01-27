---
uid: Microsoft.Quantum.Canon.UncurriedOpA
title: UncurriedOpA işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpA
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `A` indicates that the operations are adjointable.
ms.openlocfilehash: feb5da771ee6cb6a750fa76f9ffd8f5a3e0b5734
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840063"
---
# <a name="uncurriedopa-function"></a>UncurriedOpA işlevi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


İşlemleri döndüren bir işlev verildiğinde, her iki girişi de tanımlama grubu olarak alan yeni bir işlem döndürür.
Değiştirici, `A` işlemlerin adjointable olduğunu gösterir.

```qsharp
function UncurriedOpA<'T, 'U> (curriedOp : ('T -> ('U => Unit is Adj))) : (('T, 'U) => Unit is Adj)
```


## <a name="input"></a>Giriş

### <a name="curriedop--t---u--unit--is-adj"></a>curriedOp: 'T-> ' U => [birimi](xref:microsoft.quantum.lang-ref.unit)  sıfatı

İşlemleri döndüren bir işlev.



## <a name="output--tu--unit--is-adj"></a>Çıkış: ('T, ' U) => [birimi](xref:microsoft.quantum.lang-ref.unit)  sıfatı

`op`İle eşdeğer olan yeni bir işlem `op(t, u)` `(curriedOp(t))(u)` .

## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen

Bir curried işlevinin ilk bağımsız değişkeninin türü.
### <a name="u"></a>' U

Bir curried işlevinin ikinci bağımsız değişkeninin türü.

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Canon. UncurriedOp](xref:Microsoft.Quantum.Canon.UncurriedOp)