---
uid: Microsoft.Quantum.Arithmetic.MultiplyAndAddPhaseByModularInteger
title: Multiplyandadddphasebymodularınteger işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyAndAddPhaseByModularInteger
qsharp.summary: The same as MultiplyAndAddByModularInteger, but assumes that the summand encodes integers in QFT basis.
ms.openlocfilehash: b1214acc2cafc3fede9fcb6663a435c0b1d2cf4a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843072"
---
# <a name="multiplyandaddphasebymodularinteger-operation"></a>Multiplyandadddphasebymodularınteger işlemi

Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Multiplyandavddbymodularınteger ile aynıdır, ancak summve tamsayıların QFT temelinde kodladığını varsayar.

```qsharp
operation MultiplyAndAddPhaseByModularInteger (constMultiplier : Int, modulus : Int, multiplier : Microsoft.Quantum.Arithmetic.LittleEndian, phaseSummand : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>Giriş

### <a name="constmultiplier--int"></a>constMultiplier: [Int](xref:microsoft.quantum.lang-ref.int)

Her temel durum etiketine eklenecek bir tamsayı $a.


### <a name="modulus--int"></a>mod: [Int](xref:microsoft.quantum.lang-ref.int)

Mod $N $, ne kadar toplama ve çarpma işlemi yapılır.


### <a name="multiplier--littleendian"></a>çarpan: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Her bir temel durum etiketine eklenecek olan işaretsiz bir tamsayıyı temsil eden bir hisse kaydı `summand` .


### <a name="phasesummand--phaselittleendian"></a>phaseSummand: [Phaselitttaendian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)

Bu işlem için hedef olarak kullanılacak işaretsiz bir tamsayıyı temsil eden bir hisse kaydı.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Açıklamalar

`phaseSummand`En yüksek bit 0 olarak ayarlanmış olduğunu varsayar.
Ayrıca değerinin `phaseSummand` $N $ değerinden küçük olduğunu varsayar.

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. aritmetik. Multiplyandadddbymodularınteger](xref:Microsoft.Quantum.Arithmetic.MultiplyAndAddByModularInteger)