---
uid: Microsoft.Quantum.Arrays.ForEach
title: ForEach işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ForEach
qsharp.summary: Given an array and an operation that is defined for the elements of the array, returns a new array that consists of the images of the original array under the operation.
ms.openlocfilehash: 90dd6f94408d37d2b32d82e772a482b0e69c523f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848595"
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