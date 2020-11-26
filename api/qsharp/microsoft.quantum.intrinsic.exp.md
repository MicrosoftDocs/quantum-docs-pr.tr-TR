---
uid: Microsoft.Quantum.Intrinsic.Exp
title: Exp işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Exp
qsharp.summary: >-
  Applies the exponential of a multi-qubit Pauli operator.

  \begin{align} e^{i \theta [P_0 \otimes P_1 \cdots P_{N-1}]}, \end{align} where $P_i$ is the $i$th element of `paulis`, and where $N = $`Length(paulis)`.
ms.openlocfilehash: 2eea29ec08260ea9cee1bafde80a0942e06f5abc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96212418"
---
# <a name="exp-operation"></a><span data-ttu-id="e15b0-102">Exp işlemi</span><span class="sxs-lookup"><span data-stu-id="e15b0-102">Exp operation</span></span>

<span data-ttu-id="e15b0-103">Ad alanı: [Microsoft. hisse. iç](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="e15b0-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="e15b0-104">Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="e15b0-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="e15b0-105">Multi-qubit Pauli işlecinin üstel değeri uygular.</span><span class="sxs-lookup"><span data-stu-id="e15b0-105">Applies the exponential of a multi-qubit Pauli operator.</span></span>

<span data-ttu-id="e15b0-106">\begin{hizalaması} e ^ {ı \teta [P_0 \otimes P_1 \cnoktalar P_ {N-1}]}, \end{hizalaması}; burada $P _i $, $i $ th öğesi `paulis` ve burada $N = $ `Length(paulis)` .</span><span class="sxs-lookup"><span data-stu-id="e15b0-106">\begin{align} e^{i \theta [P_0 \otimes P_1 \cdots P_{N-1}]}, \end{align} where $P_i$ is the $i$th element of `paulis`, and where $N = $`Length(paulis)`.</span></span>

```qsharp
operation Exp (paulis : Pauli[], theta : Double, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="e15b0-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="e15b0-107">Input</span></span>

### <a name="paulis--pauli"></a><span data-ttu-id="e15b0-108">Paulis: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="e15b0-108">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="e15b0-109">Her bir qubit üzerinde Tensor ürün faktörleri belirten tek qubit Pauli değerlerinin dizisi.</span><span class="sxs-lookup"><span data-stu-id="e15b0-109">Array of single-qubit Pauli values indicating the tensor product factors on each qubit.</span></span>


### <a name="theta--double"></a><span data-ttu-id="e15b0-110">Teta: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e15b0-110">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e15b0-111">Hedef yazmacın döndürüleceği, verilen Multi-qubit Pauli operatörü ile ilgili açı.</span><span class="sxs-lookup"><span data-stu-id="e15b0-111">Angle about the given multi-qubit Pauli operator by which the target register is to be rotated.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="e15b0-112">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="e15b0-112">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="e15b0-113">Verilen dönüşü öğesine uygulamak için kaydolun.</span><span class="sxs-lookup"><span data-stu-id="e15b0-113">Register to apply the given rotation to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e15b0-114">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e15b0-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

