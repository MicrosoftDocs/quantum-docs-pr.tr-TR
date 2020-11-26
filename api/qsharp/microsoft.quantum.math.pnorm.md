---
uid: Microsoft.Quantum.Math.PNorm
title: PNorm işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PNorm
qsharp.summary: >-
  Returns the `L(p)` norm of a vector of `Double`s.

  That is, given an array $x$ of type `Double[]`, this returns the $p$-norm $\|x\|\_p= (\sum_{j}|x_j|^{p})^{1/p}$.
ms.openlocfilehash: 3fe029bd893fc4d11aaf351f7ea566256cac5a9e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194738"
---
# <a name="pnorm-function"></a><span data-ttu-id="767a1-102">PNorm işlevi</span><span class="sxs-lookup"><span data-stu-id="767a1-102">PNorm function</span></span>

<span data-ttu-id="767a1-103">Ad alanı: [Microsoft. hisse. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="767a1-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="767a1-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="767a1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="767a1-105">`L(p)`Bir vektörün vektörini döndürür `Double` .</span><span class="sxs-lookup"><span data-stu-id="767a1-105">Returns the `L(p)` norm of a vector of `Double`s.</span></span>

<span data-ttu-id="767a1-106">Diğer bir deyişle, türünde bir dizi $x olarak belirtilen `Double[]` Bu, $-norm $ \| x \| \_ p = (\ sum_ {j} | x_j | ^ {p}) ^ {1/p} $ $p döndürür.</span><span class="sxs-lookup"><span data-stu-id="767a1-106">That is, given an array $x$ of type `Double[]`, this returns the $p$-norm $\|x\|\_p= (\sum_{j}|x_j|^{p})^{1/p}$.</span></span>

```qsharp
function PNorm (p : Double, array : Double[]) : Double
```


## <a name="input"></a><span data-ttu-id="767a1-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="767a1-107">Input</span></span>

### <a name="p--double"></a><span data-ttu-id="767a1-108">p: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="767a1-108">p : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="767a1-109">$P $-norm içindeki üs $p $.</span><span class="sxs-lookup"><span data-stu-id="767a1-109">The exponent $p$ in the $p$-norm.</span></span>


### <a name="array--double"></a><span data-ttu-id="767a1-110">dizi: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="767a1-110">array : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>





## <a name="output--double"></a><span data-ttu-id="767a1-111">Çıkış: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="767a1-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="767a1-112">$P $-norm $ \| x \| _p $.</span><span class="sxs-lookup"><span data-stu-id="767a1-112">The $p$-norm $\|x\|_p$.</span></span>