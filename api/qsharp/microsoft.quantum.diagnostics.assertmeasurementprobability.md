---
uid: Microsoft.Quantum.Diagnostics.AssertMeasurementProbability
title: AssertMeasurementProbability işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertMeasurementProbability
qsharp.summary: Asserts that measuring the given qubits in the given Pauli basis will have the given result with the given probability, within some tolerance.
ms.openlocfilehash: 032b9224ad728f0637596668c2928a889deeba55
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202371"
---
# <a name="assertmeasurementprobability-operation"></a>AssertMeasurementProbability işlemi

Ad alanı: [Microsoft. hisse. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Verilen Pabdtabanında verilen qubit 'leri ölçmeye yönelik onaylar, belirli bir tolerans dahilinde verilen olasılığa sahip olur.

```qsharp
operation AssertMeasurementProbability (bases : Pauli[], qubits : Qubit[], result : Result, prob : Double, msg : String, tol : Double) : Unit is Adj + Ctl
```


## <a name="input"></a>Giriş

### <a name="bases--pauli"></a>tabanlar: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

Bir multi-qubit Pauli işleci olarak ifade edilen olasılığını onaylama için bir ölçüm etkisi.


### <a name="qubits--qubit"></a>qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Onaylama yapılacak bir kayıt.


### <a name="result--__invalidresult__"></a>Sonuç: __geçersiz <Result>__

Beklenen sonucu `Measure(bases, qubits)` .


### <a name="prob--double"></a>prob: [Double](xref:microsoft.quantum.lang-ref.double)

Verilen sonucun beklenildiği olasılık.


### <a name="msg--string"></a>Msg: [String](xref:microsoft.quantum.lang-ref.string)

Onaylama başarısız olursa bildirilecek bir ileti.


### <a name="tol--double"></a>tol: [Double](xref:microsoft.quantum.lang-ref.double)





## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Açıklamalar

Bu işlemin adjoint ve kontrollü sürümlerinin koşulu denetyacağını unutmayın.

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Diagnostics. Assertölçüm](xref:Microsoft.Quantum.Diagnostics.AssertMeasurement)