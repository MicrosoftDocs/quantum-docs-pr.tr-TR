---
uid: Microsoft.Quantum.MachineLearning.DefaultTrainingOptions
title: Defaulttraıningoptions işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: DefaultTrainingOptions
qsharp.summary: Returns a default set of options for training classifiers.
ms.openlocfilehash: 474683ce5b9ec22bec686fb29d87728afe24d23a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856002"
---
# <a name="defaulttrainingoptions-function"></a>Defaulttraıningoptions işlevi

Ad alanı: [Microsoft. hisse. Machinöğrenim](xref:Microsoft.Quantum.MachineLearning)

Paket: [Microsoft. hisse. Machine-öğrenim](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Eğitim sınıflandırıcıları için varsayılan seçenek kümesini döndürür.

```qsharp
function DefaultTrainingOptions () : Microsoft.Quantum.MachineLearning.TrainingOptions
```


## <a name="output--trainingoptions"></a>Çıkış: [Traıningoptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)

Sınıflandırıcılardaki eğitim sırasında kullanılmak üzere makul bir varsayılan eğitim seçenekleri kümesi.

## <a name="example"></a>Örnek

Varsayılan seçenekleri kullanmak için, ancak ek ölçümler ile `w/` işlecini kullanın:

```qsharp
let options = DefaultTrainingOptions()
    w/ NMeasurements <- 1000000;
```