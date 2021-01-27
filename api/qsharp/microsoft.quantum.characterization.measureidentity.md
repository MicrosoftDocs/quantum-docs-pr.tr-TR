---
uid: Microsoft.Quantum.Characterization.MeasureIdentity
title: Measureıdentity işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: MeasureIdentity
qsharp.summary: Measures the identity operator on a register of qubits.
ms.openlocfilehash: f8cf5975ac9407e8c532ace08455a41d3c08d6f0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851818"
---
# <a name="measureidentity-operation"></a>Measureıdentity işlemi

Ad alanı: [Microsoft. hisse. karakterleştirme](xref:Microsoft.Quantum.Characterization)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Qubits 'in bir kaydındaki kimlik işlecini ölçer.

```qsharp
operation MeasureIdentity (register : Qubit[]) : Result
```


## <a name="input"></a>Giriş

### <a name="register--qubit"></a>kaydol: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Ölçülecek kayıt.



## <a name="output--__invalidresult__"></a>Çıkış: __geçersiz <Result>__

Sonuç değeri `Zero` .

## <a name="remarks"></a>Açıklamalar

$ \Cıvadone $ yalnızca eigenvalue $1 $ olduğundan ve negatif bir eigenvalue olmadığından, bu işlem her zaman `Zero` , eigenvalue $ + 1 = (-1) ^ 0 $ öğesine karşılık gelir ve durumunun daraltımasına neden olmaz `register` .

Bu işlem, kendi kendine yararlı değildir, ancak bir hisse işleminin izleme koruması hakkında bilgi sağladığından işlem tografı bağlamında faydalıdır.
Özellikle, kayıplı ölçeli bir hedef makine, bu işlemi $ \cıvadone $ gerçek ölçimiyle değiştirecek.