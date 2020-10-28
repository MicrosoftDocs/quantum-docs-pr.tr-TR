---
uid: Microsoft.Quantum.Logical.LessThanOrEqualI
title: Lesskıdan Okarşılandığından ali işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanOrEqualI
qsharp.summary: Returns true if and only if a number is less than or equal to another number.
ms.openlocfilehash: dd934fde3fae9c1a43032b4b08ac03afa72798d1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726029"
---
# <a name="lessthanorequali-function"></a>Lesskıdan Okarşılandığından ali işlevi

Ad alanı: [Microsoft. hisse. Logical](xref:Microsoft.Quantum.Logical)

Leyebilir [](https://nuget.org/packages/)


Yalnızca bir sayı başka bir sayıdan küçük veya ona eşitse true değerini döndürür.

```qsharp
function LessThanOrEqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a>Giriş

### <a name="a--int"></a>y: [Int](xref:microsoft.quantum.lang-ref.int)

Karşılaştırılacak ilk değer.


### <a name="b--int"></a>b: [Int](xref:microsoft.quantum.lang-ref.int)

Karşılaştırılacak ikinci değer.



## <a name="output--bool"></a>Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` ve yalnızca, değerinden `a` küçükse veya eşitse `b` .

## <a name="remarks"></a>Açıklamalar

Aşağıdakiler eşdeğerdir:

```Q#
let cond = a <= b;
let cond = LessThanOrEqualI(a, b);
```