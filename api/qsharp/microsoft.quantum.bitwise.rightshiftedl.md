---
uid: Microsoft.Quantum.Bitwise.RightShiftedL
title: Rightkaydırıcı işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: RightShiftedL
qsharp.summary: Shifts the bitwise representation of a number right by a given number of bits.
ms.openlocfilehash: 03ed69c7151e62b91c4a036e301f99b45ce5ab62
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842089"
---
# <a name="rightshiftedl-function"></a>Rightkaydırıcı işlevi

Ad alanı: [Microsoft. hisse. bit düzeyinde](xref:Microsoft.Quantum.Bitwise)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir sayının bit düzeyinde gösterimini verilen bit sayısı ile sağa kaydırır.

```qsharp
function RightShiftedL (value : BigInt, amount : Int) : BigInt
```


## <a name="input"></a>Giriş

### <a name="value--bigint"></a>değer: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

Bit düzeyinde temsilinin sağına kaydırılacağı sayı (daha az önemli).


### <a name="amount--int"></a>tutar: [Int](xref:microsoft.quantum.lang-ref.int)

`value`Sağa kaydırılacağı bit sayısı.



## <a name="output--bigint"></a>Çıkış: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

Değeri `value` , bitler tarafından sağa kaydırılan değer `amount` .

## <a name="remarks"></a>Açıklamalar

Aşağıdakiler eşdeğerdir:

```qsharp
let c = a >>> b;
let c = RightShiftedL(a, b);
```