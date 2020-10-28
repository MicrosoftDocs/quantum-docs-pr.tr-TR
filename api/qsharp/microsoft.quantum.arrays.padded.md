---
uid: Microsoft.Quantum.Arrays.Padded
title: Doldurulmuş işlev
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Padded
qsharp.summary: Returns an array padded at with specified values up to a specified length.
ms.openlocfilehash: 8742d4726e7ee32349bf3d0bd5077352ffca350b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730090"
---
# <a name="padded-function"></a>Doldurulmuş işlev

Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)

Leyebilir [](https://nuget.org/packages/)


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