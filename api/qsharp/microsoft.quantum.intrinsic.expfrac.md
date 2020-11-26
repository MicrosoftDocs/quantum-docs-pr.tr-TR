---
uid: Microsoft.Quantum.Intrinsic.ExpFrac
title: ExpFrac işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: ExpFrac
qsharp.summary: >-
  Applies the exponential of a multi-qubit Pauli operator with an argument given by a dyadic fraction.

  \begin{align} e^{i \pi k [P_0 \otimes P_1 \cdots P_{N-1}] / 2^n}, \end{align} where $P_i$ is the $i$th element of `paulis`, and where $N = $`Length(paulis)`.
ms.openlocfilehash: 8ccea068dd61aaf8c1ba384969adef5644e8401e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96199004"
---
# <a name="expfrac-operation"></a><span data-ttu-id="4ccec-102">ExpFrac işlemi</span><span class="sxs-lookup"><span data-stu-id="4ccec-102">ExpFrac operation</span></span>

<span data-ttu-id="4ccec-103">Ad alanı: [Microsoft. hisse. iç](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="4ccec-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="4ccec-104">Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="4ccec-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="4ccec-105">Bir multi-qubit Pauli işlecinin üstel değeri bir dyadic kesri tarafından verilen bağımsız değişkenle uygular.</span><span class="sxs-lookup"><span data-stu-id="4ccec-105">Applies the exponential of a multi-qubit Pauli operator with an argument given by a dyadic fraction.</span></span>

<span data-ttu-id="4ccec-106">\begin{hizalaması} e ^ {ı \pı k [P_0 \otimes P_1 \cnoktalar P_ {N-1}]/2 ^ N}, \end{hizalaması}; burada $P _i $, $i $ th öğesi `paulis` ve burada $N = $ `Length(paulis)` .</span><span class="sxs-lookup"><span data-stu-id="4ccec-106">\begin{align} e^{i \pi k [P_0 \otimes P_1 \cdots P_{N-1}] / 2^n}, \end{align} where $P_i$ is the $i$th element of `paulis`, and where $N = $`Length(paulis)`.</span></span>

```qsharp
operation ExpFrac (paulis : Pauli[], numerator : Int, power : Int, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="4ccec-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="4ccec-107">Input</span></span>

### <a name="paulis--pauli"></a><span data-ttu-id="4ccec-108">Paulis: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="4ccec-108">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="4ccec-109">Her bir qubit üzerinde Tensor ürün faktörleri belirten tek qubit Pauli değerlerinin dizisi.</span><span class="sxs-lookup"><span data-stu-id="4ccec-109">Array of single-qubit Pauli values indicating the tensor product factors on each qubit.</span></span>


### <a name="numerator--int"></a><span data-ttu-id="4ccec-110">pay: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4ccec-110">numerator : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4ccec-111">, Qubit yazmacın döndürüleceği açının dyadic kesir gösteriminde pay ($k $).</span><span class="sxs-lookup"><span data-stu-id="4ccec-111">Numerator ($k$) in the dyadic fraction representation of the angle by which the qubit register is to be rotated.</span></span>


### <a name="power--int"></a><span data-ttu-id="4ccec-112">güç: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4ccec-112">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4ccec-113">İki ($n $) üssü, qubit yazmacın döndürüleceği açının paydasını belirten.</span><span class="sxs-lookup"><span data-stu-id="4ccec-113">Power of two ($n$) specifying the denominator of the angle by which the qubit register is to be rotated.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="4ccec-114">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="4ccec-114">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="4ccec-115">Verilen dönüşü öğesine uygulamak için kaydolun.</span><span class="sxs-lookup"><span data-stu-id="4ccec-115">Register to apply the given rotation to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4ccec-116">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4ccec-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

