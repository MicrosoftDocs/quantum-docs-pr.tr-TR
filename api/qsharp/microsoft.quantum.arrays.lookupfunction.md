---
uid: Microsoft.Quantum.Arrays.LookupFunction
title: LookupFunction işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: LookupFunction
qsharp.summary: Given an array, returns a function which returns elements of that array.
ms.openlocfilehash: db20795719d11138cbdc5a38c0a19d0f247af059
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220782"
---
# <a name="lookupfunction-function"></a>LookupFunction işlevi

Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Dizi verildiğinde, bu dizinin öğelerini döndüren bir işlev döndürür.

```qsharp
function LookupFunction<'T> (array : 'T[]) : (Int -> 'T)
```


## <a name="input"></a>Giriş

### <a name="array--t"></a>dizi: 'T []

Arama işlevi olarak temsil edilecek dizi.



## <a name="output--int---t"></a>Çıkış: [Int](xref:microsoft.quantum.lang-ref.int) -> 't

Bunun `f` gibi bir işlev `f(idx) == f[idx]` .

## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen

Arama işlevi olarak temsil edilen dizinin öğelerinin türü.

## <a name="remarks"></a>Açıklamalar

Bu işlev, işlevleri bağımsız değişkenleri olarak alan işlevler ve işlemlerle birlikte çalışmak için genellikle faydalıdır `Int -> 'T` . Bu, örneğin, bir diziyi belleğin tamamına kaydetme gereksinimini ortadan kaldırmak için işlevin kullanıldığı Oluşturucu temsili kitaplığı içinde yaygın olarak kullanılır.