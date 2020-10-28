---
uid: Microsoft.Quantum.Arrays.LookupFunction
title: LookupFunction işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: LookupFunction
qsharp.summary: Given an array, returns a function which returns elements of that array.
ms.openlocfilehash: c929054b96ee499db896cacf0e3ae4da6f6c4b98
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730151"
---
# <a name="lookupfunction-function"></a>LookupFunction işlevi

Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)

Leyebilir [](https://nuget.org/packages/)


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