---
uid: Microsoft.Quantum.Bitwise.LeftShiftedI
title: Leftkaydırıcı Tedi işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: LeftShiftedI
qsharp.summary: Shifts the bitwise representation of a number left by a given number of bits.
ms.openlocfilehash: 3a7220489bfa241e2337df14291bafb1d6e0e19e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209868"
---
# <a name="leftshiftedi-function"></a>Leftkaydırıcı Tedi işlevi

Ad alanı: [Microsoft. hisse. bit düzeyinde](xref:Microsoft.Quantum.Bitwise)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir sayının bit düzeyinde gösterimini verilen bit sayısı ile sola kaydırır.

```qsharp
function LeftShiftedI (value : Int, amount : Int) : Int
```


## <a name="input"></a>Giriş

### <a name="value--int"></a>değer: [Int](xref:microsoft.quantum.lang-ref.int)

Bit düzeyinde temsilinin sola kaydırılacağı sayı (daha fazla önemli).


### <a name="amount--int"></a>tutar: [Int](xref:microsoft.quantum.lang-ref.int)

`value`Sola kaydırılacağı bit sayısı.



## <a name="output--int"></a>Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)

`value`Bit olarak sola kaydırılan değeri `amount` .

## <a name="remarks"></a>Açıklamalar

Aşağıdakiler eşdeğerdir:

```Q#
let c = a <<< b;
let c = LeftShiftedI(a, b);
```