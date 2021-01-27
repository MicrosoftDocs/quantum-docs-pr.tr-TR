---
uid: Microsoft.Quantum.Math.ComplexPolar
title: Karmaşıkkutupsal Kullanıcı tanımlı tür
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ComplexPolar
qsharp.summary: >-
  Represents a complex number in polar form.

  The polar representation of a complex number is $c=r e^{i t}$.
ms.openlocfilehash: 174e75b82a3ee740cd4d07e5bcd091de65bbc6b6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847342"
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