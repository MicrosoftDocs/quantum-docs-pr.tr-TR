---
uid: Microsoft.Quantum.Simulation.InterpolateGeneratorSystems
title: Enterpolategeneratorsystems işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: InterpolateGeneratorSystems
qsharp.summary: Returns a `TimeDependentGeneratorSystem` representing the linear interpolation between two `GeneratorSystem`s.
ms.openlocfilehash: c56f1eaf13afb649777c0d9368e97d85996cc67b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842273"
---
# <a name="interpolategeneratorsystems-function"></a>Enterpolategeneratorsystems işlevi

Ad alanı: [Microsoft. hisse. benzetim](xref:Microsoft.Quantum.Simulation)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


`TimeDependentGeneratorSystem`İki s arasındaki doğrusal ilişkilendirmeyi temsil eden bir döndürür `GeneratorSystem` .

```qsharp
function InterpolateGeneratorSystems (generatorSystemStart : Microsoft.Quantum.Simulation.GeneratorSystem, generatorSystemEnd : Microsoft.Quantum.Simulation.GeneratorSystem) : Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem
```


## <a name="input"></a>Giriş

### <a name="generatorsystemstart--generatorsystem"></a>generatorSystemStart: [Generatorsystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

Başlat `GeneratorSystem` .


### <a name="generatorsystemend--generatorsystem"></a>generatorSystemEnd: [Generatorsystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

Son `GeneratorSystem` .



## <a name="output--timedependentgeneratorsystem"></a>Çıkış: [Timedependentgeneratorsystem](xref:Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem)

`TimeDependentGeneratorSystem`Ağırlık $ (1-s) $ on `generatorSystemStart` ve ağırlık $s $ on ile giriş Oluşturucu sistemlerinin toplamı olan bir sistemi temsil eden bir sistemdir `generatorSystemEnd` .

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. simülasyon. GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)
- [Microsoft. hisse. simülasyon. TimeDependentGeneratorSystem](xref:Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem)