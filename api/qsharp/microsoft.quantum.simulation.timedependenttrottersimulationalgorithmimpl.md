---
uid: Microsoft.Quantum.Simulation.TimeDependentTrotterSimulationAlgorithmImpl
title: TimeDependentTrotterSimulationAlgorithmImpl işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TimeDependentTrotterSimulationAlgorithmImpl
qsharp.summary: Implementation of multiple Trotter steps to approximate a unitary operator that solves the time-dependent Schrödinger equation.
ms.openlocfilehash: c6d1c976d29c69d3ac14d9a2be09826602c8cc1d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730674"
---
# <a name="timedependenttrottersimulationalgorithmimpl-operation"></a><span data-ttu-id="d59ac-102">TimeDependentTrotterSimulationAlgorithmImpl işlemi</span><span class="sxs-lookup"><span data-stu-id="d59ac-102">TimeDependentTrotterSimulationAlgorithmImpl operation</span></span>

<span data-ttu-id="d59ac-103">Ad alanı: [Microsoft. hisse. benzetim](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="d59ac-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="d59ac-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d59ac-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d59ac-105">Zamana bağlı Schrödinger denklemini çözen bir Unitary işlecinin yaklaşık olması için birden çok rahatlık adımı uygulama.</span><span class="sxs-lookup"><span data-stu-id="d59ac-105">Implementation of multiple Trotter steps to approximate a unitary operator that solves the time-dependent Schrödinger equation.</span></span>

```qsharp
operation TimeDependentTrotterSimulationAlgorithmImpl (trotterStepSize : Double, trotterOrder : Int, maxTime : Double, evolutionSchedule : Microsoft.Quantum.Simulation.EvolutionSchedule, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="d59ac-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="d59ac-106">Input</span></span>

### <a name="trotterstepsize--double"></a><span data-ttu-id="d59ac-107">Troesstepsize: [çift](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="d59ac-107">trotterStepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="d59ac-108">Tek bir rahatlık adımında benzetimli zaman-gelişme süresi.</span><span class="sxs-lookup"><span data-stu-id="d59ac-108">Duration of simulated time-evolution in single Trotter step.</span></span>


### <a name="trotterorder--int"></a><span data-ttu-id="d59ac-109">Trokorder: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d59ac-109">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d59ac-110">Araba tümleştirici sırası.</span><span class="sxs-lookup"><span data-stu-id="d59ac-110">Order of Trotter integrator.</span></span> <span data-ttu-id="d59ac-111">Bu, 1 veya çift bir sayı olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="d59ac-111">This must be either 1 or an even number.</span></span>


### <a name="maxtime--double"></a><span data-ttu-id="d59ac-112">maxTime: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="d59ac-112">maxTime : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="d59ac-113">Simülasyon $t toplam süresi.</span><span class="sxs-lookup"><span data-stu-id="d59ac-113">Total duration of simulation $t$.</span></span>


### <a name="evolutionschedule--evolutionschedule"></a><span data-ttu-id="d59ac-114">Açılım zamanlaması: [Evolutionschedule](xref:Microsoft.Quantum.Simulation.EvolutionSchedule)</span><span class="sxs-lookup"><span data-stu-id="d59ac-114">evolutionSchedule : [EvolutionSchedule](xref:Microsoft.Quantum.Simulation.EvolutionSchedule)</span></span>

<span data-ttu-id="d59ac-115">Benzetim yapılacak zamana bağlı sistemin tam bir açıklaması.</span><span class="sxs-lookup"><span data-stu-id="d59ac-115">A complete description of the time-dependent system to be simulated.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="d59ac-116">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="d59ac-116">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="d59ac-117">Bu, simülasyonu tarafından üzerinde işlem yaptığı.</span><span class="sxs-lookup"><span data-stu-id="d59ac-117">Qubits acted on by simulation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d59ac-118">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d59ac-118">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

