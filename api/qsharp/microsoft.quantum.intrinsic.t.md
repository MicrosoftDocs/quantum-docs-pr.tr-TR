---
uid: Microsoft.Quantum.Intrinsic.T
title: T işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: T
qsharp.summary: Applies the T gate to a single qubit.
ms.openlocfilehash: 868031386c95f65ae956b5e444c6d87d7ea0a697
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731338"
---
# <a name="t-operation"></a><span data-ttu-id="a4f91-102">T işlemi</span><span class="sxs-lookup"><span data-stu-id="a4f91-102">T operation</span></span>

<span data-ttu-id="a4f91-103">Ad alanı: [Microsoft. hisse. iç](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="a4f91-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="a4f91-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a4f91-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a4f91-105">T geçidini tek bir qubit 'e uygular.</span><span class="sxs-lookup"><span data-stu-id="a4f91-105">Applies the T gate to a single qubit.</span></span>

```qsharp
operation T (qubit : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="a4f91-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="a4f91-106">Description</span></span>

<span data-ttu-id="a4f91-107">Bu işlem, Unitary matrisi \ Begin{hizalaması} T \mathrel{: =} \begin{bmatrix} 1 & 0 \\ \\ 0 & e ^ {ı \ Pi/4} \end{bmatrix} tarafından benzetilir.</span><span class="sxs-lookup"><span data-stu-id="a4f91-107">This operation can be simulated by the unitary matrix \begin{align} T \mathrel{:=} \begin{bmatrix} 1 & 0 \\\\ 0 & e^{i \pi / 4} \end{bmatrix}.</span></span>
<span data-ttu-id="a4f91-108">\end{hizalaması}</span><span class="sxs-lookup"><span data-stu-id="a4f91-108">\end{align}</span></span>

## <a name="input"></a><span data-ttu-id="a4f91-109">Giriş</span><span class="sxs-lookup"><span data-stu-id="a4f91-109">Input</span></span>

### <a name="qubit--qubit"></a><span data-ttu-id="a4f91-110">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="a4f91-110">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="a4f91-111">Gate 'in uygulanması gereken qubit.</span><span class="sxs-lookup"><span data-stu-id="a4f91-111">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a4f91-112">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a4f91-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

