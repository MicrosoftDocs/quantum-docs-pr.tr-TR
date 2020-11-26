---
uid: Microsoft.Quantum.Random.MaybeChooseElement
title: MaybeChooseElement işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: MaybeChooseElement
qsharp.summary: Given an array of data and an a distribution over its indices, attempts to choose an element at random.
ms.openlocfilehash: 1a69c8d5a6ae022ceda9269e17434b740809b107
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192868"
---
# <a name="maybechooseelement-operation"></a>MaybeChooseElement işlemi

Ad alanı: [Microsoft. hisse. Random](xref:Microsoft.Quantum.Random)

Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Veri dizisi ve dizinleri üzerinde bir dağıtım verildiğinde, rastgele bir öğe seçme girişiminde bulunur.

```qsharp
operation MaybeChooseElement<'T> (data : 'T[], indexDistribution : Microsoft.Quantum.Random.DiscreteDistribution) : (Bool, 'T)
```


## <a name="input"></a>Giriş

### <a name="data--t"></a>veri: 'T []

Bir öğenin seçilmesi gereken dizi.


### <a name="indexdistribution--discretedistribution"></a>ındexdistribution: [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)

Dizinleri üzerinden bir dağıtım `data` .



## <a name="output--boolt"></a>Çıkış: ([bool](xref:microsoft.quantum.lang-ref.bool), 't)



## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen

