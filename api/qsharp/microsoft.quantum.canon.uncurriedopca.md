---
uid: Microsoft.Quantum.Canon.UncurriedOpCA
title: UncurriedOpCA işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpCA
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `CA` indicates that the operations are controllable and adjointable.
ms.openlocfilehash: 6a0f2e1b345d0ba3ac5c779c5dc2bfffaf659a0b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728286"
---
# <a name="uncurriedopca-function"></a>UncurriedOpCA işlevi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Leyebilir [](https://nuget.org/packages/)


İşlemleri döndüren bir işlev verildiğinde, her iki girişi de tanımlama grubu olarak alan yeni bir işlem döndürür.
Değiştirici, `CA` işlemlerin denetlenebilir ve adjointable olduğunu gösterir.

```qsharp
function UncurriedOpCA<'T, 'U> (curriedOp : ('T -> ('U => Unit is Ctl + Adj))) : (('T, 'U) => Unit is Ctl + Adj)
```


## <a name="input"></a>Giriş

### <a name="curriedop--t---u--unit-ctl--adj"></a>curriedOp: 'T-> ' U => [birim](xref:microsoft.quantum.lang-ref.unit) CTL + ayarlanabilir

İşlemleri döndüren bir işlev.



## <a name="output--tu--unit-ctl--adj"></a>Çıkış: ('T, ' U) => [Unit](xref:microsoft.quantum.lang-ref.unit) CTL + ayarlanabilir

`op`İle eşdeğer olan yeni bir işlem `op(t, u)` `(curriedOp(t))(u)` .

## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen

Bir curried işlevinin ilk bağımsız değişkeninin türü.
### <a name="u"></a>' U

Bir curried işlevinin ikinci bağımsız değişkeninin türü.

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Canon. UncurriedOp](xref:Microsoft.Quantum.Canon.UncurriedOp)