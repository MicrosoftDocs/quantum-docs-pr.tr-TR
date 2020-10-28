---
uid: Microsoft.Quantum.MachineLearning.InferredLabel
title: Inferredlabel işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InferredLabel
qsharp.summary: Given a of classification probability and a bias, returns the label inferred from that probability.
ms.openlocfilehash: 1d6edec94f731fe96da797f0c3d77e6eba565149
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732370"
---
# <a name="inferredlabel-function"></a>Inferredlabel işlevi

Ad alanı: [Microsoft. hisse. Machinöğrenim](xref:Microsoft.Quantum.MachineLearning)

Leyebilir [](https://nuget.org/packages/)


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