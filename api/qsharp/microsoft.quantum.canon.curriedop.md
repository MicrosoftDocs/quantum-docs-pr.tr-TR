---
uid: Microsoft.Quantum.Canon.CurriedOp
title: CurriedOp işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CurriedOp
qsharp.summary: >-
  Returns a curried version of an operation on two inputs.

  That is, given an operation with two inputs, this function applies Curry's isomorphism $f(x, y) \equiv f(x)(y)$ to return an operation of one input which returns an operation of one input.
ms.openlocfilehash: f811347d65a6460690163e9df631979c906bd89f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840777"
---
# <a name="curriedop-function"></a>CurriedOp işlevi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


İki giriş üzerinde bir işlemin curried sürümünü döndürür.

Diğer bir deyişle, iki girişli bir işlem söz konusu olduğunda, bu işlev bir girişin bir işlemini döndüren tek bir girdinin işlemini döndürmek için Curry 'nin isomorphism $f (x, y) \equf (x) (y) $ ' u uygular.

```qsharp
function CurriedOp<'T, 'U> (op : (('T, 'U) => Unit)) : ('T -> ('U => Unit))
```


## <a name="input"></a>Giriş

### <a name="op--tu--unit"></a>Op: ('T, ' U) => [birimi](xref:microsoft.quantum.lang-ref.unit) 

Girdisi bir çift olan bir işlem.



## <a name="output--t---u--unit"></a>Çıkış: 'T-> ' U => [Unit](xref:microsoft.quantum.lang-ref.unit) 

Bir çiftin ilk öğesini kabul eden ve özgün işlem girişinin ikinci öğesini girdi olarak kabul eden bir işlem döndüren bir işlem.

## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen

Çiftler üzerinde tanımlanan bir işlevin ilk bileşen türü.
### <a name="u"></a>' U

Çiftler üzerinde tanımlanan bir işlevin ikinci bileşen türü.

## <a name="remarks"></a>Açıklamalar

Aşağıdakiler eşdeğerdir:

```qsharp
op(x, y);

let curried = CurriedOp(op);
let partial = curried(x);
partial(y);
```