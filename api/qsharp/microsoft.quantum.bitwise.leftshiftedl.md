---
uid: Microsoft.Quantum.Bitwise.LeftShiftedL
title: Leftlatedl işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: LeftShiftedL
qsharp.summary: Shifts the bitwise representation of a number left by a given number of bits.
ms.openlocfilehash: 014653011574d0fabb4b9aa04cedf58b87ddf798
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842150"
---
# <a name="leftshiftedl-function"></a>Leftlatedl işlevi

Ad alanı: [Microsoft. hisse. bit düzeyinde](xref:Microsoft.Quantum.Bitwise)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


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

```qsharp
let c = a <<< b;
let c = LeftShiftedL(a, b);
```