---
uid: Microsoft.Quantum.Diagnostics.AllowAtMostNCallsCA
title: AllowAtMostNCallsCA işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllowAtMostNCallsCA
qsharp.summary: Between a call to this operation and its adjoint, asserts that a given operation is called at most a certain number of times.
ms.openlocfilehash: 1a9975d2d2026749238430b247cf47738de545cd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727368"
---
# <a name="allowatmostncallsca-operation"></a>AllowAtMostNCallsCA işlemi

Ad alanı: [Microsoft. hisse. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Leyebilir [](https://nuget.org/packages/)


Bu işleme ve Adjoint çağrısı arasında, belirli bir işlemin en çok birkaç kez çağrıldığını onaylar.

```qsharp
operation AllowAtMostNCallsCA<'TInput, 'TOutput> (nTimes : Int, op : ('TInput => 'TOutput is Adj + Ctl), message : String) : Unit
```


## <a name="input"></a>Giriş

### <a name="ntimes--int"></a>nTimes: [Int](xref:microsoft.quantum.lang-ref.int)

Çağrılabilen en fazla sayı `op` .


### <a name="op--tinput--toutput-adj--ctl"></a>Op: ' TInput => ' TOutput ayarlama + CTL

Çağrıları kısıtlanmış olan bir işlem.


### <a name="message--string"></a>ileti: [dize](xref:microsoft.quantum.lang-ref.string)

Hata durumunda görüntülenecek bir ileti.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Tür Parametreleri

### <a name="tinput"></a>' TInput


### <a name="toutput"></a>' TOutput



## <a name="remarks"></a>Açıklamalar

Bu işlem, onu desteklemeyen hedefler üzerinde bir işleç ile değiştirilebilir.