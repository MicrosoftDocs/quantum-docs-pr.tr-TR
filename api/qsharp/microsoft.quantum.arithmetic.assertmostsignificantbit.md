---
uid: Microsoft.Quantum.Arithmetic.AssertMostSignificantBit
title: AssertMostSignificantBit işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertMostSignificantBit
qsharp.summary: Asserts that the most significant qubit of a qubit register representing an unsigned integer is in a particular state.
ms.openlocfilehash: 41381455d1a96970647f887e038f7dff3a4eb204
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223791"
---
# <a name="assertmostsignificantbit-operation"></a>AssertMostSignificantBit işlemi

Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir qubit kayıt 'nın, işaretsiz bir tamsayıyı temsil eden en önemli qubitin belirli bir durumda olduğunu onaylar.

```qsharp
operation AssertMostSignificantBit (value : Result, number : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>Giriş

### <a name="value--__invalidresult__"></a>değer: __geçersiz <Result>__

Belirtilmekte olan en yüksek bit değeri.


### <a name="number--littleendian"></a>Sayı: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

En yüksek bitin denetlenme işaretsiz tamsayı.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Açıklamalar

Bu işlemin denetlenen sürümü denetimleri yoksayar.

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Iç. onaylama](xref:Microsoft.Quantum.Intrinsic.Assert)