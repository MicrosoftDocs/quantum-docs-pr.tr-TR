---
uid: Microsoft.Quantum.Logical.Conditioned
title: Koşullu işlev
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Conditioned
qsharp.summary: Returns one of two values, depending on the value of a Boolean condition.
ms.openlocfilehash: ea3b8eba960acceb6540978c6fccd9f796b0f67d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98817296"
---
# <a name="conditioned-function"></a>Koşullu işlev

Ad alanı: [Microsoft. hisse. Logical](xref:Microsoft.Quantum.Logical)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


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

```qsharp
let x = condition ? ifTrue | ifFalse;
let x = Conditioned(condition, ifTrue, ifFalse);
```