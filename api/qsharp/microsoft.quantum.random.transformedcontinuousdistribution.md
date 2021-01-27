---
uid: Microsoft.Quantum.Random.TransformedContinuousDistribution
title: TransformedContinuousDistribution işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: TransformedContinuousDistribution
qsharp.summary: Given a continuous distribution, returns a new distribution that transforms the original by a given function.
ms.openlocfilehash: 353442a4245a9e20bb1e4c46d2e8a84d4c9534b0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857766"
---
# <a name="transformedcontinuousdistribution-function"></a>TransformedContinuousDistribution işlevi

Ad alanı: [Microsoft. hisse. Random](xref:Microsoft.Quantum.Random)

Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Sürekli dağıtım verildiğinde, belirli bir işlev tarafından orijinali dönüştüren yeni bir dağıtım döndürür.

```qsharp
function TransformedContinuousDistribution (transform : (Double -> Double), distribution : Microsoft.Quantum.Random.ContinuousDistribution) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a>Giriş

### <a name="transform--double---double"></a>Dönüştür: [çift](xref:microsoft.quantum.lang-ref.double) -> [çift](xref:microsoft.quantum.lang-ref.double)

Özgün dağıtımın varisayısını dönüştürülmüş dağıtıma dönüştüren bir işlev.


### <a name="distribution--continuousdistribution"></a>Dağıtım: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)

Dönüştürülecek orijinal dağıtım.



## <a name="output--continuousdistribution"></a>Çıkış: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)

Tarafından verilen dönüşümde ile ilişkili yeni bir dağıtım `distribution` `transform` .

## <a name="example"></a>Örnek

Aşağıdaki iki dağıtım aynıdır:

```qsharp
let dist1 = ContinuousUniformDistribution(1.0, 2.0);
let dist2 = TransformedContinuousDistribution(
    PlusD(1.0, _),
    ContinuousUniformDistribution(0.0, 1.0)
);
```