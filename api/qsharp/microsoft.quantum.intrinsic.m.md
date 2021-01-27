---
uid: Microsoft.Quantum.Intrinsic.M
title: A işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: M
qsharp.summary: >-
  Performs a measurement of a single qubit in the Pauli $Z$ basis.

  The output result is given by the distribution \begin{align} \Pr(\texttt{Zero} | \ket{\psi}) = \braket{\psi | 0} \braket{0 | \psi}. \end{align}
ms.openlocfilehash: 0037d7f5ad060857c6ca2c863b1d24aca3e338cf
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98818867"
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