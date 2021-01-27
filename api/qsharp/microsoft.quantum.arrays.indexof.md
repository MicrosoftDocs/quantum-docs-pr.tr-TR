---
uid: Microsoft.Quantum.Arrays.IndexOf
title: IndexOf işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexOf
qsharp.summary: Returns the first index of the first element in an array that satisfies a given predicate. If no such element exists, returns -1.
ms.openlocfilehash: 64db55e831078a7130a3ced6a30bfbd2299c392d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848521"
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



## <a name="example"></a>Örnek

Öğesinin `IsEven : Int -> Bool` `true` ve yalnızca girdisi çift ise, döndüren bir işlev olduğunu varsayalım. Bu durumda, `IndexOf` bir dizideki ilk çift öğeyi bulmak için ile kullanılabilir:

```qsharp
let items = [1, 3, 17, 2, 21];
let idx = IndexOf(IsEven, items); // returns 3
```