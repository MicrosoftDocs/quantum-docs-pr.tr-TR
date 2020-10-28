---
uid: Microsoft.Quantum.Arrays.ColumnAt
title: ColumnAt işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ColumnAt
qsharp.summary: Extracts a column from a matrix.
ms.openlocfilehash: ad09ada1a2253a54e70dddd6dba8aa243d2cd5a6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730407"
---
# <a name="columnat-function"></a>ColumnAt işlevi

Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)

Leyebilir [](https://nuget.org/packages/)


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