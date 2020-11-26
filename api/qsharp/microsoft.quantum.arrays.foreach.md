---
uid: Microsoft.Quantum.Arrays.ForEach
title: ForEach işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ForEach
qsharp.summary: Given an array and an operation that is defined for the elements of the array, returns a new array that consists of the images of the original array under the operation.
ms.openlocfilehash: b362d28e77c8dea2b3daeed4a4d605e1dd42e487
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221156"
---
# <a name="foreach-operation"></a>ForEach işlemi

Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Dizi öğeleri için tanımlanan bir dizi ve bir işlem verildiğinde, işlem altındaki orijinal dizinin görüntülerinden oluşan yeni bir dizi döndürür.

```qsharp
operation ForEach<'T, 'U> (action : ('T => 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a>Giriş

### <a name="action--t--u"></a>eylem: 'T => ' U 

`'T`Her öğesine öğesinden öğesine bir işlem `'U` uygulanır.


### <a name="array--t"></a>dizi: 'T []

Öğesinden bir dizi öğe `'T` .



## <a name="output--u"></a>Çıkış: ' U []

`'U[]`İşlem tarafından eşlenen öğelerin dizisi `action` .

## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen

`array`Öğelerin türü.
### <a name="u"></a>' U

İşlemin sonuç türü `action` .

## <a name="remarks"></a>Açıklamalar

İşlem genel türler için tanımlanmıştır, yani bir dizi `'T[]` ve bir işlem olduğunda `action : 'T -> 'U` dizinin öğelerini eşleyebilir ve yeni türde bir dizi üretebilir `'U[]` .