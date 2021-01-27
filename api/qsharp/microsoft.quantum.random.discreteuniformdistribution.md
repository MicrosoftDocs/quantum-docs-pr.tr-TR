---
uid: Microsoft.Quantum.Random.DiscreteUniformDistribution
title: DiscreteUniformDistribution işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DiscreteUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive range.
ms.openlocfilehash: f909e7def5439ec0feef4ca4dc0cf8ed12374dfe
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853716"
---
# <a name="discreteuniformdistribution-function"></a><span data-ttu-id="01bd6-102">DiscreteUniformDistribution işlevi</span><span class="sxs-lookup"><span data-stu-id="01bd6-102">DiscreteUniformDistribution function</span></span>

<span data-ttu-id="01bd6-103">Ad alanı: [Microsoft. hisse. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="01bd6-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="01bd6-104">Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="01bd6-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="01bd6-105">Verili bir kapsayıcı aralığı üzerinde Tekdüzen dağılımı döndürür.</span><span class="sxs-lookup"><span data-stu-id="01bd6-105">Returns a uniform distribution over a given inclusive range.</span></span>

```qsharp
function DiscreteUniformDistribution (min : Int, max : Int) : Microsoft.Quantum.Random.DiscreteDistribution
```


## <a name="input"></a><span data-ttu-id="01bd6-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="01bd6-106">Input</span></span>

### <a name="min--int"></a><span data-ttu-id="01bd6-107">Min: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="01bd6-107">min : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="01bd6-108">Çizilecek en küçük tamsayı.</span><span class="sxs-lookup"><span data-stu-id="01bd6-108">The smallest integer to be drawn.</span></span>


### <a name="max--int"></a><span data-ttu-id="01bd6-109">Max: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="01bd6-109">max : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="01bd6-110">Çizilecek en büyük tamsayı.</span><span class="sxs-lookup"><span data-stu-id="01bd6-110">The largest integer to be drawn.</span></span>



## <a name="output--discretedistribution"></a><span data-ttu-id="01bd6-111">Çıkış: [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span><span class="sxs-lookup"><span data-stu-id="01bd6-111">Output : [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span></span>

<span data-ttu-id="01bd6-112">Rastgele değiştireni, kapsamlı `min` olasılığa sahip olan ve arasında bir tamsayı olan bir dağıtım `max` .</span><span class="sxs-lookup"><span data-stu-id="01bd6-112">A distribution whose random variates are integers in the inclusive range from `min` to `max` with uniform probability.</span></span>

## <a name="example"></a><span data-ttu-id="01bd6-113">Örnek</span><span class="sxs-lookup"><span data-stu-id="01bd6-113">Example</span></span>

<span data-ttu-id="01bd6-114">Aşağıdaki Q # kod parçacığı rastgele altı taraflı bir zar kaydeder:</span><span class="sxs-lookup"><span data-stu-id="01bd6-114">The following Q# snippet randomly rolls a six-sided die:</span></span>

```qsharp
let dieDistribution = DiscreteUniformDistribution(1, 6);
let dieRoll = dieDistribution::Sample();
```

## <a name="remarks"></a><span data-ttu-id="01bd6-115">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="01bd6-115">Remarks</span></span>

<span data-ttu-id="01bd6-116">Başarısız olur `max <= min` .</span><span class="sxs-lookup"><span data-stu-id="01bd6-116">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="01bd6-117">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="01bd6-117">See Also</span></span>

- [<span data-ttu-id="01bd6-118">Microsoft. hisse. DrawRandomDouble</span><span class="sxs-lookup"><span data-stu-id="01bd6-118">Microsoft.Quantum.DrawRandomDouble</span></span>](xref:Microsoft.Quantum.DrawRandomDouble)