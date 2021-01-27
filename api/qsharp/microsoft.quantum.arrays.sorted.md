---
uid: Microsoft.Quantum.Arrays.Sorted
title: Sıralanmış işlev
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Sorted
qsharp.summary: Given an array, returns the elements of that array sorted by a given comparison function.
ms.openlocfilehash: cb8a1ef438d798c8201ed9f52677e253770df1d3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845438"
---
# <a name="sorted-function"></a>Sıralanmış işlev

Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Dizi verildiğinde, belirli bir karşılaştırma işlevine göre sıralanan bu dizinin öğelerini döndürür.

```qsharp
function Sorted<'T> (comparison : (('T, 'T) -> Bool), array : 'T[]) : 'T[]
```


## <a name="input"></a>Giriş

### <a name="comparison--tt---bool"></a>Karşılaştırma: ('T, 'T)-> [bool](xref:microsoft.quantum.lang-ref.bool)

İki öğeyi karşılaştıran bir işlev `a` , daha küçük veya eşittir olarak kabul edilir `b` `comparison(a, b)` `true` .


### <a name="array--t"></a>dizi: 'T []

Sıralanacak dizi.



## <a name="output--t"></a>Çıkış: 'T []



## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen

Her öğesinin türü `array` .

## <a name="example"></a>Örnek

Aşağıdaki kod parçacığı, bir tamsayılar dizisini artan sırada gerçekleşecek şekilde sıralar:

```qsharp
let sortedArray = Sorted(LessThanOrEqualI, [3, 17, 11, -201, -11]);
```

## <a name="remarks"></a>Açıklamalar

İşlevin `comparison` geçişli olduğu varsayılır, `comparison(a, b)` ve `comparison(b, c)` daha sonra `comparison(a, c)` varsayılır. Bu özellik tutmadıysanız, bu işlevin çıktısı yanlış olabilir.

Bu bir işlev olduğundan, iki öğe içinde eşit kabul edildiğinde bile sonuçlar tamamen belirleyici olur `comparison` ; Yani, `comparison(a, b)` ve `comparison(b, a)` her ikisi de olur `true` .
Özellikle, bu işlev tarafından gerçekleştirilen sıralamanın kararlı olduğu garanti edilir. böylece, iki öğe ve `a` `b` içinde bu sırada gerçekleşirse `array` `comparison` , ve sonrasında `a` da daha önce de görüntülenir `b` .

Örnek:

```qsharp
function LastDigitLessThanOrEqual(left : Int, right : Int) : Bool {
    return LessThanOrEqualI(
        left % 10, right % 10
    );
}

function SortedByLastDigit() : Int[] {
    return Sorted(LastDigitLessThanOrEqual, [3, 37, 11, 17]);
}
// returns [11, 3, 37, 17].
```