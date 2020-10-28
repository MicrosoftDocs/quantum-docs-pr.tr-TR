---
uid: Microsoft.Quantum.Canon.CX
title: CX işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CX
qsharp.summary: >-
  Applies the controlled-X (CX) gate to a pair of qubits.

  $$ \begin{align} \left(\begin{matrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{matrix}\right) \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.
ms.openlocfilehash: c430525b71ad4ef0812d90a8ff20c41a5d5b8708
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728789"
---
# <a name="cx-operation"></a><span data-ttu-id="aa3a3-102">CX işlemi</span><span class="sxs-lookup"><span data-stu-id="aa3a3-102">CX operation</span></span>

<span data-ttu-id="aa3a3-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="aa3a3-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="aa3a3-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="aa3a3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="aa3a3-105">Denetlenen X (CX) kapısını bir qubit çiftiyle uygular.</span><span class="sxs-lookup"><span data-stu-id="aa3a3-105">Applies the controlled-X (CX) gate to a pair of qubits.</span></span>

<span data-ttu-id="aa3a3-106">$ $ \begin{hizalaması} \left (\begin{Matrix} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 & 1 \\ \\ 0 & 0 & 1 & 0 \end{Matrix}\right) \end{hizalaması}, $ $ burada satırlar ve sütunlar hisse kavramları kılavuzunda olduğu gibi düzenlenmiştir.</span><span class="sxs-lookup"><span data-stu-id="aa3a3-106">$$ \begin{align} \left(\begin{matrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{matrix}\right) \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.</span></span>

```qsharp
operation CX (control : Qubit, target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="aa3a3-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="aa3a3-107">Input</span></span>

### <a name="control--qubit"></a><span data-ttu-id="aa3a3-108">Denetim: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="aa3a3-108">control : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="aa3a3-109">CX kapısı için denetim qubit.</span><span class="sxs-lookup"><span data-stu-id="aa3a3-109">Control qubit for the CX gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="aa3a3-110">Hedef: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="aa3a3-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="aa3a3-111">CX kapısı için hedef qubit.</span><span class="sxs-lookup"><span data-stu-id="aa3a3-111">Target qubit for the CX gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="aa3a3-112">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="aa3a3-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="aa3a3-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="aa3a3-113">Remarks</span></span>

<span data-ttu-id="aa3a3-114">Eşdeğer:</span><span class="sxs-lookup"><span data-stu-id="aa3a3-114">Equivalent to:</span></span>

```qsharp
Controlled X([control], target);
```

<span data-ttu-id="aa3a3-115">ve için:</span><span class="sxs-lookup"><span data-stu-id="aa3a3-115">and to:</span></span>

```qsharp
CNOT(control, target);
```