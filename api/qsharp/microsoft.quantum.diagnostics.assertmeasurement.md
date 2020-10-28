---
uid: Microsoft.Quantum.Diagnostics.AssertMeasurement
title: Assertölçüm işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertMeasurement
qsharp.summary: Asserts that measuring the given qubits in the given Pauli basis will always have the given result.
ms.openlocfilehash: 09024cd8cd6e713360dcf7f42f55941590f35883
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727356"
---
# <a name="assertmeasurement-operation"></a>Assertölçüm işlemi

Ad alanı: [Microsoft. hisse. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Leyebilir [](https://nuget.org/packages/)


Verilen Pauli tabanında verilen qubits ölçmeye yönelik onaylar, her zaman verilen sonuca sahip olur.

```qsharp
operation AssertMeasurement (bases : Pauli[], qubits : Qubit[], result : Result, msg : String) : Unit
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