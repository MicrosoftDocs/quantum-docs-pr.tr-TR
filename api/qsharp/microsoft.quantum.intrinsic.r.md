---
uid: Microsoft.Quantum.Intrinsic.R
title: R işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: R
qsharp.summary: >-
  Applies a rotation about the given Pauli axis.

  \begin{align} R_{\mu}(\theta) \mathrel{:=} e^{-i \theta \sigma_{\mu} / 2}, \end{align} where $\mu \in \{I, X, Y, Z\}$.
ms.openlocfilehash: 89aa5b2867068d4352a0b9550e8d22aa77439111
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96199038"
---
# <a name="r-operation"></a><span data-ttu-id="5b3e9-102">R işlemi</span><span class="sxs-lookup"><span data-stu-id="5b3e9-102">R operation</span></span>

<span data-ttu-id="5b3e9-103">Ad alanı: [Microsoft. hisse. iç](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="5b3e9-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="5b3e9-104">Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="5b3e9-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="5b3e9-105">Verilen Pauli ekseni hakkında bir döndürme uygular.</span><span class="sxs-lookup"><span data-stu-id="5b3e9-105">Applies a rotation about the given Pauli axis.</span></span>

<span data-ttu-id="5b3e9-106">\begin{hizalaması} R_ {\mu} (\teta) \mathrel{: =} e ^ {-i \teta \ sigma_ {\mu}/2}, \end{hizalaması}; burada $ \mu \ in \{ i, X, Y, Z \} $.</span><span class="sxs-lookup"><span data-stu-id="5b3e9-106">\begin{align} R_{\mu}(\theta) \mathrel{:=} e^{-i \theta \sigma_{\mu} / 2}, \end{align} where $\mu \in \{I, X, Y, Z\}$.</span></span>

```qsharp
operation R (pauli : Pauli, theta : Double, qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="5b3e9-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="5b3e9-107">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="5b3e9-108">Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="5b3e9-108">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="5b3e9-109">Dönüşü oluşturmak için Pauli işleci ($ \mu $) üs olarak dağıtılır.</span><span class="sxs-lookup"><span data-stu-id="5b3e9-109">Pauli operator ($\mu$) to be exponentiated to form the rotation.</span></span>


### <a name="theta--double"></a><span data-ttu-id="5b3e9-110">Teta: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="5b3e9-110">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="5b3e9-111">Qubitin döndürüleceği açı.</span><span class="sxs-lookup"><span data-stu-id="5b3e9-111">Angle about which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="5b3e9-112">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="5b3e9-112">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="5b3e9-113">Gate 'in uygulanması gereken qubit.</span><span class="sxs-lookup"><span data-stu-id="5b3e9-113">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5b3e9-114">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5b3e9-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="5b3e9-115">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="5b3e9-115">Remarks</span></span>

<span data-ttu-id="5b3e9-116">İle çağrıldığında `pauli = PauliI` , bu işlem *genel bir aşama* uygular.</span><span class="sxs-lookup"><span data-stu-id="5b3e9-116">When called with `pauli = PauliI`, this operation applies a *global phase*.</span></span> <span data-ttu-id="5b3e9-117">Bu aşama, functor ile kullanıldığında önemli olabilir `Controlled` .</span><span class="sxs-lookup"><span data-stu-id="5b3e9-117">This phase can be significant when used with the `Controlled` functor.</span></span>