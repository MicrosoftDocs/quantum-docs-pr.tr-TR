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
# <a name="validatesequentialclassifier-operation"></a>ValidateSequentialClassifier işlemi

Ad alanı: [Microsoft. hisse. Machinöğrenim](xref:Microsoft.Quantum.MachineLearning)

Paket: [Microsoft. hisse. Machine-öğrenim](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Belirli bir sıralı sınıflandırıcının belirtilen bir önceden etiketlenmiş örnek kümesine karşı doğrular.

```qsharp
operation ValidateSequentialClassifier (model : Microsoft.Quantum.MachineLearning.SequentialModel, samples : Microsoft.Quantum.MachineLearning.LabeledSample[], tolerance : Double, nMeasurements : Int, validationSchedule : Microsoft.Quantum.MachineLearning.SamplingSchedule) : Microsoft.Quantum.MachineLearning.ValidationResults
```


## <a name="input"></a>Giriş

### <a name="model--sequentialmodel"></a>Model: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)

Doğrulanacak sıralı model.


### <a name="samples--labeledsample"></a>örnekler: [Labeledsample](xref:Microsoft.Quantum.MachineLearning.LabeledSample)[]

Verilen modeli doğrulamak için kullanılacak örnekler.


### <a name="tolerance--double"></a>Tolerans: [Double](xref:microsoft.quantum.lang-ref.double)

Her örneği sıralı sınıflandırıcının girişi olarak kodlamada kullanılacak yaklaşık tolerans.


### <a name="nmeasurements--int"></a>Nölçümler: [Int](xref:microsoft.quantum.lang-ref.int)

Her örneği sınıflandırırken kullanılacak ölçüm sayısı.


### <a name="validationschedule--samplingschedule"></a>validationSchedule: [Samplingschedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)

Örneklerin doğrulama kümesinden çizilmesi gereken zamanlama.



## <a name="output--validationresults"></a>Çıkış: [ValidationResults](xref:Microsoft.Quantum.MachineLearning.ValidationResults)

Verilen doğrulamanın sonuçları.