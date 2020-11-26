---
uid: Microsoft.Quantum.MachineLearning.NMisclassifications
title: Nmissınıflandırmalar işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: NMisclassifications
qsharp.summary: Given a set of inferred labels and a set of correct labels, returns the number of indices at which each set of labels differ.
ms.openlocfilehash: 30d049ba54630cd2f5f350280bad7f587599f459
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196319"
---
# <a name="nmisclassifications-function"></a>Nmissınıflandırmalar işlevi

Ad alanı: [Microsoft. hisse. Machinöğrenim](xref:Microsoft.Quantum.MachineLearning)

Paket: [Microsoft. hisse. Machine-öğrenim](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Çıkarılan Etiketler kümesi ve doğru Etiketler kümesi verildiğinde, her etiket kümesinin farklı olduğu dizin sayısını döndürür.

```qsharp
function NMisclassifications (proposed : Int[], actual : Int[]) : Int
```


## <a name="input"></a>Giriş

### <a name="proposed--int"></a>Önerilen: [Int](xref:microsoft.quantum.lang-ref.int)[]




### <a name="actual--int"></a>gerçek: [Int](xref:microsoft.quantum.lang-ref.int)[]





## <a name="output--int"></a>Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)

Bu şekilde dizin sayısı `idx` `inferredLabels[idx] != actualLabels[idx]` .