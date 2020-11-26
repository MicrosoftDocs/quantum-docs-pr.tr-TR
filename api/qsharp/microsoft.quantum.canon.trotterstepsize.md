---
uid: Microsoft.Quantum.Canon.TrotterStepSize
title: Troesstepsize işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TrotterStepSize
qsharp.summary: Computes Trotter step size in recursive implementation of Trotter simulation algorithm.
ms.openlocfilehash: aa5b63e058e1ea726b0d4c6eca73078831daaf3b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204700"
---
# <a name="trotterstepsize-function"></a>Troesstepsize işlevi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


, Trour benzetim algoritmasının özyinelemeli uygulamasında araba adım boyutunu hesaplar.

```qsharp
function TrotterStepSize (order : Int) : Double
```


## <a name="input"></a>Giriş

### <a name="order--int"></a>sıra: [Int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--double"></a>Çıkış: [Double](xref:microsoft.quantum.lang-ref.double)



## <a name="remarks"></a>Açıklamalar

Bu işlem, [Quant-pH/0508139](https://arxiv.org/abs/quant-ph/0508139)öğesinden farklı bir dizin oluşturma kuralı kullanıyor. Özellikle, `DecomposedIntoTimeStepsCA(_, 4)` Quant-pH/0508139 içindeki skaler $p _2 (\lambda) $ öğesine karşılık gelir.