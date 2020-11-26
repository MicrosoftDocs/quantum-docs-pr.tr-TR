---
uid: Microsoft.Quantum.Canon.UncurriedOpCA
title: UncurriedOpCA işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpCA
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `CA` indicates that the operations are controllable and adjointable.
ms.openlocfilehash: 45526c0202e417213aab3fe7819827588e794e23
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216396"
---
# <a name="uncurriedopca-function"></a>UncurriedOpCA işlevi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


İşlemleri döndüren bir işlev verildiğinde, her iki girişi de tanımlama grubu olarak alan yeni bir işlem döndürür.
Değiştirici, `CA` işlemlerin denetlenebilir ve adjointable olduğunu gösterir.

```qsharp
function UncurriedOpCA<'T, 'U> (curriedOp : ('T -> ('U => Unit is Ctl + Adj))) : (('T, 'U) => Unit is Ctl + Adj)
```


## <a name="input"></a>Giriş

### <a name="curriedop--t---u--unit--is-adj--ctl"></a>curriedOp: 'T-> ' U => [birimi](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL

İşlemleri döndüren bir işlev.



## <a name="output--tu--unit--is-adj--ctl"></a>Çıkış: ('T, ' U) => [birimi](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL

`op`İle eşdeğer olan yeni bir işlem `op(t, u)` `(curriedOp(t))(u)` .

## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen

Bir curried işlevinin ilk bağımsız değişkeninin türü.
### <a name="u"></a>' U

Bir curried işlevinin ikinci bağımsız değişkeninin türü.

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Canon. UncurriedOp](xref:Microsoft.Quantum.Canon.UncurriedOp)