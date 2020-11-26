---
uid: Microsoft.Quantum.Arrays.MappedByIndex
title: Mappedbyındex işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MappedByIndex
qsharp.summary: Given an array and a function that is defined for the indexed elements of the array, returns a new array that consists of the images of the original array under the function.
ms.openlocfilehash: 430495517974b641c249fa146aa9effec542e825
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209936"
---
# <a name="mappedbyindex-function"></a>Mappedbyındex işlevi

Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir dizi ve dizinin dizinli öğeleri için tanımlanan bir işlev verildiğinde, işlevin altındaki orijinal dizinin görüntülerinden oluşan yeni bir dizi döndürür.

```qsharp
function MappedByIndex<'T, 'U> (mapper : ((Int, 'T) -> 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a>Giriş

### <a name="mapper--intt---u"></a>Eşleyici: ([Int](xref:microsoft.quantum.lang-ref.int), 't)-> ' U

`(Int, 'T)` `'U` Öğesi ve bunların dizinlerini eşlemek için kullanılan öğesinden bir işlevi.


### <a name="array--t"></a>dizi: 'T []

Öğesinden bir dizi öğe `'T` .



## <a name="output--u"></a>Çıkış: ' U []

`'U[]`İşlev tarafından eşlenen öğelerin dizisi `mapper` .

## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen

`array`Öğelerin türü.
### <a name="u"></a>' U

İşlevin sonuç türü `mapper` .

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Arrays. eşlenmiş](xref:Microsoft.Quantum.Arrays.Mapped)