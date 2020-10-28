---
uid: Microsoft.Quantum.Random.CategoricalDistribution
title: CategoricalDistribution işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: CategoricalDistribution
qsharp.summary: Returns a discrete categorical distribution, in which the probability for each of a finite list of given outcomes is explicitly specified.
ms.openlocfilehash: 756e9e95cac5554ab8f885dab7c47ac1b174c0f3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732543"
---
# <a name="categoricaldistribution-function"></a><span data-ttu-id="75ed0-102">CategoricalDistribution işlevi</span><span class="sxs-lookup"><span data-stu-id="75ed0-102">CategoricalDistribution function</span></span>

<span data-ttu-id="75ed0-103">Ad alanı: [Microsoft. hisse. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="75ed0-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="75ed0-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="75ed0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="75ed0-105">Belirli bir sonuçların sınırlı listesinin her biri için olasılık açıkça belirtildiğinde ayrık bir kategorik dağıtım döndürür.</span><span class="sxs-lookup"><span data-stu-id="75ed0-105">Returns a discrete categorical distribution, in which the probability for each of a finite list of given outcomes is explicitly specified.</span></span>

```qsharp
function CategoricalDistribution (probs : Double[]) : Microsoft.Quantum.Random.DiscreteDistribution
```


## <a name="input"></a><span data-ttu-id="75ed0-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="75ed0-106">Input</span></span>

### <a name="probs--double"></a><span data-ttu-id="75ed0-107">probs: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="75ed0-107">probs : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="75ed0-108">Kategorik dağılıklarından her bir sonuç için olasılıkların.</span><span class="sxs-lookup"><span data-stu-id="75ed0-108">The probabilities for each outcome from the categorical distribution.</span></span>
<span data-ttu-id="75ed0-109">Bu olasılıkların normalleştirilmeyebilir, ancak tümünün negatif olmaması gerekir.</span><span class="sxs-lookup"><span data-stu-id="75ed0-109">These probabilities may not be normalized, but must all be non-negative.</span></span>



## <a name="output--discretedistribution"></a><span data-ttu-id="75ed0-110">Çıkış: [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span><span class="sxs-lookup"><span data-stu-id="75ed0-110">Output : [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span></span>

<span data-ttu-id="75ed0-111">`i`Olasılığı olan dizin `probs[i] / sum` ,, `sum` `probs` tarafından verilen `Fold(PlusD, 0.0, probs)` .</span><span class="sxs-lookup"><span data-stu-id="75ed0-111">The index `i` with probability `probs[i] / sum`, where `sum` is the sum of `probs` given by `Fold(PlusD, 0.0, probs)`.</span></span>