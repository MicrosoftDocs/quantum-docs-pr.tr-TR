---
uid: Microsoft.Quantum.MachineLearning.InferredLabels
title: Inferredlabels işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InferredLabels
qsharp.summary: Given an array of classification probabilities and a bias, returns the label inferred from each probability.
ms.openlocfilehash: 668ab89ed45c49d33ce50ff5d892f4d57246c12a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196370"
---
# <a name="inferredlabels-function"></a><span data-ttu-id="c39b0-102">Inferredlabels işlevi</span><span class="sxs-lookup"><span data-stu-id="c39b0-102">InferredLabels function</span></span>

<span data-ttu-id="c39b0-103">Ad alanı: [Microsoft. hisse. Machinöğrenim](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="c39b0-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="c39b0-104">Paket: [Microsoft. hisse. Machine-öğrenim](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="c39b0-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="c39b0-105">Sınıflandırma olasılıkların ve bir sapmanın dizisi verildiğinde, her olasılığa göre gösterilen etiketi döndürür.</span><span class="sxs-lookup"><span data-stu-id="c39b0-105">Given an array of classification probabilities and a bias, returns the label inferred from each probability.</span></span>

```qsharp
function InferredLabels (bias : Double, probabilities : Double[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="c39b0-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="c39b0-106">Input</span></span>

### <a name="bias--double"></a><span data-ttu-id="c39b0-107">sapma: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c39b0-107">bias : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c39b0-108">İki sınıf arasındaki sapma genellikle sınıflandırıcının eğitiminin sonucu.</span><span class="sxs-lookup"><span data-stu-id="c39b0-108">The bias between two classes, typically the result of training a classifier.</span></span>


### <a name="probabilities--double"></a><span data-ttu-id="c39b0-109">olasılıklara: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="c39b0-109">probabilities : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="c39b0-110">Genellikle sınıflandırma sıklıklarından kaynaklanan bir örnek kümesi için sınıflandırma olasılıkları dizisi.</span><span class="sxs-lookup"><span data-stu-id="c39b0-110">An array of classification probabilities for a set of samples, typically resulting from estimating classification frequencies.</span></span>



## <a name="output--int"></a><span data-ttu-id="c39b0-111">Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="c39b0-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="c39b0-112">Her sınıflandırma olasılığının çıkartılan etiket.</span><span class="sxs-lookup"><span data-stu-id="c39b0-112">The label inferred from each classification probability.</span></span>