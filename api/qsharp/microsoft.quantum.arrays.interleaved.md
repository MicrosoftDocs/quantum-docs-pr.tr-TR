---
uid: Microsoft.Quantum.Arrays.Interleaved
title: Araya eklemeli işlev
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Interleaved
qsharp.summary: Interleaves two arrays of (almost) same size.
ms.openlocfilehash: 3605c0d0bc43cdb1097d025861c3ec2424763c86
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848109"
---
# <a name="interleaved-function"></a>Araya eklemeli işlev

Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


İki dizi (neredeyse) aynı boyutta bırakılır.

```qsharp
function Interleaved<'T> (first : 'T[], second : 'T[]) : 'T[]
```


## <a name="description"></a>Description

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

## <a name="example"></a>Örnek

```qsharp
// same as int1 = [1, -1, 2, -2, 3, -3]
let int1 = Interleaved([1, 2, 3], [-1, -2, -3])

// same as int2 = [false, true, false, true, false]
let int2 = Interleaved(ConstantArray(3, false), ConstantArray(2, true));
```