---
uid: Microsoft.Quantum.Math.PNorm
title: PNorm işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PNorm
qsharp.summary: >-
  Returns the `L(p)` norm of a vector of `Double`s.

  That is, given an array $x$ of type `Double[]`, this returns the $p$-norm $\|x\|\_p= (\sum_{j}|x_j|^{p})^{1/p}$.
ms.openlocfilehash: cea85715e448305486f6d8a6c10e11da56edf3ee
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732247"
---
# <a name="pnorm-function"></a><span data-ttu-id="8a240-102">PNorm işlevi</span><span class="sxs-lookup"><span data-stu-id="8a240-102">PNorm function</span></span>

<span data-ttu-id="8a240-103">Ad alanı: [Microsoft. hisse. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="8a240-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="8a240-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8a240-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8a240-105">`L(p)`Bir vektörün vektörini döndürür `Double` .</span><span class="sxs-lookup"><span data-stu-id="8a240-105">Returns the `L(p)` norm of a vector of `Double`s.</span></span>

<span data-ttu-id="8a240-106">Diğer bir deyişle, türünde bir dizi $x olarak belirtilen `Double[]` Bu, $-norm $ \| x \| \_ p = (\ sum_ {j} | x_j | ^ {p}) ^ {1/p} $ $p döndürür.</span><span class="sxs-lookup"><span data-stu-id="8a240-106">That is, given an array $x$ of type `Double[]`, this returns the $p$-norm $\|x\|\_p= (\sum_{j}|x_j|^{p})^{1/p}$.</span></span>

```qsharp
function PNorm (p : Double, array : Double[]) : Double
```


## <a name="input"></a><span data-ttu-id="8a240-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="8a240-107">Input</span></span>

### <a name="p--double"></a><span data-ttu-id="8a240-108">p: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="8a240-108">p : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="8a240-109">$P $-norm içindeki üs $p $.</span><span class="sxs-lookup"><span data-stu-id="8a240-109">The exponent $p$ in the $p$-norm.</span></span>


### <a name="array--double"></a><span data-ttu-id="8a240-110">dizi: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="8a240-110">array : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>





## <a name="output--double"></a><span data-ttu-id="8a240-111">Çıkış: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="8a240-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="8a240-112">$P $-norm $ \| x \| _p $.</span><span class="sxs-lookup"><span data-stu-id="8a240-112">The $p$-norm $\|x\|_p$.</span></span>