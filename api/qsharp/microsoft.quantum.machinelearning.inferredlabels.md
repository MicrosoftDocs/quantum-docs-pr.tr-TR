---
uid: Microsoft.Quantum.MachineLearning.InferredLabels
title: Inferredlabels işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InferredLabels
qsharp.summary: Given an array of classification probabilities and a bias, returns the label inferred from each probability.
ms.openlocfilehash: 874d1a2f7cc6d67567e0d2baa70b0d26b639a029
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732351"
---
# <a name="inferredlabels-function"></a><span data-ttu-id="13ef9-102">Inferredlabels işlevi</span><span class="sxs-lookup"><span data-stu-id="13ef9-102">InferredLabels function</span></span>

<span data-ttu-id="13ef9-103">Ad alanı: [Microsoft. hisse. Machinöğrenim](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="13ef9-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="13ef9-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="13ef9-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="13ef9-105">Sınıflandırma olasılıkların ve bir sapmanın dizisi verildiğinde, her olasılığa göre gösterilen etiketi döndürür.</span><span class="sxs-lookup"><span data-stu-id="13ef9-105">Given an array of classification probabilities and a bias, returns the label inferred from each probability.</span></span>

```qsharp
function InferredLabels (bias : Double, probabilities : Double[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="13ef9-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="13ef9-106">Input</span></span>

### <a name="bias--double"></a><span data-ttu-id="13ef9-107">sapma: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="13ef9-107">bias : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="13ef9-108">İki sınıf arasındaki sapma genellikle sınıflandırıcının eğitiminin sonucu.</span><span class="sxs-lookup"><span data-stu-id="13ef9-108">The bias between two classes, typically the result of training a classifier.</span></span>


### <a name="probabilities--double"></a><span data-ttu-id="13ef9-109">olasılıklara: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="13ef9-109">probabilities : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="13ef9-110">Genellikle sınıflandırma sıklıklarından kaynaklanan bir örnek kümesi için sınıflandırma olasılıkları dizisi.</span><span class="sxs-lookup"><span data-stu-id="13ef9-110">An array of classification probabilities for a set of samples, typically resulting from estimating classification frequencies.</span></span>



## <a name="output--int"></a><span data-ttu-id="13ef9-111">Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="13ef9-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="13ef9-112">Her sınıflandırma olasılığının çıkartılan etiket.</span><span class="sxs-lookup"><span data-stu-id="13ef9-112">The label inferred from each classification probability.</span></span>