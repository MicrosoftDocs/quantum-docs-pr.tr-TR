---
uid: Microsoft.Quantum.Arrays.Diagonal
title: Köşegen işlev
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Diagonal
qsharp.summary: Returns an array of diagonal elements of a 2-dimensional array
ms.openlocfilehash: fe6bac0acfa07b14620c7c35ae5e1cec2287d13d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221547"
---
# <a name="diagonal-function"></a>Köşegen işlev

Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


2 boyutlu bir dizinin köşegen öğelerinin dizisini döndürür

```qsharp
function Diagonal<'T> (matrix : 'T[][]) : 'T[]
```


## <a name="description"></a>Açıklama

2 boyutlu dizide kare şekli yoksa, en az satır ve sütun sayısına göre aşağı köşegen döndürülür.

## <a name="input"></a>Giriş

### <a name="matrix--t"></a>Matris: 'T [] []

satır temelinde sıralı 2 boyutlu matris



## <a name="output--t"></a>Çıkış: 'T []



## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen

Her öğesinin türü `matrix` .

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Arrays. Transdüğü](xref:Microsoft.Quantum.Arrays.Transposed)