---
uid: Microsoft.Quantum.Simulation.TrotterStep
title: Trobir Step işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TrotterStep
qsharp.summary: Implements a single time-step of time-evolution by the system described in an `EvolutionGenerator` using a Trotter–Suzuki decomposition.
ms.openlocfilehash: 7a1a27ba4dc4b8b7bbc4da6a378d4a1494bc9415
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733991"
---
# <a name="trotterstep-function"></a>Trobir Step işlevi

Ad alanı: [Microsoft. hisse. benzetim](xref:Microsoft.Quantum.Simulation)

Leyebilir [](https://nuget.org/packages/)


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



## <a name="output--qubit--unit-adj--ctl"></a>Output: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [birim](xref:microsoft.quantum.lang-ref.unit) ayarlama ve CTL

Süre için tek bir zaman gelişini yaklaştırın Unitary işlemi `trotterStepSize` .

## <a name="remarks"></a>Açıklamalar

Trour – Suzuki ayrıştırma hakkında daha fazla bilgi için bkz. [zaman Içinde sıralı bileşim](/quantum/libraries/control-flow#time-ordered-composition).