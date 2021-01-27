---
uid: Microsoft.Quantum.Arrays.MappedOverRange
title: MappedOverRange işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MappedOverRange
qsharp.summary: Given a range and a function that takes an integer as input, returns a new array that consists of the images of the range values under the function.
ms.openlocfilehash: 7093043e2a290e6132774b8fe154d3627a254f27
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845645"
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

## <a name="example"></a>Örnek

Bu örnek, çift sayı aralığına 1 ekler:

```qsharp
let numbers = MappedOverRange(PlusI(1, _), 0..2..10);
// numbers = [1, 3, 5, 7, 9, 11]
```

## <a name="remarks"></a>Açıklamalar

İşlevi genel türler için tanımlanmıştır, yani, bir işlevimiz olduğunda `mapper: Int -> 'T` aralığın değerlerini eşleyebilir ve türünde bir dizi üretebilir `'T[]` .

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Arrays. eşlenmiş](xref:Microsoft.Quantum.Arrays.Mapped)