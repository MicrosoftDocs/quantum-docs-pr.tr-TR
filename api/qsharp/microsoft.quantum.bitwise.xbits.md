---
uid: Microsoft.Quantum.Bitwise.XBits
title: XBits işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: XBits
qsharp.summary: Returns an integer representing the X bits of an array of Pauli operators.
ms.openlocfilehash: 969be01204bad497496ff24cb64213f5fe1f089b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209766"
---
# <a name="xbits-function"></a>XBits işlevi

Ad alanı: [Microsoft. hisse. bit düzeyinde](xref:Microsoft.Quantum.Bitwise)

Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Pauli işleçleri dizisinin X bitlerini temsil eden bir tamsayı döndürür.

```qsharp
function XBits (paulis : Pauli[]) : Int
```


## <a name="input"></a>Giriş

### <a name="paulis--pauli"></a>Paulis: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

Bir tamsayı olarak temsil edilecek Pauli işleçleri dizisi.



## <a name="output--int"></a>Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)

İkili temsili $ (p_ {62} \, P_ {61} \, \noktalar p_0) $ olan bir tamsayı $x $ \, , burada $p _i = $0, veya ise $p `paulis[i]` `PauliI` `PauliZ` = $1 ' dir `paulis[i]` `PauliX` `PauliY` .

## <a name="remarks"></a>Açıklamalar

Dizi uzunluğu 63 ' den büyükse işlev oluşturulur `paulis` .

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. bit düzeyinde. ZBits](xref:Microsoft.Quantum.Bitwise.ZBits)