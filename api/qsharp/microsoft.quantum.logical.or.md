---
uid: Microsoft.Quantum.Logical.Or
title: OR işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Or
qsharp.summary: Returns the Boolean disjunction of two values.
ms.openlocfilehash: 98a416229386461b241d087b7ae95f078f8be70a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730754"
---
# <a name="or-function"></a>OR işlevi

Ad alanı: [Microsoft. hisse. Logical](xref:Microsoft.Quantum.Logical)

Leyebilir [](https://nuget.org/packages/)


İki değerden oluşan Boole birleşim durumunu döndürür.

```qsharp
function Or (a : Bool, b : Bool) : Bool
```


## <a name="input"></a>Giriş

### <a name="a--bool"></a>y: [bool](xref:microsoft.quantum.lang-ref.bool)

Göz önünde bulundurmanız için ilk değer.


### <a name="b--bool"></a>b: [bool](xref:microsoft.quantum.lang-ref.bool)

Göz önünde bulundurmanız için ikinci değer.



## <a name="output--bool"></a>Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` yalnızca ya da varsa `a` `b` `true` .

## <a name="remarks"></a>Açıklamalar

İşlecin aksine `or` , bu işlev kısa devre değildir, her iki giriş de tam olarak değerlendirilir.

En fazla kısa devre davranýþý, şunlar eşdeğerdir:

```Q#
let x = a or b;
let x = Or(a, b);
```