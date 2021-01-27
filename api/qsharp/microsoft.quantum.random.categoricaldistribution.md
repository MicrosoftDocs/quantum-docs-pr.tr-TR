---
uid: Microsoft.Quantum.Random.CategoricalDistribution
title: CategoricalDistribution işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: CategoricalDistribution
qsharp.summary: Returns a discrete categorical distribution, in which the probability for each of a finite list of given outcomes is explicitly specified.
ms.openlocfilehash: 754ada71078bd5446f78885ace31d92dce6bf1a4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842359"
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

## <a name="example"></a>Örnek

Aşağıdaki Q # kodu 0 ' dan %30 ' a ve 1 ' i %70 ' i içeren 1 olarak görüntüleyecektir

```qsharp
let dist = CategoricalDistribution([0.3, 0.7]);
Message($"Got sample: {dist::Sample()}");
```