---
uid: Microsoft.Quantum.MachineLearning.EstimateClassificationProbability
title: EstimateClassificationProbability işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: EstimateClassificationProbability
qsharp.summary: Given a sample and a sequential classifier, estimates the classification probability for that sample by repeatedly measuring the output of the classifier on the given sample.
ms.openlocfilehash: c2b74bc55ad9005a8f52d05796e856f4f2fb62ba
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853948"
---
# <a name="estimateclassificationprobability-operation"></a>EstimateClassificationProbability işlemi

Ad alanı: [Microsoft. hisse. Machinöğrenim](xref:Microsoft.Quantum.MachineLearning)

Paket: [Microsoft. hisse. Machine-öğrenim](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Örnek ve sıralı bir sınıflandırıcı verildiğinde, verilen örnekteki sınıflandırıcının çıkışını sürekli olarak ölçerek söz konusu örnek için sınıflandırma olasılığını tahmin eder.

```qsharp
operation EstimateClassificationProbability (tolerance : Double, model : Microsoft.Quantum.MachineLearning.SequentialModel, sample : Double[], nMeasurements : Int) : Double
```


## <a name="input"></a>Giriş

### <a name="tolerance--double"></a>Tolerans: [Double](xref:microsoft.quantum.lang-ref.double)

Örneği bir durum hazırlama işlemine kodlamaya izin veren tolerans.


### <a name="model--sequentialmodel"></a>Model: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)

Verilen örnek için sınıflandırma olasılığını tahmin etmek üzere kullanılacak sıralı model.


### <a name="sample--double"></a>Örnek: [Double](xref:microsoft.quantum.lang-ref.double)[]

Sınıflandırılacak örnek için özellik vektörü.


### <a name="nmeasurements--int"></a>Nölçümler: [Int](xref:microsoft.quantum.lang-ref.int)

Sınıflandırma olasılığını tahmin etmek için kullanılacak ölçüm sayısı.



## <a name="output--double"></a>Çıkış: [Double](xref:microsoft.quantum.lang-ref.double)

Belirtilen örnek için sınıflandırma olasılığının tahmini.