---
uid: Microsoft.Quantum.Intrinsic.Measure
title: Ölçüm işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Measure
qsharp.summary: >-
  Performs a joint measurement of one or more qubits in the specified Pauli bases.

  The output result is given by the distribution: \begin{align} \Pr(\texttt{Zero} | \ket{\psi}) = \frac12 \braket{ \psi \mid| \left( \boldone + P_0 \otimes P_1 \otimes \cdots \otimes P_{N-1} \right) \mid| \psi }, \end{align} where $P_i$ is the $i$th element of `bases`, and where $N = \texttt{Length}(\texttt{bases})$. That is, measurement returns a `Result` $d$ such that the eigenvalue of the observed measurement effect is $(-1)^d$.
ms.openlocfilehash: bf0a606b1bfc8c4762245422450ec26907ec1946
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98818779"
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