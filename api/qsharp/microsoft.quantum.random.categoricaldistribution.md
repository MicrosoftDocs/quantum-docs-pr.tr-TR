---
uid: Microsoft.Quantum.Random.CategoricalDistribution
title: CategoricalDistribution işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: CategoricalDistribution
qsharp.summary: Returns a discrete categorical distribution, in which the probability for each of a finite list of given outcomes is explicitly specified.
ms.openlocfilehash: 2e3d9b17939d5a9a5bc5e7d89a843e0ff5a848ba
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210259"
---
# <a name="categoricaldistribution-function"></a><span data-ttu-id="d8a56-102">CategoricalDistribution işlevi</span><span class="sxs-lookup"><span data-stu-id="d8a56-102">CategoricalDistribution function</span></span>

<span data-ttu-id="d8a56-103">Ad alanı: [Microsoft. hisse. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="d8a56-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="d8a56-104">Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="d8a56-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="d8a56-105">Belirli bir sonuçların sınırlı listesinin her biri için olasılık açıkça belirtildiğinde ayrık bir kategorik dağıtım döndürür.</span><span class="sxs-lookup"><span data-stu-id="d8a56-105">Returns a discrete categorical distribution, in which the probability for each of a finite list of given outcomes is explicitly specified.</span></span>

```qsharp
function CategoricalDistribution (probs : Double[]) : Microsoft.Quantum.Random.DiscreteDistribution
```


## <a name="input"></a><span data-ttu-id="d8a56-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="d8a56-106">Input</span></span>

### <a name="probs--double"></a><span data-ttu-id="d8a56-107">probs: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="d8a56-107">probs : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="d8a56-108">Kategorik dağılıklarından her bir sonuç için olasılıkların.</span><span class="sxs-lookup"><span data-stu-id="d8a56-108">The probabilities for each outcome from the categorical distribution.</span></span>
<span data-ttu-id="d8a56-109">Bu olasılıkların normalleştirilmeyebilir, ancak tümünün negatif olmaması gerekir.</span><span class="sxs-lookup"><span data-stu-id="d8a56-109">These probabilities may not be normalized, but must all be non-negative.</span></span>



## <a name="output--discretedistribution"></a><span data-ttu-id="d8a56-110">Çıkış: [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span><span class="sxs-lookup"><span data-stu-id="d8a56-110">Output : [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span></span>

<span data-ttu-id="d8a56-111">`i`Olasılığı olan dizin `probs[i] / sum` ,, `sum` `probs` tarafından verilen `Fold(PlusD, 0.0, probs)` .</span><span class="sxs-lookup"><span data-stu-id="d8a56-111">The index `i` with probability `probs[i] / sum`, where `sum` is the sum of `probs` given by `Fold(PlusD, 0.0, probs)`.</span></span>