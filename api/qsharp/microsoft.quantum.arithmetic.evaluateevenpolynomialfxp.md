---
uid: Microsoft.Quantum.Arithmetic.EvaluateEvenPolynomialFxP
title: EvaluateEvenPolynomialFxP işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: EvaluateEvenPolynomialFxP
qsharp.summary: Evaluates an even polynomial in a fixed-point representation.
ms.openlocfilehash: c3129cb796a344f7ad38a585183db285d48892bf
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843240"
---
# <a name="evaluateevenpolynomialfxp-operation"></a>EvaluateEvenPolynomialFxP işlemi

Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)

Paket: [Microsoft. hisse. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)


Sabit noktalı bir gösterimde çift bir polinom değerlendirir.

```qsharp
operation EvaluateEvenPolynomialFxP (coefficients : Double[], fpx : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a>Giriş

### <a name="coefficients--double"></a>katsayılar: [Double](xref:microsoft.quantum.lang-ref.double)[]

Çift bir dizi olarak eşit polinom 'un katsayısı; Yani, Çift polinom $P (x) = a_0 + a_1 x ^ 2 + \cnoktalar + a_k x ^ {2k} $ için dizi $ [a_0, a_1,..., a_k] $.


### <a name="fpx--fixedpoint"></a>FPX: [Fixedpoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

Polinom 'un değerlendirileceği sabit noktalı sayı girin.


### <a name="result--fixedpoint"></a>Sonuç: [Fixedpoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

$P (x) $ ' i barındıracak olan çıkış sabit noktası numarası. Başlangıçta $ \ket $ durumunda olmalıdır {0} .



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)

