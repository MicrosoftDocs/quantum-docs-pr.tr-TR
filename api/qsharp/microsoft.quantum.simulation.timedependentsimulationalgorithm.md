---
uid: Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm
title: TimeDependentSimulationAlgorithm Kullanıcı tanımlı tür
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TimeDependentSimulationAlgorithm
qsharp.summary: >-
  Represents a time-dependent simulation algorithm.

  A time-dependent simulation technique converts an <xref:microsoft.quantum.simulation.evolutionschedule> to unitary time-evolution for some time-interval.
ms.openlocfilehash: b495a9fd96c78872f84e8f8183105f6290f70655
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192528"
---
# <a name="timedependentsimulationalgorithm-user-defined-type"></a><span data-ttu-id="ccb96-102">TimeDependentSimulationAlgorithm Kullanıcı tanımlı tür</span><span class="sxs-lookup"><span data-stu-id="ccb96-102">TimeDependentSimulationAlgorithm user defined type</span></span>

<span data-ttu-id="ccb96-103">Ad alanı: [Microsoft. hisse. benzetim](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="ccb96-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="ccb96-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ccb96-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ccb96-105">Zamana bağlı bir simülasyon algoritmasını temsil eder.</span><span class="sxs-lookup"><span data-stu-id="ccb96-105">Represents a time-dependent simulation algorithm.</span></span>

<span data-ttu-id="ccb96-106">Zamana bağlı simülasyon tekniği bir <xref:microsoft.quantum.simulation.evolutionschedule></span><span class="sxs-lookup"><span data-stu-id="ccb96-106">A time-dependent simulation technique converts an <xref:microsoft.quantum.simulation.evolutionschedule></span></span>
<span data-ttu-id="ccb96-107">belirli bir zaman aralığı için Unitary zaman-gelişini.</span><span class="sxs-lookup"><span data-stu-id="ccb96-107">to unitary time-evolution for some time-interval.</span></span>

```qsharp

newtype TimeDependentSimulationAlgorithm = (((Double, Microsoft.Quantum.Simulation.EvolutionSchedule, Qubit[]) => Unit is Adj + Ctl));
```

