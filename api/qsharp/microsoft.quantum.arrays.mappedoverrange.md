---
uid: Microsoft.Quantum.Arrays.MappedOverRange
title: MappedOverRange işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MappedOverRange
qsharp.summary: Given a range and a function that takes an integer as input, returns a new array that consists of the images of the range values under the function.
ms.openlocfilehash: b1d73c2503e63ed09a3d6a56421760ca29eb0c3f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220697"
---
# <a name="mappedoverrange-function"></a>MappedOverRange işlevi

Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir Aralık ve girdi olarak tamsayı alan bir işlev verildiğinde, işlev altındaki Aralık değerlerinin görüntülerinden oluşan yeni bir dizi döndürür.

```qsharp
function MappedOverRange<'T> (mapper : (Int -> 'T), range : Range) : 'T[]
```


## <a name="input"></a>Giriş

### <a name="mapper--int---t"></a>Eşleyici: [Int](xref:microsoft.quantum.lang-ref.int) -> 't

`Int`Aralık değerlerini eşlemek için ' den ' a bir işlev `'T` kullanılır.


### <a name="range--range"></a>Aralık: [Aralık](xref:microsoft.quantum.lang-ref.range)

Bir dizi tamsayı.



## <a name="output--t"></a>Çıkış: 'T []

`'T[]`İşlev tarafından eşlenen öğelerin dizisi `mapper` .

## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen

İşlevin sonuç türü `mapper` .

## <a name="remarks"></a>Açıklamalar

İşlevi genel türler için tanımlanmıştır, yani, bir işlevimiz olduğunda `mapper: Int -> 'T` aralığın değerlerini eşleyebilir ve türünde bir dizi üretebilir `'T[]` .

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Arrays. eşlenmiş](xref:Microsoft.Quantum.Arrays.Mapped)