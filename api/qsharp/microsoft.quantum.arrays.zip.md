---
uid: Microsoft.Quantum.Arrays.Zip
title: Zip işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zip
qsharp.summary: >-
  > [!WARNING]

  > Zip has been deprecated. Please use <xref:Microsoft.Quantum.Arrays.Zipped> instead.


  Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.
ms.openlocfilehash: 8ed658003f749efd31b8d841cecbb0a23a471af5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850893"
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

## <a name="example"></a>Örnek

```qsharp
let left = [1, 3, 71];
let right = [false, true];
let pairs = Zip(left, right); // [(1, false), (3, true)]
```

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft.Quantum.Arrays.Zip3](xref:Microsoft.Quantum.Arrays.Zip3)
- [Microsoft.Quantum.Arrays.Zip4](xref:Microsoft.Quantum.Arrays.Zip4)
- [Microsoft. hisse. Arrays. zip sıkıştırması](xref:Microsoft.Quantum.Arrays.Unzipped)