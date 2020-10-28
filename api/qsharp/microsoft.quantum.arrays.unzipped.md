---
uid: Microsoft.Quantum.Arrays.Unzipped
title: Sıkıştırılmış olmayan işlev
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Unzipped
qsharp.summary: Given an array of 2-tuples, returns a tuple of two arrays, each containing the elements of the tuples of the input array.
ms.openlocfilehash: 37c960dc5dbdb8099fbebe1ad63cb44ce642733c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729962"
---
# <a name="unzipped-function"></a>Sıkıştırılmış olmayan işlev

Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)

Leyebilir [](https://nuget.org/packages/)


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

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft.Quantum.Arrays.Zipuygulanmış](xref:Microsoft.Quantum.Arrays.Zipped)