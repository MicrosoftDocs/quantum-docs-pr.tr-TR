---
uid: Microsoft.Quantum.Convert.FunctionAsOperation
title: FunctionAsOperation işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: FunctionAsOperation
qsharp.summary: Converts functions to operations.
ms.openlocfilehash: cf4f8c97bf38b3a64eb952d0a502bc21c29c579c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98833833"
---
# <a name="functionasoperation-function"></a>FunctionAsOperation işlevi

Ad alanı: [Microsoft. hisse. Convert](xref:Microsoft.Quantum.Convert)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


İşlevleri işlemlere dönüştürür.

```qsharp
function FunctionAsOperation<'Input, 'Output> (fn : ('Input -> 'Output)) : ('Input => 'Output)
```


## <a name="description"></a>Description

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