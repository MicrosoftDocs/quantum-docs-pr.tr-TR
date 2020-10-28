---
uid: Microsoft.Quantum.Intrinsic.M
title: A işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: M
qsharp.summary: >-
  Performs a measurement of a single qubit in the Pauli $Z$ basis.

  The output result is given by the distribution \begin{align} \Pr(\texttt{Zero} | \ket{\psi}) = \braket{\psi | 0} \braket{0 | \psi}. \end{align}
ms.openlocfilehash: 8d4b120385bfc7086a7cb0e3f77034c760d78d92
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731394"
---
# <a name="m-operation"></a>A işlemi

Ad alanı: [Microsoft. hisse. iç](xref:Microsoft.Quantum.Intrinsic)

Leyebilir [](https://nuget.org/packages/)


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