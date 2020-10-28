---
uid: Microsoft.Quantum.Diagnostics.AssertQubit
title: AssertQubit işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertQubit
qsharp.summary: Asserts that the qubit `q` is in the expected eigenstate of the Pauli Z operator.
ms.openlocfilehash: fa1f52da5a011cd914a0fda69b78cf5a4fd71e16
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727319"
---
# <a name="assertqubit-operation"></a>AssertQubit işlemi

Ad alanı: [Microsoft. hisse. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Leyebilir [](https://nuget.org/packages/)


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