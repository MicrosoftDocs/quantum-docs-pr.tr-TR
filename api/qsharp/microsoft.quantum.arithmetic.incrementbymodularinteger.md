---
uid: Microsoft.Quantum.Arithmetic.IncrementByModularInteger
title: Incrementbymodularınteger işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementByModularInteger
qsharp.summary: Performs a modular increment of a qubit register by an integer constant.
ms.openlocfilehash: f5bacef299ab0b3627e757abdcaa798cf9b2e7b3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846595"
---
# <a name="incrementbymodularinteger-operation"></a>Incrementbymodularınteger işlemi

Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir tamsayı sabiti ile bir qubit yazmacının modüler artışını gerçekleştirir.

```qsharp
operation IncrementByModularInteger (increment : Int, modulus : Int, target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>Description

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