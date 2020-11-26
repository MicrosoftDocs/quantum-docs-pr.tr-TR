---
uid: Microsoft.Quantum.Diagnostics.AssertQubitWithinTolerance
title: Assertqubitwithıntoleransı işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertQubitWithinTolerance
qsharp.summary: Asserts that the qubit `q` is in the expected eigenstate of the Pauli Z operator up to a given tolerance.
ms.openlocfilehash: 56b7f93f33ae18146c1fb13d404fc1d119eee72e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202201"
---
# <a name="assertqubitwithintolerance-operation"></a>Assertqubitwithıntoleransı işlemi

Ad alanı: [Microsoft. hisse. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Qubit 'in `q` Pauli Z işlecinin, belirli bir toleransa kadar beklenen eigenstate olduğunu onaylar.

```qsharp
operation AssertQubitWithinTolerance (expected : Result, q : Qubit, tolerance : Double) : Unit
```


## <a name="input"></a>Giriş

### <a name="expected--__invalidresult__"></a>beklenen: __geçersiz <Result>__

Qubitin nerede olması beklenen durum: `Zero` veya `One` .


### <a name="q--qubit"></a>s: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Durumu onaylanan qubit.


### <a name="tolerance--double"></a>Tolerans: [Double](xref:microsoft.quantum.lang-ref.double)

Beklenen sonucu döndüren qubit ölçüsünün toleransı.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Açıklamalar

<xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> Yalnızca $Z $ eigenstates yerine rastgele qubit durumlarını ele almasına izin verir.

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Diagnostics. Assertqubitişsınstatewithıntoleransı](xref:Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance)