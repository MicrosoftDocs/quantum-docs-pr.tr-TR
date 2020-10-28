---
uid: Microsoft.Quantum.Logical.LessThanL
title: Lessbir l işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanL
qsharp.summary: Returns true if and only if a number is less than another number.
ms.openlocfilehash: fde57bcd9960056461bddac54300c298def8f7d5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726036"
---
# <a name="lessthanl-function"></a>Lessbir l işlevi

Ad alanı: [Microsoft. hisse. Logical](xref:Microsoft.Quantum.Logical)

Leyebilir [](https://nuget.org/packages/)


Yalnızca bir sayı başka bir sayıdan küçükse true değerini döndürür.

```qsharp
function LessThanL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a>Giriş

### <a name="a--bigint"></a>y: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

Karşılaştırılacak ilk değer.


### <a name="b--bigint"></a>b: büyük [tamsayı](xref:microsoft.quantum.lang-ref.bigint)

Karşılaştırılacak ikinci değer.



## <a name="output--bool"></a>Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` yalnızca ve ' `a` den tamamen küçükse `b` .

## <a name="remarks"></a>Açıklamalar

Aşağıdakiler eşdeğerdir:

```Q#
let cond = a < b;
let cond = LessThanL(a, b);
```