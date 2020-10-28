---
uid: Microsoft.Quantum.Arithmetic.EvaluateEvenPolynomialFxP
title: EvaluateEvenPolynomialFxP işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: EvaluateEvenPolynomialFxP
qsharp.summary: Evaluates an even polynomial in a fixed-point representation.
ms.openlocfilehash: e49a6d47553a60766b561525e8cfa37e95fda9e8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731570"
---
# <a name="evaluateevenpolynomialfxp-operation"></a><span data-ttu-id="0390c-102">EvaluateEvenPolynomialFxP işlemi</span><span class="sxs-lookup"><span data-stu-id="0390c-102">EvaluateEvenPolynomialFxP operation</span></span>

<span data-ttu-id="0390c-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="0390c-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="0390c-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0390c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0390c-105">Sabit noktalı bir gösterimde çift bir polinom değerlendirir.</span><span class="sxs-lookup"><span data-stu-id="0390c-105">Evaluates an even polynomial in a fixed-point representation.</span></span>

```qsharp
operation EvaluateEvenPolynomialFxP (coefficients : Double[], fpx : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit
```


## <a name="input"></a><span data-ttu-id="0390c-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="0390c-106">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="0390c-107">katsayılar: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="0390c-107">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="0390c-108">Çift bir dizi olarak eşit polinom 'un katsayısı; Yani, Çift polinom $P (x) = a_0 + a_1 x ^ 2 + \cnoktalar + a_k x ^ {2k} $ için dizi $ [a_0, a_1,..., a_k] $.</span><span class="sxs-lookup"><span data-stu-id="0390c-108">Coefficients of the even polynomial as a double array, i.e., the array $[a_0, a_1, ..., a_k]$ for the even polynomial $P(x) = a_0 + a_1 x^2 + \cdots + a_k x^{2k}$.</span></span>


### <a name="fpx--fixedpoint"></a><span data-ttu-id="0390c-109">FPX: [Fixedpoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="0390c-109">fpx : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="0390c-110">Polinom 'un değerlendirileceği sabit noktalı sayı girin.</span><span class="sxs-lookup"><span data-stu-id="0390c-110">Input fixed-point number for which to evaluate the polynomial.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="0390c-111">Sonuç: [Fixedpoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="0390c-111">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="0390c-112">$P (x) $ ' i barındıracak olan çıkış sabit noktası numarası.</span><span class="sxs-lookup"><span data-stu-id="0390c-112">Output fixed-point number which will hold $P(x)$.</span></span> <span data-ttu-id="0390c-113">Başlangıçta $ \ket $ durumunda olmalıdır {0} .</span><span class="sxs-lookup"><span data-stu-id="0390c-113">Must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0390c-114">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0390c-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

