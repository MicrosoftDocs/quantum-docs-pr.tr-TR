---
uid: Microsoft.Quantum.Simulation.EvolutionUnitary
title: EvolutionUnitary Kullanıcı tanımlı tür
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: EvolutionUnitary
qsharp.summary: >-
  Represents a unitary time-evolution operator.

  The first parameter is is duration of time-evolution, and the second parameter is the qubit register acted upon by the unitary.
ms.openlocfilehash: 38e7da28d4146df9cc132ad69ee939c44bc917f7
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225270"
---
# <a name="evolutionunitary-user-defined-type"></a><span data-ttu-id="bcc65-102">EvolutionUnitary Kullanıcı tanımlı tür</span><span class="sxs-lookup"><span data-stu-id="bcc65-102">EvolutionUnitary user defined type</span></span>

<span data-ttu-id="bcc65-103">Ad alanı: [Microsoft. hisse. benzetim](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="bcc65-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="bcc65-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="bcc65-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="bcc65-105">Bir Unitary zaman-gelişme işlecini temsil eder.</span><span class="sxs-lookup"><span data-stu-id="bcc65-105">Represents a unitary time-evolution operator.</span></span>

<span data-ttu-id="bcc65-106">İlk parametre zaman evrimi olur ve ikinci parametre Unitary tarafından üzerinde işlem yapan qubit kayıt olur.</span><span class="sxs-lookup"><span data-stu-id="bcc65-106">The first parameter is is duration of time-evolution, and the second parameter is the qubit register acted upon by the unitary.</span></span>

```qsharp

newtype EvolutionUnitary = (((Double, Qubit[]) => Unit is Adj + Ctl));
```

