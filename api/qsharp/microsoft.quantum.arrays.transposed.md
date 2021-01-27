---
uid: Microsoft.Quantum.Arrays.Transposed
title: Dönüştürülmüş işlev
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Transposed
qsharp.summary: Returns the transpose of a matrix represented as an array of arrays.
ms.openlocfilehash: 913f1829ef53ec3eb6944be8b8e3eb37b431f27e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850926"
---
# <a name="transposed-function"></a>Dönüştürülmüş işlev

Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Dizi dizisi olarak temsil edilen bir matrisin sırasını döndürür.

```qsharp
function Transposed<'T> (matrix : 'T[][]) : 'T[][]
```


## <a name="description"></a>Description

$R $ Rows ve $c $ sütunları ile $r \times c $ matrisi olarak girin.  Matris satır tabanlıdır, yani `matrix[i][j]` $i $ ve column $j $ sütunundaki öğeye erişir.

Bu işlev, giriş matrisinin sırasını değiştir olan \times r $ matrisini $c döndürür.

## <a name="input"></a>Giriş

### <a name="matrix--t"></a>Matris: 'T [] []

Satır tabanlı $r \times c $ matrisi



## <a name="output--t"></a>Çıkış: 'T [] []

Dönüştürülmüş $c \times r $ matrisi

## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen

Her öğesinin türü `matrix` .

## <a name="example"></a>Örnek

```qsharp
// same as [[1, 4], [2, 5], [3, 6]]
let transposed = Transposed([[1, 2, 3], [4, 5, 6]]);
```