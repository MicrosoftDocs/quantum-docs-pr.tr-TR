---
uid: Microsoft.Quantum.Arithmetic.IncrementPhaseByModularInteger
title: Incrementphasebymodülarınteger işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementPhaseByModularInteger
qsharp.summary: Performs a modular increment of a qubit register by an integer constant.
ms.openlocfilehash: 52309c056a3eae25ffdfbfa848f94bf744c71132
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731474"
---
# <a name="incrementphasebymodularinteger-operation"></a>Incrementphasebymodülarınteger işlemi

Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)

Leyebilir [](https://nuget.org/packages/)


Bir tamsayı sabiti ile bir qubit yazmacının modüler artışını gerçekleştirir.

```qsharp
operation IncrementPhaseByModularInteger (increment : Int, modulus : Int, target : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit
```


## <a name="description"></a>Açıklama

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