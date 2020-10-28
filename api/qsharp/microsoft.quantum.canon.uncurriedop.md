---
uid: Microsoft.Quantum.Canon.UncurriedOp
title: UncurriedOp işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOp
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple.
ms.openlocfilehash: 359c0b2a9dd56445fb39fadc6580809dd9fbf628
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728303"
---
# <a name="uncurriedop-function"></a>UncurriedOp işlevi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Leyebilir [](https://nuget.org/packages/)


İşlemleri döndüren bir işlev verildiğinde, her iki girişi de tanımlama grubu olarak alan yeni bir işlem döndürür.

```qsharp
function UncurriedOp<'T, 'U> (curriedOp : ('T -> ('U => Unit))) : (('T, 'U) => Unit)
```


## <a name="input"></a>Giriş

### <a name="curriedop--t---u--unit"></a>curriedOp: 'T-> ' U => [Unit](xref:microsoft.quantum.lang-ref.unit) 

İşlemleri döndüren bir işlev.



## <a name="output--tu--unit"></a>Çıkış: ('T, ' U) => [birimi](xref:microsoft.quantum.lang-ref.unit) 

`op`İle eşdeğer olan yeni bir işlem `op(t, u)` `(curriedOp(t))(u)` .

## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen

Bir curried işlemine ilk girişin türü.
### <a name="u"></a>' U

Bir curried işlemine ikinci girişin türü.

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Canon. UncurriedOpC](xref:Microsoft.Quantum.Canon.UncurriedOpC)
- [Microsoft. hisse. Canon. UncurriedOpA](xref:Microsoft.Quantum.Canon.UncurriedOpA)
- [Microsoft. hisse. Canon. UncurriedOpCA](xref:Microsoft.Quantum.Canon.UncurriedOpCA)