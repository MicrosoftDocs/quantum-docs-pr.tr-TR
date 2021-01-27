---
uid: Microsoft.Quantum.MachineLearning.InferredLabel
title: Inferredlabel işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InferredLabel
qsharp.summary: Given a of classification probability and a bias, returns the label inferred from that probability.
ms.openlocfilehash: 46b24c283a01e6ac1c959ee4a6899591ee708ff7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848415"
---
# <a name="inferredlabel-function"></a>Inferredlabel işlevi

Ad alanı: [Microsoft. hisse. Machinöğrenim](xref:Microsoft.Quantum.MachineLearning)

Paket: [Microsoft. hisse. Machine-öğrenim](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Sınıflandırma olasılığı ve bir sapma verildiğinde, bu olasılığa göre çıkarılan etiketi döndürür.

```qsharp
function InferredLabel (bias : Double, probability : Double) : Int
```


## <a name="input"></a>Giriş

### <a name="bias--double"></a>sapma: [Double](xref:microsoft.quantum.lang-ref.double)

İki sınıf arasındaki sapma genellikle sınıflandırıcının eğitiminin sonucu.


### <a name="probability--double"></a>olasılık: [Double](xref:microsoft.quantum.lang-ref.double)

Belirli bir örnek için bir sınıflandırma olasılıklarını, genellikle sınıflandırma sıklığını tahmin etmeye yol açar.



## <a name="output--int"></a>Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)

Verilen sınıflandırma olasıslarından çıkarılan etiket.