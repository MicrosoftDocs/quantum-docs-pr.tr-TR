---
uid: Microsoft.Quantum.Random.MaybeChooseElement
title: MaybeChooseElement işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: MaybeChooseElement
qsharp.summary: Given an array of data and an a distribution over its indices, attempts to choose an element at random.
ms.openlocfilehash: 12640d9dc3aad301146eff7bcbbaae33d3ccd420
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732170"
---
# <a name="maybechooseelement-operation"></a>MaybeChooseElement işlemi

Ad alanı: [Microsoft. hisse. Random](xref:Microsoft.Quantum.Random)

Leyebilir [](https://nuget.org/packages/)


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

