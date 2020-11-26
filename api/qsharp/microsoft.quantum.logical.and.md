---
uid: Microsoft.Quantum.Logical.And
title: And işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: And
qsharp.summary: Returns the Boolean conjunction of two values.
ms.openlocfilehash: 279221ed785dd76e28146e4c22e70290936bf529
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198580"
---
# <a name="and-function"></a>And işlevi

Ad alanı: [Microsoft. hisse. Logical](xref:Microsoft.Quantum.Logical)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


İki değerden oluşan Boole değeri döndürür.

```qsharp
function And (a : Bool, b : Bool) : Bool
```


## <a name="input"></a>Giriş

### <a name="a--bool"></a>y: [bool](xref:microsoft.quantum.lang-ref.bool)

Göz önünde bulundurmanız için ilk değer.


### <a name="b--bool"></a>b: [bool](xref:microsoft.quantum.lang-ref.bool)

Göz önünde bulundurmanız için ikinci değer.



## <a name="output--bool"></a>Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` ve yalnızca ise `a` ve ise `b` `true` .

## <a name="remarks"></a>Açıklamalar

İşlecin aksine `and` , bu işlev kısa devre değildir, her iki giriş de tam olarak değerlendirilir.

En fazla kısa devre davranýþý, şunlar eşdeğerdir:

```Q#
let x = a and b;
let x = And(a, b);
```