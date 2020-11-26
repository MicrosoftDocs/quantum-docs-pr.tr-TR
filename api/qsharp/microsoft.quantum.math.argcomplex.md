---
uid: Microsoft.Quantum.Math.ArgComplex
title: ArgComplex işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ArgComplex
qsharp.summary: Returns the phase of a complex number of type `Complex`.
ms.openlocfilehash: 259296f397207cde4a7d6dfe6cfb1a18e8055216
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211109"
---
# <a name="argcomplex-function"></a>ArgComplex işlevi

Ad alanı: [Microsoft. hisse. Math](xref:Microsoft.Quantum.Math)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Karmaşık sayıda türden aşamayı döndürür `Complex` .

```qsharp
function ArgComplex (input : Microsoft.Quantum.Math.Complex) : Double
```


## <a name="input"></a>Giriş

### <a name="input--complex"></a>Giriş: [karmaşık](xref:Microsoft.Quantum.Math.Complex)

Karmaşık sayı $c = x + i y $.



## <a name="output--double"></a>Çıkış: [Double](xref:microsoft.quantum.lang-ref.double)

Aşama $ \text{Arg} [c] = \text{ArcTan} (y, x) \In (-\pi, \pi] $).