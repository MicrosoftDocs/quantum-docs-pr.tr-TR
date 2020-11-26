---
uid: Microsoft.Quantum.Arrays.Zipped
title: Daraltılmış işlev
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zipped
qsharp.summary: Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.
ms.openlocfilehash: 56ed97d573bf29dddb7cdb1c3f360218bf97889a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219762"
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

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft.Quantum.Arrays.Zipped3](xref:Microsoft.Quantum.Arrays.Zipped3)
- [Microsoft.Quantum.Arrays.Zipped4](xref:Microsoft.Quantum.Arrays.Zipped4)
- [Microsoft. hisse. Arrays. zip sıkıştırması](xref:Microsoft.Quantum.Arrays.Unzipped)