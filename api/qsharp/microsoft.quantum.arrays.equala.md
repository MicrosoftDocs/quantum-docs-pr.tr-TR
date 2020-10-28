---
uid: Microsoft.Quantum.Arrays.EqualA
title: EqualA işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: EqualA
qsharp.summary: Given two arrays of the same type and a predicate that is defined for pairs of elements of the arrays, checks whether the arrays are equal.
ms.openlocfilehash: 24fd76aaeb66081d6d8f1eaa3056117f54b5a5e7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730295"
---
# <a name="equala-function"></a>EqualA işlevi

Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)

Leyebilir [](https://nuget.org/packages/)


Aynı türde iki dizi ve dizilerin öğe çiftleri için tanımlanan bir koşul verildiğinde, dizilerin eşit olup olmadığını denetler.

```qsharp
function EqualA<'T> (equal : (('T, 'T) -> Bool), array1 : 'T[], array2 : 'T[]) : Bool
```


## <a name="input"></a>Giriş

### <a name="equal--tt---bool"></a>eşittir: ('T, 'T)-> [bool](xref:microsoft.quantum.lang-ref.bool)

`('T, 'T)` `Bool` Dizi içindeki iki öğenin eşit olup olmadığını denetlemek için kullanılan, kayıt kümesinden bir işlev.


### <a name="array1--t"></a>Dizi1: 'T []

Karşılaştırılacak ilk dizi.


### <a name="array2--t"></a>dizi2: 'T []

Karşılaştırılacak ikinci dizi.



## <a name="output--bool"></a>Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)

Yalnızca ve `true` `array1` `array2` eşitse değeri.
Diğer bir deyişle, her iki dizi de aynı uzunluktadır ve tüm öğeler tarafından tanımlanan şekilde eşittir `equal` .

## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen

Her bir dizinin öğelerinin türü.

## <a name="remarks"></a>Açıklamalar

Bu işlev genel türler için tanımlanmıştır; Yani, iki dizimiz `'T[]` ve bir işlev olduğunda `equal: ('T, 'T) -> Bool` , bu işlev `Bool` dizilerinin eşit olup olmadığını gösteren bir değer döndürür.
Eşit kabul edilmesi için iki dizinin eşit olması gerekir ve dizilerdeki aynı konumlarda bulunan öğelerin eşit olması gerekir.