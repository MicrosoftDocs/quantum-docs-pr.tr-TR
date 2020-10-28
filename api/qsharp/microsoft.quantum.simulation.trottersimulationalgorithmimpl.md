---
uid: Microsoft.Quantum.Simulation.TrotterSimulationAlgorithmImpl
title: TrotterSimulationAlgorithmImpl işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TrotterSimulationAlgorithmImpl
qsharp.summary: Makes repeated calls to `TrotterStep` to approximate the time-evolution operator exp(_-iHt_).
ms.openlocfilehash: 2af68532d700a1fb5b037707ce4650696cbe1a64
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733994"
---
# <a name="trottersimulationalgorithmimpl-operation"></a><span data-ttu-id="3ba17-102">TrotterSimulationAlgorithmImpl işlemi</span><span class="sxs-lookup"><span data-stu-id="3ba17-102">TrotterSimulationAlgorithmImpl operation</span></span>

<span data-ttu-id="3ba17-103">Ad alanı: [Microsoft. hisse. benzetim](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="3ba17-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="3ba17-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3ba17-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3ba17-105">`TrotterStep`, Zaman-gelişme işlecinin exp ( _-IHV_ ) yaklaşık olarak için yinelenen çağrılar yapar.</span><span class="sxs-lookup"><span data-stu-id="3ba17-105">Makes repeated calls to `TrotterStep` to approximate the time-evolution operator exp( _-iHt_ ).</span></span>

```qsharp
operation TrotterSimulationAlgorithmImpl (trotterStepSize : Double, trotterOrder : Int, maxTime : Double, evolutionGenerator : Microsoft.Quantum.Simulation.EvolutionGenerator, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="3ba17-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="3ba17-106">Input</span></span>

### <a name="trotterstepsize--double"></a><span data-ttu-id="3ba17-107">Troesstepsize: [çift](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="3ba17-107">trotterStepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="3ba17-108">Tek bir rahatlık adımında benzetimli zaman-gelişme süresi.</span><span class="sxs-lookup"><span data-stu-id="3ba17-108">Duration of simulated time-evolution in single Trotter step.</span></span>


### <a name="trotterorder--int"></a><span data-ttu-id="3ba17-109">Trokorder: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3ba17-109">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3ba17-110">Araba tümleştirici sırası.</span><span class="sxs-lookup"><span data-stu-id="3ba17-110">Order of Trotter integrator.</span></span> <span data-ttu-id="3ba17-111">Bu, 1 veya çift bir sayı olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="3ba17-111">This must be either 1 or an even number.</span></span>


### <a name="maxtime--double"></a><span data-ttu-id="3ba17-112">maxTime: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="3ba17-112">maxTime : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="3ba17-113">Simülasyon $t toplam süresi.</span><span class="sxs-lookup"><span data-stu-id="3ba17-113">Total duration of simulation $t$.</span></span>


### <a name="evolutiongenerator--evolutiongenerator"></a><span data-ttu-id="3ba17-114">evolutionGenerator: [Evolutiongenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span><span class="sxs-lookup"><span data-stu-id="3ba17-114">evolutionGenerator : [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span></span>

<span data-ttu-id="3ba17-115">Benzetim yapılacak sistemin tüm açıklaması.</span><span class="sxs-lookup"><span data-stu-id="3ba17-115">A complete description of the system to be simulated.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="3ba17-116">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="3ba17-116">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="3ba17-117">Bu, simülasyonu tarafından üzerinde işlem yaptığı.</span><span class="sxs-lookup"><span data-stu-id="3ba17-117">Qubits acted on by simulation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3ba17-118">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3ba17-118">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

