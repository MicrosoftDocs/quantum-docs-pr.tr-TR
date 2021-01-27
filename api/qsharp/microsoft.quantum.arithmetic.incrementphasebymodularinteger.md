---
uid: Microsoft.Quantum.Arithmetic.IncrementPhaseByModularInteger
title: Incrementphasebymodülarınteger işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementPhaseByModularInteger
qsharp.summary: Performs a modular increment of a qubit register by an integer constant.
ms.openlocfilehash: 4ba35010d56ad01c73cb563646dc8150842da12e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846587"
---
# <a name="incrementphasebymodularinteger-operation"></a>Incrementphasebymodülarınteger işlemi

Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir tamsayı sabiti ile bir qubit yazmacının modüler artışını gerçekleştirir.

```qsharp
operation IncrementPhaseByModularInteger (increment : Int, modulus : Int, target : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>Description

`increment`$A $, `modulus` $N $ ile $y $ ' de kodlanmış tamsayı olarak belirlememize izin verin `target` .
Sonra işlem şu dönüşümü gerçekleştirir: \begin{hizalaması} \ket{y} \mapsto \ket{(y + a) \operatorname{mod} N} \end{hizalaması} tamsayılar, QFT 'de küçük endian biçiminde kodlanır.

## <a name="input"></a>Giriş

### <a name="increment--int"></a>artış: [Int](xref:microsoft.quantum.lang-ref.int)

$Y $ öğesine eklenecek $ $a tamsayı artışı.


### <a name="modulus--int"></a>mod: [Int](xref:microsoft.quantum.lang-ref.int)

Integer $N $ bu mods $y + a $.


### <a name="target--phaselittleendian"></a>Hedef: [Phaselitttaendian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)

`increment`$A $ ' nin eklendiği, aşamalı olarak kodlanmış küçük endian biçimindeki tamsayı $y $.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Açıklamalar

`target`En yüksek bit 0 olarak ayarlanmış olduğunu varsayar.
Ayrıca hedefin değerinin $N $ ' den küçük olduğunu varsayar.

Devre diyagramı ve açıklama için, [Arxıv: Quant-pH/, 5095v3 sayfa 5 sayfasında](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=5)Şekil 5 ' i inceleyin.

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. aritmetik. ıncrementbymodularınteger](xref:Microsoft.Quantum.Arithmetic.IncrementByModularInteger)