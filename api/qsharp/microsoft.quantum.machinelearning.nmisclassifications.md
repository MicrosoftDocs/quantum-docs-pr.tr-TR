---
uid: Microsoft.Quantum.MachineLearning.NMisclassifications
title: Nmissınıflandırmalar işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: NMisclassifications
qsharp.summary: Given a set of inferred labels and a set of correct labels, returns the number of indices at which each set of labels differ.
ms.openlocfilehash: 9e356d68233519978e007e5a2999ca1be8cb7f83
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725945"
---
# <a name="nmisclassifications-function"></a>Nmissınıflandırmalar işlevi

Ad alanı: [Microsoft. hisse. Machinöğrenim](xref:Microsoft.Quantum.MachineLearning)

Leyebilir [](https://nuget.org/packages/)


Çıkarılan Etiketler kümesi ve doğru Etiketler kümesi verildiğinde, her etiket kümesinin farklı olduğu dizin sayısını döndürür.

```qsharp
function NMisclassifications (proposed : Int[], actual : Int[]) : Int
```


## <a name="input"></a>Giriş

### <a name="proposed--int"></a>Önerilen: [Int](xref:microsoft.quantum.lang-ref.int)[]




### <a name="actual--int"></a>gerçek: [Int](xref:microsoft.quantum.lang-ref.int)[]





## <a name="output--int"></a>Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)

Bu şekilde dizin sayısı `idx` `inferredLabels[idx] != actualLabels[idx]` .