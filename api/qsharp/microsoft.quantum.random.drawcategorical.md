---
uid: Microsoft.Quantum.Random.DrawCategorical
title: DrawCategorical işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawCategorical
qsharp.summary: Draws a random sample from a categorical distribution specified by a list of probablities.
ms.openlocfilehash: fdc5ae3a9341cb11e8fda129bdd030289b6c99c2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730959"
---
# <a name="drawcategorical-operation"></a><span data-ttu-id="c743c-102">DrawCategorical işlemi</span><span class="sxs-lookup"><span data-stu-id="c743c-102">DrawCategorical operation</span></span>

<span data-ttu-id="c743c-103">Ad alanı: [Microsoft. hisse. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="c743c-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="c743c-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c743c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c743c-105">Bir olasılık listesi tarafından belirtilen kategorik bir dağılıdan rastgele bir örnek çizer.</span><span class="sxs-lookup"><span data-stu-id="c743c-105">Draws a random sample from a categorical distribution specified by a list of probablities.</span></span>

```qsharp
operation DrawCategorical (probs : Double[]) : Int
```


## <a name="description"></a><span data-ttu-id="c743c-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="c743c-106">Description</span></span>

<span data-ttu-id="c743c-107">Belirli bir dizini seçme olasılığı, bu dizindeki dizi öğesinin değeri ile orantılıdır.</span><span class="sxs-lookup"><span data-stu-id="c743c-107">The probability of selecting a specific index is proportional to the value of the array element at that index.</span></span>
<span data-ttu-id="c743c-108">Sıfıra eşit dizi öğeleri yok sayılır ve bunların dizinleri hiçbir şekilde döndürülmez.</span><span class="sxs-lookup"><span data-stu-id="c743c-108">Array elements that are equal to zero are ignored and their indices are never returned.</span></span> <span data-ttu-id="c743c-109">Herhangi bir dizi öğesi sıfırdan küçükse veya hiçbir dizi öğesi sıfırdan büyükse, işlem başarısız olur.</span><span class="sxs-lookup"><span data-stu-id="c743c-109">If any array element is less than zero, or if no array element is greater than zero, then the operation fails.</span></span>

## <a name="input"></a><span data-ttu-id="c743c-110">Giriş</span><span class="sxs-lookup"><span data-stu-id="c743c-110">Input</span></span>

### <a name="probs--double"></a><span data-ttu-id="c743c-111">probs: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="c743c-111">probs : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="c743c-112">Kayan noktalı sayıların dizisi her bir dizini seçme olasılığa göre orantılıdır.</span><span class="sxs-lookup"><span data-stu-id="c743c-112">An array of floating-point numbers proportional to the probability of selecting each index.</span></span>



## <a name="output--int"></a><span data-ttu-id="c743c-113">Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c743c-113">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c743c-114">Olasılık $ \Pr (i) = p_i/\ sum_i p_i $ olan bir tamsayı $i $, burada $p _i $, $i $ TH öğesidir `probs` .</span><span class="sxs-lookup"><span data-stu-id="c743c-114">An integer $i$ with probability $\Pr(i) = p_i / \sum_i p_i$, where $p_i$ is the $i$th element of `probs`.</span></span>

## <a name="see-also"></a><span data-ttu-id="c743c-115">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="c743c-115">See Also</span></span>

- [<span data-ttu-id="c743c-116">Microsoft. hisse. Random. CategoricalDistribution</span><span class="sxs-lookup"><span data-stu-id="c743c-116">Microsoft.Quantum.Random.CategoricalDistribution</span></span>](xref:Microsoft.Quantum.Random.CategoricalDistribution)