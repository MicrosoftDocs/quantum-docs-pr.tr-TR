---
uid: Microsoft.Quantum.Canon.CurriedOp
title: CurriedOp işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CurriedOp
qsharp.summary: >-
  Returns a curried version of an operation on two inputs.

  That is, given an operation with two inputs, this function applies Curry's isomorphism $f(x, y) \equiv f(x)(y)$ to return an operation of one input which returns an operation of one input.
ms.openlocfilehash: 13bc3e195d8a4ba26b726f96e4dc6b83da43c3e7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728784"
---
# <a name="curriedop-function"></a>CurriedOp işlevi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Leyebilir [](https://nuget.org/packages/)


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