---
uid: Microsoft.Quantum.Bitwise.XBits
title: XBits işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: XBits
qsharp.summary: Returns an integer representing the X bits of an array of Pauli operators.
ms.openlocfilehash: 91619803c7efe56e617b16637f5302aa0b7978ec
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729810"
---
# <a name="xbits-function"></a>XBits işlevi

Ad alanı: [Microsoft. hisse. bit düzeyinde](xref:Microsoft.Quantum.Bitwise)

Leyebilir [](https://nuget.org/packages/)


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