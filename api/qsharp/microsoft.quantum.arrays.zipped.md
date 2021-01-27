---
uid: Microsoft.Quantum.Arrays.Zipped
title: Daraltılmış işlev
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zipped
qsharp.summary: Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.
ms.openlocfilehash: 5177ab0ade5a9ad7788e60c1028befb84b0191d4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845344"
---
# <a name="zipped-function"></a>Daraltılmış işlev

Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


İki dizi verildiğinde, her bir çiftin her orijinal diziden bir öğe içermesi gibi yeni bir çift dizisi döndürür.

```qsharp
function Zipped<'T, 'U> (left : 'T[], right : 'U[]) : ('T, 'U)[]
```


## <a name="input"></a>Giriş

### <a name="left--t"></a>Sol: 'T []

Her kayıt düzeninin ilk öğesi için değerler içeren bir dizi.


### <a name="right--u"></a>Sağ: ' U []

Her bir kayıt düzeninin ikinci öğesi için değerler içeren bir dizi.



## <a name="output--tu"></a>Çıkış: ('T, ' U) []

Her biri için form çiftlerini içeren bir dizi `(left[idx], right[idx])` `idx` . İki dizi eşit değilse, çıkış girişlerin daha kısa olduğu uzunlukta olur.

## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen

Sol dizi öğelerinin türü.
### <a name="u"></a>' U

Sağ dizi öğelerinin türü.

## <a name="example"></a>Örnek

```qsharp
let left = [1, 3, 71];
let right = [false, true];
let pairs = Zipped(left, right); // [(1, false), (3, true)]
```

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft.Quantum.Arrays.Zipped3](xref:Microsoft.Quantum.Arrays.Zipped3)
- [Microsoft.Quantum.Arrays.Zipped4](xref:Microsoft.Quantum.Arrays.Zipped4)
- [Microsoft. hisse. Arrays. zip sıkıştırması](xref:Microsoft.Quantum.Arrays.Unzipped)