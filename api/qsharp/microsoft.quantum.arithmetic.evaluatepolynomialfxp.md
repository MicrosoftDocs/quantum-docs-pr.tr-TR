---
uid: Microsoft.Quantum.Arithmetic.EvaluatePolynomialFxP
title: EvaluatePolynomialFxP işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: EvaluatePolynomialFxP
qsharp.summary: Evaluates a polynomial in a fixed-point representation.
ms.openlocfilehash: 3903bf69d5b0a6e57530f2c6a44e1d351c8a605f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731559"
---
# <a name="evaluatepolynomialfxp-operation"></a><span data-ttu-id="bd2f0-102">EvaluatePolynomialFxP işlemi</span><span class="sxs-lookup"><span data-stu-id="bd2f0-102">EvaluatePolynomialFxP operation</span></span>

<span data-ttu-id="bd2f0-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="bd2f0-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="bd2f0-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="bd2f0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="bd2f0-105">Sabit noktalı bir gösterimde bir polinom değerlendirir.</span><span class="sxs-lookup"><span data-stu-id="bd2f0-105">Evaluates a polynomial in a fixed-point representation.</span></span>

```qsharp
operation EvaluatePolynomialFxP (coefficients : Double[], fpx : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit
```


## <a name="input"></a><span data-ttu-id="bd2f0-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="bd2f0-106">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="bd2f0-107">katsayılar: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="bd2f0-107">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="bd2f0-108">Polinom $P (x) = a_0 + a_1 x + \cnoktalar + a_d x ^ d $ için dizi $ [a_0, a_1,..., a_d] $ şeklinde polinom 'un katsayısıdır.</span><span class="sxs-lookup"><span data-stu-id="bd2f0-108">Coefficients of the polynomial as a double array, i.e., the array $[a_0, a_1, ..., a_d]$ for the polynomial $P(x) = a_0 + a_1 x + \cdots + a_d x^d$.</span></span>


### <a name="fpx--fixedpoint"></a><span data-ttu-id="bd2f0-109">FPX: [Fixedpoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="bd2f0-109">fpx : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="bd2f0-110">Polinom 'un değerlendirileceği sabit noktalı sayı girin.</span><span class="sxs-lookup"><span data-stu-id="bd2f0-110">Input fixed-point number for which to evaluate the polynomial.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="bd2f0-111">Sonuç: [Fixedpoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="bd2f0-111">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="bd2f0-112">$P (x) $ ' i barındıracak olan çıkış sabit noktası numarası.</span><span class="sxs-lookup"><span data-stu-id="bd2f0-112">Output fixed-point number which will hold $P(x)$.</span></span> <span data-ttu-id="bd2f0-113">Başlangıçta $ \ket $ durumunda olmalıdır {0} .</span><span class="sxs-lookup"><span data-stu-id="bd2f0-113">Must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="bd2f0-114">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bd2f0-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

