---
uid: Microsoft.Quantum.Random.DrawRandomInt
title: DrawRandomInt işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomInt
qsharp.summary: Draws a random integer in a given inclusive range.
ms.openlocfilehash: f7b6cb75f761e4c45295245ed4bd4fb82c592809
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192919"
---
# <a name="drawrandomint-operation"></a><span data-ttu-id="8d661-102">DrawRandomInt işlemi</span><span class="sxs-lookup"><span data-stu-id="8d661-102">DrawRandomInt operation</span></span>

<span data-ttu-id="8d661-103">Ad alanı: [Microsoft. hisse. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="8d661-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="8d661-104">Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="8d661-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="8d661-105">Verili bir kapsayıcı aralığında rastgele bir tamsayı çizer.</span><span class="sxs-lookup"><span data-stu-id="8d661-105">Draws a random integer in a given inclusive range.</span></span>

```qsharp
operation DrawRandomInt (min : Int, max : Int) : Int
```


## <a name="input"></a><span data-ttu-id="8d661-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="8d661-106">Input</span></span>

### <a name="min--int"></a><span data-ttu-id="8d661-107">Min: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8d661-107">min : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="8d661-108">Çizilecek en küçük tamsayı.</span><span class="sxs-lookup"><span data-stu-id="8d661-108">The smallest integer to be drawn.</span></span>


### <a name="max--int"></a><span data-ttu-id="8d661-109">Max: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8d661-109">max : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="8d661-110">Çizilecek en büyük tamsayı.</span><span class="sxs-lookup"><span data-stu-id="8d661-110">The largest integer to be drawn.</span></span>



## <a name="output--int"></a><span data-ttu-id="8d661-111">Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8d661-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="8d661-112">İle arasında, tek bir tamsayı `min` `max` olasılığa sahip.</span><span class="sxs-lookup"><span data-stu-id="8d661-112">An integer in the inclusive range from `min` to `max` with uniform probability.</span></span>

## <a name="remarks"></a><span data-ttu-id="8d661-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="8d661-113">Remarks</span></span>

<span data-ttu-id="8d661-114">Başarısız olur `max <= min` .</span><span class="sxs-lookup"><span data-stu-id="8d661-114">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="8d661-115">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="8d661-115">See Also</span></span>

- [<span data-ttu-id="8d661-116">Microsoft. hisse. DiscreteUniformDistribution</span><span class="sxs-lookup"><span data-stu-id="8d661-116">Microsoft.Quantum.DiscreteUniformDistribution</span></span>](xref:Microsoft.Quantum.DiscreteUniformDistribution)