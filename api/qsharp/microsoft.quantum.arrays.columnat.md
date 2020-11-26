---
uid: Microsoft.Quantum.Arrays.ColumnAt
title: ColumnAt işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ColumnAt
qsharp.summary: Extracts a column from a matrix.
ms.openlocfilehash: 097b3fdd6fc1843ada27052fcf08ee80d894d25a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210122"
---
# <a name="columnat-function"></a>ColumnAt işlevi

Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir matrisi bir sütundan ayıklar.

```qsharp
function ColumnAt<'T> (column : Int, matrix : 'T[][]) : 'T[]
```


## <a name="description"></a>Açıklama

Bu işlev, bir matrisi satır temelinde sırayla ayıklar.
Satır bağıntılarını ilk dizinin öğe erişimine ayıkladıktan sonra başka bir işleme gerek yoktur.

## <a name="input"></a>Giriş

### <a name="column--int"></a>sütun: [Int](xref:microsoft.quantum.lang-ref.int)

Matrisin sütunu


### <a name="matrix--t"></a>Matris: 'T [] []

satır temelinde sıralı 2 boyutlu matris



## <a name="output--t"></a>Çıkış: 'T []



## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen

Her öğesinin türü `matrix` .

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Arrays. Transdüğü](xref:Microsoft.Quantum.Arrays.Transposed)
- [Microsoft. hisse. Arrays. köşegen](xref:Microsoft.Quantum.Arrays.Diagonal)