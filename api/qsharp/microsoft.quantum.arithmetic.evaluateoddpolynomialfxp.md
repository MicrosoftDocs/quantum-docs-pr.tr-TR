---
uid: Microsoft.Quantum.Arithmetic.EvaluateOddPolynomialFxP
title: EvaluateOddPolynomialFxP işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: EvaluateOddPolynomialFxP
qsharp.summary: Evaluates an odd polynomial in a fixed-point representation.
ms.openlocfilehash: 1bf9b6e7c416e994e70b93e5967caefd444f6426
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223230"
---
# <a name="evaluateoddpolynomialfxp-operation"></a>EvaluateOddPolynomialFxP işlemi

Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)

Paket: [Microsoft. hisse. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)


Sabit noktalı bir gösterimde tek bir polinom değerlendirir.

```qsharp
operation EvaluateOddPolynomialFxP (coefficients : Double[], fpx : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a>Giriş

### <a name="coefficients--double"></a>katsayılar: [Double](xref:microsoft.quantum.lang-ref.double)[]

Tek polinom $P (x) = a_0 x + a_1 x ^ 3 + \cnoktalar + a_k x ^ {2k + 1} $ için dizi $ [a_0, a_1,..., a_k] $ için çift dizi olarak tek polinom 'in katsayısıdır.


### <a name="fpx--fixedpoint"></a>FPX: [Fixedpoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

Polinom 'un değerlendirileceği sabit noktalı sayı girin.


### <a name="result--fixedpoint"></a>Sonuç: [Fixedpoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

Çıkış sabit noktalı sayı, P (x) ' i tutacaktır. Başlangıçta $ \ket $ durumunda olmalıdır {0} .



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)

