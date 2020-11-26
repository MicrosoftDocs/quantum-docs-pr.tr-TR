---
uid: Microsoft.Quantum.Simulation.TimeDependentTrotterSimulationAlgorithm
title: TimeDependentTrotterSimulationAlgorithm işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TimeDependentTrotterSimulationAlgorithm
qsharp.summary: '`TimeDependentSimulationAlgorithm` function that uses a Trotter–Suzuki decomposition to approximate a unitary operator that solves the time-dependent Schrodinger equation.'
ms.openlocfilehash: 94bc606fdc46d77e8beb1470c78102a63e6d4e81
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192783"
---
# <a name="timedependenttrottersimulationalgorithm-function"></a><span data-ttu-id="88c95-102">TimeDependentTrotterSimulationAlgorithm işlevi</span><span class="sxs-lookup"><span data-stu-id="88c95-102">TimeDependentTrotterSimulationAlgorithm function</span></span>

<span data-ttu-id="88c95-103">Ad alanı: [Microsoft. hisse. benzetim](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="88c95-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="88c95-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="88c95-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="88c95-105">`TimeDependentSimulationAlgorithm` zamana bağlı Schrodinger denklemini çözen bir Unitary işlecini yaklaşık olarak tahmin etmek için bir Trour – Suzuki ayrıştırma kullanan işlev.</span><span class="sxs-lookup"><span data-stu-id="88c95-105">`TimeDependentSimulationAlgorithm` function that uses a Trotter–Suzuki decomposition to approximate a unitary operator that solves the time-dependent Schrodinger equation.</span></span>

```qsharp
function TimeDependentTrotterSimulationAlgorithm (trotterStepSize : Double, trotterOrder : Int) : Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm
```


## <a name="input"></a><span data-ttu-id="88c95-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="88c95-106">Input</span></span>

### <a name="trotterstepsize--double"></a><span data-ttu-id="88c95-107">Troesstepsize: [çift](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="88c95-107">trotterStepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="88c95-108">Tek bir rahatlık adımında benzetimli zaman-gelişme süresi.</span><span class="sxs-lookup"><span data-stu-id="88c95-108">Duration of simulated time-evolution in single Trotter step.</span></span>


### <a name="trotterorder--int"></a><span data-ttu-id="88c95-109">Trokorder: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="88c95-109">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="88c95-110">Araba tümleştirici sırası.</span><span class="sxs-lookup"><span data-stu-id="88c95-110">Order of Trotter integrator.</span></span> <span data-ttu-id="88c95-111">Bu, 1 veya çift bir sayı olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="88c95-111">This must be either 1 or an even number.</span></span>



## <a name="output--timedependentsimulationalgorithm"></a><span data-ttu-id="88c95-112">Çıkış: [TimeDependentSimulationAlgorithm](xref:Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm)</span><span class="sxs-lookup"><span data-stu-id="88c95-112">Output : [TimeDependentSimulationAlgorithm](xref:Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm)</span></span>

<span data-ttu-id="88c95-113">Bir `TimeDependentSimulationAlgorithm` tür.</span><span class="sxs-lookup"><span data-stu-id="88c95-113">A `TimeDependentSimulationAlgorithm` type.</span></span>