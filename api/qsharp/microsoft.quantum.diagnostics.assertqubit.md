---
uid: Microsoft.Quantum.Diagnostics.AssertQubit
title: AssertQubit işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertQubit
qsharp.summary: Asserts that the qubit `q` is in the expected eigenstate of the Pauli Z operator.
ms.openlocfilehash: 8fcdd8de9250348e1dd1173052b53be978f2a0c5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853449"
---
# <a name="assertqubit-operation"></a>AssertQubit işlemi

Ad alanı: [Microsoft. hisse. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Qubitin `q` Pauli Z işlecinin beklenen eigenstate öğesinde olduğunu onaylar.

```qsharp
operation AssertQubit (expected : Result, q : Qubit) : Unit
```


## <a name="input"></a>Giriş

### <a name="expected--__invalidresult__"></a>beklenen: __geçersiz <Result>__

Qubitin nerede olması beklenen durum: `Zero` veya `One` .


### <a name="q--qubit"></a>s: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Durumu onaylanan qubit.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Açıklamalar

<xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> Yalnızca $Z $ eigenstates yerine rastgele qubit durumlarını ele almasına izin verir.

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Diagnostics. Assertqubitişsınstatewithıntoleransı](xref:Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance)