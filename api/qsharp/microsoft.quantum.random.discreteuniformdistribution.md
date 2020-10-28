---
uid: Microsoft.Quantum.Random.DiscreteUniformDistribution
title: DiscreteUniformDistribution işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DiscreteUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive range.
ms.openlocfilehash: 5e93c66d891d9b6aec548c0cf266df35e6090c92
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730967"
---
# <a name="discreteuniformdistribution-function"></a><span data-ttu-id="1346e-102">DiscreteUniformDistribution işlevi</span><span class="sxs-lookup"><span data-stu-id="1346e-102">DiscreteUniformDistribution function</span></span>

<span data-ttu-id="1346e-103">Ad alanı: [Microsoft. hisse. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="1346e-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="1346e-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1346e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1346e-105">Verili bir kapsayıcı aralığı üzerinde Tekdüzen dağılımı döndürür.</span><span class="sxs-lookup"><span data-stu-id="1346e-105">Returns a uniform distribution over a given inclusive range.</span></span>

```qsharp
function DiscreteUniformDistribution (min : Int, max : Int) : Microsoft.Quantum.Random.DiscreteDistribution
```


## <a name="input"></a><span data-ttu-id="1346e-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="1346e-106">Input</span></span>

### <a name="min--int"></a><span data-ttu-id="1346e-107">Min: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1346e-107">min : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1346e-108">Çizilecek en küçük tamsayı.</span><span class="sxs-lookup"><span data-stu-id="1346e-108">The smallest integer to be drawn.</span></span>


### <a name="max--int"></a><span data-ttu-id="1346e-109">Max: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1346e-109">max : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1346e-110">Çizilecek en büyük tamsayı.</span><span class="sxs-lookup"><span data-stu-id="1346e-110">The largest integer to be drawn.</span></span>



## <a name="output--discretedistribution"></a><span data-ttu-id="1346e-111">Çıkış: [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span><span class="sxs-lookup"><span data-stu-id="1346e-111">Output : [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span></span>

<span data-ttu-id="1346e-112">Rastgele değiştireni, kapsamlı `min` olasılığa sahip olan ve arasında bir tamsayı olan bir dağıtım `max` .</span><span class="sxs-lookup"><span data-stu-id="1346e-112">A distribution whose random variates are integers in the inclusive range from `min` to `max` with uniform probability.</span></span>

## <a name="remarks"></a><span data-ttu-id="1346e-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="1346e-113">Remarks</span></span>

<span data-ttu-id="1346e-114">Başarısız olur `max <= min` .</span><span class="sxs-lookup"><span data-stu-id="1346e-114">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="1346e-115">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="1346e-115">See Also</span></span>

- [<span data-ttu-id="1346e-116">Microsoft. hisse. DrawRandomDouble</span><span class="sxs-lookup"><span data-stu-id="1346e-116">Microsoft.Quantum.DrawRandomDouble</span></span>](xref:Microsoft.Quantum.DrawRandomDouble)