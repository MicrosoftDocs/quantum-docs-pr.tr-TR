---
uid: Microsoft.Quantum.Arithmetic.Sum
title: Toplam işlem
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: Sum
qsharp.summary: Implements a reversible sum gate. Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2`.
ms.openlocfilehash: 7758e29c9f08f4d05253defbe5a43a5316289522
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221802"
---
# <a name="sum-operation"></a>Toplam işlem

Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Ters çevrilebilir bir toplam kapısı uygular. , Qubit `carryIn` ve ile kodlanmış iki summand bit ile kodlanmış bir birlikte alma bit ve `summand1` ve ' de ve, `summand2` `carryIn` `summand1` `summand2` qubit 'in bit düzeyinde xor değeri hesaplar `summand2` .

```qsharp
operation Sum (carryIn : Qubit, summand1 : Qubit, summand2 : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a>Giriş

### <a name="carryin--qubit"></a>carryIn: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Devam eden qubit.


### <a name="summand1--qubit"></a>summand1: [qubit](xref:microsoft.quantum.lang-ref.qubit)

İlk summve qubit.


### <a name="summand2--qubit"></a>summand2: [qubit](xref:microsoft.quantum.lang-ref.qubit)

İkinci summand qubit, ve toplamının alt bitimiyle değiştirilmiştir `summand1` `summand2` .



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Açıklamalar

`Carry`İşlemin aksine, bu, yerine getirme bitini hesaplamaz.