---
uid: Microsoft.Quantum.Arrays.Zipped4
title: Zipped4 işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zipped4
qsharp.summary: Given four arrays, returns a new array of 4-tuples such that each 4-tuple contains an element from each original array.
ms.openlocfilehash: e932cd4c266b39a3a88da48e649448d0028f61e3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845323"
---
# <a name="zipped4-function"></a>Zipped4 işlevi

Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Dört dizi verildiğinde, her 4 tanımlama grubu her bir orijinal diziden bir öğe içerdiği için, yeni bir 4-tanımlama dizisi dizisi döndürür.

```qsharp
function Zipped4<'T1, 'T2, 'T3, 'T4> (first : 'T1[], second : 'T2[], third : 'T3[], fourth : 'T4[]) : ('T1, 'T2, 'T3, 'T4)[]
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

- [Microsoft.Quantum.Arrays.Zipuygulanmış](xref:Microsoft.Quantum.Arrays.Zipped)
- [Microsoft.Quantum.Arrays.Zipped3](xref:Microsoft.Quantum.Arrays.Zipped3)