---
uid: Microsoft.Quantum.Arrays.Zipped
title: Daraltılmış işlev
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zipped
qsharp.summary: Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.
ms.openlocfilehash: 67170fa005675f0e5d788c9c3b350fb9a961a597
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729911"
---
# <a name="zipped-function"></a>Daraltılmış işlev

Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)

Leyebilir [](https://nuget.org/packages/)


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