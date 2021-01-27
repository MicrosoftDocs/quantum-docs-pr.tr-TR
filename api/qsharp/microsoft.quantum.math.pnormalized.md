---
uid: Microsoft.Quantum.Math.PNormalized
title: Pnormalleştirilmiş işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PNormalized
qsharp.summary: >-
  Normalizes a vector of `Double`s in the `L(p)` norm.

  That is, given an array $x$ of type `Double[]`, this returns an array where all elements are divided by the $p$-norm $\|x\|_p$.
ms.openlocfilehash: ea6a88d07d3b246f666b793f0b10ab6598ea4ff6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854842"
---
# <a name="pnormalized-function"></a><span data-ttu-id="43b53-102">Pnormalleştirilmiş işlevi</span><span class="sxs-lookup"><span data-stu-id="43b53-102">PNormalized function</span></span>

<span data-ttu-id="43b53-103">Ad alanı: [Microsoft. hisse. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="43b53-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="43b53-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="43b53-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="43b53-105">Norm içindeki bir vektörü normalleştirir `Double` `L(p)` .</span><span class="sxs-lookup"><span data-stu-id="43b53-105">Normalizes a vector of `Double`s in the `L(p)` norm.</span></span>

<span data-ttu-id="43b53-106">Diğer bir deyişle, türünde bir dizi $x `Double[]` , bu, tüm öğelerin $p $-norm $ \| x _p $ tarafından bölündüğü bir dizi döndürür \| .</span><span class="sxs-lookup"><span data-stu-id="43b53-106">That is, given an array $x$ of type `Double[]`, this returns an array where all elements are divided by the $p$-norm $\|x\|_p$.</span></span>

```qsharp
function PNormalized (p : Double, array : Double[]) : Double[]
```


## <a name="input"></a><span data-ttu-id="43b53-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="43b53-107">Input</span></span>

### <a name="p--double"></a><span data-ttu-id="43b53-108">p: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="43b53-108">p : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="43b53-109">$P $-norm içindeki üs $p $.</span><span class="sxs-lookup"><span data-stu-id="43b53-109">The exponent $p$ in the $p$-norm.</span></span>


### <a name="array--double"></a><span data-ttu-id="43b53-110">dizi: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="43b53-110">array : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>





## <a name="output--double"></a><span data-ttu-id="43b53-111">Çıkış: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="43b53-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="43b53-112">Dizi $x $-norm $ \| x _p $ $p tarafından normalleştirilmelidir \| .</span><span class="sxs-lookup"><span data-stu-id="43b53-112">The array $x$ normalized by the $p$-norm $\|x\|_p$.</span></span>

## <a name="see-also"></a><span data-ttu-id="43b53-113">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="43b53-113">See Also</span></span>

- [<span data-ttu-id="43b53-114">Microsoft. hisse. Math. PNorm</span><span class="sxs-lookup"><span data-stu-id="43b53-114">Microsoft.Quantum.Math.PNorm</span></span>](xref:Microsoft.Quantum.Math.PNorm)