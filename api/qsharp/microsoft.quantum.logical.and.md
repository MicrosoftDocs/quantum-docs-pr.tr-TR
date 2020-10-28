---
uid: Microsoft.Quantum.Logical.And
title: And işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: And
qsharp.summary: Returns the Boolean conjunction of two values.
ms.openlocfilehash: cc81f650216c4db219a79c4fe89a42447a4e95b8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731303"
---
# <a name="and-function"></a>And işlevi

Ad alanı: [Microsoft. hisse. Logical](xref:Microsoft.Quantum.Logical)

Leyebilir [](https://nuget.org/packages/)


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