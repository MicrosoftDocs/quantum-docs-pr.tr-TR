---
uid: Microsoft.Quantum.Random.DiscreteUniformDistribution
title: DiscreteUniformDistribution işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DiscreteUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive range.
ms.openlocfilehash: 08a62805f59df339ef6b91dff802c40c407808f4
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193021"
---
# <a name="discreteuniformdistribution-function"></a><span data-ttu-id="dedbd-102">DiscreteUniformDistribution işlevi</span><span class="sxs-lookup"><span data-stu-id="dedbd-102">DiscreteUniformDistribution function</span></span>

<span data-ttu-id="dedbd-103">Ad alanı: [Microsoft. hisse. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="dedbd-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="dedbd-104">Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="dedbd-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="dedbd-105">Verili bir kapsayıcı aralığı üzerinde Tekdüzen dağılımı döndürür.</span><span class="sxs-lookup"><span data-stu-id="dedbd-105">Returns a uniform distribution over a given inclusive range.</span></span>

```qsharp
function DiscreteUniformDistribution (min : Int, max : Int) : Microsoft.Quantum.Random.DiscreteDistribution
```


## <a name="input"></a><span data-ttu-id="dedbd-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="dedbd-106">Input</span></span>

### <a name="min--int"></a><span data-ttu-id="dedbd-107">Min: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="dedbd-107">min : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="dedbd-108">Çizilecek en küçük tamsayı.</span><span class="sxs-lookup"><span data-stu-id="dedbd-108">The smallest integer to be drawn.</span></span>


### <a name="max--int"></a><span data-ttu-id="dedbd-109">Max: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="dedbd-109">max : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="dedbd-110">Çizilecek en büyük tamsayı.</span><span class="sxs-lookup"><span data-stu-id="dedbd-110">The largest integer to be drawn.</span></span>



## <a name="output--discretedistribution"></a><span data-ttu-id="dedbd-111">Çıkış: [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span><span class="sxs-lookup"><span data-stu-id="dedbd-111">Output : [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span></span>

<span data-ttu-id="dedbd-112">Rastgele değiştireni, kapsamlı `min` olasılığa sahip olan ve arasında bir tamsayı olan bir dağıtım `max` .</span><span class="sxs-lookup"><span data-stu-id="dedbd-112">A distribution whose random variates are integers in the inclusive range from `min` to `max` with uniform probability.</span></span>

## <a name="remarks"></a><span data-ttu-id="dedbd-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="dedbd-113">Remarks</span></span>

<span data-ttu-id="dedbd-114">Başarısız olur `max <= min` .</span><span class="sxs-lookup"><span data-stu-id="dedbd-114">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="dedbd-115">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="dedbd-115">See Also</span></span>

- [<span data-ttu-id="dedbd-116">Microsoft. hisse. DrawRandomDouble</span><span class="sxs-lookup"><span data-stu-id="dedbd-116">Microsoft.Quantum.DrawRandomDouble</span></span>](xref:Microsoft.Quantum.DrawRandomDouble)