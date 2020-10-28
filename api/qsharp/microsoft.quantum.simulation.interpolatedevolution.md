---
uid: Microsoft.Quantum.Simulation.InterpolatedEvolution
title: Enterpolategerileme işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: InterpolatedEvolution
qsharp.summary: Interpolates between two generators with a uniform schedule, returning an operation that applies simulated evolution under the resulting time-dependent generator to a qubit register.
ms.openlocfilehash: 18026b9872f6a3344a1e5c2122f55927975ccb59
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726306"
---
# <a name="interpolatedevolution-function"></a>Enterpolategerileme işlevi

Ad alanı: [Microsoft. hisse. benzetim](xref:Microsoft.Quantum.Simulation)

Leyebilir [](https://nuget.org/packages/)


, Zaman içinde zamana bağlı Oluşturucu altında bir qubit kaydına benzetimci uygulayan bir işlem döndüren, tek düzen ile iki üretici arasında enterpolasyonlar.

```qsharp
function InterpolatedEvolution (interpolationTime : Double, evolutionGeneratorStart : Microsoft.Quantum.Simulation.EvolutionGenerator, evolutionGeneratorEnd : Microsoft.Quantum.Simulation.EvolutionGenerator, timeDependentSimulationAlgorithm : Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a>Giriş

### <a name="interpolationtime--double"></a>Enterpolalationtime: [Double](xref:microsoft.quantum.lang-ref.double)

İlişkilendirmeyi gerçekleştirme süresi.


### <a name="evolutiongeneratorstart--evolutiongenerator"></a>evolutionGeneratorStart: [Evolutiongenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)

Altında gelişmeye benzetim yapılacak ilk Oluşturucu.


### <a name="evolutiongeneratorend--evolutiongenerator"></a>evolutionGeneratorEnd: [Evolutiongenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)

Altındaki evçanın benzetimini yapmak için nihai Oluşturucu.


### <a name="timedependentsimulationalgorithm--timedependentsimulationalgorithm"></a>timeDependentSimulationAlgorithm: [timeDependentSimulationAlgorithm](xref:Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm)

Tekdüzen ilişkilendirme zamanlaması sırasında evrimde benzetimini yapmak için kullanılacak zamana bağlı bir simülasyon algoritması.



## <a name="output--qubit--unit-adj--ctl"></a>Output: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [birim](xref:microsoft.quantum.lang-ref.unit) ayarlama ve CTL



## <a name="remarks"></a>Açıklamalar

Enterpolasyon süresi Adiabatik koşullarını karşılayacak şekilde seçilirse, bu işlev son dinamik üreticisi için Adiabatik durum hazırlığı gerçekleştiren bir işlem döndürür.