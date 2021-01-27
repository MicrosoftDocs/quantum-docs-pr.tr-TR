---
uid: Microsoft.Quantum.Simulation.EvolutionSet
title: EvolutionSet Kullanıcı tanımlı tür
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: EvolutionSet
qsharp.summary: >-
  Represents a set of gates that can be readily implemented and used to implement simulation algorithms.

  Elements in the set are indexed by a  <xref:microsoft.quantum.simulation.generatorindex>, and each set is described by a function from `GeneratorIndex` to  <xref:microsoft.quantum.simulation.evolutionunitary>, which are operations parameterized by a real number representing time
ms.openlocfilehash: 35c0b24da284a5871fd11b6d624102b853b89d19
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856063"
---
# <a name="evolutionset-user-defined-type"></a><span data-ttu-id="c4839-102">EvolutionSet Kullanıcı tanımlı tür</span><span class="sxs-lookup"><span data-stu-id="c4839-102">EvolutionSet user defined type</span></span>

<span data-ttu-id="c4839-103">Ad alanı: [Microsoft. hisse. benzetim](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="c4839-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="c4839-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c4839-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c4839-105">Kolay bir şekilde uygulanabilecek ve benzetim algoritmalarını uygulamak için kullanılan bir kapı kümesini temsil eder.</span><span class="sxs-lookup"><span data-stu-id="c4839-105">Represents a set of gates that can be readily implemented and used to implement simulation algorithms.</span></span>

<span data-ttu-id="c4839-106">Kümesindeki öğeler bir tarafından dizine alınır  <xref:microsoft.quantum.simulation.generatorindex> ve her küme, `GeneratorIndex`  <xref:microsoft.quantum.simulation.evolutionunitary> zamanı temsil eden gerçek bir sayıyla parametreli işlemler olan ' dan ' a bir işlevi tarafından tanımlanır</span><span class="sxs-lookup"><span data-stu-id="c4839-106">Elements in the set are indexed by a  <xref:microsoft.quantum.simulation.generatorindex>, and each set is described by a function from `GeneratorIndex` to  <xref:microsoft.quantum.simulation.evolutionunitary>, which are operations parameterized by a real number representing time</span></span>

```qsharp

newtype EvolutionSet = ((Microsoft.Quantum.Simulation.GeneratorIndex -> Microsoft.Quantum.Simulation.EvolutionUnitary));
```

