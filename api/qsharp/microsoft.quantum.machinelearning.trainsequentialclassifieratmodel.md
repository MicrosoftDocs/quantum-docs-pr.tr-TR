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
# <a name="trainsequentialclassifieratmodel-operation"></a>TrainSequentialClassifierAtModel işlemi

Ad alanı: [Microsoft. hisse. Machinöğrenim](xref:Microsoft.Quantum.MachineLearning)

Leyebilir [](https://nuget.org/packages/)


Sıralı bir sınıflandırıcının yapısı verildiğinde, belirli bir modelden başlayarak, belirli bir etiketli eğitim kümesindeki sınıflandırıcının kullanımını yapın.

```qsharp
operation TrainSequentialClassifierAtModel (model : Microsoft.Quantum.MachineLearning.SequentialModel, samples : Microsoft.Quantum.MachineLearning.LabeledSample[], options : Microsoft.Quantum.MachineLearning.TrainingOptions, trainingSchedule : Microsoft.Quantum.MachineLearning.SamplingSchedule, validationSchedule : Microsoft.Quantum.MachineLearning.SamplingSchedule) : (Microsoft.Quantum.MachineLearning.SequentialModel, Int)
```


## <a name="input"></a>Giriş

### <a name="model--sequentialmodel"></a>Model: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)

Eğitim için bir başlangıç noktası olarak kullanılacak sıralı model.


### <a name="samples--labeledsample"></a>örnekler: [Labeledsample](xref:Microsoft.Quantum.MachineLearning.LabeledSample)[]

Eğitim yapmak için kullanılacak bir etiketli eğitim verileri kümesi.


### <a name="options--trainingoptions"></a>Seçenekler: [Traıningoptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)

Eğitim sırasında kullanılacak yapılandırma; @"microsoft.quantum.machinelearning.trainingoptions" @"microsoft.quantum.machinelearning.defaulttrainingoptions" daha fazla ayrıntı için bkz. ve.


### <a name="trainingschedule--samplingschedule"></a>Traıningschedule: [Samplingschedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)

Eğitim adımları sırasında eğitim verilerinden örnek seçerken kullanılacak örnekleme zamanlaması.


### <a name="validationschedule--samplingschedule"></a>validationSchedule: [Samplingschedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)

Eğitim verilerinden örnek seçerken kullanılacak örnekleme zamanlaması, en iyi sınıflandırıcı puanına neden olan başlangıç noktasını seçerken kullanılır.



## <a name="output--sequentialmodelint"></a>Çıkış: ([SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel),[Int](xref:microsoft.quantum.lang-ref.int))

- Verili sınıflandırıcının parametreleştirmesi ve iki sınıf arasındaki bir farkı, belirtilen başlangıç noktalarından her birinin en iyi sonucuna karşılık gelen bir şekilde bir araya getirme.
- En iyi sınıflandırıcı modelinde gözlemlendi isabetsizlik sayısı.

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Machinöğrenim. TrainSequentialClassifier](xref:Microsoft.Quantum.MachineLearning.TrainSequentialClassifier)
- [Microsoft. hisse. Machinöğrenim. ValidateSequentialClassifier](xref:Microsoft.Quantum.MachineLearning.ValidateSequentialClassifier)