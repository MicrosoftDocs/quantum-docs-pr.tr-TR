---
uid: Microsoft.Quantum.Arithmetic.MultiplyFxP
title: Çoğullyfxp işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyFxP
qsharp.summary: Multiplies two fixed-point numbers in quantum registers.
ms.openlocfilehash: 776ccb7a9e1ba1a34b28da6e1cf3a0aafe9da76b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843043"
---
# <a name="multiplyfxp-operation"></a>Çoğullyfxp işlemi

Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)

Paket: [Microsoft. hisse. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)


Hisse kasalarındaki iki sabit noktalı sayıyı çarpar.

```qsharp
operation MultiplyFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a>Giriş

### <a name="fp1--fixedpoint"></a>FP1: [Fixedpoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

İlk sabit noktalı sayı.


### <a name="fp2--fixedpoint"></a>FP2: [Fixedpoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

İkinci sabit noktalı sayı.


### <a name="result--fixedpoint"></a>Sonuç: [Fixedpoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

Sonuç sabit noktalı sayı, başlangıçta $ \ demet $ durumunda olmalıdır {0} .



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Açıklamalar

Geçerli uygulama, üç sabit noktalı sayının aynı nokta konumuna ve aynı sayıda qubit 'e sahip olmasını gerektirir.