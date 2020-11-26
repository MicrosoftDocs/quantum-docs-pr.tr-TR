---
uid: Microsoft.Quantum.MachineLearning.TrainSequentialClassifier
title: TrainSequentialClassifier işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: TrainSequentialClassifier
qsharp.summary: Given the structure of a sequential classifier, trains the classifier on a given labeled training set.
ms.openlocfilehash: d0b0587ffa93141739bcd6f39324571ffc28dacc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228670"
---
# <a name="trainsequentialclassifier-operation"></a>TrainSequentialClassifier işlemi

Ad alanı: [Microsoft. hisse. Machinöğrenim](xref:Microsoft.Quantum.MachineLearning)

Paket: [Microsoft. hisse. Machine-öğrenim](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Sıralı bir sınıflandırıcının yapısı verildiğinde, belirli bir etiketli eğitim kümesindeki sınıflandırıcının kullanımını yapın.

```qsharp
operation TrainSequentialClassifier (models : Microsoft.Quantum.MachineLearning.SequentialModel[], samples : Microsoft.Quantum.MachineLearning.LabeledSample[], options : Microsoft.Quantum.MachineLearning.TrainingOptions, trainingSchedule : Microsoft.Quantum.MachineLearning.SamplingSchedule, validationSchedule : Microsoft.Quantum.MachineLearning.SamplingSchedule) : (Microsoft.Quantum.MachineLearning.SequentialModel, Int)
```


## <a name="input"></a>Giriş

### <a name="models--sequentialmodel"></a>modeller: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)[]

Eğitim sırasında başlangıç noktaları olarak kullanılacak modeller dizisi.


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

- [Microsoft. hisse. Machinöğrenim. TrainSequentialClassifierAtModel](xref:Microsoft.Quantum.MachineLearning.TrainSequentialClassifierAtModel)
- [Microsoft. hisse. Machinöğrenim. ValidateSequentialClassifier](xref:Microsoft.Quantum.MachineLearning.ValidateSequentialClassifier)