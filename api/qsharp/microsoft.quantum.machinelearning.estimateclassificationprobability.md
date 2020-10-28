---
uid: Microsoft.Quantum.MachineLearning.EstimateClassificationProbability
title: EstimateClassificationProbability işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: EstimateClassificationProbability
qsharp.summary: Given a sample and a sequential classifier, estimates the classification probability for that sample by repeatedly measuring the output of the classifier on the given sample.
ms.openlocfilehash: 79e40bc4bc0954dc6742307122609950bf22ec71
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725958"
---
# <a name="estimateclassificationprobability-operation"></a><span data-ttu-id="c3a66-102">EstimateClassificationProbability işlemi</span><span class="sxs-lookup"><span data-stu-id="c3a66-102">EstimateClassificationProbability operation</span></span>

<span data-ttu-id="c3a66-103">Ad alanı: [Microsoft. hisse. Machinöğrenim](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="c3a66-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="c3a66-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c3a66-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c3a66-105">Örnek ve sıralı bir sınıflandırıcı verildiğinde, verilen örnekteki sınıflandırıcının çıkışını sürekli olarak ölçerek söz konusu örnek için sınıflandırma olasılığını tahmin eder.</span><span class="sxs-lookup"><span data-stu-id="c3a66-105">Given a sample and a sequential classifier, estimates the classification probability for that sample by repeatedly measuring the output of the classifier on the given sample.</span></span>

```qsharp
operation EstimateClassificationProbability (tolerance : Double, model : Microsoft.Quantum.MachineLearning.SequentialModel, sample : Double[], nMeasurements : Int) : Double
```


## <a name="input"></a><span data-ttu-id="c3a66-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="c3a66-106">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="c3a66-107">Tolerans: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c3a66-107">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c3a66-108">Örneği bir durum hazırlama işlemine kodlamaya izin veren tolerans.</span><span class="sxs-lookup"><span data-stu-id="c3a66-108">The tolerance to allow in encoding the sample into a state preparation operation.</span></span>


### <a name="model--sequentialmodel"></a><span data-ttu-id="c3a66-109">Model: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="c3a66-109">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>

<span data-ttu-id="c3a66-110">Verilen örnek için sınıflandırma olasılığını tahmin etmek üzere kullanılacak sıralı model.</span><span class="sxs-lookup"><span data-stu-id="c3a66-110">The sequential model to be used to estimate the classification probability for the given sample.</span></span>


### <a name="sample--double"></a><span data-ttu-id="c3a66-111">Örnek: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="c3a66-111">sample : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="c3a66-112">Sınıflandırılacak örnek için özellik vektörü.</span><span class="sxs-lookup"><span data-stu-id="c3a66-112">The feature vector for the sample to be classified.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="c3a66-113">Nölçümler: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c3a66-113">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c3a66-114">Sınıflandırma olasılığını tahmin etmek için kullanılacak ölçüm sayısı.</span><span class="sxs-lookup"><span data-stu-id="c3a66-114">The number of measurements to use in estimating the classification probability.</span></span>



## <a name="output--double"></a><span data-ttu-id="c3a66-115">Çıkış: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c3a66-115">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c3a66-116">Belirtilen örnek için sınıflandırma olasılığının tahmini.</span><span class="sxs-lookup"><span data-stu-id="c3a66-116">An estimate of the classification probability for the given sample.</span></span>