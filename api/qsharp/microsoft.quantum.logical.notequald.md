---
uid: Microsoft.Quantum.Logical.NotEqualD
title: NotEqualD işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualD
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: dd21fcc1d0d73bd210303bfbf4f336386b912107
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732919"
---
# <a name="notequald-function"></a>NotEqualD işlevi

Ad alanı: [Microsoft. hisse. Logical](xref:Microsoft.Quantum.Logical)

Leyebilir [](https://nuget.org/packages/)


Yalnızca iki giriş eşitse true değerini döndürür.

```qsharp
function NotEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a>Giriş

### <a name="a--double"></a>y: [Double](xref:microsoft.quantum.lang-ref.double)

Karşılaştırılacak ilk değer.


### <a name="b--double"></a>b: [Double](xref:microsoft.quantum.lang-ref.double)

Karşılaştırılacak ikinci değer.



## <a name="output--bool"></a>Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` ve yalnızca `a` değerine eşit değilse `b` .

## <a name="remarks"></a>Açıklamalar

Aşağıdakiler eşdeğerdir:

```Q#
let cond = a != b;
let cond = NotEqualD(a, b);
```