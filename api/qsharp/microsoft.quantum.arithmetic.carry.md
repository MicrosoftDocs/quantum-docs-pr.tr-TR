---
uid: Microsoft.Quantum.Arithmetic.Carry
title: İşlemleri taşıma
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: Carry
qsharp.summary: Implements a reversible carry gate. Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2` and the carry-out is xored to the qubit `carryOut`.
ms.openlocfilehash: 53f8d2a8ba89a912e3d4c08452208a899b2b85de
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223604"
---
# <a name="carry-operation"></a>İşlemleri taşıma

Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Ters bir taşıma geçidi uygular. , Qubit `carryIn` ve ile kodlanmış iki summand bit olarak kodlanmış bir taşıma bit değeri verildiğinden ve bit `summand1` `summand2` düzeyinde xor, `carryIn` `summand1` `summand2` qubit ve `summand2` XORed ise qubit ile birlikte kullanılır `carryOut` .

```qsharp
operation Carry (carryIn : Qubit, summand1 : Qubit, summand2 : Qubit, carryOut : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a>Giriş

### <a name="carryin--qubit"></a>carryIn: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Devam eden qubit.


### <a name="summand1--qubit"></a>summand1: [qubit](xref:microsoft.quantum.lang-ref.qubit)

İlk summve qubit.


### <a name="summand2--qubit"></a>summand2: [qubit](xref:microsoft.quantum.lang-ref.qubit)

İkinci summand qubit, ve toplamının alt bitimiyle değiştirilmiştir `summand1` `summand2` .


### <a name="carryout--qubit"></a>carryOut: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Yerine getirme qubit, toplamın daha yüksek bitine sahip XORed olacaktır.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)

