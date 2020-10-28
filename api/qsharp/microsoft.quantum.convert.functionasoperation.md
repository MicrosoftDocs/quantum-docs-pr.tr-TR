---
uid: Microsoft.Quantum.Convert.FunctionAsOperation
title: FunctionAsOperation işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: FunctionAsOperation
qsharp.summary: Converts functions to operations.
ms.openlocfilehash: 90e9f0c922a77fbb6d6faf8945d4f5d1c8ff33b7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727560"
---
# <a name="functionasoperation-function"></a>FunctionAsOperation işlevi

Ad alanı: [Microsoft. hisse. Convert](xref:Microsoft.Quantum.Convert)

Leyebilir [](https://nuget.org/packages/)


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