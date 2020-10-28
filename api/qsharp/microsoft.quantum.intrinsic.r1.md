---
uid: Microsoft.Quantum.Intrinsic.R1
title: R1 işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: R1
qsharp.summary: >-
  Applies a rotation about the $\ket{1}$ state by a given angle.

  \begin{align} R_1(\theta) \mathrel{:=} \operatorname{diag}(1, e^{i\theta}). \end{align}
ms.openlocfilehash: 87302a4338af144ee6a8cec83ed1803581597482
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731383"
---
# <a name="r1-operation"></a><span data-ttu-id="6c5e0-102">R1 işlemi</span><span class="sxs-lookup"><span data-stu-id="6c5e0-102">R1 operation</span></span>

<span data-ttu-id="6c5e0-103">Ad alanı: [Microsoft. hisse. iç](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="6c5e0-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="6c5e0-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6c5e0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6c5e0-105">$ \Ket {1} $ durumu hakkında verilen bir açıda bir döndürme uygular.</span><span class="sxs-lookup"><span data-stu-id="6c5e0-105">Applies a rotation about the $\ket{1}$ state by a given angle.</span></span>

<span data-ttu-id="6c5e0-106">\begin{hizalaması} R_1 (\teta) \mathrel{: =} \operatorname{diag} (1, e ^ {i\teta}).</span><span class="sxs-lookup"><span data-stu-id="6c5e0-106">\begin{align} R_1(\theta) \mathrel{:=} \operatorname{diag}(1, e^{i\theta}).</span></span>
<span data-ttu-id="6c5e0-107">\end{hizalaması}</span><span class="sxs-lookup"><span data-stu-id="6c5e0-107">\end{align}</span></span>

```qsharp
operation R1 (theta : Double, qubit : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="6c5e0-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="6c5e0-108">Input</span></span>

### <a name="theta--double"></a><span data-ttu-id="6c5e0-109">Teta: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="6c5e0-109">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="6c5e0-110">Qubitin döndürüleceği açı.</span><span class="sxs-lookup"><span data-stu-id="6c5e0-110">Angle about which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="6c5e0-111">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="6c5e0-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="6c5e0-112">Gate 'in uygulanması gereken qubit.</span><span class="sxs-lookup"><span data-stu-id="6c5e0-112">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6c5e0-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6c5e0-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="6c5e0-114">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="6c5e0-114">Remarks</span></span>

<span data-ttu-id="6c5e0-115">Eşdeğer:</span><span class="sxs-lookup"><span data-stu-id="6c5e0-115">Equivalent to:</span></span>

```qsharp
R(PauliZ, theta, qubit);
R(PauliI, -theta, qubit);
```