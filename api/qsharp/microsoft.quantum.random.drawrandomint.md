---
uid: Microsoft.Quantum.Random.DrawRandomInt
title: DrawRandomInt işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomInt
qsharp.summary: Draws a random integer in a given inclusive range.
ms.openlocfilehash: d9d8d9fbb25587ac5ccbd4edf0e555649380375f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733594"
---
# <a name="drawrandomint-operation"></a><span data-ttu-id="47590-102">DrawRandomInt işlemi</span><span class="sxs-lookup"><span data-stu-id="47590-102">DrawRandomInt operation</span></span>

<span data-ttu-id="47590-103">Ad alanı: [Microsoft. hisse. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="47590-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="47590-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="47590-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="47590-105">Verili bir kapsayıcı aralığında rastgele bir tamsayı çizer.</span><span class="sxs-lookup"><span data-stu-id="47590-105">Draws a random integer in a given inclusive range.</span></span>

```qsharp
operation DrawRandomInt (min : Int, max : Int) : Int
```


## <a name="input"></a><span data-ttu-id="47590-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="47590-106">Input</span></span>

### <a name="min--int"></a><span data-ttu-id="47590-107">Min: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="47590-107">min : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="47590-108">Çizilecek en küçük tamsayı.</span><span class="sxs-lookup"><span data-stu-id="47590-108">The smallest integer to be drawn.</span></span>


### <a name="max--int"></a><span data-ttu-id="47590-109">Max: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="47590-109">max : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="47590-110">Çizilecek en büyük tamsayı.</span><span class="sxs-lookup"><span data-stu-id="47590-110">The largest integer to be drawn.</span></span>



## <a name="output--int"></a><span data-ttu-id="47590-111">Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="47590-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="47590-112">İle arasında, tek bir tamsayı `min` `max` olasılığa sahip.</span><span class="sxs-lookup"><span data-stu-id="47590-112">An integer in the inclusive range from `min` to `max` with uniform probability.</span></span>

## <a name="remarks"></a><span data-ttu-id="47590-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="47590-113">Remarks</span></span>

<span data-ttu-id="47590-114">Başarısız olur `max <= min` .</span><span class="sxs-lookup"><span data-stu-id="47590-114">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="47590-115">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="47590-115">See Also</span></span>

- [<span data-ttu-id="47590-116">Microsoft. hisse. DiscreteUniformDistribution</span><span class="sxs-lookup"><span data-stu-id="47590-116">Microsoft.Quantum.DiscreteUniformDistribution</span></span>](xref:Microsoft.Quantum.DiscreteUniformDistribution)