---
uid: Microsoft.Quantum.Math.BigFraction
title: Bigkesir Kullanıcı tanımlı türü
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BigFraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: bfbf49e7a3d060417e506a1977c20adc08b81f0e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846910"
---
# <a name="bigfraction-user-defined-type"></a>Bigkesir Kullanıcı tanımlı türü

Ad alanı: [Microsoft. hisse. Math](xref:Microsoft.Quantum.Math)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Formun bir Rational numarasını temsil eder `p/q` . Tamsayı, `p` kayıt düzeninin ilk öğesidir ve `q` kayıt düzeninin ikinci öğesidir.

```qsharp

newtype BigFraction = (Numerator : BigInt, Denominator : BigInt);
```



## <a name="named-items"></a>Adlandırılmış öğeler

### <a name="numerator--bigint"></a>Pay: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

Kesirin pay değeri.
### <a name="denominator--bigint"></a>Payda: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

Kesir paydası/