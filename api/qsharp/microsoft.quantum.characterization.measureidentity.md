---
uid: Microsoft.Quantum.Characterization.MeasureIdentity
title: Measureıdentity işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: MeasureIdentity
qsharp.summary: Measures the identity operator on a register of qubits.
ms.openlocfilehash: 4a169355d0669c67f0eb14c80e8554b2f24b035a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216124"
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