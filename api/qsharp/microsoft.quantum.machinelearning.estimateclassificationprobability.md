---
uid: Microsoft.Quantum.MachineLearning.EstimateClassificationProbability
title: EstimateClassificationProbability işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: EstimateClassificationProbability
qsharp.summary: Given a sample and a sequential classifier, estimates the classification probability for that sample by repeatedly measuring the output of the classifier on the given sample.
ms.openlocfilehash: 79e40bc4bc0954dc6742307122609950bf22ec71
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725958"
---
# <a name="estimateclassificationprobability-operation"></a>EstimateClassificationProbability işlemi

Ad alanı: [Microsoft. hisse. Machinöğrenim](xref:Microsoft.Quantum.MachineLearning)

Leyebilir [](https://nuget.org/packages/)


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