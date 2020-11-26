---
uid: Microsoft.Quantum.Arrays.Zip
title: Zip işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zip
qsharp.summary: >-
  > [!WARNING]

  > Zip has been deprecated. Please use <xref:Microsoft.Quantum.Arrays.Zipped> instead.


  Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.
ms.openlocfilehash: 44db8d38d96babd16ead5ae6dde91da23bdee2c9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219864"
---
# <a name="zip-function"></a>Zip işlevi

Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


> [!WARNING]
> ZIP kullanım dışı bırakıldı. Lütfen <xref:Microsoft.Quantum.Arrays.Zipped> bunun yerine kullanın.

İki dizi verildiğinde, her bir çiftin her orijinal diziden bir öğe içermesi gibi yeni bir çift dizisi döndürür.

```qsharp
function Zip<'T, 'U> (left : 'T[], right : 'U[]) : ('T, 'U)[]
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

- [Microsoft.Quantum.Arrays.Zip3](xref:Microsoft.Quantum.Arrays.Zip3)
- [Microsoft.Quantum.Arrays.Zip4](xref:Microsoft.Quantum.Arrays.Zip4)
- [Microsoft. hisse. Arrays. zip sıkıştırması](xref:Microsoft.Quantum.Arrays.Unzipped)