---
uid: Microsoft.Quantum.MachineLearning._RunSingleTrainingStep
title: _RunSingleTrainingStep işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: _RunSingleTrainingStep
qsharp.summary: attempts a single parameter update in the direction of mini batch gradient
ms.openlocfilehash: 3a3fa1ae34bbcc046f3b3cef4c13c0a84c7cc2b4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853953"
---
# <a name="_runsingletrainingstep-operation"></a>_RunSingleTrainingStep işlemi

Ad alanı: [Microsoft. hisse. Machinöğrenim](xref:Microsoft.Quantum.MachineLearning)

Paket: [Microsoft. hisse. Machine-öğrenim](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Mini toplu işlem gradyanının yönündeki tek bir parametre güncelleştirmesine çalışır

```qsharp
operation _RunSingleTrainingStep (miniBatch : (Microsoft.Quantum.MachineLearning.LabeledSample, Microsoft.Quantum.MachineLearning.StateGenerator)[], options : Microsoft.Quantum.MachineLearning.TrainingOptions, model : Microsoft.Quantum.MachineLearning.SequentialModel) : (Double, Microsoft.Quantum.MachineLearning.SequentialModel)
```


## <a name="input"></a>Giriş

### <a name="minibatch--labeledsamplestategenerator"></a>Mini Batch: ([Labeledsample](xref:Microsoft.Quantum.MachineLearning.LabeledSample),[stategenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)) []

Mini toplu işte etiketlenmiş örneklerin kapsayıcısı


### <a name="options--trainingoptions"></a>Seçenekler: [Traıningoptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)




### <a name="model--sequentialmodel"></a>Model: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)





## <a name="output--doublesequentialmodel"></a>Çıkış: ([Double](xref:microsoft.quantum.lang-ref.double),[SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel))

(yardımcı program, (yeni) parametreler) çifti