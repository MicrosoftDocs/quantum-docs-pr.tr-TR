---
uid: Microsoft.Quantum.Random.ContinuousUniformDistribution
title: ContinuousUniformDistribution işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: ContinuousUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive interval.
ms.openlocfilehash: c81eb433f50277c677756ee70d916f4856260c6d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842311"
---
# <a name="continuousuniformdistribution-function"></a><span data-ttu-id="96998-102">ContinuousUniformDistribution işlevi</span><span class="sxs-lookup"><span data-stu-id="96998-102">ContinuousUniformDistribution function</span></span>

<span data-ttu-id="96998-103">Ad alanı: [Microsoft. hisse. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="96998-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="96998-104">Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="96998-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="96998-105">Verilen bir kapsayıcı aralığı üzerinde Tekdüzen dağılımı döndürür.</span><span class="sxs-lookup"><span data-stu-id="96998-105">Returns a uniform distribution over a given inclusive interval.</span></span>

```qsharp
function ContinuousUniformDistribution (min : Double, max : Double) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a><span data-ttu-id="96998-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="96998-106">Input</span></span>

### <a name="min--double"></a><span data-ttu-id="96998-107">Min: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="96998-107">min : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="96998-108">Çizilecek en küçük gerçek sayı.</span><span class="sxs-lookup"><span data-stu-id="96998-108">The smallest real number to be drawn.</span></span>


### <a name="max--double"></a><span data-ttu-id="96998-109">Max: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="96998-109">max : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="96998-110">Çizilecek en büyük gerçek sayı.</span><span class="sxs-lookup"><span data-stu-id="96998-110">The largest real number to be drawn.</span></span>



## <a name="output--continuousdistribution"></a><span data-ttu-id="96998-111">Çıkış: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="96998-111">Output : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>

<span data-ttu-id="96998-112">Rastgele `min` bultteklerini, kapsamlı olasılığa sahip olan bağımsız aralıkta gerçek sayı olan bir dağıtım `max` .</span><span class="sxs-lookup"><span data-stu-id="96998-112">A distribution whose random variates are real numbers in the inclusive interval from `min` to `max` with uniform probability.</span></span>

## <a name="example"></a><span data-ttu-id="96998-113">Örnek</span><span class="sxs-lookup"><span data-stu-id="96998-113">Example</span></span>

<span data-ttu-id="96998-114">Aşağıdaki Q # kod parçacığı $0 $ ile $2 \pı $ arasında bir açı rastgele çizer:</span><span class="sxs-lookup"><span data-stu-id="96998-114">The following Q# snippet randomly draws an angle between $0$ and $2 \pi$:</span></span>

```qsharp
let angleDistribution = ContinuousUniformDistribution(0.0, 2.0 * PI());
let angle = angleDistribution::Sample();
```

## <a name="remarks"></a><span data-ttu-id="96998-115">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="96998-115">Remarks</span></span>

<span data-ttu-id="96998-116">Başarısız olur `max <= min` .</span><span class="sxs-lookup"><span data-stu-id="96998-116">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="96998-117">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="96998-117">See Also</span></span>

- [<span data-ttu-id="96998-118">Microsoft. hisse. DrawRandomDouble</span><span class="sxs-lookup"><span data-stu-id="96998-118">Microsoft.Quantum.DrawRandomDouble</span></span>](xref:Microsoft.Quantum.DrawRandomDouble)