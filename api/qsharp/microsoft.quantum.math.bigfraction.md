---
uid: Microsoft.Quantum.Math.BigFraction
title: Bigkesir Kullanıcı tanımlı türü
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BigFraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: a8daa54947097b95040a2dfa7a4d1b90bfaff856
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732767"
---
# <a name="bigfraction-user-defined-type"></a>Bigkesir Kullanıcı tanımlı türü

Ad alanı: [Microsoft. hisse. Math](xref:Microsoft.Quantum.Math)

Leyebilir [](https://nuget.org/packages/)


Formun bir Rational numarasını temsil eder `p/q` . Tamsayı, `p` kayıt düzeninin ilk öğesidir ve `q` kayıt düzeninin ikinci öğesidir.

```qsharp

newtype BigFraction = (Numerator : BigInt, Denominator : BigInt);
```



## <a name="named-items"></a>Adlandırılmış öğeler

### <a name="numerator--bigint"></a>Pay: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

Kesirin pay değeri.
### <a name="denominator--bigint"></a>Payda: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

Kesir paydası/