---
uid: Microsoft.Quantum.Arrays.Transposed
title: Dönüştürülmüş işlev
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Transposed
qsharp.summary: Returns the transpose of a matrix represented as an array of arrays.
ms.openlocfilehash: 54071c461cf9f9411c332763b81e3bc448fb6c6e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729978"
---
# <a name="transposed-function"></a>Dönüştürülmüş işlev

Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)

Leyebilir [](https://nuget.org/packages/)


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