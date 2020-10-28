---
uid: Microsoft.Quantum.Arrays.Subarray
title: Subarray işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Subarray
qsharp.summary: Takes an array and a list of locations and produces a new array formed from the elements of the original array that match the given locations.
ms.openlocfilehash: be7b6ee1a396d67ebc311d8d97f4bd751a32d171
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729999"
---
# <a name="subarray-function"></a>Subarray işlevi

Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)

Leyebilir [](https://nuget.org/packages/)


Bir diziyi ve konumların bir listesini alır ve özgün dizinin öğelerinden belirtilen konumlara göre oluşturulmuş yeni bir dizi oluşturur.

```qsharp
function Subarray<'T> (indices : Int[], array : 'T[]) : 'T[]
```


## <a name="input"></a>Giriş

### <a name="indices--int"></a>dizinler: [Int](xref:microsoft.quantum.lang-ref.int)[]

Alt diziyi tanımlamak için kullanılan tamsayıların listesi.


### <a name="array--t"></a>dizi: 'T []

Öğesinden bir dizi öğe `'T` .



## <a name="output--t"></a>Çıkış: 'T []

`out`Dizinleri alt diziye karşılık gelen bir öğe dizisi, örneğin `out[idx] == array[indices[idx]]` .

## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen

`array`Öğelerin türü.

## <a name="remarks"></a>Açıklamalar

İşlevi genel türler için tanımlanır, yani bir dizi `'T[]` ve `Int[]` alt diziyi tanımlayan konumların bir listesi.
Alt dizinin oluşturulması, başvuruları korumanın aksine, belirtilen dizinin yeni ve derin bir kopyasını oluşturmaya göre belirlenir.

Eğer `Length(indices) < Length(array)` , bu işlev öğesinin bir alt kümesini döndürür `array` . Diğer taraftan, `indices` yinelenen öğeler içeriyorsa, karşılık gelen öğeleri de `array` aynı şekilde yinelenir.
`indices`Ve `array` aynı uzunluysa, bu işlev permütasyon sağlar `array` .