---
uid: Microsoft.Quantum.Intrinsic.CCNOT
title: CCNOT işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: CCNOT
qsharp.summary: Applies the doubly controlled–NOT (CCNOT) gate to three qubits.
ms.openlocfilehash: 715796ddd915d80036933e3f1ceefa97aa62cecf
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96212486"
---
# <a name="ccnot-operation"></a><span data-ttu-id="84721-102">CCNOT işlemi</span><span class="sxs-lookup"><span data-stu-id="84721-102">CCNOT operation</span></span>

<span data-ttu-id="84721-103">Ad alanı: [Microsoft. hisse. iç](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="84721-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="84721-104">Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="84721-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="84721-105">Üçlü denetimli (CCNOT) kapısını üç qubit 'e uygular.</span><span class="sxs-lookup"><span data-stu-id="84721-105">Applies the doubly controlled–NOT (CCNOT) gate to three qubits.</span></span>

```qsharp
operation CCNOT (control1 : Qubit, control2 : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="84721-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="84721-106">Input</span></span>

### <a name="control1--qubit"></a><span data-ttu-id="84721-107">Control1: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="84721-107">control1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="84721-108">CCNOT kapısı için ilk denetim qubit.</span><span class="sxs-lookup"><span data-stu-id="84721-108">First control qubit for the CCNOT gate.</span></span>


### <a name="control2--qubit"></a><span data-ttu-id="84721-109">Control2: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="84721-109">control2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="84721-110">CCNOT kapısı için ikinci denetim qubit.</span><span class="sxs-lookup"><span data-stu-id="84721-110">Second control qubit for the CCNOT gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="84721-111">Hedef: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="84721-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="84721-112">CCNOT kapısı için hedef qubit.</span><span class="sxs-lookup"><span data-stu-id="84721-112">Target qubit for the CCNOT gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="84721-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="84721-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="84721-114">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="84721-114">Remarks</span></span>

<span data-ttu-id="84721-115">Eşdeğer:</span><span class="sxs-lookup"><span data-stu-id="84721-115">Equivalent to:</span></span>

```qsharp
Controlled X([control1, control2], target);
```