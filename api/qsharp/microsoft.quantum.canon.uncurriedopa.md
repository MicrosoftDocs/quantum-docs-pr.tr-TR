---
uid: Microsoft.Quantum.Canon.UncurriedOpA
title: UncurriedOpA işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpA
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `A` indicates that the operations are adjointable.
ms.openlocfilehash: 21df20354ad2388891f32b1bf1c7781287904983
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728292"
---
# <a name="uncurriedopa-function"></a>UncurriedOpA işlevi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Leyebilir [](https://nuget.org/packages/)


İşlemleri döndüren bir işlev verildiğinde, her iki girişi de tanımlama grubu olarak alan yeni bir işlem döndürür.
Değiştirici, `A` işlemlerin adjointable olduğunu gösterir.

```qsharp
function UncurriedOpA<'T, 'U> (curriedOp : ('T -> ('U => Unit is Adj))) : (('T, 'U) => Unit is Adj)
```


## <a name="input"></a>Giriş

### <a name="curriedop--t---u--unit-adj"></a>curriedOp: 'T-> ' U => [Unit](xref:microsoft.quantum.lang-ref.unit) ayarlaması

İşlemleri döndüren bir işlev.



## <a name="output--tu--unit-adj"></a>Çıkış: ('T, ' U) => [Unit](xref:microsoft.quantum.lang-ref.unit) ayarlaması

`op`İle eşdeğer olan yeni bir işlem `op(t, u)` `(curriedOp(t))(u)` .

## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen

Bir curried işlevinin ilk bağımsız değişkeninin türü.
### <a name="u"></a>' U

Bir curried işlevinin ikinci bağımsız değişkeninin türü.

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Canon. UncurriedOp](xref:Microsoft.Quantum.Canon.UncurriedOp)