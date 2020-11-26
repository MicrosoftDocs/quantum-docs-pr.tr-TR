---
uid: Microsoft.Quantum.Arrays.Transposed
title: Dönüştürülmüş işlev
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Transposed
qsharp.summary: Returns the transpose of a matrix represented as an array of arrays.
ms.openlocfilehash: f293399d8e3a2cb32b2929e8d1591ac5eaefd277
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220000"
---
# <a name="transposed-function"></a>Dönüştürülmüş işlev

Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Dizi dizisi olarak temsil edilen bir matrisin sırasını döndürür.

```qsharp
function Transposed<'T> (matrix : 'T[][]) : 'T[][]
```


## <a name="description"></a>Açıklama

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