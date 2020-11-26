---
uid: Microsoft.Quantum.Arrays.IndexOf
title: IndexOf işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexOf
qsharp.summary: Returns the first index of the first element in an array that satisfies a given predicate. If no such element exists, returns -1.
ms.openlocfilehash: d63b204334611f8f2c3860f9ee1d756f637780e2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221020"
---
# <a name="indexof-function"></a>IndexOf işlevi

Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Belirli bir koşulu karşılayan dizideki ilk öğenin ilk dizinini döndürür. Böyle bir öğe yoksa-1 döndürür.

```qsharp
function IndexOf<'T> (predicate : ('T -> Bool), arr : 'T[]) : Int
```


## <a name="input"></a>Giriş

### <a name="predicate--t---bool"></a>koşul: 'T-> [bool](xref:microsoft.quantum.lang-ref.bool)

Dizi öğelerini davranan bir koşul işlevi.


### <a name="arr--t"></a>ARR: 'T []

Verilen koşul kullanılarak aranacak bir dizi.



## <a name="output--int"></a>Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)

En küçük dizin ya da `idx` `predicate(arr[idx])` böyle bir öğe yoksa-1.

## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen

