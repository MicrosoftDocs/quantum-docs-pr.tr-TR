---
uid: Microsoft.Quantum.Convert.Call
title: Çağrı işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: Call
qsharp.summary: Calls a function with a given input.
ms.openlocfilehash: 8630f846b4b9823ce1c1dfd61dc8ca81e468517d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727571"
---
# <a name="call-operation"></a>Çağrı işlemi

Ad alanı: [Microsoft. hisse. Convert](xref:Microsoft.Quantum.Convert)

Leyebilir [](https://nuget.org/packages/)


Verilen bir girişi olan bir işlev çağırır.

```qsharp
operation Call<'Input, 'Output> (fn : ('Input -> 'Output), input : 'Input) : 'Output
```


## <a name="description"></a>Açıklama

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