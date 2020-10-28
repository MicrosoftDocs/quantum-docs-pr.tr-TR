---
uid: Microsoft.Quantum.Math.ComplexPolar
title: Karmaşıkkutupsal Kullanıcı tanımlı tür
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ComplexPolar
qsharp.summary: >-
  Represents a complex number in polar form.

  The polar representation of a complex number is $c=r e^{i t}$.
ms.openlocfilehash: 0c18c3f02cb036f22a68b6e4b46fd19049dc34cc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725904"
---
# <a name="complexpolar-user-defined-type"></a>Karmaşıkkutupsal Kullanıcı tanımlı tür

Ad alanı: [Microsoft. hisse. Math](xref:Microsoft.Quantum.Math)

Leyebilir [](https://nuget.org/packages/)


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