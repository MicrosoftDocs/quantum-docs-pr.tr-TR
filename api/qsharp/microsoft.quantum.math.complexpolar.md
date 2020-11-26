---
uid: Microsoft.Quantum.Math.ComplexPolar
title: Karmaşıkkutupsal Kullanıcı tanımlı tür
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ComplexPolar
qsharp.summary: >-
  Represents a complex number in polar form.

  The polar representation of a complex number is $c=r e^{i t}$.
ms.openlocfilehash: a4f3a7b6ffa73271d7ac9674d8c718f6f09c0291
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210990"
---
# <a name="complexpolar-user-defined-type"></a>Karmaşıkkutupsal Kullanıcı tanımlı tür

Ad alanı: [Microsoft. hisse. Math](xref:Microsoft.Quantum.Math)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Kutupsal biçimdeki karmaşık bir sayıyı temsil eder.

Karmaşık bir sayının kutupsal gösterimi $c = r e ^ {ı t} $.

```qsharp

newtype ComplexPolar = (Magnitude : Double, Argument : Double);
```



## <a name="named-items"></a>Adlandırılmış öğeler

### <a name="magnitude--double"></a>Büyüklük: [Double](xref:microsoft.quantum.lang-ref.double)

Mutlak değer $r \ge $0 $c $.
### <a name="argument--double"></a>Bağımsız değişken: [Double](xref:microsoft.quantum.lang-ref.double)

$C $ öğesinin \mathbb R $ aşaması $t.