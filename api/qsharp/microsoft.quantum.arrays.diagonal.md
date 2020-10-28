---
uid: Microsoft.Quantum.Arrays.Diagonal
title: Köşegen işlev
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Diagonal
qsharp.summary: Returns an array of diagonal elements of a 2-dimensional array
ms.openlocfilehash: 180b7185c94d712fa02100cb97abfbb6c464d12a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730359"
---
# <a name="diagonal-function"></a>Köşegen işlev

Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)

Leyebilir [](https://nuget.org/packages/)


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