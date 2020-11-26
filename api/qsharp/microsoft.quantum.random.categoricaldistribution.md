---
uid: Microsoft.Quantum.Random.CategoricalDistribution
title: CategoricalDistribution işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: CategoricalDistribution
qsharp.summary: Returns a discrete categorical distribution, in which the probability for each of a finite list of given outcomes is explicitly specified.
ms.openlocfilehash: 2e3d9b17939d5a9a5bc5e7d89a843e0ff5a848ba
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210259"
---
# <a name="categoricaldistribution-function"></a>CategoricalDistribution işlevi

Ad alanı: [Microsoft. hisse. Random](xref:Microsoft.Quantum.Random)

Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Belirli bir sonuçların sınırlı listesinin her biri için olasılık açıkça belirtildiğinde ayrık bir kategorik dağıtım döndürür.

```qsharp
function CategoricalDistribution (probs : Double[]) : Microsoft.Quantum.Random.DiscreteDistribution
```


## <a name="input"></a>Giriş

### <a name="probs--double"></a>probs: [Double](xref:microsoft.quantum.lang-ref.double)[]

Kategorik dağılıklarından her bir sonuç için olasılıkların.
Bu olasılıkların normalleştirilmeyebilir, ancak tümünün negatif olmaması gerekir.



## <a name="output--discretedistribution"></a>Çıkış: [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)

`i`Olasılığı olan dizin `probs[i] / sum` ,, `sum` `probs` tarafından verilen `Fold(PlusD, 0.0, probs)` .