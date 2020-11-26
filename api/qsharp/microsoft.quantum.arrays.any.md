---
uid: Microsoft.Quantum.Arrays.Any
title: Any işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Any
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, checks if at least one element of the array satisfies the predicate.
ms.openlocfilehash: 717ab9ebcbb864a6faf1c14cd36125e589849f2e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221666"
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

## <a name="remarks"></a>Açıklamalar

İşlevi genel türler için tanımlanmıştır, yani bir dizi `'T[]` ve işlevimiz olduğunda, bir `predicate: 'T -> Bool` `Bool` öğenin karşılayıp karşılamadığını belirten bir değer üretebiliriz `predicate` .