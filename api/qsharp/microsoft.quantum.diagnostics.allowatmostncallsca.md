---
uid: Microsoft.Quantum.Diagnostics.AllowAtMostNCallsCA
title: AllowAtMostNCallsCA işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllowAtMostNCallsCA
qsharp.summary: Between a call to this operation and its adjoint, asserts that a given operation is called at most a certain number of times.
ms.openlocfilehash: bb6ba2615b571b0d9d056b93f8e36d2dec0c4a21
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853531"
---
# <a name="allowatmostncallsca-operation"></a>AllowAtMostNCallsCA işlemi

Ad alanı: [Microsoft. hisse. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bu işleme ve Adjoint çağrısı arasında, belirli bir işlemin en çok birkaç kez çağrıldığını onaylar.

```qsharp
operation AllowAtMostNCallsCA<'TInput, 'TOutput> (nTimes : Int, op : ('TInput => 'TOutput is Adj + Ctl), message : String) : Unit is Adj
```


## <a name="input"></a>Giriş

### <a name="ntimes--int"></a>nTimes: [Int](xref:microsoft.quantum.lang-ref.int)

Çağrılabilen en fazla sayı `op` .


### <a name="op--tinput--toutput--is-adj--ctl"></a>Op: ' TInput => ' TOutput, sıfatı + CTL

Çağrıları kısıtlanmış olan bir işlem.


### <a name="message--string"></a>ileti: [dize](xref:microsoft.quantum.lang-ref.string)

Hata durumunda görüntülenecek bir ileti.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Tür Parametreleri

### <a name="tinput"></a>' TInput


### <a name="toutput"></a>' TOutput



## <a name="example"></a>Örnek

Aşağıdaki kod parçacığı, bu tanılamayı destekleyen makinelerde yürütüldüğünde başarısız olur:

```qsharp
using (register = Qubit[4]) {
    within {
        AllowAtMostNCallsCA(3, H, "Too many calls to H.");
    } apply {
        // Fails since this calls H four times, rather than the
        // allowed maximum of three.
        ApplyToEach(H, register);
    }
}
```

## <a name="remarks"></a>Açıklamalar

Bu işlem, onu desteklemeyen hedefler üzerinde bir işleç ile değiştirilebilir.