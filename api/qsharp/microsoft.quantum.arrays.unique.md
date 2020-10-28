---
uid: Microsoft.Quantum.Arrays.Unique
title: Unique işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Unique
qsharp.summary: Returns a new array that has no equal adjacent elements.
ms.openlocfilehash: c5d40bb82f2de640e9c78eef0c27e4766b477826
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729959"
---
# <a name="unique-function"></a>Unique işlevi

Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)

Leyebilir [](https://nuget.org/packages/)


Eşit bitişik öğeleri olmayan yeni bir dizi döndürür.

```qsharp
function Unique<'T> (equal : (('T, 'T) -> Bool), array : 'T[]) : 'T[]
```


## <a name="description"></a>Açıklama

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

## <a name="remarks"></a>Açıklamalar

Eşit olan, diğeri yanında olmayan birden çok öğe varsa, çıkış dizisinde birden çok oluşum olur.  `Sorted`Genel benzersiz öğeler içeren bir dizi almak için bu işlevi ile birlikte kullanın.