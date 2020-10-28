---
uid: Microsoft.Quantum.Bitwise.ZBits
title: ZBits işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: ZBits
qsharp.summary: Returns an integer representing the Z bits of an array of Pauli operators.
ms.openlocfilehash: f66b8ef0370e898dd1d095ff2840c91566f32cb8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729791"
---
# <a name="zbits-function"></a>ZBits işlevi

Ad alanı: [Microsoft. hisse. bit düzeyinde](xref:Microsoft.Quantum.Bitwise)

Leyebilir [](https://nuget.org/packages/)


Pauli işleçleri dizisinin Z bitlerini temsil eden bir tamsayı döndürür.

```qsharp
function ZBits (paulis : Pauli[]) : Int
```


## <a name="input"></a>Giriş

### <a name="paulis--pauli"></a>Paulis: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

Bir tamsayı olarak temsil edilecek Pauli işleçleri dizisi.



## <a name="output--int"></a>Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)

İkili temsili $ (p_ {62} \, P_ {61} \, \noktalar p_0) $ olan bir tamsayı $x $ \, , burada $p _i = $0, veya ise $p `paulis[i]` `PauliI` `PauliX` = $1 ' dir `paulis[i]` `PauliY` `PauliZ` .

## <a name="remarks"></a>Açıklamalar

Dizi uzunluğu 63 ' den büyükse işlev oluşturulur `paulis` .

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. bit düzeyinde. Xbit](xref:Microsoft.Quantum.Bitwise.XBits)