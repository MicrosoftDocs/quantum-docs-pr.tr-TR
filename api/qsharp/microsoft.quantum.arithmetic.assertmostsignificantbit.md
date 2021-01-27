---
uid: Microsoft.Quantum.Arithmetic.AssertMostSignificantBit
title: AssertMostSignificantBit işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertMostSignificantBit
qsharp.summary: Asserts that the most significant qubit of a qubit register representing an unsigned integer is in a particular state.
ms.openlocfilehash: b0b52a4ba7492d68896669aeb0b6b550d2f27f64
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843416"
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