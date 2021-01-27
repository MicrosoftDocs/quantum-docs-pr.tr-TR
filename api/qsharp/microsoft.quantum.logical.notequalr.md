---
uid: Microsoft.Quantum.Logical.NotEqualR
title: NotEqualR işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualR
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 39601396a75d8c1b9193d4b8f34fa05466beff06
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848510"
---
# <a name="notequalr-function"></a>NotEqualR işlevi

Ad alanı: [Microsoft. hisse. Logical](xref:Microsoft.Quantum.Logical)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Yalnızca iki giriş eşitse true değerini döndürür.

```qsharp
function NotEqualR (a : Result, b : Result) : Bool
```


## <a name="input"></a>Giriş

### <a name="a--__invalidresult__"></a>y: __geçersiz <Result>__

Karşılaştırılacak ilk değer.


### <a name="b--__invalidresult__"></a>b: __geçersiz <Result>__

Karşılaştırılacak ikinci değer.



## <a name="output--bool"></a>Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` ve yalnızca `a` değerine eşit değilse `b` .

## <a name="remarks"></a>Açıklamalar

Aşağıdakiler eşdeğerdir:

```qsharp
let cond = a != b;
let cond = NotEqualR(a, b);
```