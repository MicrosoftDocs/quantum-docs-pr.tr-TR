---
uid: Microsoft.Quantum.Arrays.EqualA
title: EqualA işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: EqualA
qsharp.summary: Given two arrays of the same type and a predicate that is defined for pairs of elements of the arrays, checks whether the arrays are equal.
ms.openlocfilehash: fe22e208f67d2c289b0b2d99f19ff26fc5abc3d8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848684"
---
# <a name="equala-function"></a>EqualA işlevi

Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


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

## <a name="example"></a>Örnek

Aşağıdaki kod, farklı dizi çiftlerinin eşit olup olmadığını denetler:

```qsharp
open Microsoft.Quantum.Arrays;
open Microsoft.Quantum.Logical;

function EqualADemo() : Unit {
    let equalArrays = EqualA(EqualI, [2, 3, 4], [2, 3, 4]);
    let differentLength = EqualA(EqualD, [2.0, 3.0, 4.0], [2.0, 3.0]);
    let differentElements = EqualA(EqualR, [One, Zero], [One, One]);
    Message($"Equal arrays are {equalArrays ? "equal" | "not equal"}");
    Message($"Arrays of different length are {differentLength ? "equal" | "not equal"}");
    Message($"Arrays of the same length with different elements are {differentElements ? "equal" | "not equal"}");
}
```

## <a name="remarks"></a>Açıklamalar

Bu işlev genel türler için tanımlanmıştır; Yani, iki dizimiz `'T[]` ve bir işlev olduğunda `equal: ('T, 'T) -> Bool` , bu işlev `Bool` dizilerinin eşit olup olmadığını gösteren bir değer döndürür.
Eşit kabul edilmesi için iki dizinin eşit olması gerekir ve dizilerdeki aynı konumlarda bulunan öğelerin eşit olması gerekir.