---
uid: Microsoft.Quantum.Simulation.EvolutionSchedule
title: EvolutionSchedule Kullanıcı tanımlı türü
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: EvolutionSchedule
qsharp.summary: >-
  Represents a time-dependent dynamical generator.

  The `Double` parameter is a schedule in $[0, 1]$.
ms.openlocfilehash: 4dc8bf4028e82d3e746779ae8c7d400dcbd3ea1b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726323"
---
# <a name="evolutionschedule-user-defined-type"></a><span data-ttu-id="33aa7-102">EvolutionSchedule Kullanıcı tanımlı türü</span><span class="sxs-lookup"><span data-stu-id="33aa7-102">EvolutionSchedule user defined type</span></span>

<span data-ttu-id="33aa7-103">Ad alanı: [Microsoft. hisse. benzetim](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="33aa7-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="33aa7-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="33aa7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="33aa7-105">Zamana bağlı bir dinamik oluşturucuyu temsil eder.</span><span class="sxs-lookup"><span data-stu-id="33aa7-105">Represents a time-dependent dynamical generator.</span></span>

<span data-ttu-id="33aa7-106">`Double`Parametresi $ [0, 1] $ içinde bir zamanlama.</span><span class="sxs-lookup"><span data-stu-id="33aa7-106">The `Double` parameter is a schedule in $[0, 1]$.</span></span>

```qsharp

newtype EvolutionSchedule = (Microsoft.Quantum.Simulation.EvolutionSet, (Double -> Microsoft.Quantum.Simulation.GeneratorSystem));
```

