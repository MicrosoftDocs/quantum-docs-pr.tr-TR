---
uid: Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem
title: TimeDependentGeneratorSystem Kullanıcı tanımlı türü
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TimeDependentGeneratorSystem
qsharp.summary: Represents a time-dependent dynamical generator as a function from time to the value of the dynamical generator at that time.
ms.openlocfilehash: b9b11a5850cbf9bc0b908f1644443611e91bb258
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192460"
---
# <a name="timedependentgeneratorsystem-user-defined-type"></a><span data-ttu-id="ca2b8-102">TimeDependentGeneratorSystem Kullanıcı tanımlı türü</span><span class="sxs-lookup"><span data-stu-id="ca2b8-102">TimeDependentGeneratorSystem user defined type</span></span>

<span data-ttu-id="ca2b8-103">Ad alanı: [Microsoft. hisse. benzetim](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="ca2b8-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="ca2b8-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ca2b8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ca2b8-105">Zamana bağlı bir dinamik üreticisini, zaman içinde dinamik oluşturucusunun değerine kadar bir işlev olarak temsil eder.</span><span class="sxs-lookup"><span data-stu-id="ca2b8-105">Represents a time-dependent dynamical generator as a function from time to the value of the dynamical generator at that time.</span></span>

```qsharp

newtype TimeDependentGeneratorSystem = ((Double -> Microsoft.Quantum.Simulation.GeneratorSystem));
```

