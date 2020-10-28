---
uid: Microsoft.Quantum.Arrays.SquareArrayFact
title: Squarearrayolgu işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SquareArrayFact
qsharp.summary: Represents a condition that a 2-dimensional array has a square shape
ms.openlocfilehash: f7f0573db9098feebfd481624e11119c58fd9eed
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730007"
---
# <a name="squarearrayfact-function"></a>Squarearrayolgu işlevi

Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)

Leyebilir [](https://nuget.org/packages/)


2 boyutlu dizinin kare şekline sahip olduğu koşulu temsil eder

```qsharp
function SquareArrayFact<'T> (array : 'T[][], message : String) : Unit
```


## <a name="description"></a>Açıklama

Bu işlev, dizideki her bir satırın dizideki satırlar (öğeler) gibi çok sayıda öğesi olduğunu onaylar.

## <a name="input"></a>Giriş

### <a name="array--t"></a>dizi: 'T [] []

2 boyutlu bir öğe dizisi


### <a name="message--string"></a>ileti: [dize](xref:microsoft.quantum.lang-ref.string)

Dizi bir kare dizisi değilse yazdırılacak bir ileti



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen

Her öğesinin türü `array` .

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Arrays. Rectangulararrayolgusu](xref:Microsoft.Quantum.Arrays.RectangularArrayFact)