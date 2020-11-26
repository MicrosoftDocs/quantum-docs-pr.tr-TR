---
uid: Microsoft.Quantum.Arithmetic.SquareFxP
title: SquareFxP işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: SquareFxP
qsharp.summary: Squares a fixed-point number.
ms.openlocfilehash: 8d08cb51e3a7ae892b23be0adbb7cdf3ee0f4de5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221887"
---
# <a name="squarefxp-operation"></a><span data-ttu-id="27705-102">SquareFxP işlemi</span><span class="sxs-lookup"><span data-stu-id="27705-102">SquareFxP operation</span></span>

<span data-ttu-id="27705-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="27705-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="27705-104">Paket: [Microsoft. hisse. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="27705-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="27705-105">Sabit noktalı bir sayı için kareler.</span><span class="sxs-lookup"><span data-stu-id="27705-105">Squares a fixed-point number.</span></span>

```qsharp
operation SquareFxP (fp : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="27705-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="27705-106">Input</span></span>

### <a name="fp--fixedpoint"></a><span data-ttu-id="27705-107">FP: [Fixedpoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="27705-107">fp : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="27705-108">Sabit noktalı sayı.</span><span class="sxs-lookup"><span data-stu-id="27705-108">Fixed-point number.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="27705-109">Sonuç: [Fixedpoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="27705-109">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="27705-110">Sonuç sabit noktalı sayı, başlangıçta $ \ demet $ durumunda olmalıdır {0} .</span><span class="sxs-lookup"><span data-stu-id="27705-110">Result fixed-point number, must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="27705-111">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="27705-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

