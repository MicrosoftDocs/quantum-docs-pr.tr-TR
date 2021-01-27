---
uid: Microsoft.Quantum.Arrays.Padded
title: Doldurulmuş işlev
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Padded
qsharp.summary: Returns an array padded at with specified values up to a specified length.
ms.openlocfilehash: 556e5f5175ee54470a99f32c037eeb2cd80588d0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845558"
---
# <a name="padded-function"></a>Doldurulmuş işlev

Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Belirtilen bir uzunluğa kadar belirtilen değerlerle doldurulmuş bir dizi döndürür.

```qsharp
function Padded<'T> (nElementsTotal : Int, defaultElement : 'T, inputArray : 'T[]) : 'T[]
```


## <a name="input"></a>Giriş

### <a name="nelementstotal--int"></a>nElementsTotal: [Int](xref:microsoft.quantum.lang-ref.int)

Doldurulmuş dizinin uzunluğu. Bu pozitif ise, `inputArray` baş tarafında doldurulur. Bu negatifse, `inputArray` kuyruklu doldurulur.


### <a name="defaultelement--t"></a>defaultElement: 'T

Doldurma öğeleri için kullanılacak varsayılan değer.


### <a name="inputarray--t"></a>ınputarray: 'T []

Değerleri çıktı dizisinin başındaki dizi.



## <a name="output--t"></a>Çıkış: 'T []

En fazla `output` `inputArray` `defaultElement` uzunluğu olan s ile `output` başlayan bir dizi `nElementsTotal`

## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen

Dizi öğelerinin türü.

## <a name="example"></a>Örnek

```qsharp
let array = [10, 11, 12];
// The following line returns [10, 12, 15, 2, 2, 2].
let output = Padded(-6, array, 2);
// The following line returns [2, 2, 2, 10, 12, 15].
let output = Padded(6, array, 2);
```