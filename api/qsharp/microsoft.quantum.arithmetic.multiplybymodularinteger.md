---
uid: Microsoft.Quantum.Arithmetic.MultiplyByModularInteger
title: Multiplybymodularınteger işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyByModularInteger
qsharp.summary: Performs modular multiplication by an integer constant on a qubit register.
ms.openlocfilehash: 6deced7862ab4cb74315219eaaab97380cdf0f92
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730631"
---
# <a name="multiplybymodularinteger-operation"></a>Multiplybymodularınteger işlemi

Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)

Leyebilir [](https://nuget.org/packages/)


Bir qubit kaydındaki tamsayı sabiti ile modüler çarpma gerçekleştirir.

```qsharp
operation MultiplyByModularInteger (constMultiplier : Int, modulus : Int, multiplier : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
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