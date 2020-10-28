---
uid: Microsoft.Quantum.Math.ArgComplex
title: ArgComplex işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ArgComplex
qsharp.summary: Returns the phase of a complex number of type `Complex`.
ms.openlocfilehash: 629aa32ad80e5aa3d6f5ff75ac65df9b1a96fc15
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732799"
---
# <a name="argcomplex-function"></a>ArgComplex işlevi

Ad alanı: [Microsoft. hisse. Math](xref:Microsoft.Quantum.Math)

Leyebilir [](https://nuget.org/packages/)


Karmaşık sayıda türden aşamayı döndürür `Complex` .

```qsharp
function ArgComplex (input : Microsoft.Quantum.Math.Complex) : Double
```


## <a name="input"></a>Giriş

### <a name="input--complex"></a>Giriş: [karmaşık](xref:Microsoft.Quantum.Math.Complex)

Karmaşık sayı $c = x + i y $.



## <a name="output--double"></a>Çıkış: [Double](xref:microsoft.quantum.lang-ref.double)

Aşama $ \text{Arg} [c] = \text{ArcTan} (y, x) \In (-\pi, \pi] $).