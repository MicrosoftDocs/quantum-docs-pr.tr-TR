---
uid: Microsoft.Quantum.Random.DrawRandomInt
title: DrawRandomInt işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomInt
qsharp.summary: Draws a random integer in a given inclusive range.
ms.openlocfilehash: ebed7f52b7c4a8c538ed9d718c486b5aa94a0327
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851132"
---
# <a name="drawrandomint-operation"></a><span data-ttu-id="a8cb0-102">DrawRandomInt işlemi</span><span class="sxs-lookup"><span data-stu-id="a8cb0-102">DrawRandomInt operation</span></span>

<span data-ttu-id="a8cb0-103">Ad alanı: [Microsoft. hisse. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="a8cb0-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="a8cb0-104">Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="a8cb0-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="a8cb0-105">Verili bir kapsayıcı aralığında rastgele bir tamsayı çizer.</span><span class="sxs-lookup"><span data-stu-id="a8cb0-105">Draws a random integer in a given inclusive range.</span></span>

```qsharp
operation DrawRandomInt (min : Int, max : Int) : Int
```


## <a name="input"></a><span data-ttu-id="a8cb0-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="a8cb0-106">Input</span></span>

### <a name="min--int"></a><span data-ttu-id="a8cb0-107">Min: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a8cb0-107">min : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a8cb0-108">Çizilecek en küçük tamsayı.</span><span class="sxs-lookup"><span data-stu-id="a8cb0-108">The smallest integer to be drawn.</span></span>


### <a name="max--int"></a><span data-ttu-id="a8cb0-109">Max: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a8cb0-109">max : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a8cb0-110">Çizilecek en büyük tamsayı.</span><span class="sxs-lookup"><span data-stu-id="a8cb0-110">The largest integer to be drawn.</span></span>



## <a name="output--int"></a><span data-ttu-id="a8cb0-111">Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a8cb0-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a8cb0-112">İle arasında, tek bir tamsayı `min` `max` olasılığa sahip.</span><span class="sxs-lookup"><span data-stu-id="a8cb0-112">An integer in the inclusive range from `min` to `max` with uniform probability.</span></span>

## <a name="example"></a><span data-ttu-id="a8cb0-113">Örnek</span><span class="sxs-lookup"><span data-stu-id="a8cb0-113">Example</span></span>

<span data-ttu-id="a8cb0-114">Aşağıdaki Q # kod parçacığı rastgele altı taraflı bir zar kaydeder:</span><span class="sxs-lookup"><span data-stu-id="a8cb0-114">The following Q# snippet randomly rolls a six-sided die:</span></span>

```qsharp
let roll = DrawRandomInt(1, 6);
```

## <a name="remarks"></a><span data-ttu-id="a8cb0-115">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="a8cb0-115">Remarks</span></span>

<span data-ttu-id="a8cb0-116">Başarısız olur `max <= min` .</span><span class="sxs-lookup"><span data-stu-id="a8cb0-116">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="a8cb0-117">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="a8cb0-117">See Also</span></span>

- [<span data-ttu-id="a8cb0-118">Microsoft. hisse. DiscreteUniformDistribution</span><span class="sxs-lookup"><span data-stu-id="a8cb0-118">Microsoft.Quantum.DiscreteUniformDistribution</span></span>](xref:Microsoft.Quantum.DiscreteUniformDistribution)