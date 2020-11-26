---
uid: Microsoft.Quantum.Random.ContinuousUniformDistribution
title: ContinuousUniformDistribution işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: ContinuousUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive interval.
ms.openlocfilehash: a3911fe9962ce18daa239de0272c53d83344134a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193089"
---
# <a name="continuousuniformdistribution-function"></a><span data-ttu-id="85d6b-102">ContinuousUniformDistribution işlevi</span><span class="sxs-lookup"><span data-stu-id="85d6b-102">ContinuousUniformDistribution function</span></span>

<span data-ttu-id="85d6b-103">Ad alanı: [Microsoft. hisse. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="85d6b-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="85d6b-104">Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="85d6b-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="85d6b-105">Verilen bir kapsayıcı aralığı üzerinde Tekdüzen dağılımı döndürür.</span><span class="sxs-lookup"><span data-stu-id="85d6b-105">Returns a uniform distribution over a given inclusive interval.</span></span>

```qsharp
function ContinuousUniformDistribution (min : Double, max : Double) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a><span data-ttu-id="85d6b-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="85d6b-106">Input</span></span>

### <a name="min--double"></a><span data-ttu-id="85d6b-107">Min: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="85d6b-107">min : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="85d6b-108">Çizilecek en küçük gerçek sayı.</span><span class="sxs-lookup"><span data-stu-id="85d6b-108">The smallest real number to be drawn.</span></span>


### <a name="max--double"></a><span data-ttu-id="85d6b-109">Max: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="85d6b-109">max : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="85d6b-110">Çizilecek en büyük gerçek sayı.</span><span class="sxs-lookup"><span data-stu-id="85d6b-110">The largest real number to be drawn.</span></span>



## <a name="output--continuousdistribution"></a><span data-ttu-id="85d6b-111">Çıkış: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="85d6b-111">Output : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>

<span data-ttu-id="85d6b-112">Rastgele `min` bultteklerini, kapsamlı olasılığa sahip olan bağımsız aralıkta gerçek sayı olan bir dağıtım `max` .</span><span class="sxs-lookup"><span data-stu-id="85d6b-112">A distribution whose random variates are real numbers in the inclusive interval from `min` to `max` with uniform probability.</span></span>

## <a name="remarks"></a><span data-ttu-id="85d6b-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="85d6b-113">Remarks</span></span>

<span data-ttu-id="85d6b-114">Başarısız olur `max <= min` .</span><span class="sxs-lookup"><span data-stu-id="85d6b-114">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="85d6b-115">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="85d6b-115">See Also</span></span>

- [<span data-ttu-id="85d6b-116">Microsoft. hisse. DrawRandomDouble</span><span class="sxs-lookup"><span data-stu-id="85d6b-116">Microsoft.Quantum.DrawRandomDouble</span></span>](xref:Microsoft.Quantum.DrawRandomDouble)