---
uid: Microsoft.Quantum.MachineLearning.EstimateGradient
title: EstimateGradient işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: EstimateGradient
qsharp.summary: Estimates the training gradient for a sequential classifier at a particular model and for a given encoded input.
ms.openlocfilehash: 38edcb67e7dcc5d2e971fb507a792937774a702c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844393"
---
# <a name="estimategradient-operation"></a>EstimateGradient işlemi

Ad alanı: [Microsoft. hisse. Machinöğrenim](xref:Microsoft.Quantum.MachineLearning)

Paket: [Microsoft. hisse. Machine-öğrenim](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Belirli bir modelde ve belirli bir kodlanmış giriş için sıralı bir sınıflandırıcı için eğitim degradesini tahmin eder.

```qsharp
operation EstimateGradient (model : Microsoft.Quantum.MachineLearning.SequentialModel, encodedInput : Microsoft.Quantum.MachineLearning.StateGenerator, nMeasurements : Int) : Double[]
```


## <a name="input"></a>Giriş

### <a name="model--sequentialmodel"></a>Model: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)

Gradyanı tahmini olan sıralı model.


### <a name="encodedinput--stategenerator"></a>Encodedınput: [Stategenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)

Bir durum hazırlama işleminde kodlanan sıralı sınıflandırıcının girişi.


### <a name="nmeasurements--int"></a>Nölçümler: [Int](xref:microsoft.quantum.lang-ref.int)

Degradeyi tahmin etmek için kullanılacak ölçüm sayısı.



## <a name="output--double"></a>Çıkış: [Double](xref:microsoft.quantum.lang-ref.double)[]

Verilen giriş ve model parametrelerinde eğitim gradyanının tahmini.

## <a name="remarks"></a>Açıklamalar

Bu işlem, degradeyi tahmin etmek için bir Hadamard testi ve parametre kaydırma tekniğini kullanır.