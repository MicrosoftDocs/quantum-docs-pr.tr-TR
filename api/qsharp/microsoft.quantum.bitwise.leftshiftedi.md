---
uid: Microsoft.Quantum.Bitwise.LeftShiftedI
title: Leftkaydırıcı Tedi işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: LeftShiftedI
qsharp.summary: Shifts the bitwise representation of a number left by a given number of bits.
ms.openlocfilehash: ce68311adf211169c2fb499bb189332370a6d6ac
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729879"
---
# <a name="leftshiftedi-function"></a>Leftkaydırıcı Tedi işlevi

Ad alanı: [Microsoft. hisse. bit düzeyinde](xref:Microsoft.Quantum.Bitwise)

Leyebilir [](https://nuget.org/packages/)


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