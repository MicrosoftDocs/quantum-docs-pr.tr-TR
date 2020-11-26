---
uid: Microsoft.Quantum.Logical.LessThanOrEqualD
title: Lesskıt Okarşılandığından ald işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanOrEqualD
qsharp.summary: Returns true if and only if a number is less than or equal to another number.
ms.openlocfilehash: 3f4ccb0888e7df7c43ff73be8a3140e3fa84d4dc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197645"
---
# <a name="lessthanorequald-function"></a>Lesskıt Okarşılandığından ald işlevi

Ad alanı: [Microsoft. hisse. Logical](xref:Microsoft.Quantum.Logical)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


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