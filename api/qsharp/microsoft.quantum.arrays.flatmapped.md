---
uid: Microsoft.Quantum.Arrays.FlatMapped
title: Yatayeşlenmiş işlev
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: FlatMapped
qsharp.summary: Given an array and a function that maps an array element to some output array, returns the concatenated output arrays for each array element.
ms.openlocfilehash: e851e8503b3afcb4572f09fe39079247518c22c4
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221258"
---
# <a name="flatmapped-function"></a>Yatayeşlenmiş işlev

Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


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