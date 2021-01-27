---
uid: Microsoft.Quantum.Logical.GreaterThanOrEqualI
title: GreaterThanOrEqualI işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanOrEqualI
qsharp.summary: Returns true if and only if a number is greater than or equal to another number.
ms.openlocfilehash: c1a513500c8a70bd7628976974387cba48162e80
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849177"
---
# <a name="greaterthanorequali-function"></a>GreaterThanOrEqualI işlevi

Ad alanı: [Microsoft. hisse. Logical](xref:Microsoft.Quantum.Logical)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Yalnızca bir sayı başka bir sayıdan büyük veya buna eşitse true değerini döndürür.

```qsharp
function GreaterThanOrEqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a>Giriş

### <a name="a--int"></a>y: [Int](xref:microsoft.quantum.lang-ref.int)

Karşılaştırılacak ilk değer.


### <a name="b--int"></a>b: [Int](xref:microsoft.quantum.lang-ref.int)

Karşılaştırılacak ikinci değer.



## <a name="output--bool"></a>Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` ve yalnızca `a` değerinden büyükse veya eşitse `b` .

## <a name="remarks"></a>Açıklamalar

Aşağıdakiler eşdeğerdir:

```qsharp
let cond = a >= b;
let cond = GreaterThanOrEqualI(a, b);
```