---
uid: Microsoft.Quantum.Arithmetic.MultiplyByModularInteger
title: Multiplybymodularınteger işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyByModularInteger
qsharp.summary: Performs modular multiplication by an integer constant on a qubit register.
ms.openlocfilehash: bd4e0ad6c5bad779d9a31139690021fd9fcda210
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846503"
---
# <a name="multiplybymodularinteger-operation"></a>Multiplybymodularınteger işlemi

Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir qubit kaydındaki tamsayı sabiti ile modüler çarpma gerçekleştirir.

```qsharp
operation MultiplyByModularInteger (constMultiplier : Int, modulus : Int, multiplier : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>Description

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