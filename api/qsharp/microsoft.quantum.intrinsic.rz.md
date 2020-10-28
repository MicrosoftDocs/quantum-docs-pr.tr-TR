---
uid: Microsoft.Quantum.Intrinsic.Rz
title: RZ işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Rz
qsharp.summary: >-
  Applies a rotation about the $z$-axis by a given angle.

  \begin{align} R_z(\theta) \mathrel{:=} e^{-i \theta \sigma_z / 2} = \begin{bmatrix} e^{-i \theta / 2} & 0 \\\\ 0 & e^{i \theta / 2} \end{bmatrix}. \end{align}
ms.openlocfilehash: 954b0b097d4bffcb8047a9f0c8a4c28445653c5d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731346"
---
# <a name="rz-operation"></a><span data-ttu-id="c9f6c-102">RZ işlemi</span><span class="sxs-lookup"><span data-stu-id="c9f6c-102">Rz operation</span></span>

<span data-ttu-id="c9f6c-103">Ad alanı: [Microsoft. hisse. iç](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="c9f6c-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="c9f6c-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c9f6c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c9f6c-105">$Z $-ekseni ile verilen bir açıda bir döndürme uygular.</span><span class="sxs-lookup"><span data-stu-id="c9f6c-105">Applies a rotation about the $z$-axis by a given angle.</span></span>

<span data-ttu-id="c9f6c-106">\begin{hizalaması} R_z (\teta) \mathrel{: =} e ^ {-i \teta \ sigma_z/2} = \begin{bmatrix} e ^ {-i \teta/2} & 0 \\ \\ 0 & e ^ {ı \ teta/2} \end{bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="c9f6c-106">\begin{align} R_z(\theta) \mathrel{:=} e^{-i \theta \sigma_z / 2} = \begin{bmatrix} e^{-i \theta / 2} & 0 \\\\ 0 & e^{i \theta / 2} \end{bmatrix}.</span></span>
<span data-ttu-id="c9f6c-107">\end{hizalaması}</span><span class="sxs-lookup"><span data-stu-id="c9f6c-107">\end{align}</span></span>

```qsharp
operation Rz (theta : Double, qubit : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="c9f6c-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="c9f6c-108">Input</span></span>

### <a name="theta--double"></a><span data-ttu-id="c9f6c-109">Teta: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c9f6c-109">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c9f6c-110">Qubitin döndürüleceği açı.</span><span class="sxs-lookup"><span data-stu-id="c9f6c-110">Angle about which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="c9f6c-111">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="c9f6c-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="c9f6c-112">Gate 'in uygulanması gereken qubit.</span><span class="sxs-lookup"><span data-stu-id="c9f6c-112">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c9f6c-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c9f6c-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="c9f6c-114">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="c9f6c-114">Remarks</span></span>

<span data-ttu-id="c9f6c-115">Eşdeğer:</span><span class="sxs-lookup"><span data-stu-id="c9f6c-115">Equivalent to:</span></span>

```qsharp
R(PauliZ, theta, qubit);
```