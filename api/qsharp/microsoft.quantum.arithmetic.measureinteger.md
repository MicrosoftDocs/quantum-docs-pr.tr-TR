---
uid: Microsoft.Quantum.Arithmetic.MeasureInteger
title: Measureınteger işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MeasureInteger
qsharp.summary: Measures the content of a quantum register and converts it to an integer. The measurement is performed with respect to the standard computational basis, i.e., the eigenbasis of `PauliZ`.
ms.openlocfilehash: e3ff06e5cbb2ef8a63e4ad12308b382347c90fc3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222652"
---
# <a name="measureinteger-operation"></a>Measureınteger işlemi

Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir hisse kayıt içeriğini ölçer ve bir tamsayıya dönüştürür. Ölçüm standart hesaplama temeline göre yapılır, yani, ' nin eigenliğine göre yapılır `PauliZ` .

```qsharp
operation MeasureInteger (target : Microsoft.Quantum.Arithmetic.LittleEndian) : Int
```


## <a name="input"></a>Giriş

### <a name="target--littleendian"></a>Hedef: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Küçük endian kodlamasıyla bir hisse kayıt.



## <a name="output--int"></a>Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)

Ölçülen değerini içeren işaretsiz bir tamsayı `target` .

## <a name="remarks"></a>Açıklamalar

Bu işlem, giriş kaydını bir hedef makineye serbest bırakmak için uygun olan $ \ket{00\cnoktalara 0} $ durumuna sıfırlar.

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Canon. Measureıntegerin](xref:Microsoft.Quantum.Canon.MeasureIntegerBE)