---
uid: Microsoft.Quantum.Arithmetic.IdenticalPointPosFactFxP
title: IdenticalPointPosFactFxP işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IdenticalPointPosFactFxP
qsharp.summary: Assert that all fixed-point numbers in the provided array have identical point positions when counting from the least- significant bit. I.e., number of bits minus point position must be constant for all fixed-point numbers in the array.
ms.openlocfilehash: 907e270e1c3710fb346044ad7757171c6d5f568d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223060"
---
# <a name="identicalpointposfactfxp-function"></a>IdenticalPointPosFactFxP işlevi

Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)

Paket: [Microsoft. hisse. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)


Belirtilen dizide bulunan tüm sabit noktalı sayıların, en az önemli bir bit sayılarak aynı nokta konumlarına sahip olması onayı. Yani, dizideki tüm sabit noktalı sayılar için bit eksi nokta konumu sayısının sabit olması gerekir.

```qsharp
function IdenticalPointPosFactFxP (fixedPoints : Microsoft.Quantum.Arithmetic.FixedPoint[]) : Unit
```


## <a name="input"></a>Giriş

### <a name="fixedpoints--fixedpoint"></a>Sabit noktaları: [Fixedpoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)[]

Uyumluluk için denetlenecek hisse sabit noktalı sayıların dizisi (onaylama işlemleri kullanılarak).



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)

