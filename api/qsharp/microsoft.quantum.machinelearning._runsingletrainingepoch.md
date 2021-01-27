---
uid: Microsoft.Quantum.MachineLearning._RunSingleTrainingEpoch
title: _RunSingleTrainingEpoch işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: _RunSingleTrainingEpoch
qsharp.summary: Perform one epoch of sequential classifier training on a subset of data samples.
ms.openlocfilehash: a8ae35fdd6c4e219444e7d6f7587ea31603b9999
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856194"
---
# <a name="_runsingletrainingepoch-operation"></a>_RunSingleTrainingEpoch işlemi

Ad alanı: [Microsoft. hisse. Machinöğrenim](xref:Microsoft.Quantum.MachineLearning)

Paket: [Microsoft. hisse. Machine-öğrenim](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Veri örneklerinin bir alt kümesi üzerinde sıralı sınıflandırıcı eğitiminin tek bir dönemini gerçekleştirin.

```qsharp
operation _RunSingleTrainingEpoch (encodedSamples : (Microsoft.Quantum.MachineLearning.LabeledSample, Microsoft.Quantum.MachineLearning.StateGenerator)[], schedule : Microsoft.Quantum.MachineLearning.SamplingSchedule, periodScore : Int, options : Microsoft.Quantum.MachineLearning.TrainingOptions, model : Microsoft.Quantum.MachineLearning.SequentialModel, nPreviousBestMisses : Int) : (Int, Microsoft.Quantum.MachineLearning.SequentialModel)
```


## <a name="input"></a>Giriş

### <a name="encodedsamples--labeledsamplestategenerator"></a>encodedSamples: ([Labeledsample](xref:Microsoft.Quantum.MachineLearning.LabeledSample),[stategenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)) []




### <a name="schedule--samplingschedule"></a>zamanlama: [Samplingschedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)




### <a name="periodscore--int"></a>periodScore: [Int](xref:microsoft.quantum.lang-ref.int)

Puanlama noktaları arasında gerçekleştirilecek gradyan adımları sayısı.
En iyi doğruluk için 1 olarak ayarlayın.


### <a name="options--trainingoptions"></a>Seçenekler: [Traıningoptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)

Eğitiminde kullanılacak seçenekler.


### <a name="model--sequentialmodel"></a>Model: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)

Eğitilecek sıralı model.


### <a name="npreviousbestmisses--int"></a>Npreviousen iyi Isabetsizlik: [Int](xref:microsoft.quantum.lang-ref.int)

Önceki dönemlerinde gözlemlenen hatalı sınıflandırmaların en iyi sayısı.



## <a name="output--intsequentialmodel"></a>Çıkış: ([Int](xref:microsoft.quantum.lang-ref.int),[SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel))

- Bu dönem ile gözlemlendi en küçük yanlış sınıflandırma sayısı.
- Yeni en iyi sıralı model bulundu.