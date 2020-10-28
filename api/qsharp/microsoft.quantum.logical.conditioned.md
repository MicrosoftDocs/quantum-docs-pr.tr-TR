---
uid: Microsoft.Quantum.Logical.Conditioned
title: Koşullu işlev
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Conditioned
qsharp.summary: Returns one of two values, depending on the value of a Boolean condition.
ms.openlocfilehash: 8aabe8b018129ddee3b934c207d0a62e59fb6f4a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731295"
---
# <a name="conditioned-function"></a>Koşullu işlev

Ad alanı: [Microsoft. hisse. Logical](xref:Microsoft.Quantum.Logical)

Leyebilir [](https://nuget.org/packages/)


Boole koşulunun değerine bağlı olarak iki değerden birini döndürür.

```qsharp
function Conditioned<'T> (condition : Bool, ifTrue : 'T, ifFalse : 'T) : 'T
```


## <a name="input"></a>Giriş

### <a name="condition--bool"></a>koşul: [bool](xref:microsoft.quantum.lang-ref.bool)

Hangi girişin döndürüleceğini denetlemek için kullanılan bir koşul.


### <a name="iftrue--t"></a>IfTrue: 'T

Olduğunda döndürülecek değer `condition` `true` .


### <a name="iffalse--t"></a>IfFalse: 'T

Olduğunda döndürülecek değer `condition` `false` .



## <a name="output--t"></a>Çıkış: 'T

`ifTrue` ise `condition` `true` ve `ifFalse` Aksi durumda.

## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen



## <a name="remarks"></a>Açıklamalar

İşlecin aksine `?|` , bu işlev kısa devre değildir, her iki giriş de tam olarak değerlendirilir.

En fazla kısa devre davranýþý, şunlar eşdeğerdir:

```Q#
let x = condition ? ifTrue | ifFalse;
let x = Conditioned(condition, ifTrue, ifFalse);
```