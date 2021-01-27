---
uid: Microsoft.Quantum.Arithmetic.IncrementByInteger
title: Incrementbyınteger işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementByInteger
qsharp.summary: Increments an unsigned quantum register by a classical integer, using phase rotations.
ms.openlocfilehash: 9c7ff6947964a4dbe07106d1def9be46f631f5cc
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843164"
---
# <a name="incrementbyinteger-operation"></a>Incrementbyınteger işlemi

Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir işaretsiz hisse kaydetmeyi, bir klasik tamsayı tarafından, aşama döndürmeler kullanılarak arttırır.

```qsharp
operation IncrementByInteger (increment : Int, target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>Description

`target`Bir işaretsiz tamsayı $x $ ' i küçük endian kodlamasıyla ve `increment` $a $ ' e eşit olarak kodluyor olduğunu varsayalım.
Daha sonra bu işlem, toplama işleminin gerçekleştiği modül $2 ^ n $, burada $n = \texttt{Length (Target!)} ' nin gerçekleştirildiği, Unitary $ \ket{x} \mapsto \ket{x + a} $ öğesini uygular $.

## <a name="input"></a>Giriş

### <a name="increment--int"></a>artış: [Int](xref:microsoft.quantum.lang-ref.int)

Tarafından `target` arttırılan tamsayı.


### <a name="target--littleendian"></a>Hedef: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Hisse kaydı, küçük endian kodlaması kullanarak işaretsiz bir tamsayıyı kodlayan bir tamsayıdır.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)

