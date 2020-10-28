---
uid: Microsoft.Quantum.Simulation.InterpolateGeneratorSystems
title: Enterpolategeneratorsystems işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: InterpolateGeneratorSystems
qsharp.summary: Returns a `TimeDependentGeneratorSystem` representing the linear interpolation between two `GeneratorSystem`s.
ms.openlocfilehash: 9881c27577023dafff0bfc6d961877db44fec0eb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726299"
---
# <a name="interpolategeneratorsystems-function"></a>Enterpolategeneratorsystems işlevi

Ad alanı: [Microsoft. hisse. benzetim](xref:Microsoft.Quantum.Simulation)

Leyebilir [](https://nuget.org/packages/)


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