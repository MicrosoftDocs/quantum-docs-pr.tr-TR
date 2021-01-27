---
uid: Microsoft.Quantum.Convert.Call
title: Çağrı işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: Call
qsharp.summary: Calls a function with a given input.
ms.openlocfilehash: 93458d08aa83ffa8b7b33de8bf51c970af291db9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850205"
---
# <a name="call-operation"></a>Çağrı işlemi

Ad alanı: [Microsoft. hisse. Convert](xref:Microsoft.Quantum.Convert)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Verilen bir girişi olan bir işlev çağırır.

```qsharp
operation Call<'Input, 'Output> (fn : ('Input -> 'Output), input : 'Input) : 'Output
```


## <a name="description"></a>Description

Bir işlev ve bu işleve bir giriş verildiğinde, işlevi çağırır ve çıktısını döndürür.

## <a name="input"></a>Giriş

### <a name="fn--input---output"></a>FN: ' Input-> ' çıkışı

Çağrılacak işlev.


### <a name="input--input"></a>Giriş: ' giriş

İşleve geçirilecek giriş.



## <a name="output--output"></a>Çıkış: ' çıkış

Çağırmanın sonucu `fn` .

## <a name="type-parameters"></a>Tür Parametreleri

### <a name="input"></a>' Giriş


### <a name="output"></a>' Çıkış



## <a name="remarks"></a>Açıklamalar

Bu işlem, bir işlevin bir işlem içinde belirli bir yerde çağrılmasını zorlamak için veya bir işlemin beklendiği bir işlevi çağırmak için kullanışlıdır.