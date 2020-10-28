---
uid: Microsoft.Quantum.MachineLearning.ValidateSequentialClassifier
title: ValidateSequentialClassifier işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ValidateSequentialClassifier
qsharp.summary: Validates a given sequential classifier against a given set of pre-labeled samples.
ms.openlocfilehash: 802f1045ea4086bd371d68018a481182cb75b209
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731066"
---
# <a name="validatesequentialclassifier-operation"></a><span data-ttu-id="585f2-102">ValidateSequentialClassifier işlemi</span><span class="sxs-lookup"><span data-stu-id="585f2-102">ValidateSequentialClassifier operation</span></span>

<span data-ttu-id="585f2-103">Ad alanı: [Microsoft. hisse. Machinöğrenim](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="585f2-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="585f2-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="585f2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="585f2-105">Belirli bir sıralı sınıflandırıcının belirtilen bir önceden etiketlenmiş örnek kümesine karşı doğrular.</span><span class="sxs-lookup"><span data-stu-id="585f2-105">Validates a given sequential classifier against a given set of pre-labeled samples.</span></span>

```qsharp
operation ValidateSequentialClassifier (model : Microsoft.Quantum.MachineLearning.SequentialModel, samples : Microsoft.Quantum.MachineLearning.LabeledSample[], tolerance : Double, nMeasurements : Int, validationSchedule : Microsoft.Quantum.MachineLearning.SamplingSchedule) : Microsoft.Quantum.MachineLearning.ValidationResults
```


## <a name="input"></a><span data-ttu-id="585f2-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="585f2-106">Input</span></span>

### <a name="model--sequentialmodel"></a><span data-ttu-id="585f2-107">Model: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="585f2-107">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>

<span data-ttu-id="585f2-108">Doğrulanacak sıralı model.</span><span class="sxs-lookup"><span data-stu-id="585f2-108">The sequential model to be validated.</span></span>


### <a name="samples--labeledsample"></a><span data-ttu-id="585f2-109">örnekler: [Labeledsample](xref:Microsoft.Quantum.MachineLearning.LabeledSample)[]</span><span class="sxs-lookup"><span data-stu-id="585f2-109">samples : [LabeledSample](xref:Microsoft.Quantum.MachineLearning.LabeledSample)[]</span></span>

<span data-ttu-id="585f2-110">Verilen modeli doğrulamak için kullanılacak örnekler.</span><span class="sxs-lookup"><span data-stu-id="585f2-110">The samples to be used to validate the given model.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="585f2-111">Tolerans: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="585f2-111">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="585f2-112">Her örneği sıralı sınıflandırıcının girişi olarak kodlamada kullanılacak yaklaşık tolerans.</span><span class="sxs-lookup"><span data-stu-id="585f2-112">The approximation tolerance to use in encoding each sample as an input to the sequential classifier.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="585f2-113">Nölçümler: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="585f2-113">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="585f2-114">Her örneği sınıflandırırken kullanılacak ölçüm sayısı.</span><span class="sxs-lookup"><span data-stu-id="585f2-114">The number of measurements to use in classifying each sample.</span></span>


### <a name="validationschedule--samplingschedule"></a><span data-ttu-id="585f2-115">validationSchedule: [Samplingschedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span><span class="sxs-lookup"><span data-stu-id="585f2-115">validationSchedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span></span>

<span data-ttu-id="585f2-116">Örneklerin doğrulama kümesinden çizilmesi gereken zamanlama.</span><span class="sxs-lookup"><span data-stu-id="585f2-116">The schedule by which samples should be drawn from the validation set.</span></span>



## <a name="output--validationresults"></a><span data-ttu-id="585f2-117">Çıkış: [ValidationResults](xref:Microsoft.Quantum.MachineLearning.ValidationResults)</span><span class="sxs-lookup"><span data-stu-id="585f2-117">Output : [ValidationResults](xref:Microsoft.Quantum.MachineLearning.ValidationResults)</span></span>

<span data-ttu-id="585f2-118">Verilen doğrulamanın sonuçları.</span><span class="sxs-lookup"><span data-stu-id="585f2-118">The results of the given validation.</span></span>