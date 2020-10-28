---
uid: Microsoft.Quantum.Arrays.Mapped
title: Eşlenen işlev
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Mapped
qsharp.summary: Given an array and a function that is defined for the elements of the array, returns a new array that consists of the images of the original array under the function.
ms.openlocfilehash: 1abb9d6fb1a921b49554bef968442f4f2b346b71
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730154"
---
# <a name="mapped-function"></a>Eşlenen işlev

Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)

Leyebilir [](https://nuget.org/packages/)


Dizi öğeleri için tanımlanan bir dizi ve bir işlev verildiğinde, işlevin altındaki orijinal dizinin görüntülerinden oluşan yeni bir dizi döndürür.

```qsharp
function Mapped<'T, 'U> (mapper : ('T -> 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a>Giriş

### <a name="mapper--t---u"></a>Eşleyici: 'T-> ' U

`'T` `'U` Öğeleri eşlemek için kullanılan öğesinden öğesine bir işlev.


### <a name="array--t"></a>dizi: 'T []

Öğesinden bir dizi öğe `'T` .



## <a name="output--u"></a>Çıkış: ' U []

`'U[]`İşlev tarafından eşlenen öğelerin dizisi `mapper` .

## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen

`array`Öğelerin türü.
### <a name="u"></a>' U

İşlevin sonuç türü `mapper` .

## <a name="remarks"></a>Açıklamalar

İşlevi genel türler için tanımlanmıştır, yani bir dizi `'T[]` ve bir işlev olduğunda `mapper: 'T -> 'U` dizinin öğelerini eşleyebilir ve yeni türde bir dizi üretebilirsiniz `'U[]` .