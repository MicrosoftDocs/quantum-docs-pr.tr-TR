---
uid: Microsoft.Quantum.Logical.EqualR
title: EqualR işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualR
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 5aaa17303d75b27c3ac82cbe7d739a60016fdcb1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726071"
---
# <a name="equalr-function"></a>EqualR işlevi

Ad alanı: [Microsoft. hisse. Logical](xref:Microsoft.Quantum.Logical)

Leyebilir [](https://nuget.org/packages/)


Yalnızca iki giriş eşitse true değerini döndürür.

```qsharp
function EqualR (a : Result, b : Result) : Bool
```


## <a name="input"></a>Giriş

### <a name="a--__invalidresult__"></a>y: __geçersiz <Result>__

Karşılaştırılacak ilk değer.


### <a name="b--__invalidresult__"></a>b: __geçersiz <Result>__

Karşılaştırılacak ikinci değer.



## <a name="output--bool"></a>Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` ve yalnızca `a` eşitse `b` .

## <a name="remarks"></a>Açıklamalar

Aşağıdakiler eşdeğerdir:

```Q#
let cond = a == b;
let cond = EqualR(a, b);
```