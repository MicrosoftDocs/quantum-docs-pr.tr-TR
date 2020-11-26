---
uid: Microsoft.Quantum.Intrinsic.M
title: A işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: M
qsharp.summary: >-
  Performs a measurement of a single qubit in the Pauli $Z$ basis.

  The output result is given by the distribution \begin{align} \Pr(\texttt{Zero} | \ket{\psi}) = \braket{\psi | 0} \braket{0 | \psi}. \end{align}
ms.openlocfilehash: ced3a617a7299e169c7a58a1cd0f83f656b2f0b3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96212350"
---
# <a name="m-operation"></a>A işlemi

Ad alanı: [Microsoft. hisse. iç](xref:Microsoft.Quantum.Intrinsic)

Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Pauli $Z $ temelinde tek bir qubit ölçümü gerçekleştirir.

Çıkış sonucu, < Begin{hizalaması} \Pr (\Texttt{dd} | \ket{\psı}) = \braket{\psı | 0} \braket{0 | \psı} dağıtımı tarafından verilir.
\end{hizalaması}

```qsharp
operation M (qubit : Qubit) : Result
```


## <a name="input"></a>Giriş

### <a name="qubit--qubit"></a>qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Ölçülecek qubit.



## <a name="output--__invalidresult__"></a>Çıkış: __geçersiz <Result>__

`Zero` $ + $1 eigenvalue gözlemlenmiştir ve `One` $-$1 eigenvalue gözlemleniyorsa.

## <a name="remarks"></a>Açıklamalar

Eşdeğer:

```qsharp
Measure([PauliZ], [qubit]);
```