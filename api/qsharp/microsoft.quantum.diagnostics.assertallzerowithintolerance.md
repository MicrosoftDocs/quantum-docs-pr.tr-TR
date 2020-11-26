---
uid: Microsoft.Quantum.Diagnostics.AssertAllZeroWithinTolerance
title: Assertallsıfırlaması Withıntoleranslı işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertAllZeroWithinTolerance
qsharp.summary: Assert that given qubits are all in $\ket{0}$ state up to a given tolerance.
ms.openlocfilehash: a2e73bbc8949b3cdb7733cfc8aae35680e54d2cf
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202490"
---
# <a name="assertallzerowithintolerance-operation"></a>Assertallsıfırlaması Withıntoleranslı işlemi

Ad alanı: [Microsoft. hisse. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Verilen qubits 'in, {0} belirli bir toleranstan kadar $ \gre$ durumunda olduğu onay.

```qsharp
operation AssertAllZeroWithinTolerance (qubits : Qubit[], tolerance : Double) : Unit is Adj + Ctl
```


## <a name="input"></a>Giriş

### <a name="qubits--qubit"></a>qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

$ \ Ayraç $ durumunda olmak üzere onaylanan qubits {0} .


### <a name="tolerance--double"></a>Tolerans: [Double](xref:microsoft.quantum.lang-ref.double)

Durumun $ \ket $ durumunda olması gereken doğruluk {0}



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Diagnostics. Assertqubitwithıntoleransı](xref:Microsoft.Quantum.Diagnostics.AssertQubitWithinTolerance)