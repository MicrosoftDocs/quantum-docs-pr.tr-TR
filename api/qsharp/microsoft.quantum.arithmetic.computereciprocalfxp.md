---
uid: Microsoft.Quantum.Arithmetic.ComputeReciprocalFxP
title: ComputeReciprocalFxP işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ComputeReciprocalFxP
qsharp.summary: Computes $1/x$ for a fixed-point number $x$.
ms.openlocfilehash: db7425f1a8a9b5ddfdc6b123dad003298e3670e6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843253"
---
# <a name="computereciprocalfxp-operation"></a>ComputeReciprocalFxP işlemi

Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)

Paket: [Microsoft. hisse. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)


$1/x $ ' i $x $ bir sabit noktalı sayı için hesaplar.

```qsharp
operation ComputeReciprocalFxP (x : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a>Giriş

### <a name="x--fixedpoint"></a>x: [Fixedpoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

Ters çevrilme yapılacak sabit nokta sayısı.


### <a name="result--fixedpoint"></a>Sonuç: [Fixedpoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

Sonucu alacak sabit noktalı sayı. $ \Ket{0.0} $ olarak başlatılmalıdır.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)

