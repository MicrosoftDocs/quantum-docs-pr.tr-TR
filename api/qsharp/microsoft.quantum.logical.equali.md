---
uid: Microsoft.Quantum.Logical.EqualI
title: EqualI işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualI
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 6b805e76217e033cb0135cf85bd8f37a3eb8636a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726078"
---
# <a name="equali-function"></a>EqualI işlevi

Ad alanı: [Microsoft. hisse. Logical](xref:Microsoft.Quantum.Logical)

Leyebilir [](https://nuget.org/packages/)


Yalnızca iki giriş eşitse true değerini döndürür.

```qsharp
function EqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a>Giriş

### <a name="a--int"></a>y: [Int](xref:microsoft.quantum.lang-ref.int)

Karşılaştırılacak ilk değer.


### <a name="b--int"></a>b: [Int](xref:microsoft.quantum.lang-ref.int)

Karşılaştırılacak ikinci değer.



## <a name="output--bool"></a>Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` ve yalnızca `a` eşitse `b` .

## <a name="remarks"></a>Açıklamalar

Aşağıdakiler eşdeğerdir:

```Q#
let cond = a == b;
let cond = EqualI(a, b);
```