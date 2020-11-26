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
# <a name="m-operation"></a><span data-ttu-id="34536-102">A işlemi</span><span class="sxs-lookup"><span data-stu-id="34536-102">M operation</span></span>

<span data-ttu-id="34536-103">Ad alanı: [Microsoft. hisse. iç](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="34536-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="34536-104">Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="34536-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="34536-105">Pauli $Z $ temelinde tek bir qubit ölçümü gerçekleştirir.</span><span class="sxs-lookup"><span data-stu-id="34536-105">Performs a measurement of a single qubit in the Pauli $Z$ basis.</span></span>

<span data-ttu-id="34536-106">Çıkış sonucu, < Begin{hizalaması} \Pr (\Texttt{dd} | \ket{\psı}) = \braket{\psı | 0} \braket{0 | \psı} dağıtımı tarafından verilir.</span><span class="sxs-lookup"><span data-stu-id="34536-106">The output result is given by the distribution \begin{align} \Pr(\texttt{Zero} | \ket{\psi}) = \braket{\psi | 0} \braket{0 | \psi}.</span></span>
<span data-ttu-id="34536-107">\end{hizalaması}</span><span class="sxs-lookup"><span data-stu-id="34536-107">\end{align}</span></span>

```qsharp
operation M (qubit : Qubit) : Result
```


## <a name="input"></a><span data-ttu-id="34536-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="34536-108">Input</span></span>

### <a name="qubit--qubit"></a><span data-ttu-id="34536-109">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="34536-109">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="34536-110">Ölçülecek qubit.</span><span class="sxs-lookup"><span data-stu-id="34536-110">Qubit to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="34536-111">Çıkış: __geçersiz <Result>__</span><span class="sxs-lookup"><span data-stu-id="34536-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="34536-112">`Zero` $ + $1 eigenvalue gözlemlenmiştir ve `One` $-$1 eigenvalue gözlemleniyorsa.</span><span class="sxs-lookup"><span data-stu-id="34536-112">`Zero` if the $+1$ eigenvalue is observed, and `One` if the $-1$ eigenvalue is observed.</span></span>

## <a name="remarks"></a><span data-ttu-id="34536-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="34536-113">Remarks</span></span>

<span data-ttu-id="34536-114">Eşdeğer:</span><span class="sxs-lookup"><span data-stu-id="34536-114">Equivalent to:</span></span>

```qsharp
Measure([PauliZ], [qubit]);
```