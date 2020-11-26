---
uid: Microsoft.Quantum.Random.DrawCategorical
title: DrawCategorical işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawCategorical
qsharp.summary: Draws a random sample from a categorical distribution specified by a list of probablities.
ms.openlocfilehash: a5826aa5f658fea766db0ca5ccbb9c0d7d056d4c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193004"
---
# <a name="drawcategorical-operation"></a><span data-ttu-id="5336b-102">DrawCategorical işlemi</span><span class="sxs-lookup"><span data-stu-id="5336b-102">DrawCategorical operation</span></span>

<span data-ttu-id="5336b-103">Ad alanı: [Microsoft. hisse. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="5336b-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="5336b-104">Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="5336b-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="5336b-105">Bir olasılık listesi tarafından belirtilen kategorik bir dağılıdan rastgele bir örnek çizer.</span><span class="sxs-lookup"><span data-stu-id="5336b-105">Draws a random sample from a categorical distribution specified by a list of probablities.</span></span>

```qsharp
operation DrawCategorical (probs : Double[]) : Int
```


## <a name="description"></a><span data-ttu-id="5336b-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="5336b-106">Description</span></span>

<span data-ttu-id="5336b-107">Belirli bir dizini seçme olasılığı, bu dizindeki dizi öğesinin değeri ile orantılıdır.</span><span class="sxs-lookup"><span data-stu-id="5336b-107">The probability of selecting a specific index is proportional to the value of the array element at that index.</span></span>
<span data-ttu-id="5336b-108">Sıfıra eşit dizi öğeleri yok sayılır ve bunların dizinleri hiçbir şekilde döndürülmez.</span><span class="sxs-lookup"><span data-stu-id="5336b-108">Array elements that are equal to zero are ignored and their indices are never returned.</span></span> <span data-ttu-id="5336b-109">Herhangi bir dizi öğesi sıfırdan küçükse veya hiçbir dizi öğesi sıfırdan büyükse, işlem başarısız olur.</span><span class="sxs-lookup"><span data-stu-id="5336b-109">If any array element is less than zero, or if no array element is greater than zero, then the operation fails.</span></span>

## <a name="input"></a><span data-ttu-id="5336b-110">Giriş</span><span class="sxs-lookup"><span data-stu-id="5336b-110">Input</span></span>

### <a name="probs--double"></a><span data-ttu-id="5336b-111">probs: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="5336b-111">probs : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="5336b-112">Kayan noktalı sayıların dizisi her bir dizini seçme olasılığa göre orantılıdır.</span><span class="sxs-lookup"><span data-stu-id="5336b-112">An array of floating-point numbers proportional to the probability of selecting each index.</span></span>



## <a name="output--int"></a><span data-ttu-id="5336b-113">Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5336b-113">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5336b-114">Olasılık $ \Pr (i) = p_i/\ sum_i p_i $ olan bir tamsayı $i $, burada $p _i $, $i $ TH öğesidir `probs` .</span><span class="sxs-lookup"><span data-stu-id="5336b-114">An integer $i$ with probability $\Pr(i) = p_i / \sum_i p_i$, where $p_i$ is the $i$th element of `probs`.</span></span>

## <a name="see-also"></a><span data-ttu-id="5336b-115">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="5336b-115">See Also</span></span>

- [<span data-ttu-id="5336b-116">Microsoft. hisse. Random. CategoricalDistribution</span><span class="sxs-lookup"><span data-stu-id="5336b-116">Microsoft.Quantum.Random.CategoricalDistribution</span></span>](xref:Microsoft.Quantum.Random.CategoricalDistribution)