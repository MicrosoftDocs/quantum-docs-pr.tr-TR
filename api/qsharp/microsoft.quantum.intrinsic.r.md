---
uid: Microsoft.Quantum.Intrinsic.R
title: R işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: R
qsharp.summary: >-
  Applies a rotation about the given Pauli axis.

  \begin{align} R_{\mu}(\theta) \mathrel{:=} e^{-i \theta \sigma_{\mu} / 2}, \end{align} where $\mu \in \{I, X, Y, Z\}$.
ms.openlocfilehash: 7d1d51031f4587b1c501feab459e614fc1530457
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731391"
---
# <a name="r-operation"></a><span data-ttu-id="7c22c-102">R işlemi</span><span class="sxs-lookup"><span data-stu-id="7c22c-102">R operation</span></span>

<span data-ttu-id="7c22c-103">Ad alanı: [Microsoft. hisse. iç](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="7c22c-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="7c22c-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7c22c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7c22c-105">Verilen Pauli ekseni hakkında bir döndürme uygular.</span><span class="sxs-lookup"><span data-stu-id="7c22c-105">Applies a rotation about the given Pauli axis.</span></span>

<span data-ttu-id="7c22c-106">\begin{hizalaması} R_ {\mu} (\teta) \mathrel{: =} e ^ {-i \teta \ sigma_ {\mu}/2}, \end{hizalaması}; burada $ \mu \ in \{ i, X, Y, Z \} $.</span><span class="sxs-lookup"><span data-stu-id="7c22c-106">\begin{align} R_{\mu}(\theta) \mathrel{:=} e^{-i \theta \sigma_{\mu} / 2}, \end{align} where $\mu \in \{I, X, Y, Z\}$.</span></span>

```qsharp
operation R (pauli : Pauli, theta : Double, qubit : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="7c22c-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="7c22c-107">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="7c22c-108">Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="7c22c-108">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="7c22c-109">Dönüşü oluşturmak için Pauli işleci ($ \mu $) üs olarak dağıtılır.</span><span class="sxs-lookup"><span data-stu-id="7c22c-109">Pauli operator ($\mu$) to be exponentiated to form the rotation.</span></span>


### <a name="theta--double"></a><span data-ttu-id="7c22c-110">Teta: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="7c22c-110">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="7c22c-111">Qubitin döndürüleceği açı.</span><span class="sxs-lookup"><span data-stu-id="7c22c-111">Angle about which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="7c22c-112">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="7c22c-112">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="7c22c-113">Gate 'in uygulanması gereken qubit.</span><span class="sxs-lookup"><span data-stu-id="7c22c-113">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7c22c-114">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7c22c-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="7c22c-115">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="7c22c-115">Remarks</span></span>

<span data-ttu-id="7c22c-116">İle çağrıldığında `pauli = PauliI` , bu işlem *genel bir aşama* uygular.</span><span class="sxs-lookup"><span data-stu-id="7c22c-116">When called with `pauli = PauliI`, this operation applies a *global phase* .</span></span> <span data-ttu-id="7c22c-117">Bu aşama, functor ile kullanıldığında önemli olabilir `Controlled` .</span><span class="sxs-lookup"><span data-stu-id="7c22c-117">This phase can be significant when used with the `Controlled` functor.</span></span>