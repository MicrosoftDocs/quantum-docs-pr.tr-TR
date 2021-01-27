---
uid: Microsoft.Quantum.Simulation.EvolutionGenerator
title: EvolutionGenerator Kullanıcı tanımlı türü
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: EvolutionGenerator
qsharp.summary: >-
  Represents a dynamical generator as a set of simulatable gates and an expansion in terms of that basis.

  Last parameter for number of terms.
ms.openlocfilehash: 98241f77bfbd73929896bb114fad060001016a86
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856079"
---
# <a name="evolutiongenerator-user-defined-type"></a>EvolutionGenerator Kullanıcı tanımlı türü

Ad alanı: [Microsoft. hisse. benzetim](xref:Microsoft.Quantum.Simulation)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir dinamik üreticisini bir simulatable Gates kümesi ve bu temelde bir genişletme olarak temsil eder.

Terim sayısı için son parametre.

```qsharp

newtype EvolutionGenerator = (Microsoft.Quantum.Simulation.EvolutionSet, Microsoft.Quantum.Simulation.GeneratorSystem);
```

