---
uid: Microsoft.Quantum.Arrays.Count
title: Count işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Count
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, returns the number of elements an array that consists of those elements that satisfy the predicate.
ms.openlocfilehash: e178ee63526e3485e8cc83a3ba8f827d8ecac552
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842844"
---
# <a name="count-function"></a>Count işlevi

Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Dizi öğeleri için tanımlanan bir dizi ve koşul verildiğinde, koşulu karşılayan öğelerden oluşan bir dizi öğe sayısını döndürür.

```qsharp
function Count<'T> (predicate : ('T -> Bool), array : 'T[]) : Int
```


## <a name="input"></a>Giriş

### <a name="predicate--t---bool"></a>koşul: 'T-> [bool](xref:microsoft.quantum.lang-ref.bool)

`'T`Öğeleri filtrelemek için kullanılan Boolean ile bir işlev.


### <a name="array--t"></a>dizi: 'T []

Öğesinden bir dizi öğe `'T` .



## <a name="output--int"></a>Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)

`array`Koşulunu karşılayan öğe sayısı.

## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen

`array`Öğelerin türü.

## <a name="example"></a>Örnek

Aşağıdaki kod "Count" işlevini gösterir.
İşlevi kullanılarak bir koşul tanımlanmıştır @"microsoft.quantum.logical.greaterthani" :

```qsharp
 let predicate = GreaterThanI(_, 5);
 let count = Count(predicate, [2, 5, 9, 1, 8]);
 // count = 2
```

## <a name="remarks"></a>Açıklamalar

İşlevi genel türler için tanımlanmıştır, yani bir dizi `'T[]` ve `'T -> Bool` öğeleri filtreleyebilmemiz için bir koşul.