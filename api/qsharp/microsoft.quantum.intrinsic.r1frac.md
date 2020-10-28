---
uid: Microsoft.Quantum.Intrinsic.R1Frac
title: R1Frac işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: R1Frac
qsharp.summary: >-
  Applies a rotation about the $\ket{1}$ state by an angle specified as a dyadic fraction.

  \begin{align} R_1(n, k) \mathrel{:=} \operatorname{diag}(1, e^{i \pi k / 2^n}). \end{align}

  > [!WARNING] > This operation uses the **opposite** sign convention from > @"microsoft.quantum.intrinsic.r", and does not include the > factor of $1/ 2$ included by @"microsoft.quantum.intrinsic.r1".
ms.openlocfilehash: bfa6cd60eebd05feec8cfa2bf71e09dc0d02843a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731370"
---
# <a name="r1frac-operation"></a><span data-ttu-id="217fc-102">R1Frac işlemi</span><span class="sxs-lookup"><span data-stu-id="217fc-102">R1Frac operation</span></span>

<span data-ttu-id="217fc-103">Ad alanı: [Microsoft. hisse. iç](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="217fc-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="217fc-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="217fc-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="217fc-105">$ \Ket {1} $ durumu ile dyadic kesri olarak belirtilen bir açıda bir döndürme uygular.</span><span class="sxs-lookup"><span data-stu-id="217fc-105">Applies a rotation about the $\ket{1}$ state by an angle specified as a dyadic fraction.</span></span>

<span data-ttu-id="217fc-106">\begin{hizalaması} R_1 (n, k) \mathrel{: =} \operatorname{diag} (1, e ^ {ı \ Pi k/2 ^ n}).</span><span class="sxs-lookup"><span data-stu-id="217fc-106">\begin{align} R_1(n, k) \mathrel{:=} \operatorname{diag}(1, e^{i \pi k / 2^n}).</span></span>
<span data-ttu-id="217fc-107">\end{hizalaması}</span><span class="sxs-lookup"><span data-stu-id="217fc-107">\end{align}</span></span>

> [!WARNING]
> <span data-ttu-id="217fc-108">Bu işlem, öğesinden **ters** oturum açma kuralını kullanır @"microsoft.quantum.intrinsic.r" ve tarafından dahil edilen $1/2 $ faktörünü içermez @"microsoft.quantum.intrinsic.r1" .</span><span class="sxs-lookup"><span data-stu-id="217fc-108">This operation uses the **opposite** sign convention from @"microsoft.quantum.intrinsic.r", and does not include the factor of $1/ 2$ included by @"microsoft.quantum.intrinsic.r1".</span></span>

```qsharp
operation R1Frac (numerator : Int, power : Int, qubit : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="217fc-109">Giriş</span><span class="sxs-lookup"><span data-stu-id="217fc-109">Input</span></span>

### <a name="numerator--int"></a><span data-ttu-id="217fc-110">pay: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="217fc-110">numerator : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="217fc-111">Dyadic kesir gösteriminde, qubitin döndürüleceği açının değeri.</span><span class="sxs-lookup"><span data-stu-id="217fc-111">Numerator in the dyadic fraction representation of the angle by which the qubit is to be rotated.</span></span>


### <a name="power--int"></a><span data-ttu-id="217fc-112">güç: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="217fc-112">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="217fc-113">İkinin, qubitin döndürüleceği açının paydasını belirten iki üssü.</span><span class="sxs-lookup"><span data-stu-id="217fc-113">Power of two specifying the denominator of the angle by which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="217fc-114">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="217fc-114">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="217fc-115">Gate 'in uygulanması gereken qubit.</span><span class="sxs-lookup"><span data-stu-id="217fc-115">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="217fc-116">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="217fc-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="217fc-117">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="217fc-117">Remarks</span></span>

<span data-ttu-id="217fc-118">Eşdeğer:</span><span class="sxs-lookup"><span data-stu-id="217fc-118">Equivalent to:</span></span>

```qsharp
RFrac(PauliZ, -numerator, denominator + 1, qubit);
RFrac(PauliI, numerator, denominator + 1, qubit);
```