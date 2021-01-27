---
uid: Microsoft.Quantum.Arrays.Unzipped
title: Sıkıştırılmış olmayan işlev
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Unzipped
qsharp.summary: Given an array of 2-tuples, returns a tuple of two arrays, each containing the elements of the tuples of the input array.
ms.openlocfilehash: 7eea7982721dc596b8660be5f3634df71b1ddf95
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845376"
---
# <a name="unzipped-function"></a>Sıkıştırılmış olmayan işlev

Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


2 tanımlama grubu dizisi verildiğinde, her biri giriş dizisinin tanımlama gruplarının öğelerini içeren iki dizinin bir kümesini döndürür.

```qsharp
function Unzipped<'T, 'U> (arr : ('T, 'U)[]) : ('T[], 'U[])
```


## <a name="input"></a>Giriş

### <a name="arr--tu"></a>ARR: ('T, ' U) []

2 tanımlama grubu içeren bir dizi



## <a name="output--tu"></a>Çıkış: ('T [], ' U [])

İlk biri giriş tanımlama gruplarının tüm ilk öğelerini içeren, ikinci diğeri giriş tanımlama gruplarının tüm ikinci öğelerini içeren iki dizi.

## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen

Her bir tanımlama alanındaki ilk öğenin türü
### <a name="u"></a>' U

Her bir tanımlama alanındaki ikinci öğe türü

## <a name="example"></a>Örnek

```qsharp
// split is same as ([6, 5, 5, 3, 2, 1], [true, false, false, false, true, false])
let split = Unzipped([(6, true), (5, false), (5, false), (3, false), (2, true), (1, false)]);
```

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft.Quantum.Arrays.Zipuygulanmış](xref:Microsoft.Quantum.Arrays.Zipped)