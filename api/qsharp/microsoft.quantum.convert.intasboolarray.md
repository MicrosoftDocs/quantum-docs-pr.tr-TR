---
uid: Microsoft.Quantum.Convert.IntAsBoolArray
title: IntAsBoolArray işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: IntAsBoolArray
qsharp.summary: Produces a binary representation of a positive integer, using the little-endian representation for the returned array.
ms.openlocfilehash: f89cb3d7ca29d7deaaf49573b2670534166caded
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224352"
---
# <a name="intasboolarray-function"></a>IntAsBoolArray işlevi

Ad alanı: [Microsoft. hisse. Convert](xref:Microsoft.Quantum.Convert)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


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