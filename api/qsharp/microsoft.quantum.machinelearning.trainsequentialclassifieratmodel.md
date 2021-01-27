---
uid: Microsoft.Quantum.MachineLearning.TrainSequentialClassifierAtModel
title: TrainSequentialClassifierAtModel işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: TrainSequentialClassifierAtModel
qsharp.summary: Given the structure of a sequential classifier, trains the classifier on a given labeled training set, starting from a particular model.
ms.openlocfilehash: 4164c190cb19b6d3ea74d9803a77d2b19607279b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857150"
---
# <a name="trainsequentialclassifieratmodel-operation"></a>TrainSequentialClassifierAtModel işlemi

Ad alanı: [Microsoft. hisse. Machinöğrenim](xref:Microsoft.Quantum.MachineLearning)

Paket: [Microsoft. hisse. Machine-öğrenim](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


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