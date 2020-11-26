---
uid: Microsoft.Quantum.Random.DrawRandomDouble
title: DrawRandomDouble işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomDouble
qsharp.summary: Draws a random real number in a given inclusive interval.
ms.openlocfilehash: d62416f4a222716edb9393fe4f43731d0e8aa9d3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192953"
---
# <a name="drawrandomdouble-operation"></a><span data-ttu-id="e8c9b-102">DrawRandomDouble işlemi</span><span class="sxs-lookup"><span data-stu-id="e8c9b-102">DrawRandomDouble operation</span></span>

<span data-ttu-id="e8c9b-103">Ad alanı: [Microsoft. hisse. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="e8c9b-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="e8c9b-104">Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="e8c9b-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="e8c9b-105">Verili bir kapsayıcı aralığında rastgele bir gerçek sayı çizer.</span><span class="sxs-lookup"><span data-stu-id="e8c9b-105">Draws a random real number in a given inclusive interval.</span></span>

```qsharp
operation DrawRandomDouble (min : Double, max : Double) : Double
```


## <a name="input"></a><span data-ttu-id="e8c9b-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="e8c9b-106">Input</span></span>

### <a name="min--double"></a><span data-ttu-id="e8c9b-107">Min: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e8c9b-107">min : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e8c9b-108">Çizilecek en küçük gerçek sayı.</span><span class="sxs-lookup"><span data-stu-id="e8c9b-108">The smallest real number to be drawn.</span></span>


### <a name="max--double"></a><span data-ttu-id="e8c9b-109">Max: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e8c9b-109">max : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e8c9b-110">Çizilecek en büyük gerçek sayı.</span><span class="sxs-lookup"><span data-stu-id="e8c9b-110">The largest real number to be drawn.</span></span>



## <a name="output--double"></a><span data-ttu-id="e8c9b-111">Çıkış: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e8c9b-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e8c9b-112">Kapsamlı `min` olasılığa sahip olan ve arasında rastgele bir gerçek sayı `max` .</span><span class="sxs-lookup"><span data-stu-id="e8c9b-112">A random real number in the inclusive interval from `min` to `max` with uniform probability.</span></span>

## <a name="remarks"></a><span data-ttu-id="e8c9b-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="e8c9b-113">Remarks</span></span>

<span data-ttu-id="e8c9b-114">Başarısız olur `max <= min` .</span><span class="sxs-lookup"><span data-stu-id="e8c9b-114">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="e8c9b-115">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="e8c9b-115">See Also</span></span>

- [<span data-ttu-id="e8c9b-116">Microsoft. hisse. ContinuousUniformDistribution</span><span class="sxs-lookup"><span data-stu-id="e8c9b-116">Microsoft.Quantum.ContinuousUniformDistribution</span></span>](xref:Microsoft.Quantum.ContinuousUniformDistribution)