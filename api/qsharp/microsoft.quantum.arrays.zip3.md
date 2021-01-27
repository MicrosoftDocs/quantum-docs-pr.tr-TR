---
uid: Microsoft.Quantum.Arrays.Zip3
title: Zip3 işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zip3
qsharp.summary: >-
  > [!WARNING]

  > Zip3 has been deprecated. Please use <xref:Microsoft.Quantum.Arrays.Zipped3> instead.


  Given three arrays, returns a new array of 3-tuples such that each 3-tuple contains an element from each original array.
ms.openlocfilehash: b41b0789cdf90db534ee7a50ff25eb3a931ec683
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845365"
---
# <a name="zip3-function"></a>Zip3 işlevi

Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


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