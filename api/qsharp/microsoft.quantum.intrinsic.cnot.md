---
uid: Microsoft.Quantum.Intrinsic.CNOT
title: CNOT işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: CNOT
qsharp.summary: >-
  Applies the controlled-NOT (CNOT) gate to a pair of qubits.

  \begin{align} \operatorname{CNOT} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{bmatrix}, \end{align}

  where rows and columns are ordered as in the quantum concepts guide.
ms.openlocfilehash: 90e84f7d0ea7373498632474dfafa23335f0c78e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96199039"
---
# <a name="cnot-operation"></a><span data-ttu-id="7c55c-102">CNOT işlemi</span><span class="sxs-lookup"><span data-stu-id="7c55c-102">CNOT operation</span></span>

<span data-ttu-id="7c55c-103">Ad alanı: [Microsoft. hisse. iç](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="7c55c-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="7c55c-104">Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="7c55c-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="7c55c-105">Denetlenen-NOT (CNOT) kapısını bir qubit çiftiyle uygular.</span><span class="sxs-lookup"><span data-stu-id="7c55c-105">Applies the controlled-NOT (CNOT) gate to a pair of qubits.</span></span>

<span data-ttu-id="7c55c-106">\begin{hizalaması} \operatorname{CNOT} \mathrel{: =} \begin{bmatrix} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 0 & 0 \\ \\ & 0 & 1 \\ \\ 0 & 0 & 1 & 0 \end{bmatrix}, \end{hizalaması}</span><span class="sxs-lookup"><span data-stu-id="7c55c-106">\begin{align} \operatorname{CNOT} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{bmatrix}, \end{align}</span></span>

<span data-ttu-id="7c55c-107">satırlar ve sütunlar hisse kavramları kılavuzunda olduğu gibi sıralanır.</span><span class="sxs-lookup"><span data-stu-id="7c55c-107">where rows and columns are ordered as in the quantum concepts guide.</span></span>

```qsharp
operation CNOT (control : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="7c55c-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="7c55c-108">Input</span></span>

### <a name="control--qubit"></a><span data-ttu-id="7c55c-109">Denetim: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="7c55c-109">control : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="7c55c-110">CNOT kapısı için denetim qubit.</span><span class="sxs-lookup"><span data-stu-id="7c55c-110">Control qubit for the CNOT gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="7c55c-111">Hedef: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="7c55c-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="7c55c-112">CNOT kapısı için hedef qubit.</span><span class="sxs-lookup"><span data-stu-id="7c55c-112">Target qubit for the CNOT gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7c55c-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7c55c-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="7c55c-114">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="7c55c-114">Remarks</span></span>

<span data-ttu-id="7c55c-115">Eşdeğer:</span><span class="sxs-lookup"><span data-stu-id="7c55c-115">Equivalent to:</span></span>

```qsharp
Controlled X([control], target);
```