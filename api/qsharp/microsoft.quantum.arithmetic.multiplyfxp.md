---
uid: Microsoft.Quantum.Arithmetic.MultiplyFxP
title: Çoğullyfxp işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyFxP
qsharp.summary: Multiplies two fixed-point numbers in quantum registers.
ms.openlocfilehash: 3c9ef9ade660e1f420d85162104d773b96722eeb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222618"
---
# <a name="multiplyfxp-operation"></a><span data-ttu-id="951d4-102">Çoğullyfxp işlemi</span><span class="sxs-lookup"><span data-stu-id="951d4-102">MultiplyFxP operation</span></span>

<span data-ttu-id="951d4-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="951d4-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="951d4-104">Paket: [Microsoft. hisse. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="951d4-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="951d4-105">Hisse kasalarındaki iki sabit noktalı sayıyı çarpar.</span><span class="sxs-lookup"><span data-stu-id="951d4-105">Multiplies two fixed-point numbers in quantum registers.</span></span>

```qsharp
operation MultiplyFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="951d4-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="951d4-106">Input</span></span>

### <a name="fp1--fixedpoint"></a><span data-ttu-id="951d4-107">FP1: [Fixedpoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="951d4-107">fp1 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="951d4-108">İlk sabit noktalı sayı.</span><span class="sxs-lookup"><span data-stu-id="951d4-108">First fixed-point number.</span></span>


### <a name="fp2--fixedpoint"></a><span data-ttu-id="951d4-109">FP2: [Fixedpoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="951d4-109">fp2 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="951d4-110">İkinci sabit noktalı sayı.</span><span class="sxs-lookup"><span data-stu-id="951d4-110">Second fixed-point number.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="951d4-111">Sonuç: [Fixedpoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="951d4-111">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="951d4-112">Sonuç sabit noktalı sayı, başlangıçta $ \ demet $ durumunda olmalıdır {0} .</span><span class="sxs-lookup"><span data-stu-id="951d4-112">Result fixed-point number, must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="951d4-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="951d4-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="951d4-114">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="951d4-114">Remarks</span></span>

<span data-ttu-id="951d4-115">Geçerli uygulama, üç sabit noktalı sayının aynı nokta konumuna ve aynı sayıda qubit 'e sahip olmasını gerektirir.</span><span class="sxs-lookup"><span data-stu-id="951d4-115">The current implementation requires the three fixed-point numbers to have the same point position and the same number of qubits.</span></span>