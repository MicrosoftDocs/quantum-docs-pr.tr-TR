---
uid: Microsoft.Quantum.Canon.CZ
title: CZ işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CZ
qsharp.summary: >-
  Applies the controlled-Z (CZ) gate to a pair of qubits.

  $$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 0 & 0 & -1 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.
ms.openlocfilehash: bc38cd43a0dcaf7aea735ef6468a394e91c85593
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728777"
---
# <a name="cz-operation"></a><span data-ttu-id="3af2f-102">CZ işlemi</span><span class="sxs-lookup"><span data-stu-id="3af2f-102">CZ operation</span></span>

<span data-ttu-id="3af2f-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="3af2f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="3af2f-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3af2f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3af2f-105">Denetlenen-Z (CZ) kapısını bir qubit çiftiyle uygular.</span><span class="sxs-lookup"><span data-stu-id="3af2f-105">Applies the controlled-Z (CZ) gate to a pair of qubits.</span></span>

<span data-ttu-id="3af2f-106">$ $ \begin{hizalaması} 1 & 0 & 0 & 0 0 \\ \\ & 1 & 0 & 0 0 & 0 & \\ \\ 1 & 0 \\ \\ 0 & 0 & 0 &-1 \end{hizalaması}, $ $ burada satırlar ve sütunlar, hisse kavramları kılavuzunda olduğu gibi düzenlenmiştir.</span><span class="sxs-lookup"><span data-stu-id="3af2f-106">$$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 0 & 0 & -1 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.</span></span>

```qsharp
operation CZ (control : Qubit, target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="3af2f-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="3af2f-107">Input</span></span>

### <a name="control--qubit"></a><span data-ttu-id="3af2f-108">Denetim: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="3af2f-108">control : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="3af2f-109">CZ kapısı için denetim qubit.</span><span class="sxs-lookup"><span data-stu-id="3af2f-109">Control qubit for the CZ gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="3af2f-110">Hedef: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="3af2f-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="3af2f-111">CZ kapısı için hedef qubit.</span><span class="sxs-lookup"><span data-stu-id="3af2f-111">Target qubit for the CZ gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3af2f-112">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3af2f-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="3af2f-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="3af2f-113">Remarks</span></span>

<span data-ttu-id="3af2f-114">Eşdeğer:</span><span class="sxs-lookup"><span data-stu-id="3af2f-114">Equivalent to:</span></span>

```qsharp
Controlled Z([control], target);
```