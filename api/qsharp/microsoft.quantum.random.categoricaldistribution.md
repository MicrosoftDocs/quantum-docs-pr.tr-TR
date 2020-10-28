---
uid: Microsoft.Quantum.Random.CategoricalDistribution
title: CategoricalDistribution işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: CategoricalDistribution
qsharp.summary: Returns a discrete categorical distribution, in which the probability for each of a finite list of given outcomes is explicitly specified.
ms.openlocfilehash: 756e9e95cac5554ab8f885dab7c47ac1b174c0f3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732543"
---
# <a name="categoricaldistribution-function"></a>CategoricalDistribution işlevi

Ad alanı: [Microsoft. hisse. Random](xref:Microsoft.Quantum.Random)

Leyebilir [](https://nuget.org/packages/)


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