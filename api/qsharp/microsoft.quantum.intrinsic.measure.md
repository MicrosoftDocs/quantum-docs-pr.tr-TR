---
uid: Microsoft.Quantum.Intrinsic.Measure
title: Ölçüm işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Measure
qsharp.summary: >-
  Performs a joint measurement of one or more qubits in the specified Pauli bases.

  The output result is given by the distribution: \begin{align} \Pr(\texttt{Zero} | \ket{\psi}) = \frac12 \braket{ \psi \mid| \left( \boldone + P_0 \otimes P_1 \otimes \cdots \otimes P_{N-1} \right) \mid| \psi }, \end{align} where $P_i$ is the $i$th element of `bases`, and where $N = \texttt{Length}(\texttt{bases})$. That is, measurement returns a `Result` $d$ such that the eigenvalue of the observed measurement effect is $(-1)^d$.
ms.openlocfilehash: 804ae72ed2d5302b14011b737b7ed3ad2b9a14ca
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96212299"
---
# <a name="measure-operation"></a>Ölçüm işlemi

Ad alanı: [Microsoft. hisse. iç](xref:Microsoft.Quantum.Intrinsic)

Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Belirtilen Pauli tabanlarında bir veya daha fazla qubits 'in Birleşik ölçüsünü gerçekleştirir.

Çıkış sonucu dağıtım tarafından verilir: \begin{hizalaması} \Pr (\Texttt{dd} | \ket{\psı}) = \frac12 \braket{\psı \ Mid | \left (\cıvadone + P_0 \otimes P_1 \otimes \cnoktalar \otimes P_ {N-1} \right) \mid | \psı}, \end{hizalaması}; burada $P _i $, $i $ TH öğesidir. `bases` ve burada $N = \texttt{Length} (\texttt{Bases}) $.
Diğer bir deyişle, ölçüm, `Result` gözlemlenen ölçüm efektinin eigenvalue değeri $ (-1) ^ d $ olacak şekilde bir $d $ döndürür.

```qsharp
operation Measure (bases : Pauli[], qubits : Qubit[]) : Result
```


## <a name="input"></a>Giriş

### <a name="bases--pauli"></a>tabanlar: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

Her bir qubit üzerinde Tensor ürün faktörleri belirten tek qubit Pauli değerlerinin dizisi.


### <a name="qubits--qubit"></a>qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Ölçülecek qubits 'in kaydı.



## <a name="output--__invalidresult__"></a>Çıkış: __geçersiz <Result>__

`Zero` $ + $1 eigenvalue gözlemlenmiştir ve `One` $-$1 eigenvalue gözlemleniyorsa.

## <a name="remarks"></a>Açıklamalar

Temel dizi ve qubit dizisi farklı uzunluklardır, işlem başarısız olur.