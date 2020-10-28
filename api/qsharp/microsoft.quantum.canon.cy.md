---
uid: Microsoft.Quantum.Canon.CY
title: CY işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CY
qsharp.summary: >-
  Applies the controlled-Y (CY) gate to a pair of qubits.

  $$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & -i \\\\ 0 & 0 & i & 0 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.
ms.openlocfilehash: 291891457ff39cf7092d17aa1d900dd0d35d9cf8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728783"
---
# <a name="cy-operation"></a><span data-ttu-id="685d5-102">CY işlemi</span><span class="sxs-lookup"><span data-stu-id="685d5-102">CY operation</span></span>

<span data-ttu-id="685d5-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="685d5-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="685d5-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="685d5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="685d5-105">Denetimli-Y (CY) kapısını bir qubit çiftiyle uygular.</span><span class="sxs-lookup"><span data-stu-id="685d5-105">Applies the controlled-Y (CY) gate to a pair of qubits.</span></span>

<span data-ttu-id="685d5-106">$ $ \begin{hizalaması} 1 & 0 & 0 & 0 0 \\ \\ & 1 & 0 & 0 0 & 0 & \\ \\ 0 &-ı 0 & 0 & \\ \\ ı & 0 \ End{hizalaması}, $ $ burada satır ve sütun, hisse kavramları kılavuzunda olduğu gibi düzenlenmiştir.</span><span class="sxs-lookup"><span data-stu-id="685d5-106">$$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & -i \\\\ 0 & 0 & i & 0 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.</span></span>

```qsharp
operation CY (control : Qubit, target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="685d5-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="685d5-107">Input</span></span>

### <a name="control--qubit"></a><span data-ttu-id="685d5-108">Denetim: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="685d5-108">control : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="685d5-109">CY kapısı için qubit denetimi.</span><span class="sxs-lookup"><span data-stu-id="685d5-109">Control qubit for the CY gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="685d5-110">Hedef: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="685d5-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="685d5-111">CY kapısı için hedef qubit.</span><span class="sxs-lookup"><span data-stu-id="685d5-111">Target qubit for the CY gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="685d5-112">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="685d5-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="685d5-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="685d5-113">Remarks</span></span>

<span data-ttu-id="685d5-114">Eşdeğer:</span><span class="sxs-lookup"><span data-stu-id="685d5-114">Equivalent to:</span></span>

```qsharp
Controlled Y([control], target);
```