---
uid: Microsoft.Quantum.Characterization.MeasureIdentity
title: Measureıdentity işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: MeasureIdentity
qsharp.summary: Measures the identity operator on a register of qubits.
ms.openlocfilehash: 71a103fddb3a27703318975bea94bc7a22a9ce81
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728184"
---
# <a name="measureidentity-operation"></a>Measureıdentity işlemi

Ad alanı: [Microsoft. hisse. karakterleştirme](xref:Microsoft.Quantum.Characterization)

Leyebilir [](https://nuget.org/packages/)


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