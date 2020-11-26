---
uid: Microsoft.Quantum.Intrinsic.Measure
title: Ölçüm işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Measure
qsharp.summary: >-
  Performs a joint measurement of one or more qubits in the specified Pauli bases.

  The output result is given by the distribution: \begin{align} \Pr(\texttt{Zero} | \ket{\psi}) = \frac12 \braket{ \psi \mid| \left( \boldone + P_0 \otimes P_1 \otimes \cdots \otimes P_{N-1} \right) \mid| \psi }, \end{align} where $P_i$ is the $i$th element of `bases`, and where $N = \texttt{Length}(\texttt{bases})$. That is, measurement returns a `Result` $d$ such that the eigenvalue of the observed measurement effect is $(-1)^d$.
ms.openlocfilehash: 804ae72ed2d5302b14011b737b7ed3ad2b9a14ca
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96212299"
---
# <a name="measure-operation"></a><span data-ttu-id="4dd36-102">Ölçüm işlemi</span><span class="sxs-lookup"><span data-stu-id="4dd36-102">Measure operation</span></span>

<span data-ttu-id="4dd36-103">Ad alanı: [Microsoft. hisse. iç](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="4dd36-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="4dd36-104">Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="4dd36-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="4dd36-105">Belirtilen Pauli tabanlarında bir veya daha fazla qubits 'in Birleşik ölçüsünü gerçekleştirir.</span><span class="sxs-lookup"><span data-stu-id="4dd36-105">Performs a joint measurement of one or more qubits in the specified Pauli bases.</span></span>

<span data-ttu-id="4dd36-106">Çıkış sonucu dağıtım tarafından verilir: \begin{hizalaması} \Pr (\Texttt{dd} | \ket{\psı}) = \frac12 \braket{\psı \ Mid | \left (\cıvadone + P_0 \otimes P_1 \otimes \cnoktalar \otimes P_ {N-1} \right) \mid | \psı}, \end{hizalaması}; burada $P _i $, $i $ TH öğesidir. `bases` ve burada $N = \texttt{Length} (\texttt{Bases}) $.</span><span class="sxs-lookup"><span data-stu-id="4dd36-106">The output result is given by the distribution: \begin{align} \Pr(\texttt{Zero} | \ket{\psi}) = \frac12 \braket{ \psi \mid| \left( \boldone + P_0 \otimes P_1 \otimes \cdots \otimes P_{N-1} \right) \mid| \psi }, \end{align} where $P_i$ is the $i$th element of `bases`, and where $N = \texttt{Length}(\texttt{bases})$.</span></span>
<span data-ttu-id="4dd36-107">Diğer bir deyişle, ölçüm, `Result` gözlemlenen ölçüm efektinin eigenvalue değeri $ (-1) ^ d $ olacak şekilde bir $d $ döndürür.</span><span class="sxs-lookup"><span data-stu-id="4dd36-107">That is, measurement returns a `Result` $d$ such that the eigenvalue of the observed measurement effect is $(-1)^d$.</span></span>

```qsharp
operation Measure (bases : Pauli[], qubits : Qubit[]) : Result
```


## <a name="input"></a><span data-ttu-id="4dd36-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="4dd36-108">Input</span></span>

### <a name="bases--pauli"></a><span data-ttu-id="4dd36-109">tabanlar: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="4dd36-109">bases : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="4dd36-110">Her bir qubit üzerinde Tensor ürün faktörleri belirten tek qubit Pauli değerlerinin dizisi.</span><span class="sxs-lookup"><span data-stu-id="4dd36-110">Array of single-qubit Pauli values indicating the tensor product factors on each qubit.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="4dd36-111">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="4dd36-111">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="4dd36-112">Ölçülecek qubits 'in kaydı.</span><span class="sxs-lookup"><span data-stu-id="4dd36-112">Register of qubits to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="4dd36-113">Çıkış: __geçersiz <Result>__</span><span class="sxs-lookup"><span data-stu-id="4dd36-113">Output : __invalid<Result>__</span></span>

<span data-ttu-id="4dd36-114">`Zero` $ + $1 eigenvalue gözlemlenmiştir ve `One` $-$1 eigenvalue gözlemleniyorsa.</span><span class="sxs-lookup"><span data-stu-id="4dd36-114">`Zero` if the $+1$ eigenvalue is observed, and `One` if the $-1$ eigenvalue is observed.</span></span>

## <a name="remarks"></a><span data-ttu-id="4dd36-115">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="4dd36-115">Remarks</span></span>

<span data-ttu-id="4dd36-116">Temel dizi ve qubit dizisi farklı uzunluklardır, işlem başarısız olur.</span><span class="sxs-lookup"><span data-stu-id="4dd36-116">If the basis array and qubit array are different lengths, then the operation will fail.</span></span>