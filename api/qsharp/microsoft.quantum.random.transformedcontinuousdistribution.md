---
uid: Microsoft.Quantum.Random.TransformedContinuousDistribution
title: TransformedContinuousDistribution işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: TransformedContinuousDistribution
qsharp.summary: Given a continuous distribution, returns a new distribution that transforms the original by a given function.
ms.openlocfilehash: 6a6e0c26bd650fd4c05208197ff23f951d1c3b5c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726461"
---
# <a name="transformedcontinuousdistribution-function"></a>TransformedContinuousDistribution işlevi

Ad alanı: [Microsoft. hisse. Random](xref:Microsoft.Quantum.Random)

Leyebilir [](https://nuget.org/packages/)


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