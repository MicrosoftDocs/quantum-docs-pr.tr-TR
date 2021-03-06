---
uid: Microsoft.Quantum.Math.Fraction
title: Kesir Kullanıcı tanımlı türü
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: Fraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: a56d28e34938729a8e4ffda5f870e0b6a25be017
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857507"
---
# <a name="fraction-user-defined-type"></a>Kesir Kullanıcı tanımlı türü

Ad alanı: [Microsoft. hisse. Math](xref:Microsoft.Quantum.Math)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Formun bir Rational numarasını temsil eder `p/q` . Tamsayı, `p` kayıt düzeninin ilk öğesidir ve `q` kayıt düzeninin ikinci öğesidir.

```qsharp

newtype Fraction = (Numerator : Int, Denominator : Int);
```



## <a name="named-items"></a>Adlandırılmış öğeler

### <a name="numerator--int"></a>Pay: [Int](xref:microsoft.quantum.lang-ref.int)

Kesirin pay değeri.
### <a name="denominator--int"></a>Payda: [Int](xref:microsoft.quantum.lang-ref.int)

Kesir paydası/