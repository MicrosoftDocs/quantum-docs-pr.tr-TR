---
uid: Microsoft.Quantum.Intrinsic.RFrac
title: RFrac işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: RFrac
qsharp.summary: >-
  Applies a rotation about the given Pauli axis by an angle specified as a dyadic fraction.

  \begin{align} R_{\mu}(n, k) \mathrel{:=} e^{i \pi n \sigma_{\mu} / 2^k}, \end{align} where $\mu \in \{I, X, Y, Z\}$.

  > [!WARNING] > This operation uses the **opposite** sign convention from > @"microsoft.quantum.intrinsic.r".
ms.openlocfilehash: bd182ea50d747e07bb0f8051c5dbc128b7ff7674
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198648"
---
# <a name="rfrac-operation"></a><span data-ttu-id="04654-102">RFrac işlemi</span><span class="sxs-lookup"><span data-stu-id="04654-102">RFrac operation</span></span>

<span data-ttu-id="04654-103">Ad alanı: [Microsoft. hisse. iç](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="04654-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="04654-104">Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="04654-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="04654-105">Verilen Pauli ekseni ile dyadic kesri olarak belirtilen bir açıda bir döndürme uygular.</span><span class="sxs-lookup"><span data-stu-id="04654-105">Applies a rotation about the given Pauli axis by an angle specified as a dyadic fraction.</span></span>

<span data-ttu-id="04654-106">\begin{hizalaması} R_ {\mu} (n, k) \mathrel{: =} e ^ {ı \pi n \ sigma_ {\mu}/2 ^ k}, \end{hizalaması}; burada $ \mu \ in \{ i, X, Y, Z \} $.</span><span class="sxs-lookup"><span data-stu-id="04654-106">\begin{align} R_{\mu}(n, k) \mathrel{:=} e^{i \pi n \sigma_{\mu} / 2^k}, \end{align} where $\mu \in \{I, X, Y, Z\}$.</span></span>

> [!WARNING]
> <span data-ttu-id="04654-107">Bu işlem, öğesinden **ters** oturum açma kuralını kullanır @"microsoft.quantum.intrinsic.r" .</span><span class="sxs-lookup"><span data-stu-id="04654-107">This operation uses the **opposite** sign convention from @"microsoft.quantum.intrinsic.r".</span></span>

```qsharp
operation RFrac (pauli : Pauli, numerator : Int, power : Int, qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="04654-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="04654-108">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="04654-109">Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="04654-109">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="04654-110">Dönüşü oluşturmak için üs olacak Pauli işleci.</span><span class="sxs-lookup"><span data-stu-id="04654-110">Pauli operator to be exponentiated to form the rotation.</span></span>


### <a name="numerator--int"></a><span data-ttu-id="04654-111">pay: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="04654-111">numerator : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="04654-112">Dyadic kesir gösteriminde, qubitin döndürüleceği açının değeri.</span><span class="sxs-lookup"><span data-stu-id="04654-112">Numerator in the dyadic fraction representation of the angle by which the qubit is to be rotated.</span></span>


### <a name="power--int"></a><span data-ttu-id="04654-113">güç: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="04654-113">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="04654-114">İkinin, qubitin döndürüleceği açının paydasını belirten iki üssü.</span><span class="sxs-lookup"><span data-stu-id="04654-114">Power of two specifying the denominator of the angle by which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="04654-115">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="04654-115">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="04654-116">Gate 'in uygulanması gereken qubit.</span><span class="sxs-lookup"><span data-stu-id="04654-116">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="04654-117">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="04654-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="04654-118">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="04654-118">Remarks</span></span>

<span data-ttu-id="04654-119">Eşdeğer:</span><span class="sxs-lookup"><span data-stu-id="04654-119">Equivalent to:</span></span>

```qsharp
// PI() is a Q# function that returns an approximation of π.
R(pauli, -PI() * IntAsDouble(numerator) / IntAsDouble(2 ^ (power - 1)), qubit);
```