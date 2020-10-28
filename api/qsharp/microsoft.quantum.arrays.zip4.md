---
uid: Microsoft.Quantum.Arrays.Zip4
title: Zip4 işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zip4
qsharp.summary: >-
  > [!WARNING]

  > Zip4 has been deprecated. Please use <xref:Microsoft.Quantum.Arrays.Zipped4> instead.


  Given four arrays, returns a new array of 4-tuples such that each 4-tuple contains an element from each original array.
ms.openlocfilehash: d42b3b6db059163f6c766d4f133551be293c153d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729903"
---
# <a name="zip4-function"></a>Zip4 işlevi

Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)

Leyebilir [](https://nuget.org/packages/)


> [!WARNING]
> Zip4 kullanım dışı bırakıldı. Lütfen <xref:Microsoft.Quantum.Arrays.Zipped4> bunun yerine kullanın.

Dört dizi verildiğinde, her 4 tanımlama grubu her bir orijinal diziden bir öğe içerdiği için, yeni bir 4-tanımlama dizisi dizisi döndürür.

```qsharp
function Zip4<'T1, 'T2, 'T3, 'T4> (first : 'T1[], second : 'T2[], third : 'T3[], fourth : 'T4[]) : ('T1, 'T2, 'T3, 'T4)[]
```


## <a name="input"></a>Giriş

### <a name="first--t1"></a>ilk: 1 []

Her kayıt düzeninin ilk öğesi için değerler içeren bir dizi.


### <a name="second--t2"></a>İkinci: 'T 2 []

Her bir kayıt düzeninin ikinci öğesi için değerler içeren bir dizi.


### <a name="third--t3"></a>Üçüncü: 'T []

Her kayıt düzeninin üçüncü öğesi için değerler içeren bir dizi.


### <a name="fourth--t4"></a>Dördüncü: 'T 4 []

Her kayıt düzeninin dördüncü öğesi için değerler içeren bir dizi.



## <a name="output--t1t2t3t4"></a>Çıkış: (1, 'T 2, 't 3, 'T 4) []

Her biri için formun 4-tanımlama gruplarını içeren bir dizi `(first[idx], second[idx], third[idx], fourth[idx])` `idx` . Dört dizi eşit değilse, çıkış girişlerin daha kısa olduğu uzunlukta olur.

## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t1"></a>1 'T

İlk dizi öğelerinin türü.
### <a name="t2"></a>2.

İkinci dizi öğelerinin türü.
### <a name="t3"></a>1 'T

Üçüncü dizi öğelerinin türü.
### <a name="t4"></a>4 'T

Dördüncü dizi öğelerinin türü.

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft.Quantum.Arrays.Zip](xref:Microsoft.Quantum.Arrays.Zip)
- [Microsoft.Quantum.Arrays.Zip3](xref:Microsoft.Quantum.Arrays.Zip3)