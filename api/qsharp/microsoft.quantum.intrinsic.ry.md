---
uid: Microsoft.Quantum.Intrinsic.Ry
title: Ry işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Ry
qsharp.summary: >-
  Applies a rotation about the $y$-axis by a given angle.

  \begin{align} R_y(\theta) \mathrel{:=} e^{-i \theta \sigma_y / 2} = \begin{bmatrix} \cos \frac{\theta}{2} & -\sin \frac{\theta}{2}  \\\\ \sin \frac{\theta}{2} & \cos \frac{\theta}{2} \end{bmatrix}. \end{align}
ms.openlocfilehash: 9966693eb7283e855f7b72e910aa3604d6c2bd61
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730775"
---
# <a name="ry-operation"></a><span data-ttu-id="6a9c7-102">Ry işlemi</span><span class="sxs-lookup"><span data-stu-id="6a9c7-102">Ry operation</span></span>

<span data-ttu-id="6a9c7-103">Ad alanı: [Microsoft. hisse. iç](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="6a9c7-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="6a9c7-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6a9c7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6a9c7-105">$Y $-ekseni ile verilen bir açıda bir döndürme uygular.</span><span class="sxs-lookup"><span data-stu-id="6a9c7-105">Applies a rotation about the $y$-axis by a given angle.</span></span>

<span data-ttu-id="6a9c7-106">\begin{hizalaması} R_y (\teta) \mathrel{: =} e ^ {-i \teta \ sigma_y/2} = \begin{bmatrix} \cos \frac{\theta} {2} &-\sin \ FRAC{\theta} {2} \\ \\ \sin \frac{\theta} {2} & \cos \frac{\theta} {2} \end{bmatrix}.  </span><span class="sxs-lookup"><span data-stu-id="6a9c7-106">\begin{align} R_y(\theta) \mathrel{:=} e^{-i \theta \sigma_y / 2} = \begin{bmatrix} \cos \frac{\theta}{2} & -\sin \frac{\theta}{2}  \\\\ \sin \frac{\theta}{2} & \cos \frac{\theta}{2} \end{bmatrix}.</span></span>
<span data-ttu-id="6a9c7-107">\end{hizalaması}</span><span class="sxs-lookup"><span data-stu-id="6a9c7-107">\end{align}</span></span>

```qsharp
operation Ry (theta : Double, qubit : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="6a9c7-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="6a9c7-108">Input</span></span>

### <a name="theta--double"></a><span data-ttu-id="6a9c7-109">Teta: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="6a9c7-109">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="6a9c7-110">Qubitin döndürüleceği açı.</span><span class="sxs-lookup"><span data-stu-id="6a9c7-110">Angle about which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="6a9c7-111">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="6a9c7-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="6a9c7-112">Gate 'in uygulanması gereken qubit.</span><span class="sxs-lookup"><span data-stu-id="6a9c7-112">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6a9c7-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6a9c7-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="6a9c7-114">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="6a9c7-114">Remarks</span></span>

<span data-ttu-id="6a9c7-115">Eşdeğer:</span><span class="sxs-lookup"><span data-stu-id="6a9c7-115">Equivalent to:</span></span>

```qsharp
R(PauliY, theta, qubit);
```