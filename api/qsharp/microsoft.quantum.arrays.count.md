---
uid: Microsoft.Quantum.Arrays.Count
title: Count işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Count
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, returns the number of elements an array that consists of those elements that satisfy the predicate.
ms.openlocfilehash: 48b75cc6d6584f899223a0803f31fd174836f303
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221564"
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

## <a name="remarks"></a>Açıklamalar

İşlevi genel türler için tanımlanmıştır, yani bir dizi `'T[]` ve `'T -> Bool` öğeleri filtreleyebilmemiz için bir koşul.