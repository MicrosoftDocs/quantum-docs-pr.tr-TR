---
uid: Microsoft.Quantum.Convert.FunctionAsOperation
title: FunctionAsOperation işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: FunctionAsOperation
qsharp.summary: Converts functions to operations.
ms.openlocfilehash: 10703818242cf6b3853f08a45bfb9094f397f6c2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224386"
---
# <a name="functionasoperation-function"></a>FunctionAsOperation işlevi

Ad alanı: [Microsoft. hisse. Convert](xref:Microsoft.Quantum.Convert)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


İşlevleri işlemlere dönüştürür.

```qsharp
function FunctionAsOperation<'Input, 'Output> (fn : ('Input -> 'Output)) : ('Input => 'Output)
```


## <a name="description"></a>Açıklama

Bir işlev verildiğinde, bu işlevi çağıran ve başka hiçbir şey yapan bir işlem döndürür.

## <a name="input"></a>Giriş

### <a name="fn--input---output"></a>FN: ' Input-> ' çıkışı

Bir işleme dönüştürülecek bir işlev.



## <a name="output--input--output"></a>Çıkış: ' Input => ' çıkışı 

Bir işlem `op` `op(input)` , tümü için ile özdeş `fn(input)` `input` .

## <a name="type-parameters"></a>Tür Parametreleri

### <a name="input"></a>' Giriş

Dönüştürülecek işlevin giriş türü.
### <a name="output"></a>' Çıkış

Dönüştürülecek işlevin çıkış türü.

## <a name="remarks"></a>Açıklamalar

Bu, genellikle bir işlemi giriş olarak bekleyen işlevlere veya işlemlere geçirmek için kullanışlıdır.