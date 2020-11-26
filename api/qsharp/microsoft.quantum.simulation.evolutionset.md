---
uid: Microsoft.Quantum.Simulation.EvolutionSet
title: EvolutionSet Kullanıcı tanımlı tür
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: EvolutionSet
qsharp.summary: >-
  Represents a set of gates that can be readily implemented and used to implement simulation algorithms.

  Elements in the set are indexed by a  <xref:microsoft.quantum.simulation.generatorindex>, and each set is described by a function from `GeneratorIndex` to  <xref:microsoft.quantum.simulation.evolutionunitary>, which are operations parameterized by a real number representing time
ms.openlocfilehash: ee8f3c0716f035dcb0c4fad557092fbf8dd3c356
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229418"
---
# <a name="evolutionset-user-defined-type"></a>EvolutionSet Kullanıcı tanımlı tür

Ad alanı: [Microsoft. hisse. benzetim](xref:Microsoft.Quantum.Simulation)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Kolay bir şekilde uygulanabilecek ve benzetim algoritmalarını uygulamak için kullanılan bir kapı kümesini temsil eder.

Kümesindeki öğeler bir tarafından dizine alınır  <xref:microsoft.quantum.simulation.generatorindex> ve her küme, `GeneratorIndex`  <xref:microsoft.quantum.simulation.evolutionunitary> zamanı temsil eden gerçek bir sayıyla parametreli işlemler olan ' dan ' a bir işlevi tarafından tanımlanır

```qsharp

newtype EvolutionSet = ((Microsoft.Quantum.Simulation.GeneratorIndex -> Microsoft.Quantum.Simulation.EvolutionUnitary));
```

