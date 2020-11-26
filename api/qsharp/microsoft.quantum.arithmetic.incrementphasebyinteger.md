---
uid: Microsoft.Quantum.Arithmetic.IncrementPhaseByInteger
title: Incrementphasebyınteger işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementPhaseByInteger
qsharp.summary: Increments an unsigned quantum register by a classical integer, using phase rotations.
ms.openlocfilehash: 54b83b3d4460c05478543c51f8f9c0b0e7f5b1fa
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222924"
---
# <a name="incrementphasebyinteger-operation"></a>Incrementphasebyınteger işlemi

Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir işaretsiz hisse kaydetmeyi, bir klasik tamsayı tarafından, aşama döndürmeler kullanılarak arttırır.

```qsharp
operation IncrementPhaseByInteger (increment : Int, target : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>Açıklama

`target`Bir işaretsiz tamsayı $x $ ' i küçük endian kodlamasıyla ve `increment` $a $ ' e eşit olarak kodluyor olduğunu varsayalım.
Daha sonra bu işlem, toplama işleminin gerçekleştiği modül $2 ^ n $, burada $n = \texttt{Length (Target!)} ' nin gerçekleştirildiği, Unitary $ \ket{x} \mapsto \ket{x + a} $ öğesini uygular $.

## <a name="input"></a>Giriş

### <a name="increment--int"></a>artış: [Int](xref:microsoft.quantum.lang-ref.int)

Tarafından `target` arttırılan tamsayı.


### <a name="target--phaselittleendian"></a>Hedef: [Phaselitttaendian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)

Hisse kaydı, Çift (QFT) temelinde küçük endian kodlaması kullanarak işaretsiz bir tamsayıyı kodlama.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Açıklamalar

Artış, hisse senedi kaydı değil, klasik bir sabit olduğundan, devreyi basitleştirdik.

Devre diyagramı ve açıklama için [ sayfa 6 ' nın Arxıv: Quant-pH/0008033v1 sayfasında ](https://arxiv.org/pdf/quant-ph/0008033.pdf#page=6) yer alan şekle bakın.

## <a name="references"></a>Başvurular

- [*Thomas G. Draper*, arxıv: Quant-pH/0008033](https://arxiv.org/pdf/quant-ph/0008033v1.pdf)

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. aritmetik. ıncrementbyınteger](xref:Microsoft.Quantum.Arithmetic.IncrementByInteger)