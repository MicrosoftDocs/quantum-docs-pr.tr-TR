---
uid: Microsoft.Quantum.Random.DrawRandomDouble
title: DrawRandomDouble işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomDouble
qsharp.summary: Draws a random real number in a given inclusive interval.
ms.openlocfilehash: 792e9c714b761b48618aec2091e167a359c2b522
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847619"
---
# <a name="drawrandomdouble-operation"></a><span data-ttu-id="2686c-102">DrawRandomDouble işlemi</span><span class="sxs-lookup"><span data-stu-id="2686c-102">DrawRandomDouble operation</span></span>

<span data-ttu-id="2686c-103">Ad alanı: [Microsoft. hisse. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="2686c-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="2686c-104">Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="2686c-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="2686c-105">Verili bir kapsayıcı aralığında rastgele bir gerçek sayı çizer.</span><span class="sxs-lookup"><span data-stu-id="2686c-105">Draws a random real number in a given inclusive interval.</span></span>

```qsharp
operation DrawRandomDouble (min : Double, max : Double) : Double
```


## <a name="input"></a><span data-ttu-id="2686c-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="2686c-106">Input</span></span>

### <a name="min--double"></a><span data-ttu-id="2686c-107">Min: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="2686c-107">min : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="2686c-108">Çizilecek en küçük gerçek sayı.</span><span class="sxs-lookup"><span data-stu-id="2686c-108">The smallest real number to be drawn.</span></span>


### <a name="max--double"></a><span data-ttu-id="2686c-109">Max: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="2686c-109">max : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="2686c-110">Çizilecek en büyük gerçek sayı.</span><span class="sxs-lookup"><span data-stu-id="2686c-110">The largest real number to be drawn.</span></span>



## <a name="output--double"></a><span data-ttu-id="2686c-111">Çıkış: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="2686c-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="2686c-112">Kapsamlı `min` olasılığa sahip olan ve arasında rastgele bir gerçek sayı `max` .</span><span class="sxs-lookup"><span data-stu-id="2686c-112">A random real number in the inclusive interval from `min` to `max` with uniform probability.</span></span>

## <a name="example"></a><span data-ttu-id="2686c-113">Örnek</span><span class="sxs-lookup"><span data-stu-id="2686c-113">Example</span></span>

<span data-ttu-id="2686c-114">Aşağıdaki Q # kod parçacığı $0 $ ile $2 \pı $ arasında bir açı rastgele çizer:</span><span class="sxs-lookup"><span data-stu-id="2686c-114">The following Q# snippet randomly draws an angle between $0$ and $2 \pi$:</span></span>

```qsharp
let angle = DrawRandomDouble(0.0, 2.0 * PI());
```

## <a name="remarks"></a><span data-ttu-id="2686c-115">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="2686c-115">Remarks</span></span>

<span data-ttu-id="2686c-116">Başarısız olur `max <= min` .</span><span class="sxs-lookup"><span data-stu-id="2686c-116">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="2686c-117">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="2686c-117">See Also</span></span>

- [<span data-ttu-id="2686c-118">Microsoft. hisse. ContinuousUniformDistribution</span><span class="sxs-lookup"><span data-stu-id="2686c-118">Microsoft.Quantum.ContinuousUniformDistribution</span></span>](xref:Microsoft.Quantum.ContinuousUniformDistribution)