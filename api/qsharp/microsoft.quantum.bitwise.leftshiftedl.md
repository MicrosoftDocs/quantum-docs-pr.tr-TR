---
uid: Microsoft.Quantum.Bitwise.LeftShiftedL
title: Leftlatedl işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: LeftShiftedL
qsharp.summary: Shifts the bitwise representation of a number left by a given number of bits.
ms.openlocfilehash: 17e5c845755f74e9703381bc82bfd63be836d038
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729858"
---
# <a name="leftshiftedl-function"></a>Leftlatedl işlevi

Ad alanı: [Microsoft. hisse. bit düzeyinde](xref:Microsoft.Quantum.Bitwise)

Leyebilir [](https://nuget.org/packages/)


Bir sayının bit düzeyinde gösterimini verilen bit sayısı ile sola kaydırır.

```qsharp
function LeftShiftedL (value : BigInt, amount : Int) : BigInt
```


## <a name="input"></a>Giriş

### <a name="value--bigint"></a>değer: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

Bit düzeyinde temsilinin sola kaydırılacağı sayı (daha fazla önemli).


### <a name="amount--int"></a>tutar: [Int](xref:microsoft.quantum.lang-ref.int)

`value`Sola kaydırılacağı bit sayısı.



## <a name="output--bigint"></a>Çıkış: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

`value`Bit olarak sola kaydırılan değeri `amount` .

## <a name="remarks"></a>Açıklamalar

Aşağıdakiler eşdeğerdir:

```Q#
let c = a <<< b;
let c = LeftShiftedL(a, b);
```