---
uid: Microsoft.Quantum.Arithmetic.EvaluateEvenPolynomialFxP
title: EvaluateEvenPolynomialFxP işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: EvaluateEvenPolynomialFxP
qsharp.summary: Evaluates an even polynomial in a fixed-point representation.
ms.openlocfilehash: 21c700ccb2b87b906fc4d8b65eddf962353948c1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223264"
---
# <a name="evaluateevenpolynomialfxp-operation"></a><span data-ttu-id="4b0d9-102">EvaluateEvenPolynomialFxP işlemi</span><span class="sxs-lookup"><span data-stu-id="4b0d9-102">EvaluateEvenPolynomialFxP operation</span></span>

<span data-ttu-id="4b0d9-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="4b0d9-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="4b0d9-104">Paket: [Microsoft. hisse. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="4b0d9-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="4b0d9-105">Sabit noktalı bir gösterimde çift bir polinom değerlendirir.</span><span class="sxs-lookup"><span data-stu-id="4b0d9-105">Evaluates an even polynomial in a fixed-point representation.</span></span>

```qsharp
operation EvaluateEvenPolynomialFxP (coefficients : Double[], fpx : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="4b0d9-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="4b0d9-106">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="4b0d9-107">katsayılar: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="4b0d9-107">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="4b0d9-108">Çift bir dizi olarak eşit polinom 'un katsayısı; Yani, Çift polinom $P (x) = a_0 + a_1 x ^ 2 + \cnoktalar + a_k x ^ {2k} $ için dizi $ [a_0, a_1,..., a_k] $.</span><span class="sxs-lookup"><span data-stu-id="4b0d9-108">Coefficients of the even polynomial as a double array, i.e., the array $[a_0, a_1, ..., a_k]$ for the even polynomial $P(x) = a_0 + a_1 x^2 + \cdots + a_k x^{2k}$.</span></span>


### <a name="fpx--fixedpoint"></a><span data-ttu-id="4b0d9-109">FPX: [Fixedpoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="4b0d9-109">fpx : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="4b0d9-110">Polinom 'un değerlendirileceği sabit noktalı sayı girin.</span><span class="sxs-lookup"><span data-stu-id="4b0d9-110">Input fixed-point number for which to evaluate the polynomial.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="4b0d9-111">Sonuç: [Fixedpoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="4b0d9-111">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="4b0d9-112">$P (x) $ ' i barındıracak olan çıkış sabit noktası numarası.</span><span class="sxs-lookup"><span data-stu-id="4b0d9-112">Output fixed-point number which will hold $P(x)$.</span></span> <span data-ttu-id="4b0d9-113">Başlangıçta $ \ket $ durumunda olmalıdır {0} .</span><span class="sxs-lookup"><span data-stu-id="4b0d9-113">Must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4b0d9-114">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4b0d9-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

