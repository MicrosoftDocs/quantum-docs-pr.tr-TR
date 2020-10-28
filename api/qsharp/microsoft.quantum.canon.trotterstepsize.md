---
uid: Microsoft.Quantum.Canon.TrotterStepSize
title: Troesstepsize işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TrotterStepSize
qsharp.summary: Computes Trotter step size in recursive implementation of Trotter simulation algorithm.
ms.openlocfilehash: fabfbff74572b3c96c701de5443e4265a0468d78
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728297"
---
# <a name="trotterstepsize-function"></a>Troesstepsize işlevi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Leyebilir [](https://nuget.org/packages/)


, Trour benzetim algoritmasının özyinelemeli uygulamasında araba adım boyutunu hesaplar.

```qsharp
function TrotterStepSize (order : Int) : Double
```


## <a name="input"></a>Giriş

### <a name="order--int"></a>sıra: [Int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--double"></a>Çıkış: [Double](xref:microsoft.quantum.lang-ref.double)



## <a name="remarks"></a>Açıklamalar

Bu işlem, [Quant-pH/0508139](https://arxiv.org/abs/quant-ph/0508139)öğesinden farklı bir dizin oluşturma kuralı kullanıyor. Özellikle, `DecomposedIntoTimeStepsCA(_, 4)` Quant-pH/0508139 içindeki skaler $p _2 (\lambda) $ öğesine karşılık gelir.