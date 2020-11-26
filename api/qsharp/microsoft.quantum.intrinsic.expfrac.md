---
uid: Microsoft.Quantum.Intrinsic.ExpFrac
title: ExpFrac işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: ExpFrac
qsharp.summary: >-
  Applies the exponential of a multi-qubit Pauli operator with an argument given by a dyadic fraction.

  \begin{align} e^{i \pi k [P_0 \otimes P_1 \cdots P_{N-1}] / 2^n}, \end{align} where $P_i$ is the $i$th element of `paulis`, and where $N = $`Length(paulis)`.
ms.openlocfilehash: 8ccea068dd61aaf8c1ba384969adef5644e8401e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96199004"
---
# <a name="expfrac-operation"></a>ExpFrac işlemi

Ad alanı: [Microsoft. hisse. iç](xref:Microsoft.Quantum.Intrinsic)

Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Bir multi-qubit Pauli işlecinin üstel değeri bir dyadic kesri tarafından verilen bağımsız değişkenle uygular.

\begin{hizalaması} e ^ {ı \pı k [P_0 \otimes P_1 \cnoktalar P_ {N-1}]/2 ^ N}, \end{hizalaması}; burada $P _i $, $i $ th öğesi `paulis` ve burada $N = $ `Length(paulis)` .

```qsharp
operation ExpFrac (paulis : Pauli[], numerator : Int, power : Int, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Giriş

### <a name="paulis--pauli"></a>Paulis: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

Her bir qubit üzerinde Tensor ürün faktörleri belirten tek qubit Pauli değerlerinin dizisi.


### <a name="numerator--int"></a>pay: [Int](xref:microsoft.quantum.lang-ref.int)

, Qubit yazmacın döndürüleceği açının dyadic kesir gösteriminde pay ($k $).


### <a name="power--int"></a>güç: [Int](xref:microsoft.quantum.lang-ref.int)

İki ($n $) üssü, qubit yazmacın döndürüleceği açının paydasını belirten.


### <a name="qubits--qubit"></a>qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Verilen dönüşü öğesine uygulamak için kaydolun.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)

