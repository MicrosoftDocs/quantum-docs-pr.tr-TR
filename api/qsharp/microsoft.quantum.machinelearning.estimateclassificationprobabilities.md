---
uid: Microsoft.Quantum.MachineLearning.EstimateClassificationProbabilities
title: EstimateClassificationProbabilities işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: EstimateClassificationProbabilities
qsharp.summary: Given a set of samples and a sequential classifier, estimates the classification probability for those samples by repeatedly measuring the output of the classifier on each sample.
ms.openlocfilehash: 2b7845d39256f718cc3e415207b8a47b24620bdb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725964"
---
# <a name="estimateclassificationprobabilities-operation"></a><span data-ttu-id="b4f4b-102">EstimateClassificationProbabilities işlemi</span><span class="sxs-lookup"><span data-stu-id="b4f4b-102">EstimateClassificationProbabilities operation</span></span>

<span data-ttu-id="b4f4b-103">Ad alanı: [Microsoft. hisse. Machinöğrenim](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="b4f4b-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="b4f4b-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b4f4b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b4f4b-105">Bir dizi örnek ve sıralı sınıflandırıcı verildiğinde, her örnekteki sınıflandırıcının çıkışını tekrar tekrar ölçerek, bu örneklerin sınıflandırma olasılığını tahmin eder.</span><span class="sxs-lookup"><span data-stu-id="b4f4b-105">Given a set of samples and a sequential classifier, estimates the classification probability for those samples by repeatedly measuring the output of the classifier on each sample.</span></span>

```qsharp
operation EstimateClassificationProbabilities (tolerance : Double, model : Microsoft.Quantum.MachineLearning.SequentialModel, samples : Double[][], nMeasurements : Int) : Double[]
```


## <a name="input"></a><span data-ttu-id="b4f4b-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="b4f4b-106">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="b4f4b-107">Tolerans: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b4f4b-107">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b4f4b-108">Örneği bir durum hazırlama işlemine kodlamaya izin veren tolerans.</span><span class="sxs-lookup"><span data-stu-id="b4f4b-108">The tolerance to allow in encoding the sample into a state preparation operation.</span></span>


### <a name="model--sequentialmodel"></a><span data-ttu-id="b4f4b-109">Model: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="b4f4b-109">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>

<span data-ttu-id="b4f4b-110">Verilen örnekler için sınıflandırma olasılıkların tahmin edilmesi için kullanılacak sıralı model.</span><span class="sxs-lookup"><span data-stu-id="b4f4b-110">The sequential model to be used to estimate the classification probabilities for the given samples.</span></span>


### <a name="samples--double"></a><span data-ttu-id="b4f4b-111">örnekler: [Double](xref:microsoft.quantum.lang-ref.double)[] []</span><span class="sxs-lookup"><span data-stu-id="b4f4b-111">samples : [Double](xref:microsoft.quantum.lang-ref.double)[][]</span></span>

<span data-ttu-id="b4f4b-112">Sınıflandırılacak her örnek için bir özellik vektörü dizisi.</span><span class="sxs-lookup"><span data-stu-id="b4f4b-112">An array of feature vectors for each sample to be classified.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="b4f4b-113">Nölçümler: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b4f4b-113">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b4f4b-114">Sınıflandırma olasılığını tahmin etmek için kullanılacak ölçüm sayısı.</span><span class="sxs-lookup"><span data-stu-id="b4f4b-114">The number of measurements to use in estimating the classification probability.</span></span>



## <a name="output--double"></a><span data-ttu-id="b4f4b-115">Çıkış: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="b4f4b-115">Output : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="b4f4b-116">Verilen her örnek için sınıflandırma olasılığının tahminlerinin bir dizisi.</span><span class="sxs-lookup"><span data-stu-id="b4f4b-116">An array of estimates of the classification probability for each given sample.</span></span>