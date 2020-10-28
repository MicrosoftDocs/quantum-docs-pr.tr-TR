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
# <a name="_fliptobasis-operation"></a><span data-ttu-id="8bc4d-102">_flipToBasis işlemi</span><span class="sxs-lookup"><span data-stu-id="8bc4d-102">_flipToBasis operation</span></span>

<span data-ttu-id="8bc4d-103">Ad alanı: [Microsoft. hisse. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="8bc4d-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="8bc4d-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8bc4d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8bc4d-105">$ \Ket {0} \otimes\cdots\tus$ {0} to $ \ket{\ psi_0} \otimes \ket{\ psi_ {n-1}} $, $ \ket{\ psi_k} $ öğesine bağlı olan unitçler uygular `basis[k]` .</span><span class="sxs-lookup"><span data-stu-id="8bc4d-105">Applies unitaries that map $\ket{0}\otimes\cdots\ket{0}$ to $\ket{\psi_0} \otimes \ket{\psi_{n - 1}}$, where $\ket{\psi_k}$ depends on `basis[k]`.</span></span>

<span data-ttu-id="8bc4d-106">`basis[k]`Ve $ \ket{\ psi_k} $ değeri arasındaki yazışmalar şunlardır:</span><span class="sxs-lookup"><span data-stu-id="8bc4d-106">The correspondence between value of `basis[k]` and $\ket{\psi_k}$ is the following:</span></span>

- <span data-ttu-id="8bc4d-107">`basis[k]=0` $ \ sağtarsatır \ayraç {0} $.</span><span class="sxs-lookup"><span data-stu-id="8bc4d-107">`basis[k]=0` $\rightarrow \ket{0}$.</span></span>
- <span data-ttu-id="8bc4d-108">`basis[k]=1` $ \ sağtarsatır \ayraç {1} $.</span><span class="sxs-lookup"><span data-stu-id="8bc4d-108">`basis[k]=1` $\rightarrow \ket{1}$.</span></span>
- <span data-ttu-id="8bc4d-109">`basis[k]=2` $ \sağtarrow \ket{+} $.</span><span class="sxs-lookup"><span data-stu-id="8bc4d-109">`basis[k]=2` $\rightarrow \ket{+}$.</span></span>
- <span data-ttu-id="8bc4d-110">`basis[k]=3` $ \sağtarrow \ket{i} $ (+ 1 Pauli Y).</span><span class="sxs-lookup"><span data-stu-id="8bc4d-110">`basis[k]=3` $\rightarrow \ket{i}$ ( +1 eigenstate of Pauli Y ).</span></span>

```qsharp
operation _flipToBasis (basis : Int[], qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="8bc4d-111">Giriş</span><span class="sxs-lookup"><span data-stu-id="8bc4d-111">Input</span></span>

### <a name="basis--int"></a><span data-ttu-id="8bc4d-112">temel: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="8bc4d-112">basis : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="8bc4d-113">Her qubit öğesi için bir tane olmak üzere tek qubit tabanlı durum kimliklerinin dizisi (0 <= ID <= 3).</span><span class="sxs-lookup"><span data-stu-id="8bc4d-113">Array of single-qubit basis state IDs (0 <= id <= 3), one for each element of qubits.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="8bc4d-114">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="8bc4d-114">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="8bc4d-115">Üzerinde çalıştırılacak qubit.</span><span class="sxs-lookup"><span data-stu-id="8bc4d-115">Qubit to be operated on.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8bc4d-116">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8bc4d-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

