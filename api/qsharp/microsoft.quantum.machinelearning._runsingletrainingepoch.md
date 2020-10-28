---
uid: Microsoft.Quantum.MachineLearning._RunSingleTrainingEpoch
title: _RunSingleTrainingEpoch işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: _RunSingleTrainingEpoch
qsharp.summary: Perform one epoch of sequential classifier training on a subset of data samples.
ms.openlocfilehash: 2b4f629eac0bd8e60bd4d86077521c60085d4809
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731191"
---
# <a name="_runsingletrainingepoch-operation"></a><span data-ttu-id="dee7f-102">_RunSingleTrainingEpoch işlemi</span><span class="sxs-lookup"><span data-stu-id="dee7f-102">_RunSingleTrainingEpoch operation</span></span>

<span data-ttu-id="dee7f-103">Ad alanı: [Microsoft. hisse. Machinöğrenim](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="dee7f-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="dee7f-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="dee7f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="dee7f-105">Veri örneklerinin bir alt kümesi üzerinde sıralı sınıflandırıcı eğitiminin tek bir dönemini gerçekleştirin.</span><span class="sxs-lookup"><span data-stu-id="dee7f-105">Perform one epoch of sequential classifier training on a subset of data samples.</span></span>

```qsharp
operation _RunSingleTrainingEpoch (encodedSamples : (Microsoft.Quantum.MachineLearning.LabeledSample, Microsoft.Quantum.MachineLearning.StateGenerator)[], schedule : Microsoft.Quantum.MachineLearning.SamplingSchedule, periodScore : Int, options : Microsoft.Quantum.MachineLearning.TrainingOptions, model : Microsoft.Quantum.MachineLearning.SequentialModel, nPreviousBestMisses : Int) : (Int, Microsoft.Quantum.MachineLearning.SequentialModel)
```


## <a name="input"></a><span data-ttu-id="dee7f-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="dee7f-106">Input</span></span>

### <a name="encodedsamples--labeledsamplestategenerator"></a><span data-ttu-id="dee7f-107">encodedSamples: ([Labeledsample](xref:Microsoft.Quantum.MachineLearning.LabeledSample),[stategenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)) []</span><span class="sxs-lookup"><span data-stu-id="dee7f-107">encodedSamples : ([LabeledSample](xref:Microsoft.Quantum.MachineLearning.LabeledSample),[StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator))[]</span></span>




### <a name="schedule--samplingschedule"></a><span data-ttu-id="dee7f-108">zamanlama: [Samplingschedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span><span class="sxs-lookup"><span data-stu-id="dee7f-108">schedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span></span>




### <a name="periodscore--int"></a><span data-ttu-id="dee7f-109">periodScore: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="dee7f-109">periodScore : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="dee7f-110">Puanlama noktaları arasında gerçekleştirilecek gradyan adımları sayısı.</span><span class="sxs-lookup"><span data-stu-id="dee7f-110">The number of gradient steps to be taken between scoring points.</span></span>
<span data-ttu-id="dee7f-111">En iyi doğruluk için 1 olarak ayarlayın.</span><span class="sxs-lookup"><span data-stu-id="dee7f-111">For best accuracy, set to 1.</span></span>


### <a name="options--trainingoptions"></a><span data-ttu-id="dee7f-112">Seçenekler: [Traıningoptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)</span><span class="sxs-lookup"><span data-stu-id="dee7f-112">options : [TrainingOptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)</span></span>

<span data-ttu-id="dee7f-113">Eğitiminde kullanılacak seçenekler.</span><span class="sxs-lookup"><span data-stu-id="dee7f-113">Options to be used in training.</span></span>


### <a name="model--sequentialmodel"></a><span data-ttu-id="dee7f-114">Model: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="dee7f-114">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>

<span data-ttu-id="dee7f-115">Eğitilecek sıralı model.</span><span class="sxs-lookup"><span data-stu-id="dee7f-115">The sequential model to be trained.</span></span>


### <a name="npreviousbestmisses--int"></a><span data-ttu-id="dee7f-116">Npreviousen iyi Isabetsizlik: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="dee7f-116">nPreviousBestMisses : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="dee7f-117">Önceki dönemlerinde gözlemlenen hatalı sınıflandırmaların en iyi sayısı.</span><span class="sxs-lookup"><span data-stu-id="dee7f-117">The best number of misclassifications observed in previous epochs.</span></span>



## <a name="output--intsequentialmodel"></a><span data-ttu-id="dee7f-118">Çıkış: ([Int](xref:microsoft.quantum.lang-ref.int),[SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel))</span><span class="sxs-lookup"><span data-stu-id="dee7f-118">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel))</span></span>

- <span data-ttu-id="dee7f-119">Bu dönem ile gözlemlendi en küçük yanlış sınıflandırma sayısı.</span><span class="sxs-lookup"><span data-stu-id="dee7f-119">The smallest number of misclassifications observed through to this epoch.</span></span>
- <span data-ttu-id="dee7f-120">Yeni en iyi sıralı model bulundu.</span><span class="sxs-lookup"><span data-stu-id="dee7f-120">The new best sequential model found.</span></span>