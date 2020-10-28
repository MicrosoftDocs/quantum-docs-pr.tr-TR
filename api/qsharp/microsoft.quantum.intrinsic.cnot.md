---
uid: Microsoft.Quantum.Intrinsic.CNOT
title: CNOT işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: CNOT
qsharp.summary: >-
  Applies the controlled-NOT (CNOT) gate to a pair of qubits.

  \begin{align} \operatorname{CNOT} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{bmatrix}, \end{align}

  where rows and columns are ordered as in the quantum concepts guide.
ms.openlocfilehash: 2fb5b4df189fb3ab23b2ca5cb273b2451ffcc067
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732458"
---
# <a name="cnot-operation"></a><span data-ttu-id="54757-102">CNOT işlemi</span><span class="sxs-lookup"><span data-stu-id="54757-102">CNOT operation</span></span>

<span data-ttu-id="54757-103">Ad alanı: [Microsoft. hisse. iç](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="54757-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="54757-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="54757-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="54757-105">Denetlenen-NOT (CNOT) kapısını bir qubit çiftiyle uygular.</span><span class="sxs-lookup"><span data-stu-id="54757-105">Applies the controlled-NOT (CNOT) gate to a pair of qubits.</span></span>

<span data-ttu-id="54757-106">\begin{hizalaması} \operatorname{CNOT} \mathrel{: =} \begin{bmatrix} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 0 & 0 \\ \\ & 0 & 1 \\ \\ 0 & 0 & 1 & 0 \end{bmatrix}, \end{hizalaması}</span><span class="sxs-lookup"><span data-stu-id="54757-106">\begin{align} \operatorname{CNOT} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{bmatrix}, \end{align}</span></span>

<span data-ttu-id="54757-107">satırlar ve sütunlar hisse kavramları kılavuzunda olduğu gibi sıralanır.</span><span class="sxs-lookup"><span data-stu-id="54757-107">where rows and columns are ordered as in the quantum concepts guide.</span></span>

```qsharp
operation CNOT (control : Qubit, target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="54757-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="54757-108">Input</span></span>

### <a name="control--qubit"></a><span data-ttu-id="54757-109">Denetim: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="54757-109">control : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="54757-110">CNOT kapısı için denetim qubit.</span><span class="sxs-lookup"><span data-stu-id="54757-110">Control qubit for the CNOT gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="54757-111">Hedef: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="54757-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="54757-112">CNOT kapısı için hedef qubit.</span><span class="sxs-lookup"><span data-stu-id="54757-112">Target qubit for the CNOT gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="54757-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="54757-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="54757-114">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="54757-114">Remarks</span></span>

<span data-ttu-id="54757-115">Eşdeğer:</span><span class="sxs-lookup"><span data-stu-id="54757-115">Equivalent to:</span></span>

```qsharp
Controlled X([control], target);
```