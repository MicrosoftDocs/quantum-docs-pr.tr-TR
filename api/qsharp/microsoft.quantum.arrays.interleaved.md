---
uid: Microsoft.Quantum.Arrays.Interleaved
title: Araya eklemeli işlev
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Interleaved
qsharp.summary: Interleaves two arrays of (almost) same size.
ms.openlocfilehash: 8405cabca17f2dd7c2680833bfab5c3768fcf752
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730199"
---
# <a name="interleaved-function"></a>Araya eklemeli işlev

Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)

Leyebilir [](https://nuget.org/packages/)


İki dizi (neredeyse) aynı boyutta bırakılır.

```qsharp
function Interleaved<'T> (first : 'T[], second : 'T[]) : 'T[]
```


## <a name="description"></a>Açıklama

Bu işlev, ilk dizideki ilk öğe, sonra ikinci dizideki ilk öğe ve benzeri gibi iki dizinin araya ekleme işlemi döndürür.

İlk dizi ikinciyle aynı uzunlukta olmalıdır ya da bir daha fazla öğeye sahip olabilir.

## <a name="input"></a>Giriş

### <a name="first--t"></a>ilk: 'T []

Araya eklemeli ilk dizi.


### <a name="second--t"></a>İkinci: 'T []

Araya eklemeli ikinci dizi.



## <a name="output--t"></a>Çıkış: 'T []

Araya eklemeli dizi

## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen

Ve öğelerinin her öğesinin türü `first` `second` .