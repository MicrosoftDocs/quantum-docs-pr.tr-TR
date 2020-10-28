---
uid: Microsoft.Quantum.MachineLearning.EstimateClassificationProbabilities
title: EstimateClassificationProbabilities işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: EstimateClassificationProbabilities
qsharp.summary: Given a set of samples and a sequential classifier, estimates the classification probability for those samples by repeatedly measuring the output of the classifier on each sample.
ms.openlocfilehash: 2b7845d39256f718cc3e415207b8a47b24620bdb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725964"
---
# <a name="estimateclassificationprobabilities-operation"></a>EstimateClassificationProbabilities işlemi

Ad alanı: [Microsoft. hisse. Machinöğrenim](xref:Microsoft.Quantum.MachineLearning)

Leyebilir [](https://nuget.org/packages/)


Bir dizi örnek ve sıralı sınıflandırıcı verildiğinde, her örnekteki sınıflandırıcının çıkışını tekrar tekrar ölçerek, bu örneklerin sınıflandırma olasılığını tahmin eder.

```qsharp
operation EstimateClassificationProbabilities (tolerance : Double, model : Microsoft.Quantum.MachineLearning.SequentialModel, samples : Double[][], nMeasurements : Int) : Double[]
```


## <a name="input"></a>Giriş

### <a name="tolerance--double"></a>Tolerans: [Double](xref:microsoft.quantum.lang-ref.double)

Örneği bir durum hazırlama işlemine kodlamaya izin veren tolerans.


### <a name="model--sequentialmodel"></a>Model: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)

Verilen örnekler için sınıflandırma olasılıkların tahmin edilmesi için kullanılacak sıralı model.


### <a name="samples--double"></a>örnekler: [Double](xref:microsoft.quantum.lang-ref.double)[] []

Sınıflandırılacak her örnek için bir özellik vektörü dizisi.


### <a name="nmeasurements--int"></a>Nölçümler: [Int](xref:microsoft.quantum.lang-ref.int)

Sınıflandırma olasılığını tahmin etmek için kullanılacak ölçüm sayısı.



## <a name="output--double"></a>Çıkış: [Double](xref:microsoft.quantum.lang-ref.double)[]

Verilen her örnek için sınıflandırma olasılığının tahminlerinin bir dizisi.