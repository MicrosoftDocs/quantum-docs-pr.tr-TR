---
uid: Microsoft.Quantum.Arithmetic.MultiplyByModularInteger
title: Multiplybymodularınteger işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyByModularInteger
qsharp.summary: Performs modular multiplication by an integer constant on a qubit register.
ms.openlocfilehash: 080414d208a2a0c114857db8e93efb4cd74a4d8d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222584"
---
# <a name="multiplybymodularinteger-operation"></a>Multiplybymodularınteger işlemi

Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir qubit kaydındaki tamsayı sabiti ile modüler çarpma gerçekleştirir.

```qsharp
operation MultiplyByModularInteger (constMultiplier : Int, modulus : Int, multiplier : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>Açıklama

`modulus`$N $ ve $a $ ile bu şekilde bir daha sunmamıza izin verin `constMultiplier` .
Bu işlem, şu eşleme tarafından hesaplama temelinde tanımlanan bir Unitary işlemi uygular: $ $ \begin{hizalaması} \ket{y} \mapsto \ket{(a \cdot y) \operatorname{mod} N} \end{hizalaması} $ $ ile $0 $ ve $N-$1 arasında tüm $y $.

## <a name="input"></a>Giriş

### <a name="constmultiplier--int"></a>constMultiplier: [Int](xref:microsoft.quantum.lang-ref.int)

Çarpanın çarpıldığı sabit. Mod için ortak ana olmalıdır.


### <a name="modulus--int"></a>mod: [Int](xref:microsoft.quantum.lang-ref.int)

Çarpma işlemi, mod gerçekleştirdi `modulus` .


### <a name="multiplier--littleendian"></a>çarpan: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Bir sabit ile Çarpılmakta olan sayı.
Bu, küçük endian biçimindeki bir tamsayıyı kodlayan bir qubits dizisidir.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Açıklamalar

- Devre diyagramı ve açıklama için, bkz. Şekil 7 [-Arxıv: Quant-pH/, 5095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=8)
- Bu işlem, [Arxıv: Quant-pH/, 5095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf) içindeki u ₐ 'a karşılık gelir