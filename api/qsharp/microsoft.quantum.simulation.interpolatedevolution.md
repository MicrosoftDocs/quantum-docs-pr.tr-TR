---
uid: Microsoft.Quantum.Simulation.InterpolatedEvolution
title: Enterpolategerileme işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: InterpolatedEvolution
qsharp.summary: Interpolates between two generators with a uniform schedule, returning an operation that applies simulated evolution under the resulting time-dependent generator to a qubit register.
ms.openlocfilehash: 4d2e04513c96c6e5f41e85f1df685e91e2973098
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858085"
---
# <a name="interpolatedevolution-function"></a>Enterpolategerileme işlevi

Ad alanı: [Microsoft. hisse. benzetim](xref:Microsoft.Quantum.Simulation)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


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



## <a name="output--qubit--unit--is-adj--ctl"></a>Output: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [birimi](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL



## <a name="remarks"></a>Açıklamalar

Enterpolasyon süresi Adiabatik koşullarını karşılayacak şekilde seçilirse, bu işlev son dinamik üreticisi için Adiabatik durum hazırlığı gerçekleştiren bir işlem döndürür.