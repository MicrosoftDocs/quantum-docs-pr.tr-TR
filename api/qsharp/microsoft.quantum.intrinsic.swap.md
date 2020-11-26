---
uid: Microsoft.Quantum.Intrinsic.SWAP
title: DEĞIŞTIRME işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: SWAP
qsharp.summary: >-
  Applies the SWAP gate to a pair of qubits.

  \begin{align} \operatorname{SWAP} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \end{bmatrix}, \end{align}

  where rows and columns are ordered as in the quantum concepts guide.
ms.openlocfilehash: e93c976f2fdf02de77fafa4d22e95fe9a33a9ba6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198427"
---
# <a name="swap-operation"></a><span data-ttu-id="1cb16-102">DEĞIŞTIRME işlemi</span><span class="sxs-lookup"><span data-stu-id="1cb16-102">SWAP operation</span></span>

<span data-ttu-id="1cb16-103">Ad alanı: [Microsoft. hisse. iç](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="1cb16-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="1cb16-104">Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="1cb16-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="1cb16-105">DEĞIŞTIRME kapısını bir qubits çiftine uygular.</span><span class="sxs-lookup"><span data-stu-id="1cb16-105">Applies the SWAP gate to a pair of qubits.</span></span>

<span data-ttu-id="1cb16-106">\begin{hizalaması} \operatorname{SWAP} \mathrel{: =} \begin{bmatrix} 1 & 0 & 0 & 0 \\ \\ 0 & 0 & 1 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 & 1 \ End{bmatrix}, \end{hizalaması}</span><span class="sxs-lookup"><span data-stu-id="1cb16-106">\begin{align} \operatorname{SWAP} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \end{bmatrix}, \end{align}</span></span>

<span data-ttu-id="1cb16-107">satırlar ve sütunlar hisse kavramları kılavuzunda olduğu gibi sıralanır.</span><span class="sxs-lookup"><span data-stu-id="1cb16-107">where rows and columns are ordered as in the quantum concepts guide.</span></span>

```qsharp
operation SWAP (qubit1 : Qubit, qubit2 : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="1cb16-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="1cb16-108">Input</span></span>

### <a name="qubit1--qubit"></a><span data-ttu-id="1cb16-109">qubit1: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="1cb16-109">qubit1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="1cb16-110">Takas edilecek ilk qubit.</span><span class="sxs-lookup"><span data-stu-id="1cb16-110">First qubit to be swapped.</span></span>


### <a name="qubit2--qubit"></a><span data-ttu-id="1cb16-111">qubit2: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="1cb16-111">qubit2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="1cb16-112">Takas edilecek ikinci qubit.</span><span class="sxs-lookup"><span data-stu-id="1cb16-112">Second qubit to be swapped.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1cb16-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1cb16-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="1cb16-114">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="1cb16-114">Remarks</span></span>

<span data-ttu-id="1cb16-115">Eşdeğer:</span><span class="sxs-lookup"><span data-stu-id="1cb16-115">Equivalent to:</span></span>

```qsharp
CNOT(qubit1, qubit2);
CNOT(qubit2, qubit1);
CNOT(qubit1, qubit2);
```