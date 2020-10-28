---
uid: Microsoft.Quantum.Arithmetic.MultiplyFxP
title: Çoğullyfxp işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyFxP
qsharp.summary: Multiplies two fixed-point numbers in quantum registers.
ms.openlocfilehash: 18883f3f4c3793b91e248f4bd89f9def640bf254
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730623"
---
# <a name="multiplyfxp-operation"></a><span data-ttu-id="18322-102">Çoğullyfxp işlemi</span><span class="sxs-lookup"><span data-stu-id="18322-102">MultiplyFxP operation</span></span>

<span data-ttu-id="18322-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="18322-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="18322-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="18322-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="18322-105">Hisse kasalarındaki iki sabit noktalı sayıyı çarpar.</span><span class="sxs-lookup"><span data-stu-id="18322-105">Multiplies two fixed-point numbers in quantum registers.</span></span>

```qsharp
operation MultiplyFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit
```


## <a name="input"></a><span data-ttu-id="18322-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="18322-106">Input</span></span>

### <a name="fp1--fixedpoint"></a><span data-ttu-id="18322-107">FP1: [Fixedpoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="18322-107">fp1 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="18322-108">İlk sabit noktalı sayı.</span><span class="sxs-lookup"><span data-stu-id="18322-108">First fixed-point number.</span></span>


### <a name="fp2--fixedpoint"></a><span data-ttu-id="18322-109">FP2: [Fixedpoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="18322-109">fp2 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="18322-110">İkinci sabit noktalı sayı.</span><span class="sxs-lookup"><span data-stu-id="18322-110">Second fixed-point number.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="18322-111">Sonuç: [Fixedpoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="18322-111">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="18322-112">Sonuç sabit noktalı sayı, başlangıçta $ \ demet $ durumunda olmalıdır {0} .</span><span class="sxs-lookup"><span data-stu-id="18322-112">Result fixed-point number, must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="18322-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="18322-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="18322-114">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="18322-114">Remarks</span></span>

<span data-ttu-id="18322-115">Geçerli uygulama, üç sabit noktalı sayının aynı nokta konumuna ve aynı sayıda qubit 'e sahip olmasını gerektirir.</span><span class="sxs-lookup"><span data-stu-id="18322-115">The current implementation requires the three fixed-point numbers to have the same point position and the same number of qubits.</span></span>