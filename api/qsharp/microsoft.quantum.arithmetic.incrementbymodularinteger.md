---
uid: Microsoft.Quantum.Arithmetic.IncrementByModularInteger
title: Incrementbymodularınteger işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementByModularInteger
qsharp.summary: Performs a modular increment of a qubit register by an integer constant.
ms.openlocfilehash: 8a02d22facce8f58180752b6d063ac55d75ca537
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222958"
---
# <a name="incrementbymodularinteger-operation"></a>Incrementbymodularınteger işlemi

Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir tamsayı sabiti ile bir qubit yazmacının modüler artışını gerçekleştirir.

```qsharp
operation IncrementByModularInteger (increment : Int, modulus : Int, target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>Açıklama

`increment`$A $, `modulus` $N $ ile $y $ ' de kodlanmış tamsayı olarak belirlememize izin verin `target` .
Sonra işlem şu dönüşümü gerçekleştirir: \begin{hizalaması} \ket{y} \mapsto \ket{(y + a) \operatorname{mod} N} \end{hizalaması} tamsayılar küçük endian biçiminde kodlanır.

## <a name="input"></a>Giriş

### <a name="increment--int"></a>artış: [Int](xref:microsoft.quantum.lang-ref.int)

$Y $ öğesine eklenecek $ $a tamsayı artışı.


### <a name="modulus--int"></a>mod: [Int](xref:microsoft.quantum.lang-ref.int)

Integer $N $ bu mods $y + a $.


### <a name="target--littleendian"></a>Hedef: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

`LittleEndian`$A $ 'in eklendiği biçimde $y $ tamsayı `increment` .



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Açıklamalar

Hedefin başlangıç değerinin $N $ ' den küçük olduğunu ve artış $a $ değerinin $N $ ' den küçük olduğunu varsayar.
<xref:microsoft.quantum.arithmetic.incrementphasebymodularinteger>Aynı işlemi temelde uygulayan unutmayın `PhaseLittleEndian` .

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. aritmetik. ıncrementphasebymodularınteger](xref:Microsoft.Quantum.Arithmetic.IncrementPhaseByModularInteger)