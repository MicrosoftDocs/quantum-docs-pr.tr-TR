---
uid: Microsoft.Quantum.Intrinsic.T
title: T işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: T
qsharp.summary: Applies the T gate to a single qubit.
ms.openlocfilehash: bee252d9905aed26f6bf663f895e464e38073f44
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98817507"
---
# <a name="t-operation"></a><span data-ttu-id="6d3a6-102">T işlemi</span><span class="sxs-lookup"><span data-stu-id="6d3a6-102">T operation</span></span>

<span data-ttu-id="6d3a6-103">Ad alanı: [Microsoft. hisse. iç](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="6d3a6-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="6d3a6-104">Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="6d3a6-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="6d3a6-105">T geçidini tek bir qubit 'e uygular.</span><span class="sxs-lookup"><span data-stu-id="6d3a6-105">Applies the T gate to a single qubit.</span></span>

```qsharp
operation T (qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="6d3a6-106">Description</span><span class="sxs-lookup"><span data-stu-id="6d3a6-106">Description</span></span>

<span data-ttu-id="6d3a6-107">Bu işlem, Unitary matrisi \ Begin{hizalaması} T \mathrel{: =} \begin{bmatrix} 1 & 0 \\ \\ 0 & e ^ {ı \ Pi/4} \end{bmatrix} tarafından benzetilir.</span><span class="sxs-lookup"><span data-stu-id="6d3a6-107">This operation can be simulated by the unitary matrix \begin{align} T \mathrel{:=} \begin{bmatrix} 1 & 0 \\\\ 0 & e^{i \pi / 4} \end{bmatrix}.</span></span>
<span data-ttu-id="6d3a6-108">\end{hizalaması}</span><span class="sxs-lookup"><span data-stu-id="6d3a6-108">\end{align}</span></span>

## <a name="input"></a><span data-ttu-id="6d3a6-109">Giriş</span><span class="sxs-lookup"><span data-stu-id="6d3a6-109">Input</span></span>

### <a name="qubit--qubit"></a><span data-ttu-id="6d3a6-110">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="6d3a6-110">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="6d3a6-111">Gate 'in uygulanması gereken qubit.</span><span class="sxs-lookup"><span data-stu-id="6d3a6-111">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6d3a6-112">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6d3a6-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

