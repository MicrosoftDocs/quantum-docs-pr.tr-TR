---
uid: Microsoft.Quantum.Arithmetic.MultiplyAndAddByModularInteger
title: Multiplyandadddbymodülarınteger işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyAndAddByModularInteger
qsharp.summary: Performs a modular multiply-and-add by integer constants on a qubit register.
ms.openlocfilehash: e4de934a5776e80dbf5f0d8334bf806e6a84b743
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846510"
---
# <a name="multiplyandaddbymodularinteger-operation"></a>Multiplyandadddbymodülarınteger işlemi

Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir qubit kaydındaki modüler çarpma ve tamsayı sabitlerine göre ekleme gerçekleştirir.

```qsharp
operation MultiplyAndAddByModularInteger (constMultiplier : Int, modulus : Int, multiplier : Microsoft.Quantum.Arithmetic.LittleEndian, summand : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>Description

Verilen bir mod $N $, sabit çarpanı $a $ ve summand $y $ için $ $ \begin{hizalaması} \ket{x} \ket{b} \mapsto \ket{x} \ket{(b + a \cdot x) \operatorname{mod} N} \end{hizalaması} $ $ eşlemesini uygular.

## <a name="input"></a>Giriş

### <a name="constmultiplier--int"></a>constMultiplier: [Int](xref:microsoft.quantum.lang-ref.int)

Her temel durum etiketine eklenecek bir tamsayı $a.


### <a name="modulus--int"></a>mod: [Int](xref:microsoft.quantum.lang-ref.int)

Mod $N $, ne kadar toplama ve çarpma işlemi yapılır.


### <a name="multiplier--littleendian"></a>çarpan: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Her bir temel durum etiketine eklenecek olan işaretsiz bir tamsayıyı temsil eden bir hisse kaydı `summand` .


### <a name="summand--littleendian"></a>summand: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Bu işlem için hedef olarak kullanılacak işaretsiz bir tamsayıyı temsil eden bir hisse kaydı.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Açıklamalar

- Devre diyagramı ve açıklama için bkz. Şekil 6 ' da [Arxıv: Quant-pH/, 5095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=7)
- Bu işlem, [Arxıv: Quant-pH/, 5095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf) içindeki cmult (a) mod (N) öğesine karşılık gelir

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. aritmetik. Multiplyandadddphasebymodularınteger](xref:Microsoft.Quantum.Arithmetic.MultiplyAndAddPhaseByModularInteger)