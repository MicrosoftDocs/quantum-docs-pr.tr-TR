---
uid: Microsoft.Quantum.Arrays.FlatMapped
title: Yatayeşlenmiş işlev
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: FlatMapped
qsharp.summary: Given an array and a function that maps an array element to some output array, returns the concatenated output arrays for each array element.
ms.openlocfilehash: 3e75c7703471a2986812df660c2f9328f1536d22
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730271"
---
# <a name="flatmapped-function"></a>Yatayeşlenmiş işlev

Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)

Leyebilir [](https://nuget.org/packages/)


Bir dizi ve bir dizi öğesini bir çıktı dizisine eşleyen bir işlev verildiğinde, her dizi öğesi için birleştirilmiş çıkış dizilerini döndürür.

```qsharp
function FlatMapped<'TInput, 'TOutput> (mapper : ('TInput -> 'TOutput[]), array : 'TInput[]) : 'TOutput[]
```


## <a name="input"></a>Giriş

### <a name="mapper--tinput---toutput"></a>Eşleyici: ' TInput-> ' TOutput []

Öğesinden `'TInput` öğesine `'TOutput[]` , dizi öğelerini eşlemek için kullanılan bir işlev.


### <a name="array--tinput"></a>dizi: ' TInput []

Bir dizi öğe.



## <a name="output--toutput"></a>Çıkış: ' TOutput []

`'TOutput[]`Eşleme işlevi tarafından oluşturulan tüm dizilerin bitiştirilmesi olan dizi.

## <a name="type-parameters"></a>Tür Parametreleri

### <a name="tinput"></a>' TInput

`array`Öğelerin türü.
### <a name="toutput"></a>' TOutput

`mapper`İşlevi bu türün dizilerini döndürür.