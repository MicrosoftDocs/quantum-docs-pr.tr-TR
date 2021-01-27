---
uid: Microsoft.Quantum.MachineLearning.Misclassifications
title: Hatalı sınıflandırmalar işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: Misclassifications
qsharp.summary: Given a set of inferred labels and a set of correct labels, returns indices for where each set of labels differs.
ms.openlocfilehash: 3913395fbd9f7cf96732c17ca0c726289e5087ed
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853918"
---
# <a name="misclassifications-function"></a>Hatalı sınıflandırmalar işlevi

Ad alanı: [Microsoft. hisse. Machinöğrenim](xref:Microsoft.Quantum.MachineLearning)

Paket: [Microsoft. hisse. Machine-öğrenim](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


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

## <a name="example"></a>Örnek

```qsharp
let misclassifications = Misclassifications([0, 1, 0, 0], [0, 1, 1, 0]);
Message($"{misclassifications}"); // Will print [2].
```