---
uid: Microsoft.Quantum.Arrays.Windows
title: Windows işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Windows
qsharp.summary: Returns all consecutive subarrays of length `size`.
ms.openlocfilehash: 6071d1c3e5981855c57abd0e741b1de0201c30a3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729935"
---
# <a name="windows-function"></a>Windows işlevi

Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)

Leyebilir [](https://nuget.org/packages/)


Tüm birbirini izleyen alt dizileri döndürür `size` .

```qsharp
function Windows<'T> (size : Int, array : 'T[]) : 'T[][]
```


## <a name="description"></a>Açıklama

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