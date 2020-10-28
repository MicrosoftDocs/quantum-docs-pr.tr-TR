---
uid: Microsoft.Quantum.Intrinsic.Rx
title: RX işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Rx
qsharp.summary: >-
  Applies a rotation about the $x$-axis by a given angle.

  \begin{align} R_x(\theta) \mathrel{:=} e^{-i \theta \sigma_x / 2} = \begin{bmatrix} \cos \frac{\theta}{2} & -i\sin \frac{\theta}{2}  \\\\ -i\sin \frac{\theta}{2} & \cos \frac{\theta}{2} \end{bmatrix}. \end{align}
ms.openlocfilehash: 6d11c8fa3c3fb2c07a88fdf2cba0ff2a7f51bf6b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732935"
---
# <a name="rx-operation"></a><span data-ttu-id="07b49-102">RX işlemi</span><span class="sxs-lookup"><span data-stu-id="07b49-102">Rx operation</span></span>

<span data-ttu-id="07b49-103">Ad alanı: [Microsoft. hisse. iç](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="07b49-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="07b49-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="07b49-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="07b49-105">$X $-ekseni ile verilen bir açıda bir döndürme uygular.</span><span class="sxs-lookup"><span data-stu-id="07b49-105">Applies a rotation about the $x$-axis by a given angle.</span></span>

<span data-ttu-id="07b49-106">\begin{hizalaması} R_x (\teta) \mathrel{: =} e ^ {-i \teta \ sigma_x/2} = \begin{bmatrix} \cos \frac{\theta} {2} &-ı\sin \ FRAC{\theta}-i\sin \ FRAC{\theta} {2} \\ \\ {2} & \cos \ FRAC{\theta} {2} \end{bmatrix}.  </span><span class="sxs-lookup"><span data-stu-id="07b49-106">\begin{align} R_x(\theta) \mathrel{:=} e^{-i \theta \sigma_x / 2} = \begin{bmatrix} \cos \frac{\theta}{2} & -i\sin \frac{\theta}{2}  \\\\ -i\sin \frac{\theta}{2} & \cos \frac{\theta}{2} \end{bmatrix}.</span></span>
<span data-ttu-id="07b49-107">\end{hizalaması}</span><span class="sxs-lookup"><span data-stu-id="07b49-107">\end{align}</span></span>

```qsharp
operation Rx (theta : Double, qubit : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="07b49-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="07b49-108">Input</span></span>

### <a name="theta--double"></a><span data-ttu-id="07b49-109">Teta: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="07b49-109">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="07b49-110">Qubitin döndürüleceği açı.</span><span class="sxs-lookup"><span data-stu-id="07b49-110">Angle about which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="07b49-111">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="07b49-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="07b49-112">Gate 'in uygulanması gereken qubit.</span><span class="sxs-lookup"><span data-stu-id="07b49-112">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="07b49-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="07b49-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="07b49-114">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="07b49-114">Remarks</span></span>

<span data-ttu-id="07b49-115">Eşdeğer:</span><span class="sxs-lookup"><span data-stu-id="07b49-115">Equivalent to:</span></span>

```qsharp
R(PauliX, theta, qubit);
```