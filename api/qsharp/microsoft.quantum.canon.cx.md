---
uid: Microsoft.Quantum.Canon.CX
title: CX işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CX
qsharp.summary: >-
  Applies the controlled-X (CX) gate to a pair of qubits.

  $$ \begin{align} \left(\begin{matrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{matrix}\right) \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.
ms.openlocfilehash: e27b30a6b4609daaac2cc5eda68120115777af0c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840749"
---
# <a name="cx-operation"></a><span data-ttu-id="e4b25-102">CX işlemi</span><span class="sxs-lookup"><span data-stu-id="e4b25-102">CX operation</span></span>

<span data-ttu-id="e4b25-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e4b25-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e4b25-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e4b25-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e4b25-105">Denetlenen X (CX) kapısını bir qubit çiftiyle uygular.</span><span class="sxs-lookup"><span data-stu-id="e4b25-105">Applies the controlled-X (CX) gate to a pair of qubits.</span></span>

<span data-ttu-id="e4b25-106">$ $ \begin{hizalaması} \left (\begin{Matrix} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 & 1 \\ \\ 0 & 0 & 1 & 0 \end{Matrix}\right) \end{hizalaması}, $ $ burada satırlar ve sütunlar hisse kavramları kılavuzunda olduğu gibi düzenlenmiştir.</span><span class="sxs-lookup"><span data-stu-id="e4b25-106">$$ \begin{align} \left(\begin{matrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{matrix}\right) \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.</span></span>

```qsharp
operation CX (control : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="e4b25-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="e4b25-107">Input</span></span>

### <a name="control--qubit"></a><span data-ttu-id="e4b25-108">Denetim: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="e4b25-108">control : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="e4b25-109">CX kapısı için denetim qubit.</span><span class="sxs-lookup"><span data-stu-id="e4b25-109">Control qubit for the CX gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="e4b25-110">Hedef: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="e4b25-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="e4b25-111">CX kapısı için hedef qubit.</span><span class="sxs-lookup"><span data-stu-id="e4b25-111">Target qubit for the CX gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e4b25-112">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e4b25-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="e4b25-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="e4b25-113">Remarks</span></span>

<span data-ttu-id="e4b25-114">Eşdeğer:</span><span class="sxs-lookup"><span data-stu-id="e4b25-114">Equivalent to:</span></span>

```qsharp
Controlled X([control], target);
```

<span data-ttu-id="e4b25-115">ve için:</span><span class="sxs-lookup"><span data-stu-id="e4b25-115">and to:</span></span>

```qsharp
CNOT(control, target);
```