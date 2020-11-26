---
uid: Microsoft.Quantum.Convert.Call
title: Çağrı işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: Call
qsharp.summary: Calls a function with a given input.
ms.openlocfilehash: 92c159cef878fb587b0ed514fd6660dd19527cab
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214220"
---
# <a name="call-operation"></a>Çağrı işlemi

Ad alanı: [Microsoft. hisse. Convert](xref:Microsoft.Quantum.Convert)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


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