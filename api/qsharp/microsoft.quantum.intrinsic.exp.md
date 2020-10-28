---
uid: Microsoft.Quantum.Intrinsic.Exp
title: Exp işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Exp
qsharp.summary: >-
  Applies the exponential of a multi-qubit Pauli operator.

  \begin{align} e^{i \theta [P_0 \otimes P_1 \cdots P_{N-1}]}, \end{align} where $P_i$ is the $i$th element of `paulis`, and where $N = $`Length(paulis)`.
ms.openlocfilehash: b923374a954f90aba2deaead79dd419fbf67fea3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726708"
---
# <a name="exp-operation"></a><span data-ttu-id="60741-102">Exp işlemi</span><span class="sxs-lookup"><span data-stu-id="60741-102">Exp operation</span></span>

<span data-ttu-id="60741-103">Ad alanı: [Microsoft. hisse. iç](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="60741-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="60741-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="60741-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="60741-105">Multi-qubit Pauli işlecinin üstel değeri uygular.</span><span class="sxs-lookup"><span data-stu-id="60741-105">Applies the exponential of a multi-qubit Pauli operator.</span></span>

<span data-ttu-id="60741-106">\begin{hizalaması} e ^ {ı \teta [P_0 \otimes P_1 \cnoktalar P_ {N-1}]}, \end{hizalaması}; burada $P _i $, $i $ th öğesi `paulis` ve burada $N = $ `Length(paulis)` .</span><span class="sxs-lookup"><span data-stu-id="60741-106">\begin{align} e^{i \theta [P_0 \otimes P_1 \cdots P_{N-1}]}, \end{align} where $P_i$ is the $i$th element of `paulis`, and where $N = $`Length(paulis)`.</span></span>

```qsharp
operation Exp (paulis : Pauli[], theta : Double, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="60741-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="60741-107">Input</span></span>

### <a name="paulis--pauli"></a><span data-ttu-id="60741-108">Paulis: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="60741-108">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="60741-109">Her bir qubit üzerinde Tensor ürün faktörleri belirten tek qubit Pauli değerlerinin dizisi.</span><span class="sxs-lookup"><span data-stu-id="60741-109">Array of single-qubit Pauli values indicating the tensor product factors on each qubit.</span></span>


### <a name="theta--double"></a><span data-ttu-id="60741-110">Teta: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="60741-110">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="60741-111">Hedef yazmacın döndürüleceği, verilen Multi-qubit Pauli operatörü ile ilgili açı.</span><span class="sxs-lookup"><span data-stu-id="60741-111">Angle about the given multi-qubit Pauli operator by which the target register is to be rotated.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="60741-112">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="60741-112">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="60741-113">Verilen dönüşü öğesine uygulamak için kaydolun.</span><span class="sxs-lookup"><span data-stu-id="60741-113">Register to apply the given rotation to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="60741-114">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="60741-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

