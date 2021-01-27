---
uid: Microsoft.Quantum.Simulation.MultiplyGeneratorSystem
title: MultiplyGeneratorSystem işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: MultiplyGeneratorSystem
qsharp.summary: Multiplies the coefficient of all terms in a `GeneratorSystem`.
ms.openlocfilehash: cebd08c86ad8a3793ba7d0e9ce241d7a1ef046ae
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858506"
---
# <a name="multiplygeneratorsystem-function"></a>MultiplyGeneratorSystem işlevi

Ad alanı: [Microsoft. hisse. benzetim](xref:Microsoft.Quantum.Simulation)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


İçindeki tüm koşulların katsayısını çarpar `GeneratorSystem` .

```qsharp
function MultiplyGeneratorSystem (multiplier : Double, generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a>Giriş

### <a name="multiplier--double"></a>çarpan: [Double](xref:microsoft.quantum.lang-ref.double)

Katlayıcı üzerindeki çarpan.


### <a name="generatorsystem--generatorsystem"></a>generatorSystem: [Generatorsystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

`GeneratorSystem`Çarpmak için.



## <a name="output--generatorsystem"></a>Çıkış: [Generatorsystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

`GeneratorSystem`Çarpanların çarpanlarını daha büyük olan bir sistemi temsil eden `multiplier` .

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. simülasyon. GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)