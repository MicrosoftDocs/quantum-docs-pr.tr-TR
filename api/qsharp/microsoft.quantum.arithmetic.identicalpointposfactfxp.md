---
uid: Microsoft.Quantum.Arithmetic.IdenticalPointPosFactFxP
title: IdenticalPointPosFactFxP işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IdenticalPointPosFactFxP
qsharp.summary: Assert that all fixed-point numbers in the provided array have identical point positions when counting from the least- significant bit. I.e., number of bits minus point position must be constant for all fixed-point numbers in the array.
ms.openlocfilehash: 7212f918e1d0ee86b12b85caa6e0c27bc2cebe58
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846610"
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

