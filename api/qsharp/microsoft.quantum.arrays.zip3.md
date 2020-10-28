---
uid: Microsoft.Quantum.Arrays.Zip3
title: Zip3 işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zip3
qsharp.summary: >-
  > [!WARNING]

  > Zip3 has been deprecated. Please use <xref:Microsoft.Quantum.Arrays.Zipped3> instead.


  Given three arrays, returns a new array of 3-tuples such that each 3-tuple contains an element from each original array.
ms.openlocfilehash: f4b1a769614ee9434b2141b8fcb91f34cd071bdb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729919"
---
# <a name="zip3-function"></a>Zip3 işlevi

Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)

Leyebilir [](https://nuget.org/packages/)


> [!WARNING]
> Zip3 kullanım dışı bırakıldı. Lütfen <xref:Microsoft.Quantum.Arrays.Zipped3> bunun yerine kullanın.

Üç dizi verildiğinde, her bir 3 tanımlama grubu her bir orijinal diziden bir öğe içerdiği için, yeni bir 3-tanımlama dizisi döndürür.

```qsharp
function Zip3<'T1, 'T2, 'T3> (first : 'T1[], second : 'T2[], third : 'T3[]) : ('T1, 'T2, 'T3)[]
```


## <a name="input"></a>Giriş

### <a name="first--t1"></a>ilk: 1 []

Her kayıt düzeninin ilk öğesi için değerler içeren bir dizi.


### <a name="second--t2"></a>İkinci: 'T 2 []

Her bir kayıt düzeninin ikinci öğesi için değerler içeren bir dizi.


### <a name="third--t3"></a>Üçüncü: 'T []

Her kayıt düzeninin üçüncü öğesi için değerler içeren bir dizi.



## <a name="output--t1t2t3"></a>Çıkış: (1, 'T 2, 'T 3) []

Her biri için formun 3-tanımlama gruplarını içeren bir dizi `(first[idx], second[idx], third[idx])` `idx` . Üç dizi eşit değilse, çıkış girişlerin daha kısa olduğu uzunlukta olur.

## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t1"></a>1 'T

İlk dizi öğelerinin türü.
### <a name="t2"></a>2.

İkinci dizi öğelerinin türü.
### <a name="t3"></a>1 'T

Üçüncü dizi öğelerinin türü.

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft.Quantum.Arrays.Zip](xref:Microsoft.Quantum.Arrays.Zip)
- [Microsoft.Quantum.Arrays.Zip4](xref:Microsoft.Quantum.Arrays.Zip4)