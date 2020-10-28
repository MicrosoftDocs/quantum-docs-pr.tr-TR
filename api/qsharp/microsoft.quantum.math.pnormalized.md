---
uid: Microsoft.Quantum.Math.PNormalized
title: Pnormalleştirilmiş işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PNormalized
qsharp.summary: >-
  Normalizes a vector of `Double`s in the `L(p)` norm.

  That is, given an array $x$ of type `Double[]`, this returns an array where all elements are divided by the $p$-norm $\|x\|_p$.
ms.openlocfilehash: 6f9dfebe83f52cbf486cd8e6874d3699f5e6b8ab
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732239"
---
# <a name="pnormalized-function"></a><span data-ttu-id="1a6d6-102">Pnormalleştirilmiş işlevi</span><span class="sxs-lookup"><span data-stu-id="1a6d6-102">PNormalized function</span></span>

<span data-ttu-id="1a6d6-103">Ad alanı: [Microsoft. hisse. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="1a6d6-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="1a6d6-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1a6d6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1a6d6-105">Norm içindeki bir vektörü normalleştirir `Double` `L(p)` .</span><span class="sxs-lookup"><span data-stu-id="1a6d6-105">Normalizes a vector of `Double`s in the `L(p)` norm.</span></span>

<span data-ttu-id="1a6d6-106">Diğer bir deyişle, türünde bir dizi $x `Double[]` , bu, tüm öğelerin $p $-norm $ \| x _p $ tarafından bölündüğü bir dizi döndürür \| .</span><span class="sxs-lookup"><span data-stu-id="1a6d6-106">That is, given an array $x$ of type `Double[]`, this returns an array where all elements are divided by the $p$-norm $\|x\|_p$.</span></span>

```qsharp
function PNormalized (p : Double, array : Double[]) : Double[]
```


## <a name="input"></a><span data-ttu-id="1a6d6-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="1a6d6-107">Input</span></span>

### <a name="p--double"></a><span data-ttu-id="1a6d6-108">p: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="1a6d6-108">p : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="1a6d6-109">$P $-norm içindeki üs $p $.</span><span class="sxs-lookup"><span data-stu-id="1a6d6-109">The exponent $p$ in the $p$-norm.</span></span>


### <a name="array--double"></a><span data-ttu-id="1a6d6-110">dizi: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="1a6d6-110">array : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>





## <a name="output--double"></a><span data-ttu-id="1a6d6-111">Çıkış: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="1a6d6-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="1a6d6-112">Dizi $x $-norm $ \| x _p $ $p tarafından normalleştirilmelidir \| .</span><span class="sxs-lookup"><span data-stu-id="1a6d6-112">The array $x$ normalized by the $p$-norm $\|x\|_p$.</span></span>

## <a name="see-also"></a><span data-ttu-id="1a6d6-113">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="1a6d6-113">See Also</span></span>

- [<span data-ttu-id="1a6d6-114">Microsoft. hisse. Math. PNorm</span><span class="sxs-lookup"><span data-stu-id="1a6d6-114">Microsoft.Quantum.Math.PNorm</span></span>](xref:Microsoft.Quantum.Math.PNorm)