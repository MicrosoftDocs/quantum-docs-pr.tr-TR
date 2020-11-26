---
uid: Microsoft.Quantum.Arithmetic.CompareGreaterThanFxP
title: CompareGreaterThanFxP işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareGreaterThanFxP
qsharp.summary: Compares two fixed-point numbers stored in quantum registers, and controls a flip on the result.
ms.openlocfilehash: 1e9afc7645f62b932fa8ebc3d33e21a2a5182361
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223536"
---
# <a name="comparegreaterthanfxp-operation"></a>CompareGreaterThanFxP işlemi

Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)

Paket: [Microsoft. hisse. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)


Hisse Yazmaçları içinde depolanan iki sabit noktalı sayıyı karşılaştırır ve sonucu üzerinde bir çevir denetimi yapar.

```qsharp
operation CompareGreaterThanFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint, result : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a>Giriş

### <a name="fp1--fixedpoint"></a>FP1: [Fixedpoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

Karşılaştırılacak ilk sabit noktalı sayı.


### <a name="fp2--fixedpoint"></a>FP2: [Fixedpoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

Karşılaştırılacak ikinci sabit noktalı sayı.


### <a name="result--qubit"></a>Sonuç: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Karşılaştırmanın sonucu. İse çevrilcektir `fp1 > fp2` .



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Açıklamalar

Geçerli uygulama iki sabit noktalı sayının aynı nokta konumuna ve aynı sayıda qubit 'e sahip olmasını gerektirir.