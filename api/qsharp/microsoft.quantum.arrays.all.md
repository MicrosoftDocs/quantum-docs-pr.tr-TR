---
uid: Microsoft.Quantum.Arrays.All
title: All işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: All
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, and checks if all elements of the array satisfy the predicate.
ms.openlocfilehash: a7c83e38c3c101b712215eb664486fe29863a52b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221700"
---
# <a name="all-function"></a>All işlevi

Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Dizi öğeleri için tanımlanan bir dizi ve koşul verildiğinde, dizideki tüm öğelerin koşulu karşılayıp karşılamadığını denetler.

```qsharp
function All<'T> (predicate : ('T -> Bool), array : 'T[]) : Bool
```


## <a name="input"></a>Giriş

### <a name="predicate--t---bool"></a>koşul: 'T-> [bool](xref:microsoft.quantum.lang-ref.bool)

`'T` `Bool` Öğeleri denetlemek için kullanılan öğesinden bir işlev.


### <a name="array--t"></a>dizi: 'T []

Öğesinden bir dizi öğe `'T` .



## <a name="output--bool"></a>Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)

`Bool`Tüm öğelere uygulanan koşulun ve işlevinin değeri.

## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen

`array`Öğelerin türü.

## <a name="remarks"></a>Açıklamalar

İşlevi genel türler için tanımlanmıştır, yani bir dizi `'T[]` ve bir işlev olduğunda `predicate: 'T -> Bool` `Bool` tüm öğelerin karşılayıp karşılamadığını belirten bir değer üretebiliriz `predicate` .