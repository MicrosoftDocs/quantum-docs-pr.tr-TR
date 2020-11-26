---
uid: Microsoft.Quantum.Intrinsic.Rx
title: RX işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Rx
qsharp.summary: >-
  Applies a rotation about the $x$-axis by a given angle.

  \begin{align} R_x(\theta) \mathrel{:=} e^{-i \theta \sigma_x / 2} = \begin{bmatrix} \cos \frac{\theta}{2} & -i\sin \frac{\theta}{2}  \\\\ -i\sin \frac{\theta}{2} & \cos \frac{\theta}{2} \end{bmatrix}. \end{align}
ms.openlocfilehash: 49638c00967ff2f47dad41acfed05868d65a24a0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198597"
---
# <a name="rx-operation"></a><span data-ttu-id="2dd5b-102">RX işlemi</span><span class="sxs-lookup"><span data-stu-id="2dd5b-102">Rx operation</span></span>

<span data-ttu-id="2dd5b-103">Ad alanı: [Microsoft. hisse. iç](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="2dd5b-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="2dd5b-104">Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="2dd5b-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="2dd5b-105">$X $-ekseni ile verilen bir açıda bir döndürme uygular.</span><span class="sxs-lookup"><span data-stu-id="2dd5b-105">Applies a rotation about the $x$-axis by a given angle.</span></span>

<span data-ttu-id="2dd5b-106">\begin{hizalaması} R_x (\teta) \mathrel{: =} e ^ {-i \teta \ sigma_x/2} = \begin{bmatrix} \cos \frac{\theta} {2} &-ı\sin \ FRAC{\theta}-i\sin \ FRAC{\theta} {2} \\ \\ {2} & \cos \ FRAC{\theta} {2} \end{bmatrix}.  </span><span class="sxs-lookup"><span data-stu-id="2dd5b-106">\begin{align} R_x(\theta) \mathrel{:=} e^{-i \theta \sigma_x / 2} = \begin{bmatrix} \cos \frac{\theta}{2} & -i\sin \frac{\theta}{2}  \\\\ -i\sin \frac{\theta}{2} & \cos \frac{\theta}{2} \end{bmatrix}.</span></span>
<span data-ttu-id="2dd5b-107">\end{hizalaması}</span><span class="sxs-lookup"><span data-stu-id="2dd5b-107">\end{align}</span></span>

```qsharp
operation Rx (theta : Double, qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="2dd5b-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="2dd5b-108">Input</span></span>

### <a name="theta--double"></a><span data-ttu-id="2dd5b-109">Teta: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="2dd5b-109">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="2dd5b-110">Qubitin döndürüleceği açı.</span><span class="sxs-lookup"><span data-stu-id="2dd5b-110">Angle about which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="2dd5b-111">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="2dd5b-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="2dd5b-112">Gate 'in uygulanması gereken qubit.</span><span class="sxs-lookup"><span data-stu-id="2dd5b-112">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2dd5b-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2dd5b-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="2dd5b-114">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="2dd5b-114">Remarks</span></span>

<span data-ttu-id="2dd5b-115">Eşdeğer:</span><span class="sxs-lookup"><span data-stu-id="2dd5b-115">Equivalent to:</span></span>

```qsharp
R(PauliX, theta, qubit);
```