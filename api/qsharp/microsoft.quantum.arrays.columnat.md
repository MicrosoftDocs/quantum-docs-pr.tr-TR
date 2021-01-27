---
uid: Microsoft.Quantum.Arrays.ColumnAt
title: ColumnAt işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ColumnAt
qsharp.summary: Extracts a column from a matrix.
ms.openlocfilehash: 32dc814de9b04563c2798a768f121723a1a8252c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846267"
---
# <a name="columnat-function"></a>ColumnAt işlevi

Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir matrisi bir sütundan ayıklar.

```qsharp
function ColumnAt<'T> (column : Int, matrix : 'T[][]) : 'T[]
```


## <a name="description"></a>Description

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

## <a name="example"></a>Örnek

```qsharp
let matrix = [[1, 2, 3], [4, 5, 6], [7, 8, 9]];
let column = ColumnAt(0, matrix);
// same as: column = [1, 4, 7]
```

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Arrays. Transdüğü](xref:Microsoft.Quantum.Arrays.Transposed)
- [Microsoft. hisse. Arrays. köşegen](xref:Microsoft.Quantum.Arrays.Diagonal)