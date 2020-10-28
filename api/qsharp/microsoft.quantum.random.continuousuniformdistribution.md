---
uid: Microsoft.Quantum.Random.ContinuousUniformDistribution
title: ContinuousUniformDistribution işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: ContinuousUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive interval.
ms.openlocfilehash: 74300efb10ba7b5aa006f0b1b6aafde0da840f00
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725813"
---
# <a name="continuousuniformdistribution-function"></a><span data-ttu-id="c17dd-102">ContinuousUniformDistribution işlevi</span><span class="sxs-lookup"><span data-stu-id="c17dd-102">ContinuousUniformDistribution function</span></span>

<span data-ttu-id="c17dd-103">Ad alanı: [Microsoft. hisse. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="c17dd-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="c17dd-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c17dd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c17dd-105">Verilen bir kapsayıcı aralığı üzerinde Tekdüzen dağılımı döndürür.</span><span class="sxs-lookup"><span data-stu-id="c17dd-105">Returns a uniform distribution over a given inclusive interval.</span></span>

```qsharp
function ContinuousUniformDistribution (min : Double, max : Double) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a><span data-ttu-id="c17dd-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="c17dd-106">Input</span></span>

### <a name="min--double"></a><span data-ttu-id="c17dd-107">Min: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c17dd-107">min : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c17dd-108">Çizilecek en küçük gerçek sayı.</span><span class="sxs-lookup"><span data-stu-id="c17dd-108">The smallest real number to be drawn.</span></span>


### <a name="max--double"></a><span data-ttu-id="c17dd-109">Max: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c17dd-109">max : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c17dd-110">Çizilecek en büyük gerçek sayı.</span><span class="sxs-lookup"><span data-stu-id="c17dd-110">The largest real number to be drawn.</span></span>



## <a name="output--continuousdistribution"></a><span data-ttu-id="c17dd-111">Çıkış: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="c17dd-111">Output : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>

<span data-ttu-id="c17dd-112">Rastgele `min` bultteklerini, kapsamlı olasılığa sahip olan bağımsız aralıkta gerçek sayı olan bir dağıtım `max` .</span><span class="sxs-lookup"><span data-stu-id="c17dd-112">A distribution whose random variates are real numbers in the inclusive interval from `min` to `max` with uniform probability.</span></span>

## <a name="remarks"></a><span data-ttu-id="c17dd-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="c17dd-113">Remarks</span></span>

<span data-ttu-id="c17dd-114">Başarısız olur `max <= min` .</span><span class="sxs-lookup"><span data-stu-id="c17dd-114">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="c17dd-115">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="c17dd-115">See Also</span></span>

- [<span data-ttu-id="c17dd-116">Microsoft. hisse. DrawRandomDouble</span><span class="sxs-lookup"><span data-stu-id="c17dd-116">Microsoft.Quantum.DrawRandomDouble</span></span>](xref:Microsoft.Quantum.DrawRandomDouble)