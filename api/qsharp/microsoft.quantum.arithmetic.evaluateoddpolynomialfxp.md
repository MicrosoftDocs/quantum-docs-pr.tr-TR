---
uid: Microsoft.Quantum.Arithmetic.EvaluateOddPolynomialFxP
title: EvaluateOddPolynomialFxP işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: EvaluateOddPolynomialFxP
qsharp.summary: Evaluates an odd polynomial in a fixed-point representation.
ms.openlocfilehash: d52da4092f16d43ab9d08b03f798a4d6789c7348
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731567"
---
# <a name="evaluateoddpolynomialfxp-operation"></a><span data-ttu-id="80cd9-102">EvaluateOddPolynomialFxP işlemi</span><span class="sxs-lookup"><span data-stu-id="80cd9-102">EvaluateOddPolynomialFxP operation</span></span>

<span data-ttu-id="80cd9-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="80cd9-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="80cd9-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="80cd9-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="80cd9-105">Sabit noktalı bir gösterimde tek bir polinom değerlendirir.</span><span class="sxs-lookup"><span data-stu-id="80cd9-105">Evaluates an odd polynomial in a fixed-point representation.</span></span>

```qsharp
operation EvaluateOddPolynomialFxP (coefficients : Double[], fpx : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit
```


## <a name="input"></a><span data-ttu-id="80cd9-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="80cd9-106">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="80cd9-107">katsayılar: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="80cd9-107">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="80cd9-108">Tek polinom $P (x) = a_0 x + a_1 x ^ 3 + \cnoktalar + a_k x ^ {2k + 1} $ için dizi $ [a_0, a_1,..., a_k] $ için çift dizi olarak tek polinom 'in katsayısıdır.</span><span class="sxs-lookup"><span data-stu-id="80cd9-108">Coefficients of the odd polynomial as a double array, i.e., the array $[a_0, a_1, ..., a_k]$ for the odd polynomial $P(x) = a_0 x + a_1 x^3 + \cdots + a_k x^{2k+1}$.</span></span>


### <a name="fpx--fixedpoint"></a><span data-ttu-id="80cd9-109">FPX: [Fixedpoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="80cd9-109">fpx : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="80cd9-110">Polinom 'un değerlendirileceği sabit noktalı sayı girin.</span><span class="sxs-lookup"><span data-stu-id="80cd9-110">Input fixed-point number for which to evaluate the polynomial.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="80cd9-111">Sonuç: [Fixedpoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="80cd9-111">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="80cd9-112">Çıkış sabit noktalı sayı, P (x) ' i tutacaktır.</span><span class="sxs-lookup"><span data-stu-id="80cd9-112">Output fixed-point number which will hold P(x).</span></span> <span data-ttu-id="80cd9-113">Başlangıçta $ \ket $ durumunda olmalıdır {0} .</span><span class="sxs-lookup"><span data-stu-id="80cd9-113">Must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="80cd9-114">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="80cd9-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

