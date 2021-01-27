---
uid: Microsoft.Quantum.Arrays.SquareArrayFact
title: Squarearrayolgu işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SquareArrayFact
qsharp.summary: Represents a condition that a 2-dimensional array has a square shape
ms.openlocfilehash: a154e5becba4dae762596a3fc1b268855520fa1b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850976"
---
# <a name="squarearrayfact-function"></a>Squarearrayolgu işlevi

Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


2 boyutlu dizinin kare şekline sahip olduğu koşulu temsil eder

```qsharp
function SquareArrayFact<'T> (array : 'T[][], message : String) : Unit
```


## <a name="description"></a>Description

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

## <a name="example"></a>Örnek

```qsharp
SquareArrayFact([[1, 2], [3, 4]], "Array is not a square");       // okay
SquareArrayFact([[1, 2, 3], [4, 5, 6]], "Array is not a square"); // will fail
SquareArrayFact([[1, 2], [3, 4, 5]], "Array is not a square");    // will fail
```

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Arrays. Rectangulararrayolgusu](xref:Microsoft.Quantum.Arrays.RectangularArrayFact)