---
uid: Microsoft.Quantum.MachineLearning.InferredLabel
title: Inferredlabel işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InferredLabel
qsharp.summary: Given a of classification probability and a bias, returns the label inferred from that probability.
ms.openlocfilehash: 46b24c283a01e6ac1c959ee4a6899591ee708ff7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848415"
---
# <a name="inferredlabel-function"></a><span data-ttu-id="2b4d3-102">Inferredlabel işlevi</span><span class="sxs-lookup"><span data-stu-id="2b4d3-102">InferredLabel function</span></span>

<span data-ttu-id="2b4d3-103">Ad alanı: [Microsoft. hisse. Machinöğrenim](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="2b4d3-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="2b4d3-104">Paket: [Microsoft. hisse. Machine-öğrenim](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="2b4d3-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="2b4d3-105">Sınıflandırma olasılığı ve bir sapma verildiğinde, bu olasılığa göre çıkarılan etiketi döndürür.</span><span class="sxs-lookup"><span data-stu-id="2b4d3-105">Given a of classification probability and a bias, returns the label inferred from that probability.</span></span>

```qsharp
function InferredLabel (bias : Double, probability : Double) : Int
```


## <a name="input"></a><span data-ttu-id="2b4d3-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="2b4d3-106">Input</span></span>

### <a name="bias--double"></a><span data-ttu-id="2b4d3-107">sapma: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="2b4d3-107">bias : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="2b4d3-108">İki sınıf arasındaki sapma genellikle sınıflandırıcının eğitiminin sonucu.</span><span class="sxs-lookup"><span data-stu-id="2b4d3-108">The bias between two classes, typically the result of training a classifier.</span></span>


### <a name="probability--double"></a><span data-ttu-id="2b4d3-109">olasılık: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="2b4d3-109">probability : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="2b4d3-110">Belirli bir örnek için bir sınıflandırma olasılıklarını, genellikle sınıflandırma sıklığını tahmin etmeye yol açar.</span><span class="sxs-lookup"><span data-stu-id="2b4d3-110">A classification probabilities for a particular sample, typically resulting from estimating its classification frequency.</span></span>



## <a name="output--int"></a><span data-ttu-id="2b4d3-111">Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2b4d3-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2b4d3-112">Verilen sınıflandırma olasıslarından çıkarılan etiket.</span><span class="sxs-lookup"><span data-stu-id="2b4d3-112">The label inferred from the given classification probability.</span></span>