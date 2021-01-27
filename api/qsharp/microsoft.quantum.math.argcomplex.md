---
uid: Microsoft.Quantum.Math.ArgComplex
title: ArgComplex işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ArgComplex
qsharp.summary: Returns the phase of a complex number of type `Complex`.
ms.openlocfilehash: e8ce73a43940ab0ed66338f962cc6f76fc2b694b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842764"
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