---
uid: Microsoft.Quantum.Intrinsic.R1
title: R1 işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: R1
qsharp.summary: >-
  Applies a rotation about the $\ket{1}$ state by a given angle.

  \begin{align} R_1(\theta) \mathrel{:=} \operatorname{diag}(1, e^{i\theta}). \end{align}
ms.openlocfilehash: 07cce580b50fef5664fdac32bb4fae0ba22d25e2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849360"
---
# <a name="r1-operation"></a><span data-ttu-id="cc003-102">R1 işlemi</span><span class="sxs-lookup"><span data-stu-id="cc003-102">R1 operation</span></span>

<span data-ttu-id="cc003-103">Ad alanı: [Microsoft. hisse. iç](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="cc003-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="cc003-104">Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="cc003-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="cc003-105">$ \Ket {1} $ durumu hakkında verilen bir açıda bir döndürme uygular.</span><span class="sxs-lookup"><span data-stu-id="cc003-105">Applies a rotation about the $\ket{1}$ state by a given angle.</span></span>

<span data-ttu-id="cc003-106">\begin{hizalaması} R_1 (\teta) \mathrel{: =} \operatorname{diag} (1, e ^ {i\teta}).</span><span class="sxs-lookup"><span data-stu-id="cc003-106">\begin{align} R_1(\theta) \mathrel{:=} \operatorname{diag}(1, e^{i\theta}).</span></span>
<span data-ttu-id="cc003-107">\end{hizalaması}</span><span class="sxs-lookup"><span data-stu-id="cc003-107">\end{align}</span></span>

```qsharp
operation R1 (theta : Double, qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="cc003-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="cc003-108">Input</span></span>

### <a name="theta--double"></a><span data-ttu-id="cc003-109">Teta: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="cc003-109">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="cc003-110">Qubitin döndürüleceği açı.</span><span class="sxs-lookup"><span data-stu-id="cc003-110">Angle about which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="cc003-111">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="cc003-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="cc003-112">Gate 'in uygulanması gereken qubit.</span><span class="sxs-lookup"><span data-stu-id="cc003-112">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="cc003-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cc003-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="cc003-114">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="cc003-114">Remarks</span></span>

<span data-ttu-id="cc003-115">Eşdeğer:</span><span class="sxs-lookup"><span data-stu-id="cc003-115">Equivalent to:</span></span>

```qsharp
R(PauliZ, theta, qubit);
R(PauliI, -theta, qubit);
```