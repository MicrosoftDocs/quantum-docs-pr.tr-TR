---
uid: Microsoft.Quantum.MachineLearning.Misclassifications
title: Hatalı sınıflandırmalar işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: Misclassifications
qsharp.summary: Given a set of inferred labels and a set of correct labels, returns indices for where each set of labels differs.
ms.openlocfilehash: 500c2910f7c5616c88ff6c70ab3cc16680e199fb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732978"
---
# <a name="misclassifications-function"></a>Hatalı sınıflandırmalar işlevi

Ad alanı: [Microsoft. hisse. Machinöğrenim](xref:Microsoft.Quantum.MachineLearning)

Leyebilir [](https://nuget.org/packages/)


Çıkarılan Etiketler kümesi ve doğru Etiketler kümesi verildiğinde, her bir etiket kümesinin farklı olduğu dizinler döndürür.

```qsharp
function Misclassifications (inferredLabels : Int[], actualLabels : Int[]) : Int[]
```


## <a name="input"></a>Giriş

### <a name="inferredlabels--int"></a>ınferredlabels: [Int](xref:microsoft.quantum.lang-ref.int)[]

Belirli bir eğitim veya doğrulama kümesi için gösterilen Etiketler.


### <a name="actuallabels--int"></a>actualLabels: [Int](xref:microsoft.quantum.lang-ref.int)[]

Belirli bir eğitim veya doğrulama kümesi için doğru Etiketler.



## <a name="output--int"></a>Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)[]

Bu tür bir dizin dizisi `idx` `inferredLabels[idx] != actualLabels[idx]` .