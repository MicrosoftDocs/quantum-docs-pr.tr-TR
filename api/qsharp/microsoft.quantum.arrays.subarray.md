---
uid: Microsoft.Quantum.Arrays.Subarray
title: Subarray işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Subarray
qsharp.summary: Takes an array and a list of locations and produces a new array formed from the elements of the original array that match the given locations.
ms.openlocfilehash: ccc041da0213d1f5dc5c8b4ff7a03b8b01ad107d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845428"
---
# <a name="subarray-function"></a>Subarray işlevi

Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


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