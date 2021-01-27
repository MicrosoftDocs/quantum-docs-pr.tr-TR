---
uid: Microsoft.Quantum.Canon.UncurriedOp
title: UncurriedOp işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOp
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple.
ms.openlocfilehash: d707b52bb17f4dea795fa4ff824c785e506b8b20
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852002"
---
# <a name="uncurriedop-function"></a>UncurriedOp işlevi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


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