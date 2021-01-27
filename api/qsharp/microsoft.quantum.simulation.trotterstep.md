---
uid: Microsoft.Quantum.Simulation.TrotterStep
title: Trobir Step işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TrotterStep
qsharp.summary: Implements a single time-step of time-evolution by the system described in an `EvolutionGenerator` using a Trotter–Suzuki decomposition.
ms.openlocfilehash: 4c0e7dd89b1beae9fb6a35ae5b8d16e09d355ab8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854716"
---
# <a name="trotterstep-function"></a>Trobir Step işlevi

Ad alanı: [Microsoft. hisse. benzetim](xref:Microsoft.Quantum.Simulation)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


, `EvolutionGenerator` Bir Trour – Suzuki ayrıştırma kullanımı ile açıklanan sistem tarafından tek seferlik bir zaman adımı uygular.

```qsharp
function TrotterStep (evolutionGenerator : Microsoft.Quantum.Simulation.EvolutionGenerator, trotterOrder : Int, trotterStepSize : Double) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a>Giriş

### <a name="evolutiongenerator--evolutiongenerator"></a>evolutionGenerator: [Evolutiongenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)

Benzetim yapılacak sistemin tüm açıklaması.


### <a name="trotterorder--int"></a>Trokorder: [Int](xref:microsoft.quantum.lang-ref.int)

Araba tümleştirici sırası. Bu, 1 veya çift bir sayı olmalıdır.


### <a name="trotterstepsize--double"></a>Troesstepsize: [çift](xref:microsoft.quantum.lang-ref.double)

Tek bir rahatlık adımında benzetimli zaman-gelişme süresi.



## <a name="output--qubit--unit--is-adj--ctl"></a>Output: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [birimi](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL

Süre için tek bir zaman gelişini yaklaştırın Unitary işlemi `trotterStepSize` .

## <a name="remarks"></a>Açıklamalar

Trour – Suzuki ayrıştırma hakkında daha fazla bilgi için bkz. [zaman Içinde sıralı bileşim](/quantum/libraries/control-flow#time-ordered-composition).