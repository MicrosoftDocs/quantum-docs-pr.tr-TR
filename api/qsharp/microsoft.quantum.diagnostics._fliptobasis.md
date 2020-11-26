---
uid: Microsoft.Quantum.Diagnostics._flipToBasis
title: _flipToBasis işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _flipToBasis
qsharp.summary: >-
  Applies unitaries that map $\ket{0}\otimes\cdots\ket{0}$ to $\ket{\psi_0} \otimes \ket{\psi_{n - 1}}$, where $\ket{\psi_k}$ depends on `basis[k]`.

  The correspondence between value of `basis[k]` and $\ket{\psi_k}$ is the following:

  - `basis[k]=0` $\rightarrow \ket{0}$. - `basis[k]=1` $\rightarrow \ket{1}$. - `basis[k]=2` $\rightarrow \ket{+}$. - `basis[k]=3` $\rightarrow \ket{i}$ ( +1 eigenstate of Pauli Y ).
ms.openlocfilehash: 1581a1267902ceee81d6f01348f4ee718e49ee47
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223995"
---
# <a name="_fliptobasis-operation"></a>_flipToBasis işlemi

Ad alanı: [Microsoft. hisse. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


$ \Ket {0} \otimes\cdots\tus$ {0} to $ \ket{\ psi_0} \otimes \ket{\ psi_ {n-1}} $, $ \ket{\ psi_k} $ öğesine bağlı olan unitçler uygular `basis[k]` .

`basis[k]`Ve $ \ket{\ psi_k} $ değeri arasındaki yazışmalar şunlardır:

- `basis[k]=0` $ \ sağtarsatır \ayraç {0} $.
- `basis[k]=1` $ \ sağtarsatır \ayraç {1} $.
- `basis[k]=2` $ \sağtarrow \ket{+} $.
- `basis[k]=3` $ \sağtarrow \ket{i} $ (+ 1 Pauli Y).

```qsharp
operation _flipToBasis (basis : Int[], qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Giriş

### <a name="basis--int"></a>temel: [Int](xref:microsoft.quantum.lang-ref.int)[]

Her qubit öğesi için bir tane olmak üzere tek qubit tabanlı durum kimliklerinin dizisi (0 <= ID <= 3).


### <a name="qubits--qubit"></a>qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Üzerinde çalıştırılacak qubit.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)

