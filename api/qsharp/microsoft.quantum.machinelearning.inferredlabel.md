---
uid: Microsoft.Quantum.MachineLearning.InferredLabel
title: Inferredlabel işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InferredLabel
qsharp.summary: Given a of classification probability and a bias, returns the label inferred from that probability.
ms.openlocfilehash: 1d6edec94f731fe96da797f0c3d77e6eba565149
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732370"
---
# <a name="inferredlabel-function"></a><span data-ttu-id="695d9-102">Inferredlabel işlevi</span><span class="sxs-lookup"><span data-stu-id="695d9-102">InferredLabel function</span></span>

<span data-ttu-id="695d9-103">Ad alanı: [Microsoft. hisse. Machinöğrenim](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="695d9-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="695d9-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="695d9-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="695d9-105">Sınıflandırma olasılığı ve bir sapma verildiğinde, bu olasılığa göre çıkarılan etiketi döndürür.</span><span class="sxs-lookup"><span data-stu-id="695d9-105">Given a of classification probability and a bias, returns the label inferred from that probability.</span></span>

```qsharp
function InferredLabel (bias : Double, probability : Double) : Int
```


## <a name="input"></a><span data-ttu-id="695d9-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="695d9-106">Input</span></span>

### <a name="bias--double"></a><span data-ttu-id="695d9-107">sapma: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="695d9-107">bias : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="695d9-108">İki sınıf arasındaki sapma genellikle sınıflandırıcının eğitiminin sonucu.</span><span class="sxs-lookup"><span data-stu-id="695d9-108">The bias between two classes, typically the result of training a classifier.</span></span>


### <a name="probability--double"></a><span data-ttu-id="695d9-109">olasılık: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="695d9-109">probability : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="695d9-110">Belirli bir örnek için bir sınıflandırma olasılıklarını, genellikle sınıflandırma sıklığını tahmin etmeye yol açar.</span><span class="sxs-lookup"><span data-stu-id="695d9-110">A classification probabilities for a particular sample, typically resulting from estimating its classification frequency.</span></span>



## <a name="output--int"></a><span data-ttu-id="695d9-111">Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="695d9-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="695d9-112">Verilen sınıflandırma olasıslarından çıkarılan etiket.</span><span class="sxs-lookup"><span data-stu-id="695d9-112">The label inferred from the given classification probability.</span></span>