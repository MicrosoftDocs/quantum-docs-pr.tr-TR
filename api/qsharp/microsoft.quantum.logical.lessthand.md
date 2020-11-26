---
uid: Microsoft.Quantum.Logical.LessThanD
title: LessThanD işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanD
qsharp.summary: Returns true if and only if a number is less than another number.
ms.openlocfilehash: 40f059e49affbb1b5af7dc349f6ee53dfb357873
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197747"
---
# <a name="lessthand-function"></a>LessThanD işlevi

Ad alanı: [Microsoft. hisse. Logical](xref:Microsoft.Quantum.Logical)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Yalnızca bir sayı başka bir sayıdan küçükse true değerini döndürür.

```qsharp
function LessThanD (a : Double, b : Double) : Bool
```


## <a name="input"></a>Giriş

### <a name="a--double"></a>y: [Double](xref:microsoft.quantum.lang-ref.double)

Karşılaştırılacak ilk değer.


### <a name="b--double"></a>b: [Double](xref:microsoft.quantum.lang-ref.double)

Karşılaştırılacak ikinci değer.



## <a name="output--bool"></a>Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` yalnızca ve ' `a` den tamamen küçükse `b` .

## <a name="remarks"></a>Açıklamalar

Aşağıdakiler eşdeğerdir:

```Q#
let cond = a < b;
let cond = LessThanD(a, b);
```