---
uid: Microsoft.Quantum.Arrays.FlatMapped
title: Yatayeşlenmiş işlev
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: FlatMapped
qsharp.summary: Given an array and a function that maps an array element to some output array, returns the concatenated output arrays for each array element.
ms.openlocfilehash: bee7002c5a1e80cee7907ff9cb4ebaaedf8e9923
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848635"
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

## <a name="example"></a>Örnek

```qsharp
let Numbers = SequenceI(1, _); // generates numbers starting from 1
let values = FlatMapped(Numbers, [1, 2, 3]);
// values = [1, 1, 2, 1, 2, 3]
```