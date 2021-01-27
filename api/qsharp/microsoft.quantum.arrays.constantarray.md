---
uid: Microsoft.Quantum.Arrays.ConstantArray
title: ConstantArray işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ConstantArray
qsharp.summary: Creates an array of given length with all elements equal to given value.
ms.openlocfilehash: a3ad8a18856888a0ca6f9dd691242156b0c044d8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846242"
---
# <a name="constantarray-function"></a>ConstantArray işlevi

Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Verilen değere eşit tüm öğelerle verilen uzunlukta bir dizi oluşturur.

```qsharp
function ConstantArray<'T> (length : Int, value : 'T) : 'T[]
```


## <a name="input"></a>Giriş

### <a name="length--int"></a>Uzunluk: [Int](xref:microsoft.quantum.lang-ref.int)

Yeni dizinin uzunluğu.


### <a name="value--t"></a>değer: 'T

Yeni dizinin her öğesinin değeri.



## <a name="output--t"></a>Çıkış: 'T []

Her öğe için olan yeni bir uzunluk dizisi `length` `value` .

## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen



## <a name="example"></a>Örnek

Aşağıdaki kod, her biri şuna eşit olan 3 Boole değeri dizisi oluşturur `true` :

```qsharp
let array = ConstantArray(3, true);
```