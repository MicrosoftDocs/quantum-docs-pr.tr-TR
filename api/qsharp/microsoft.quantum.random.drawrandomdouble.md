---
uid: Microsoft.Quantum.Random.DrawRandomDouble
title: DrawRandomDouble işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomDouble
qsharp.summary: Draws a random real number in a given inclusive interval.
ms.openlocfilehash: 6c0558ded2bd018afad84c42c2d15fc029ac0d44
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733210"
---
# <a name="drawrandomdouble-operation"></a><span data-ttu-id="a8fe5-102">DrawRandomDouble işlemi</span><span class="sxs-lookup"><span data-stu-id="a8fe5-102">DrawRandomDouble operation</span></span>

<span data-ttu-id="a8fe5-103">Ad alanı: [Microsoft. hisse. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="a8fe5-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="a8fe5-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a8fe5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a8fe5-105">Verili bir kapsayıcı aralığında rastgele bir gerçek sayı çizer.</span><span class="sxs-lookup"><span data-stu-id="a8fe5-105">Draws a random real number in a given inclusive interval.</span></span>

```qsharp
operation DrawRandomDouble (min : Double, max : Double) : Double
```


## <a name="input"></a><span data-ttu-id="a8fe5-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="a8fe5-106">Input</span></span>

### <a name="min--double"></a><span data-ttu-id="a8fe5-107">Min: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="a8fe5-107">min : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="a8fe5-108">Çizilecek en küçük gerçek sayı.</span><span class="sxs-lookup"><span data-stu-id="a8fe5-108">The smallest real number to be drawn.</span></span>


### <a name="max--double"></a><span data-ttu-id="a8fe5-109">Max: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="a8fe5-109">max : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="a8fe5-110">Çizilecek en büyük gerçek sayı.</span><span class="sxs-lookup"><span data-stu-id="a8fe5-110">The largest real number to be drawn.</span></span>



## <a name="output--double"></a><span data-ttu-id="a8fe5-111">Çıkış: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="a8fe5-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="a8fe5-112">Kapsamlı `min` olasılığa sahip olan ve arasında rastgele bir gerçek sayı `max` .</span><span class="sxs-lookup"><span data-stu-id="a8fe5-112">A random real number in the inclusive interval from `min` to `max` with uniform probability.</span></span>

## <a name="remarks"></a><span data-ttu-id="a8fe5-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="a8fe5-113">Remarks</span></span>

<span data-ttu-id="a8fe5-114">Başarısız olur `max <= min` .</span><span class="sxs-lookup"><span data-stu-id="a8fe5-114">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="a8fe5-115">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="a8fe5-115">See Also</span></span>

- [<span data-ttu-id="a8fe5-116">Microsoft. hisse. ContinuousUniformDistribution</span><span class="sxs-lookup"><span data-stu-id="a8fe5-116">Microsoft.Quantum.ContinuousUniformDistribution</span></span>](xref:Microsoft.Quantum.ContinuousUniformDistribution)