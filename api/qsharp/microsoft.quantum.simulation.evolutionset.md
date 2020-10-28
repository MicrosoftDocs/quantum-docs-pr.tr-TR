---
uid: Microsoft.Quantum.Simulation.EvolutionSet
title: EvolutionSet Kullanıcı tanımlı tür
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: EvolutionSet
qsharp.summary: >-
  Represents a set of gates that can be readily implemented and used to implement simulation algorithms.

  Elements in the set are indexed by a  <xref:microsoft.quantum.simulation.generatorindex>, and each set is described by a function from `GeneratorIndex` to  <xref:microsoft.quantum.simulation.evolutionunitary>, which are operations parameterized by a real number representing time
ms.openlocfilehash: 41504837b281b1021a2d09ef75acc10315b4fd07
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726318"
---
# <a name="evolutionset-user-defined-type"></a>EvolutionSet Kullanıcı tanımlı tür

Ad alanı: [Microsoft. hisse. benzetim](xref:Microsoft.Quantum.Simulation)

Leyebilir [](https://nuget.org/packages/)


Kolay bir şekilde uygulanabilecek ve benzetim algoritmalarını uygulamak için kullanılan bir kapı kümesini temsil eder.

Kümesindeki öğeler bir tarafından dizine alınır  <xref:microsoft.quantum.simulation.generatorindex> ve her küme, `GeneratorIndex`  <xref:microsoft.quantum.simulation.evolutionunitary> zamanı temsil eden gerçek bir sayıyla parametreli işlemler olan ' dan ' a bir işlevi tarafından tanımlanır

```qsharp

newtype EvolutionSet = ((Microsoft.Quantum.Simulation.GeneratorIndex -> Microsoft.Quantum.Simulation.EvolutionUnitary));
```

