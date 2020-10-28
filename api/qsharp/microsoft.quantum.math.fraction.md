---
uid: Microsoft.Quantum.Math.Fraction
title: Kesir Kullanıcı tanımlı türü
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: Fraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: 350d470c374fc8e0a3f4c4a9a68ad8566ab88727
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733023"
---
# <a name="fraction-user-defined-type"></a>Kesir Kullanıcı tanımlı türü

Ad alanı: [Microsoft. hisse. Math](xref:Microsoft.Quantum.Math)

Leyebilir [](https://nuget.org/packages/)


Formun bir Rational numarasını temsil eder `p/q` . Tamsayı, `p` kayıt düzeninin ilk öğesidir ve `q` kayıt düzeninin ikinci öğesidir.

```qsharp

newtype Fraction = (Numerator : Int, Denominator : Int);
```



## <a name="named-items"></a>Adlandırılmış öğeler

### <a name="numerator--int"></a>Pay: [Int](xref:microsoft.quantum.lang-ref.int)

Kesirin pay değeri.
### <a name="denominator--int"></a>Payda: [Int](xref:microsoft.quantum.lang-ref.int)

Kesir paydası/