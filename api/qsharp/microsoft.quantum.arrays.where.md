---
uid: Microsoft.Quantum.Arrays.Where
title: WHERE işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Where
qsharp.summary: Given a predicate and an array, returns the indices of that array where the predicate is true.
ms.openlocfilehash: 4a938114689177f7a9ee182e6e5f36debe4edac7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842213"
---
# <a name="where-function"></a>WHERE işlevi

Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Koşul ve dizi verildiğinde, koşulun true olduğu bu dizinin dizinlerini döndürür.

```qsharp
function Where<'T> (predicate : ('T -> Bool), array : 'T[]) : Int[]
```


## <a name="input"></a>Giriş

### <a name="predicate--t---bool"></a>koşul: 'T-> [bool](xref:microsoft.quantum.lang-ref.bool)

`'T`Öğeleri filtrelemek için kullanılan Boolean ile bir işlev.


### <a name="array--t"></a>dizi: 'T []

Öğesinden bir dizi öğe `'T` .



## <a name="output--int"></a>Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)[]

True olan bir dizin dizisi `predicate` .

## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen

`array`Öğelerin türü.