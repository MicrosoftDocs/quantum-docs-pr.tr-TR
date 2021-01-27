---
uid: Microsoft.Quantum.MachineLearning.NMisclassifications
title: Nmissınıflandırmalar işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: NMisclassifications
qsharp.summary: Given a set of inferred labels and a set of correct labels, returns the number of indices at which each set of labels differ.
ms.openlocfilehash: adc7042d6108c7ec72d13340633824d3eaf5e18e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853911"
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

## <a name="example"></a>Örnek

```qsharp
let nMisclassifications = NMisclassifications([1, 1, 0, 0], [0, 1, 1, 0]);
Message($"{nMisclassifications}"); // Will print 2.
```