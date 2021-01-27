---
uid: Microsoft.Quantum.Arrays.Windows
title: Windows işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Windows
qsharp.summary: Returns all consecutive subarrays of length `size`.
ms.openlocfilehash: adfea2b9a2f6c22446817538d29586284dba723e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842204"
---
# <a name="windows-function"></a>Windows işlevi

Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Tüm birbirini izleyen alt dizileri döndürür `size` .

```qsharp
function Windows<'T> (size : Int, array : 'T[]) : 'T[][]
```


## <a name="description"></a>Description

Bu işlev, tüm `n - size + 1` alt dizileri sırasıyla döndürür `size` , burada olduğu gibi `n` `arr` .
İlk alt diziler `arr[0..size - 1], arr[1..size], arr[2..size + 1]` son alt diziye kadar `arr[n - size..n - 1]` .

`size <= 0`Veya ise `size > n` boş bir dizi döndürülür.

## <a name="input"></a>Giriş

### <a name="size--int"></a>Boyut: [Int](xref:microsoft.quantum.lang-ref.int)

Alt dizilerin uzunluğu.


### <a name="array--t"></a>dizi: 'T []

Bir dizi öğe.



## <a name="output--t"></a>Çıkış: 'T [] []



## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen

`array`Öğelerin türü.

## <a name="example"></a>Örnek

```qsharp
// same as [[1, 2, 3], [2, 3, 4], [3, 4, 5]]
let windows = Windows(3, [1, 2, 3, 4, 5]);
```