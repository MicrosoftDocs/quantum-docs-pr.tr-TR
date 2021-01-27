---
uid: Microsoft.Quantum.Diagnostics.AssertMeasurement
title: Assertölçüm işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertMeasurement
qsharp.summary: Asserts that measuring the given qubits in the given Pauli basis will always have the given result.
ms.openlocfilehash: 8f5113f1d6b8e4f104af10ca330e244e95793418
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853497"
---
# <a name="assertmeasurement-operation"></a>Assertölçüm işlemi

Ad alanı: [Microsoft. hisse. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Verilen Pauli tabanında verilen qubits ölçmeye yönelik onaylar, her zaman verilen sonuca sahip olur.

```qsharp
operation AssertMeasurement (bases : Pauli[], qubits : Qubit[], result : Result, msg : String) : Unit is Adj + Ctl
```


## <a name="input"></a>Giriş

### <a name="bases--pauli"></a>tabanlar: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

Bir multi-qubit Pauli işleci olarak ifade edilen olasılığını onaylama için bir ölçüm etkisi.


### <a name="qubits--qubit"></a>qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Onaylama yapılacak bir kayıt.


### <a name="result--__invalidresult__"></a>Sonuç: __geçersiz <Result>__

Beklenen sonucu `Measure(bases, qubits)` .


### <a name="msg--string"></a>Msg: [String](xref:microsoft.quantum.lang-ref.string)

Onaylama başarısız olursa bildirilecek bir ileti.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Açıklamalar

Bu işlemin adjoint ve kontrollü sürümlerinin koşulu denetyacağını unutmayın.

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. tanılama. AssertMeasurementProbability](xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability)