---
uid: Microsoft.Quantum.Random.CategoricalDistribution
title: CategoricalDistribution işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: CategoricalDistribution
qsharp.summary: Returns a discrete categorical distribution, in which the probability for each of a finite list of given outcomes is explicitly specified.
ms.openlocfilehash: 754ada71078bd5446f78885ace31d92dce6bf1a4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842359"
---
# <a name="categoricaldistribution-function"></a><span data-ttu-id="70880-102">CategoricalDistribution işlevi</span><span class="sxs-lookup"><span data-stu-id="70880-102">CategoricalDistribution function</span></span>

<span data-ttu-id="70880-103">Ad alanı: [Microsoft. hisse. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="70880-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="70880-104">Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="70880-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="70880-105">Belirli bir sonuçların sınırlı listesinin her biri için olasılık açıkça belirtildiğinde ayrık bir kategorik dağıtım döndürür.</span><span class="sxs-lookup"><span data-stu-id="70880-105">Returns a discrete categorical distribution, in which the probability for each of a finite list of given outcomes is explicitly specified.</span></span>

```qsharp
function CategoricalDistribution (probs : Double[]) : Microsoft.Quantum.Random.DiscreteDistribution
```


## <a name="input"></a><span data-ttu-id="70880-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="70880-106">Input</span></span>

### <a name="probs--double"></a><span data-ttu-id="70880-107">probs: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="70880-107">probs : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="70880-108">Kategorik dağılıklarından her bir sonuç için olasılıkların.</span><span class="sxs-lookup"><span data-stu-id="70880-108">The probabilities for each outcome from the categorical distribution.</span></span>
<span data-ttu-id="70880-109">Bu olasılıkların normalleştirilmeyebilir, ancak tümünün negatif olmaması gerekir.</span><span class="sxs-lookup"><span data-stu-id="70880-109">These probabilities may not be normalized, but must all be non-negative.</span></span>



## <a name="output--discretedistribution"></a><span data-ttu-id="70880-110">Çıkış: [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span><span class="sxs-lookup"><span data-stu-id="70880-110">Output : [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span></span>

<span data-ttu-id="70880-111">`i`Olasılığı olan dizin `probs[i] / sum` ,, `sum` `probs` tarafından verilen `Fold(PlusD, 0.0, probs)` .</span><span class="sxs-lookup"><span data-stu-id="70880-111">The index `i` with probability `probs[i] / sum`, where `sum` is the sum of `probs` given by `Fold(PlusD, 0.0, probs)`.</span></span>

## <a name="example"></a><span data-ttu-id="70880-112">Örnek</span><span class="sxs-lookup"><span data-stu-id="70880-112">Example</span></span>

<span data-ttu-id="70880-113">Aşağıdaki Q # kodu 0 ' dan %30 ' a ve 1 ' i %70 ' i içeren 1 olarak görüntüleyecektir</span><span class="sxs-lookup"><span data-stu-id="70880-113">The following Q# code will display 0 with probability 30% and 1 with probability 70%:</span></span>

```qsharp
let dist = CategoricalDistribution([0.3, 0.7]);
Message($"Got sample: {dist::Sample()}");
```