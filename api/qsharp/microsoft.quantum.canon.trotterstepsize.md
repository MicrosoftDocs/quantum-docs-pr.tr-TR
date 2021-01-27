---
uid: Microsoft.Quantum.Canon.TrotterStepSize
title: Troesstepsize işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TrotterStepSize
qsharp.summary: Computes Trotter step size in recursive implementation of Trotter simulation algorithm.
ms.openlocfilehash: c7b6432645dcad2bd47c62b91e04e0b42cd04ca9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840067"
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