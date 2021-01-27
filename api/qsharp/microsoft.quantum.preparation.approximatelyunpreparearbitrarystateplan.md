---
uid: Microsoft.Quantum.Preparation.ApproximatelyUnprepareArbitraryStatePlan
title: ApproximatelyUnprepareArbitraryStatePlan işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: ApproximatelyUnprepareArbitraryStatePlan
qsharp.summary: Implementation step of arbitrary state preparation procedure.
ms.openlocfilehash: d506e3a8bff365f1c99d4ed1eb41d29ba3dbeb18
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842432"
---
# <a name="approximatelyunpreparearbitrarystateplan-function"></a>ApproximatelyUnprepareArbitraryStatePlan işlevi

Ad alanı: [Microsoft. hisse. hazırlık](xref:Microsoft.Quantum.Preparation)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Rastgele durum hazırlama yordamının uygulama adımı.

```qsharp
function ApproximatelyUnprepareArbitraryStatePlan (tolerance : Double, coefficients : Microsoft.Quantum.Math.ComplexPolar[], (rngControl : Range, idxTarget : Int)) : (Qubit[] => Unit is Adj + Ctl)[]
```


## <a name="input"></a>Giriş

### <a name="tolerance--double"></a>Tolerans: [Double](xref:microsoft.quantum.lang-ref.double)




### <a name="coefficients--complexpolar"></a>katsayılar: [Complexkutupsal](xref:Microsoft.Quantum.Math.ComplexPolar)[]




### <a name="rngcontrol--range"></a>rngControl: [Range](xref:microsoft.quantum.lang-ref.range)




### <a name="idxtarget--int"></a>ıdxtarget: [Int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--qubit--unit--is-adj--ctl"></a>Output: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [birimi](xref:microsoft.quantum.lang-ref.unit)  , sıfatı + CTL []



## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. hazırlık. hazırlık Earbitrari durumu](xref:Microsoft.Quantum.Preparation.PrepareArbitraryState)
- [Microsoft. hisse. Canon. MultiplexPauli](xref:Microsoft.Quantum.Canon.MultiplexPauli)