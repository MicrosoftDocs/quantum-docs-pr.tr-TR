---
uid: Microsoft.Quantum.Intrinsic.CCNOT
title: CCNOT işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: CCNOT
qsharp.summary: Applies the doubly controlled–NOT (CCNOT) gate to three qubits.
ms.openlocfilehash: bf20ff1e9d25d72e7e8e0207ab947a57dc394cf4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726714"
---
# <a name="ccnot-operation"></a><span data-ttu-id="42dcf-102">CCNOT işlemi</span><span class="sxs-lookup"><span data-stu-id="42dcf-102">CCNOT operation</span></span>

<span data-ttu-id="42dcf-103">Ad alanı: [Microsoft. hisse. iç](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="42dcf-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="42dcf-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="42dcf-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="42dcf-105">Üçlü denetimli (CCNOT) kapısını üç qubit 'e uygular.</span><span class="sxs-lookup"><span data-stu-id="42dcf-105">Applies the doubly controlled–NOT (CCNOT) gate to three qubits.</span></span>

```qsharp
operation CCNOT (control1 : Qubit, control2 : Qubit, target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="42dcf-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="42dcf-106">Input</span></span>

### <a name="control1--qubit"></a><span data-ttu-id="42dcf-107">Control1: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="42dcf-107">control1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="42dcf-108">CCNOT kapısı için ilk denetim qubit.</span><span class="sxs-lookup"><span data-stu-id="42dcf-108">First control qubit for the CCNOT gate.</span></span>


### <a name="control2--qubit"></a><span data-ttu-id="42dcf-109">Control2: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="42dcf-109">control2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="42dcf-110">CCNOT kapısı için ikinci denetim qubit.</span><span class="sxs-lookup"><span data-stu-id="42dcf-110">Second control qubit for the CCNOT gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="42dcf-111">Hedef: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="42dcf-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="42dcf-112">CCNOT kapısı için hedef qubit.</span><span class="sxs-lookup"><span data-stu-id="42dcf-112">Target qubit for the CCNOT gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="42dcf-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="42dcf-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="42dcf-114">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="42dcf-114">Remarks</span></span>

<span data-ttu-id="42dcf-115">Eşdeğer:</span><span class="sxs-lookup"><span data-stu-id="42dcf-115">Equivalent to:</span></span>

```qsharp
Controlled X([control1, control2], target);
```