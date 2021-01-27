---
uid: Microsoft.Quantum.Arrays.Any
title: Any işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Any
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, checks if at least one element of the array satisfies the predicate.
ms.openlocfilehash: a05f9531168bf2b32977665d38cc00f3c8e64879
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846276"
---
# <a name="any-function"></a>Any işlevi

Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Dizi öğeleri için tanımlanan bir dizi ve koşul verildiğinde, dizinin en az bir öğesinin koşulu karşılayıp karşılamadığını denetler.

```qsharp
function Any<'T> (predicate : ('T -> Bool), array : 'T[]) : Bool
```


## <a name="input"></a>Giriş

### <a name="predicate--t---bool"></a>koşul: 'T-> [bool](xref:microsoft.quantum.lang-ref.bool)

`'T` `Bool` Öğeleri denetlemek için kullanılan öğesinden bir işlev.


### <a name="array--t"></a>dizi: 'T []

Öğesinden bir dizi öğe `'T` .



## <a name="output--bool"></a>Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)

`Bool`Tüm öğelere uygulanan koşulun OR işlevinin değeri.

## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen

`array`Öğelerin türü.

## <a name="example"></a>Örnek

```qsharp
open Microsoft.Quantum.Arrays;
open Microsoft.Quantum.Logical;

function IsThreePresent() : Bool {
    let arrayOfInts = [1, 2, 3, 4, 5];
    let is3Present = IsNumberPresentInArray(3, arrayOfInts);
    return is3Present;
}

function IsNumberPresentInArray(n : Int, array : Int[]) : Bool {
    return Any(EqualI(_, n), array);
}
```

## <a name="remarks"></a>Açıklamalar

İşlevi genel türler için tanımlanmıştır, yani bir dizi `'T[]` ve işlevimiz olduğunda, bir `predicate: 'T -> Bool` `Bool` öğenin karşılayıp karşılamadığını belirten bir değer üretebiliriz `predicate` .