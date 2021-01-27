---
uid: Microsoft.Quantum.Intrinsic.Rz
title: RZ işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Rz
qsharp.summary: >-
  Applies a rotation about the $z$-axis by a given angle.

  \begin{align} R_z(\theta) \mathrel{:=} e^{-i \theta \sigma_z / 2} = \begin{bmatrix} e^{-i \theta / 2} & 0 \\\\ 0 & e^{i \theta / 2} \end{bmatrix}. \end{align}
ms.openlocfilehash: 4282fcc216173234ec742991b8f0fa1be203da0d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849286"
---
# <a name="rz-operation"></a><span data-ttu-id="482c4-102">RZ işlemi</span><span class="sxs-lookup"><span data-stu-id="482c4-102">Rz operation</span></span>

<span data-ttu-id="482c4-103">Ad alanı: [Microsoft. hisse. iç](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="482c4-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="482c4-104">Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="482c4-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="482c4-105">$Z $-ekseni ile verilen bir açıda bir döndürme uygular.</span><span class="sxs-lookup"><span data-stu-id="482c4-105">Applies a rotation about the $z$-axis by a given angle.</span></span>

<span data-ttu-id="482c4-106">\begin{hizalaması} R_z (\teta) \mathrel{: =} e ^ {-i \teta \ sigma_z/2} = \begin{bmatrix} e ^ {-i \teta/2} & 0 \\ \\ 0 & e ^ {ı \ teta/2} \end{bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="482c4-106">\begin{align} R_z(\theta) \mathrel{:=} e^{-i \theta \sigma_z / 2} = \begin{bmatrix} e^{-i \theta / 2} & 0 \\\\ 0 & e^{i \theta / 2} \end{bmatrix}.</span></span>
<span data-ttu-id="482c4-107">\end{hizalaması}</span><span class="sxs-lookup"><span data-stu-id="482c4-107">\end{align}</span></span>

```qsharp
operation Rz (theta : Double, qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="482c4-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="482c4-108">Input</span></span>

### <a name="theta--double"></a><span data-ttu-id="482c4-109">Teta: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="482c4-109">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="482c4-110">Qubitin döndürüleceği açı.</span><span class="sxs-lookup"><span data-stu-id="482c4-110">Angle about which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="482c4-111">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="482c4-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="482c4-112">Gate 'in uygulanması gereken qubit.</span><span class="sxs-lookup"><span data-stu-id="482c4-112">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="482c4-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="482c4-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="482c4-114">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="482c4-114">Remarks</span></span>

<span data-ttu-id="482c4-115">Eşdeğer:</span><span class="sxs-lookup"><span data-stu-id="482c4-115">Equivalent to:</span></span>

```qsharp
R(PauliZ, theta, qubit);
```