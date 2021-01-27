---
uid: Microsoft.Quantum.Arrays.LookupFunction
title: LookupFunction işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: LookupFunction
qsharp.summary: Given an array, returns a function which returns elements of that array.
ms.openlocfilehash: 22b56bb7e9f03ebc5b2225efb2e6450d56022664
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845693"
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