---
uid: Microsoft.Quantum.Simulation.TrotterSimulationAlgorithm
title: TrotterSimulationAlgorithm işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TrotterSimulationAlgorithm
qsharp.summary: '`SimulationAlgorithm` function that uses a Trotter–Suzuki decomposition to approximate the time-evolution operator _exp(-iHt)_.'
ms.openlocfilehash: c52acf293e69c78e7a82b0cf5d94de52d0f5a293
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730679"
---
# <a name="trottersimulationalgorithm-function"></a><span data-ttu-id="1efe0-102">TrotterSimulationAlgorithm işlevi</span><span class="sxs-lookup"><span data-stu-id="1efe0-102">TrotterSimulationAlgorithm function</span></span>

<span data-ttu-id="1efe0-103">Ad alanı: [Microsoft. hisse. benzetim](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="1efe0-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="1efe0-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1efe0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1efe0-105">`SimulationAlgorithm` bir Trour – Suzuki ayrıştırma kullanan, zaman içinde geçen işlecin _exp (-IHV)_ için bir sorun.</span><span class="sxs-lookup"><span data-stu-id="1efe0-105">`SimulationAlgorithm` function that uses a Trotter–Suzuki decomposition to approximate the time-evolution operator _exp(-iHt)_ .</span></span>

```qsharp
function TrotterSimulationAlgorithm (trotterStepSize : Double, trotterOrder : Int) : Microsoft.Quantum.Simulation.SimulationAlgorithm
```


## <a name="input"></a><span data-ttu-id="1efe0-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="1efe0-106">Input</span></span>

### <a name="trotterstepsize--double"></a><span data-ttu-id="1efe0-107">Troesstepsize: [çift](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="1efe0-107">trotterStepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="1efe0-108">Tek bir rahatlık adımında benzetimli zaman-gelişme süresi.</span><span class="sxs-lookup"><span data-stu-id="1efe0-108">Duration of simulated time-evolution in single Trotter step.</span></span>


### <a name="trotterorder--int"></a><span data-ttu-id="1efe0-109">Trokorder: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1efe0-109">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1efe0-110">Araba tümleştirici sırası.</span><span class="sxs-lookup"><span data-stu-id="1efe0-110">Order of Trotter integrator.</span></span> <span data-ttu-id="1efe0-111">Bu, 1 veya çift bir sayı olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="1efe0-111">This must be either 1 or an even number.</span></span>



## <a name="output--simulationalgorithm"></a><span data-ttu-id="1efe0-112">Çıkış: [SimulationAlgorithm](xref:Microsoft.Quantum.Simulation.SimulationAlgorithm)</span><span class="sxs-lookup"><span data-stu-id="1efe0-112">Output : [SimulationAlgorithm](xref:Microsoft.Quantum.Simulation.SimulationAlgorithm)</span></span>

<span data-ttu-id="1efe0-113">Bir `SimulationAlgorithm` tür.</span><span class="sxs-lookup"><span data-stu-id="1efe0-113">A `SimulationAlgorithm` type.</span></span>