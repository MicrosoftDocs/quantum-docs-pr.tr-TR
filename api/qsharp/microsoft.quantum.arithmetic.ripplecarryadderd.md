---
uid: Microsoft.Quantum.Arithmetic.RippleCarryAdderD
title: Ripptacarryadderd işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: RippleCarryAdderD
qsharp.summary: Reversible, in-place ripple-carry addition of two integers. Given two $n$-bit integers encoded in LittleEndian registers `xs` and `ys`, and a qubit carry, the operation computes the sum of the two integers where the $n$ least significant bits of the result are held in `ys` and the carry out bit is xored to the qubit `carry`.
ms.openlocfilehash: b87c8f25acc8854d5e8d28f58cfc99dffb92a973
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222125"
---
# <a name="ripplecarryadderd-operation"></a>Ripptacarryadderd işlemi

Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Tersine çevrilebilir, yerinde Ripple-iki tamsayının eklenmesini taşır.
Litttaendian Yazmaçları ve ile kodlanmış iki $n $-bit tamsayılar `xs` ve `ys` bir qubit,, işlem, sonucun $n $ en düşük önemli bitlerinin içinde tutulduğu iki tamsayının toplamını hesaplar `ys` `carry` .

```qsharp
operation RippleCarryAdderD (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, carry : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a>Giriş

### <a name="xs--littleendian"></a>xs: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Litttaendian qubit yazmaç ilk tamsayı summand ' i çağırır.


### <a name="ys--littleendian"></a>YS: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Litttaendian qubit yazmaç ikinci tamsayı summve, toplamın $n $ en az önemli bitini tutacak şekilde değiştirildi.


### <a name="carry--qubit"></a>taşır: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit ' i taşır, toplamın en önemli biti ile XORed.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Açıklamalar

Belirtilen denetlenen işlem, her işleme bir denetim ekleyen varsayılan uygulamada geliştirme yapmak için simetri ve karşılıklı işlem iptali kullanımını sağlar.

## <a name="references"></a>Başvurular

- Thomas G. Draper: "hisse bir bilgisayara ek ekleme", 2000.
  https://arxiv.org/abs/quant-ph/0008033