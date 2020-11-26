---
uid: Microsoft.Quantum.MachineLearning.InferredLabels
title: Inferredlabels işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InferredLabels
qsharp.summary: Given an array of classification probabilities and a bias, returns the label inferred from each probability.
ms.openlocfilehash: 668ab89ed45c49d33ce50ff5d892f4d57246c12a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196370"
---
# <a name="inferredlabels-function"></a>Inferredlabels işlevi

Ad alanı: [Microsoft. hisse. Machinöğrenim](xref:Microsoft.Quantum.MachineLearning)

Paket: [Microsoft. hisse. Machine-öğrenim](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Sınıflandırma olasılıkların ve bir sapmanın dizisi verildiğinde, her olasılığa göre gösterilen etiketi döndürür.

```qsharp
function InferredLabels (bias : Double, probabilities : Double[]) : Int[]
```


## <a name="input"></a>Giriş

### <a name="bias--double"></a>sapma: [Double](xref:microsoft.quantum.lang-ref.double)

İki sınıf arasındaki sapma genellikle sınıflandırıcının eğitiminin sonucu.


### <a name="probabilities--double"></a>olasılıklara: [Double](xref:microsoft.quantum.lang-ref.double)[]

Genellikle sınıflandırma sıklıklarından kaynaklanan bir örnek kümesi için sınıflandırma olasılıkları dizisi.



## <a name="output--int"></a>Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)[]

Her sınıflandırma olasılığının çıkartılan etiket.