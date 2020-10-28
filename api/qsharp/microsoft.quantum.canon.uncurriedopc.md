---
uid: Microsoft.Quantum.Canon.UncurriedOpC
title: UncurriedOpC işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpC
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `C` indicates that the operations are controllable.
ms.openlocfilehash: f3e5ecf3f7df0393dfbb948f064c27505f04cfcf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728291"
---
# <a name="uncurriedopc-function"></a>UncurriedOpC işlevi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Leyebilir [](https://nuget.org/packages/)


İşlemleri döndüren bir işlev verildiğinde, her iki girişi de tanımlama grubu olarak alan yeni bir işlem döndürür.
Değiştirici, `C` işlemlerin denetlenebilir olduğunu gösterir.

```qsharp
function UncurriedOpC<'T, 'U> (curriedOp : ('T -> ('U => Unit is Ctl))) : (('T, 'U) => Unit is Ctl)
```


## <a name="input"></a>Giriş

### <a name="curriedop--t---u--unit-ctl"></a>curriedOp: 'T-> ' U => [birim](xref:microsoft.quantum.lang-ref.unit) CTL

İşlemleri döndüren bir işlev.



## <a name="output--tu--unit-ctl"></a>Çıkış: ('T, ' U) => [birim](xref:microsoft.quantum.lang-ref.unit) CTL

`op`İle eşdeğer olan yeni bir işlem `op(t, u)` `(curriedOp(t))(u)` .

## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen

Bir curried işlevinin ilk bağımsız değişkeninin türü.
### <a name="u"></a>' U

Bir curried işlevinin ikinci bağımsız değişkeninin türü.

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Canon. UncurriedOp](xref:Microsoft.Quantum.Canon.UncurriedOp)