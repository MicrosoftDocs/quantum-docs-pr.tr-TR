---
uid: Microsoft.Quantum.Simulation.MultiplyGeneratorSystem
title: MultiplyGeneratorSystem işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: MultiplyGeneratorSystem
qsharp.summary: Multiplies the coefficient of all terms in a `GeneratorSystem`.
ms.openlocfilehash: effb9e3ca754f77bbe1ea0fb6ca30ae49e92d531
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229163"
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