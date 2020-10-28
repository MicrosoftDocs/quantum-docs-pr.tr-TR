---
uid: Microsoft.Quantum.Logical.LessThanOrEqualD
title: Lesskıt Okarşılandığından ald işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanOrEqualD
qsharp.summary: Returns true if and only if a number is less than or equal to another number.
ms.openlocfilehash: 7b0e9da379bd67eb78a80e7a535a15dcb8ba85c7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726035"
---
# <a name="lessthanorequald-function"></a>Lesskıt Okarşılandığından ald işlevi

Ad alanı: [Microsoft. hisse. Logical](xref:Microsoft.Quantum.Logical)

Leyebilir [](https://nuget.org/packages/)


Yalnızca bir sayı başka bir sayıdan küçük veya ona eşitse true değerini döndürür.

```qsharp
function LessThanOrEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a>Giriş

### <a name="a--double"></a>y: [Double](xref:microsoft.quantum.lang-ref.double)

Karşılaştırılacak ilk değer.


### <a name="b--double"></a>b: [Double](xref:microsoft.quantum.lang-ref.double)

Karşılaştırılacak ikinci değer.



## <a name="output--bool"></a>Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` ve yalnızca, değerinden `a` küçükse veya eşitse `b` .

## <a name="remarks"></a>Açıklamalar

Aşağıdakiler eşdeğerdir:

```Q#
let cond = a <= b;
let cond = LessThanOrEqualD(a, b);
```