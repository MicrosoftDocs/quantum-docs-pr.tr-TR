---
uid: Microsoft.Quantum.Simulation.TimeDependentTrotterSimulationAlgorithm
title: TimeDependentTrotterSimulationAlgorithm işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TimeDependentTrotterSimulationAlgorithm
qsharp.summary: '`TimeDependentSimulationAlgorithm` function that uses a Trotter–Suzuki decomposition to approximate a unitary operator that solves the time-dependent Schrodinger equation.'
ms.openlocfilehash: 6129d768276b5c9d96a1b1ed9cd5a6a22d28e286
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730682"
---
# <a name="timedependenttrottersimulationalgorithm-function"></a><span data-ttu-id="f1255-102">TimeDependentTrotterSimulationAlgorithm işlevi</span><span class="sxs-lookup"><span data-stu-id="f1255-102">TimeDependentTrotterSimulationAlgorithm function</span></span>

<span data-ttu-id="f1255-103">Ad alanı: [Microsoft. hisse. benzetim](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="f1255-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="f1255-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f1255-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f1255-105">`TimeDependentSimulationAlgorithm` zamana bağlı Schrodinger denklemini çözen bir Unitary işlecini yaklaşık olarak tahmin etmek için bir Trour – Suzuki ayrıştırma kullanan işlev.</span><span class="sxs-lookup"><span data-stu-id="f1255-105">`TimeDependentSimulationAlgorithm` function that uses a Trotter–Suzuki decomposition to approximate a unitary operator that solves the time-dependent Schrodinger equation.</span></span>

```qsharp
function TimeDependentTrotterSimulationAlgorithm (trotterStepSize : Double, trotterOrder : Int) : Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm
```


## <a name="input"></a><span data-ttu-id="f1255-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="f1255-106">Input</span></span>

### <a name="trotterstepsize--double"></a><span data-ttu-id="f1255-107">Troesstepsize: [çift](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="f1255-107">trotterStepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="f1255-108">Tek bir rahatlık adımında benzetimli zaman-gelişme süresi.</span><span class="sxs-lookup"><span data-stu-id="f1255-108">Duration of simulated time-evolution in single Trotter step.</span></span>


### <a name="trotterorder--int"></a><span data-ttu-id="f1255-109">Trokorder: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f1255-109">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f1255-110">Araba tümleştirici sırası.</span><span class="sxs-lookup"><span data-stu-id="f1255-110">Order of Trotter integrator.</span></span> <span data-ttu-id="f1255-111">Bu, 1 veya çift bir sayı olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="f1255-111">This must be either 1 or an even number.</span></span>



## <a name="output--timedependentsimulationalgorithm"></a><span data-ttu-id="f1255-112">Çıkış: [TimeDependentSimulationAlgorithm](xref:Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm)</span><span class="sxs-lookup"><span data-stu-id="f1255-112">Output : [TimeDependentSimulationAlgorithm](xref:Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm)</span></span>

<span data-ttu-id="f1255-113">Bir `TimeDependentSimulationAlgorithm` tür.</span><span class="sxs-lookup"><span data-stu-id="f1255-113">A `TimeDependentSimulationAlgorithm` type.</span></span>