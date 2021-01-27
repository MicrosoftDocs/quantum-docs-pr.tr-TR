---
uid: Microsoft.Quantum.MachineLearning.ValidateSequentialClassifier
title: ValidateSequentialClassifier işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ValidateSequentialClassifier
qsharp.summary: Validates a given sequential classifier against a given set of pre-labeled samples.
ms.openlocfilehash: c100c5786b18996ce13067f1c4618cf0189578f5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848973"
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