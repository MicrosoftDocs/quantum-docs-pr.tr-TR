---
uid: Microsoft.Quantum.MachineLearning.ValidateSequentialClassifier
title: ValidateSequentialClassifier işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ValidateSequentialClassifier
qsharp.summary: Validates a given sequential classifier against a given set of pre-labeled samples.
ms.openlocfilehash: 5174085edbfd846e8f6649f33e325fd1979ae6a2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196115"
---
# <a name="validatesequentialclassifier-operation"></a><span data-ttu-id="cdec5-102">ValidateSequentialClassifier işlemi</span><span class="sxs-lookup"><span data-stu-id="cdec5-102">ValidateSequentialClassifier operation</span></span>

<span data-ttu-id="cdec5-103">Ad alanı: [Microsoft. hisse. Machinöğrenim](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="cdec5-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="cdec5-104">Paket: [Microsoft. hisse. Machine-öğrenim](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="cdec5-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="cdec5-105">Belirli bir sıralı sınıflandırıcının belirtilen bir önceden etiketlenmiş örnek kümesine karşı doğrular.</span><span class="sxs-lookup"><span data-stu-id="cdec5-105">Validates a given sequential classifier against a given set of pre-labeled samples.</span></span>

```qsharp
operation ValidateSequentialClassifier (model : Microsoft.Quantum.MachineLearning.SequentialModel, samples : Microsoft.Quantum.MachineLearning.LabeledSample[], tolerance : Double, nMeasurements : Int, validationSchedule : Microsoft.Quantum.MachineLearning.SamplingSchedule) : Microsoft.Quantum.MachineLearning.ValidationResults
```


## <a name="input"></a><span data-ttu-id="cdec5-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="cdec5-106">Input</span></span>

### <a name="model--sequentialmodel"></a><span data-ttu-id="cdec5-107">Model: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="cdec5-107">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>

<span data-ttu-id="cdec5-108">Doğrulanacak sıralı model.</span><span class="sxs-lookup"><span data-stu-id="cdec5-108">The sequential model to be validated.</span></span>


### <a name="samples--labeledsample"></a><span data-ttu-id="cdec5-109">örnekler: [Labeledsample](xref:Microsoft.Quantum.MachineLearning.LabeledSample)[]</span><span class="sxs-lookup"><span data-stu-id="cdec5-109">samples : [LabeledSample](xref:Microsoft.Quantum.MachineLearning.LabeledSample)[]</span></span>

<span data-ttu-id="cdec5-110">Verilen modeli doğrulamak için kullanılacak örnekler.</span><span class="sxs-lookup"><span data-stu-id="cdec5-110">The samples to be used to validate the given model.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="cdec5-111">Tolerans: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="cdec5-111">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="cdec5-112">Her örneği sıralı sınıflandırıcının girişi olarak kodlamada kullanılacak yaklaşık tolerans.</span><span class="sxs-lookup"><span data-stu-id="cdec5-112">The approximation tolerance to use in encoding each sample as an input to the sequential classifier.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="cdec5-113">Nölçümler: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="cdec5-113">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="cdec5-114">Her örneği sınıflandırırken kullanılacak ölçüm sayısı.</span><span class="sxs-lookup"><span data-stu-id="cdec5-114">The number of measurements to use in classifying each sample.</span></span>


### <a name="validationschedule--samplingschedule"></a><span data-ttu-id="cdec5-115">validationSchedule: [Samplingschedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span><span class="sxs-lookup"><span data-stu-id="cdec5-115">validationSchedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span></span>

<span data-ttu-id="cdec5-116">Örneklerin doğrulama kümesinden çizilmesi gereken zamanlama.</span><span class="sxs-lookup"><span data-stu-id="cdec5-116">The schedule by which samples should be drawn from the validation set.</span></span>



## <a name="output--validationresults"></a><span data-ttu-id="cdec5-117">Çıkış: [ValidationResults](xref:Microsoft.Quantum.MachineLearning.ValidationResults)</span><span class="sxs-lookup"><span data-stu-id="cdec5-117">Output : [ValidationResults](xref:Microsoft.Quantum.MachineLearning.ValidationResults)</span></span>

<span data-ttu-id="cdec5-118">Verilen doğrulamanın sonuçları.</span><span class="sxs-lookup"><span data-stu-id="cdec5-118">The results of the given validation.</span></span>