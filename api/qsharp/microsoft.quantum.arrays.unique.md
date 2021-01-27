---
uid: Microsoft.Quantum.Arrays.Unique
title: Unique işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Unique
qsharp.summary: Returns a new array that has no equal adjacent elements.
ms.openlocfilehash: b3aa03d20195bdd8bb64783a9b68cafac29e68f6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850919"
---
# <a name="unique-function"></a>Unique işlevi

Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Eşit bitişik öğeleri olmayan yeni bir dizi döndürür.

```qsharp
function Unique<'T> (equal : (('T, 'T) -> Bool), array : 'T[]) : 'T[]
```


## <a name="description"></a>Description

Bir dizi öğe ve eşitlik sınaması için bir işlev verildiğinde, bu işlev, öğelerin göreli sırasının tutulduğu yeni bir dizi döndürür, ancak eşit olan tüm bitişik öğeler yalnızca tek bir öğeye filtrelenir.

## <a name="input"></a>Giriş

### <a name="equal--tt---bool"></a>eşittir: ('T, 'T)-> [bool](xref:microsoft.quantum.lang-ref.bool)

`a` `b` `equal(a, b)` Öğesi ise, eşit olarak kabul edilen iki öğeyi karşılaştıran bir işlev `true` .


### <a name="array--t"></a>dizi: 'T []

Benzersiz öğeler için filtrelenecek dizi.



## <a name="output--t"></a>Çıkış: 'T []

Eşit bitişik öğe olmayan dizi.

## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen

Her öğesinin türü `array` .

## <a name="example"></a>Örnek

```qsharp
let unique1 = Unique(EqualI, [1, 1, 3, 3, 2, 5, 5, 5, 7]);
// same as [1, 3, 2, 5, 7]
let unique2 = Unique(EqualI, [2, 2, 1, 1, 2, 2, 1, 1]);
// same as [2, 1, 2, 1];
let unique3 = Unique(EqualI, Sorted(LessThanOrEqualI, [2, 2, 1, 1, 2, 2, 1, 1]));
// same as [1, 2];
```

## <a name="remarks"></a>Açıklamalar

Eşit olan, diğeri yanında olmayan birden çok öğe varsa, çıkış dizisinde birden çok oluşum olur.  `Sorted`Genel benzersiz öğeler içeren bir dizi almak için bu işlevi ile birlikte kullanın.