---
uid: Microsoft.Quantum.MachineLearning.InferredLabels
title: Inferredlabels işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InferredLabels
qsharp.summary: Given an array of classification probabilities and a bias, returns the label inferred from each probability.
ms.openlocfilehash: 874d1a2f7cc6d67567e0d2baa70b0d26b639a029
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732351"
---
# <a name="inferredlabels-function"></a>Inferredlabels işlevi

Ad alanı: [Microsoft. hisse. Machinöğrenim](xref:Microsoft.Quantum.MachineLearning)

Leyebilir [](https://nuget.org/packages/)


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