---
uid: Microsoft.Quantum.Arrays.RectangularArrayFact
title: Rectangulararrayolgu işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: RectangularArrayFact
qsharp.summary: Represents a condition that a 2-dimensional array has a rectangular shape
ms.openlocfilehash: b8ef7d52f7f815ca3e21ded1236e775a381646cb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220425"
---
# <a name="rectangulararrayfact-function"></a>Rectangulararrayolgu işlevi

Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


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