---
uid: Microsoft.Quantum.Arithmetic.MeasureInteger
title: Measureınteger işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MeasureInteger
qsharp.summary: Measures the content of a quantum register and converts it to an integer. The measurement is performed with respect to the standard computational basis, i.e., the eigenbasis of `PauliZ`.
ms.openlocfilehash: 288aee24e0ae6425db35312b560630a6bb9bfc80
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843115"
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