---
uid: Microsoft.Quantum.Arrays.RectangularArrayFact
title: Rectangulararrayolgu işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: RectangularArrayFact
qsharp.summary: Represents a condition that a 2-dimensional array has a rectangular shape
ms.openlocfilehash: f0d3f4d6bfa9e86f1c7a91792c09e16fe86433a0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730050"
---
# <a name="rectangulararrayfact-function"></a>Rectangulararrayolgu işlevi

Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)

Leyebilir [](https://nuget.org/packages/)


2 boyutlu dizinin dikdörtgen şekline sahip olduğu koşulu temsil eder

```qsharp
function RectangularArrayFact<'T> (array : 'T[][], message : String) : Unit
```


## <a name="description"></a>Açıklama

Bu işlev, bir dizideki her satırın aynı uzunlukta olduğunu onaylar.

## <a name="input"></a>Giriş

### <a name="array--t"></a>dizi: 'T [] []

2 boyutlu bir öğe dizisi


### <a name="message--string"></a>ileti: [dize](xref:microsoft.quantum.lang-ref.string)

Dizi dikdörtgen olmayan bir dizi değilse yazdırılacak bir ileti



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen

Her öğesinin türü `array` .

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Arrays. Squarearrayolgusu](xref:Microsoft.Quantum.Arrays.SquareArrayFact)