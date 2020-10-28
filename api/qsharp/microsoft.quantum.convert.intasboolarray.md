---
uid: Microsoft.Quantum.Convert.IntAsBoolArray
title: IntAsBoolArray işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: IntAsBoolArray
qsharp.summary: Produces a binary representation of a positive integer, using the little-endian representation for the returned array.
ms.openlocfilehash: 9783a49a77bdc39ffe8c7725196eb620f4cd0100
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727536"
---
# <a name="intasboolarray-function"></a>IntAsBoolArray işlevi

Ad alanı: [Microsoft. hisse. Convert](xref:Microsoft.Quantum.Convert)

Leyebilir [](https://nuget.org/packages/)


Döndürülen dizi için küçük endian gösterimini kullanarak pozitif bir tam sayının ikili gösterimini üretir.

```qsharp
function IntAsBoolArray (number : Int, bits : Int) : Bool[]
```


## <a name="input"></a>Giriş

### <a name="number--int"></a>Sayı: [Int](xref:microsoft.quantum.lang-ref.int)

Boole değerleri dizisine dönüştürülecek pozitif bir tamsayı.


### <a name="bits--int"></a>bit: [Int](xref:microsoft.quantum.lang-ref.int)

Öğesinin ikili temsilindeki bit sayısı `number` .



## <a name="output--bool"></a>Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)[]

Temsil eden bir Boole değerleri dizisi `number` .

## <a name="remarks"></a>Açıklamalar

Giriş `bits` 0 ile 63 arasında olmalıdır.
Giriş `number` 0 ile $2 ^ {\texttt{bits}}-$1 arasında olmalıdır.