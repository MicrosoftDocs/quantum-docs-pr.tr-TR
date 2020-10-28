---
uid: Microsoft.Quantum.MachineLearning.TrainSequentialClassifierAtModel
title: TrainSequentialClassifierAtModel işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: TrainSequentialClassifierAtModel
qsharp.summary: Given the structure of a sequential classifier, trains the classifier on a given labeled training set, starting from a particular model.
ms.openlocfilehash: b9e30e4e5bc23f56d9119083045967caff28f13a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731074"
---
# <a name="trainsequentialclassifieratmodel-operation"></a><span data-ttu-id="0569c-102">TrainSequentialClassifierAtModel işlemi</span><span class="sxs-lookup"><span data-stu-id="0569c-102">TrainSequentialClassifierAtModel operation</span></span>

<span data-ttu-id="0569c-103">Ad alanı: [Microsoft. hisse. Machinöğrenim](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="0569c-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="0569c-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0569c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0569c-105">Sıralı bir sınıflandırıcının yapısı verildiğinde, belirli bir modelden başlayarak, belirli bir etiketli eğitim kümesindeki sınıflandırıcının kullanımını yapın.</span><span class="sxs-lookup"><span data-stu-id="0569c-105">Given the structure of a sequential classifier, trains the classifier on a given labeled training set, starting from a particular model.</span></span>

```qsharp
operation TrainSequentialClassifierAtModel (model : Microsoft.Quantum.MachineLearning.SequentialModel, samples : Microsoft.Quantum.MachineLearning.LabeledSample[], options : Microsoft.Quantum.MachineLearning.TrainingOptions, trainingSchedule : Microsoft.Quantum.MachineLearning.SamplingSchedule, validationSchedule : Microsoft.Quantum.MachineLearning.SamplingSchedule) : (Microsoft.Quantum.MachineLearning.SequentialModel, Int)
```


## <a name="input"></a><span data-ttu-id="0569c-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="0569c-106">Input</span></span>

### <a name="model--sequentialmodel"></a><span data-ttu-id="0569c-107">Model: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="0569c-107">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>

<span data-ttu-id="0569c-108">Eğitim için bir başlangıç noktası olarak kullanılacak sıralı model.</span><span class="sxs-lookup"><span data-stu-id="0569c-108">The sequential model to be used as a starting point for training.</span></span>


### <a name="samples--labeledsample"></a><span data-ttu-id="0569c-109">örnekler: [Labeledsample](xref:Microsoft.Quantum.MachineLearning.LabeledSample)[]</span><span class="sxs-lookup"><span data-stu-id="0569c-109">samples : [LabeledSample](xref:Microsoft.Quantum.MachineLearning.LabeledSample)[]</span></span>

<span data-ttu-id="0569c-110">Eğitim yapmak için kullanılacak bir etiketli eğitim verileri kümesi.</span><span class="sxs-lookup"><span data-stu-id="0569c-110">A set of labeled training data that will be used to perform training.</span></span>


### <a name="options--trainingoptions"></a><span data-ttu-id="0569c-111">Seçenekler: [Traıningoptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)</span><span class="sxs-lookup"><span data-stu-id="0569c-111">options : [TrainingOptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)</span></span>

<span data-ttu-id="0569c-112">Eğitim sırasında kullanılacak yapılandırma; @"microsoft.quantum.machinelearning.trainingoptions" @"microsoft.quantum.machinelearning.defaulttrainingoptions" daha fazla ayrıntı için bkz. ve.</span><span class="sxs-lookup"><span data-stu-id="0569c-112">Configuration to be used when training; see @"microsoft.quantum.machinelearning.trainingoptions" and @"microsoft.quantum.machinelearning.defaulttrainingoptions" for more details.</span></span>


### <a name="trainingschedule--samplingschedule"></a><span data-ttu-id="0569c-113">Traıningschedule: [Samplingschedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span><span class="sxs-lookup"><span data-stu-id="0569c-113">trainingSchedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span></span>

<span data-ttu-id="0569c-114">Eğitim adımları sırasında eğitim verilerinden örnek seçerken kullanılacak örnekleme zamanlaması.</span><span class="sxs-lookup"><span data-stu-id="0569c-114">A sampling schedule to use when selecting samples from the training data during training steps.</span></span>


### <a name="validationschedule--samplingschedule"></a><span data-ttu-id="0569c-115">validationSchedule: [Samplingschedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span><span class="sxs-lookup"><span data-stu-id="0569c-115">validationSchedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span></span>

<span data-ttu-id="0569c-116">Eğitim verilerinden örnek seçerken kullanılacak örnekleme zamanlaması, en iyi sınıflandırıcı puanına neden olan başlangıç noktasını seçerken kullanılır.</span><span class="sxs-lookup"><span data-stu-id="0569c-116">A sampling schedule to use when selecting samples from the training data when selecting which start point resulted in the best classifier score.</span></span>



## <a name="output--sequentialmodelint"></a><span data-ttu-id="0569c-117">Çıkış: ([SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel),[Int](xref:microsoft.quantum.lang-ref.int))</span><span class="sxs-lookup"><span data-stu-id="0569c-117">Output : ([SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel),[Int](xref:microsoft.quantum.lang-ref.int))</span></span>

- <span data-ttu-id="0569c-118">Verili sınıflandırıcının parametreleştirmesi ve iki sınıf arasındaki bir farkı, belirtilen başlangıç noktalarından her birinin en iyi sonucuna karşılık gelen bir şekilde bir araya getirme.</span><span class="sxs-lookup"><span data-stu-id="0569c-118">A parameterization of the given classifier and a bias between the two classes, together corresponding to the best result from each of the given start points.</span></span>
- <span data-ttu-id="0569c-119">En iyi sınıflandırıcı modelinde gözlemlendi isabetsizlik sayısı.</span><span class="sxs-lookup"><span data-stu-id="0569c-119">The number of misses observed at the best classifier model.</span></span>

## <a name="see-also"></a><span data-ttu-id="0569c-120">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="0569c-120">See Also</span></span>

- [<span data-ttu-id="0569c-121">Microsoft. hisse. Machinöğrenim. TrainSequentialClassifier</span><span class="sxs-lookup"><span data-stu-id="0569c-121">Microsoft.Quantum.MachineLearning.TrainSequentialClassifier</span></span>](xref:Microsoft.Quantum.MachineLearning.TrainSequentialClassifier)
- [<span data-ttu-id="0569c-122">Microsoft. hisse. Machinöğrenim. ValidateSequentialClassifier</span><span class="sxs-lookup"><span data-stu-id="0569c-122">Microsoft.Quantum.MachineLearning.ValidateSequentialClassifier</span></span>](xref:Microsoft.Quantum.MachineLearning.ValidateSequentialClassifier)