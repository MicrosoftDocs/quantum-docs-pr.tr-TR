---
uid: Microsoft.Quantum.Diagnostics._flipToBasis
title: _flipToBasis işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _flipToBasis
qsharp.summary: >-
  Applies unitaries that map $\ket{0}\otimes\cdots\ket{0}$ to $\ket{\psi_0} \otimes \ket{\psi_{n - 1}}$, where $\ket{\psi_k}$ depends on `basis[k]`.

  The correspondence between value of `basis[k]` and $\ket{\psi_k}$ is the following:

  - `basis[k]=0` $\rightarrow \ket{0}$. - `basis[k]=1` $\rightarrow \ket{1}$. - `basis[k]=2` $\rightarrow \ket{+}$. - `basis[k]=3` $\rightarrow \ket{i}$ ( +1 eigenstate of Pauli Y ).
ms.openlocfilehash: e074ed2ae259f6aef49a8d327ce518a9e2caebfa
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727404"
---
# <a name="_fliptobasis-operation"></a>_flipToBasis işlemi

Ad alanı: [Microsoft. hisse. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Leyebilir [](https://nuget.org/packages/)


$ \Ket {0} \otimes\cdots\tus$ {0} to $ \ket{\ psi_0} \otimes \ket{\ psi_ {n-1}} $, $ \ket{\ psi_k} $ öğesine bağlı olan unitçler uygular `basis[k]` .

`basis[k]`Ve $ \ket{\ psi_k} $ değeri arasındaki yazışmalar şunlardır:

- `basis[k]=0` $ \ sağtarsatır \ayraç {0} $.
- `basis[k]=1` $ \ sağtarsatır \ayraç {1} $.
- `basis[k]=2` $ \sağtarrow \ket{+} $.
- `basis[k]=3` $ \sağtarrow \ket{i} $ (+ 1 Pauli Y).

```qsharp
operation _flipToBasis (basis : Int[], qubits : Qubit[]) : Unit
```


## <a name="input"></a>Giriş

### <a name="basis--int"></a>temel: [Int](xref:microsoft.quantum.lang-ref.int)[]

Her qubit öğesi için bir tane olmak üzere tek qubit tabanlı durum kimliklerinin dizisi (0 <= ID <= 3).


### <a name="qubits--qubit"></a>qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Üzerinde çalıştırılacak qubit.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)

