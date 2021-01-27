---
uid: Microsoft.Quantum.Arithmetic.RippleCarryAdderCDKM
title: Ripptacarryaddercdkm işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: RippleCarryAdderCDKM
qsharp.summary: Reversible, in-place ripple-carry addition of two integers.
ms.openlocfilehash: df9b62b649af532a4202aacc3e8dd4613eb8665d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846355"
---
# <a name="ripplecarryaddercdkm-operation"></a>Ripptacarryaddercdkm işlemi

Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Tersine çevrilebilir, yerinde Ripple-iki tamsayının eklenmesini taşır.

```qsharp
operation RippleCarryAdderCDKM (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, carry : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a>Description

Litttaendian Yazmaçları ve ile kodlanmış iki $n $-bit tamsayılar `xs` ve `ys` bir qubit,, işlem, sonucun $n $ en düşük önemli bitlerinin içinde tutulduğu iki tamsayının toplamını hesaplar `ys` `carry` .

## <a name="input"></a>Giriş

### <a name="xs--littleendian"></a>xs: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Litttaendian qubit yazmaç ilk tamsayı summand ' i çağırır.


### <a name="ys--littleendian"></a>YS: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Litttaendian qubit yazmaç ikinci tamsayı summve, toplamın en az önemli bitini tutacak şekilde değiştirilir.


### <a name="carry--qubit"></a>taşır: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit ' i taşır, toplamın en önemli biti ile XORed.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Açıklamalar

Bu işlem, Rippelcarryadderd ile aynı işlevselliğe sahiptir, ancak $n $ yerine yalnızca bir yardımcı qubit kullanır.

## <a name="references"></a>Başvurular

- Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutın, David Petrie Moulton: "yeni bir 2004 hisse
  https://arxiv.org/abs/quant-ph/0410184v1