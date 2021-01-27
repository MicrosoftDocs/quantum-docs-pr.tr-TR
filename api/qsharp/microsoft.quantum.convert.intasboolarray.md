---
uid: Microsoft.Quantum.Convert.IntAsBoolArray
title: IntAsBoolArray işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: IntAsBoolArray
qsharp.summary: Produces a binary representation of a non-negative integer, using the little-endian representation for the returned array.
ms.openlocfilehash: 8b3d230605cc756a5da01e45e47f91c5b8e9f541
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98833314"
---
# <a name="intasboolarray-function"></a>IntAsBoolArray işlevi

Ad alanı: [Microsoft. hisse. Convert](xref:Microsoft.Quantum.Convert)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Döndürülen dizi için küçük endian gösterimini kullanarak negatif olmayan bir tamsayı için ikili bir temsilini üretir.

```qsharp
function IntAsBoolArray (number : Int, bits : Int) : Bool[]
```


## <a name="input"></a>Giriş

### <a name="number--int"></a>Sayı: [Int](xref:microsoft.quantum.lang-ref.int)

Boole değerleri dizisine dönüştürülecek negatif olmayan bir tamsayı.


### <a name="bits--int"></a>bit: [Int](xref:microsoft.quantum.lang-ref.int)

Öğesinin ikili temsilindeki bit sayısı `number` .



## <a name="output--bool"></a>Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)[]

Temsil eden bir Boole değerleri dizisi `number` .

## <a name="remarks"></a>Açıklamalar

Giriş `bits` 0 ile 63 arasında olmalıdır.
Giriş `number` 0 ile $2 ^ {\texttt{bits}}-$1 arasında olmalıdır.