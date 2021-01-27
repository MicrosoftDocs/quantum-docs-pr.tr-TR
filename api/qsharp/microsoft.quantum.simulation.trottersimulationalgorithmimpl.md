---
uid: Microsoft.Quantum.Simulation.TrotterSimulationAlgorithmImpl
title: TrotterSimulationAlgorithmImpl işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TrotterSimulationAlgorithmImpl
qsharp.summary: Makes repeated calls to `TrotterStep` to approximate the time-evolution operator exp(_-iHt_).
ms.openlocfilehash: b2411950b90eb676b1da53bd06bde648099e2db4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858882"
---
# <a name="trottersimulationalgorithmimpl-operation"></a><span data-ttu-id="d0c7e-102">TrotterSimulationAlgorithmImpl işlemi</span><span class="sxs-lookup"><span data-stu-id="d0c7e-102">TrotterSimulationAlgorithmImpl operation</span></span>

<span data-ttu-id="d0c7e-103">Ad alanı: [Microsoft. hisse. benzetim](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="d0c7e-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="d0c7e-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d0c7e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d0c7e-105">`TrotterStep`, Zaman-gelişme işlecinin exp (_-IHV_) yaklaşık olarak için yinelenen çağrılar yapar.</span><span class="sxs-lookup"><span data-stu-id="d0c7e-105">Makes repeated calls to `TrotterStep` to approximate the time-evolution operator exp(_-iHt_).</span></span>

```qsharp
operation TrotterSimulationAlgorithmImpl (trotterStepSize : Double, trotterOrder : Int, maxTime : Double, evolutionGenerator : Microsoft.Quantum.Simulation.EvolutionGenerator, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="d0c7e-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="d0c7e-106">Input</span></span>

### <a name="trotterstepsize--double"></a><span data-ttu-id="d0c7e-107">Troesstepsize: [çift](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="d0c7e-107">trotterStepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="d0c7e-108">Tek bir rahatlık adımında benzetimli zaman-gelişme süresi.</span><span class="sxs-lookup"><span data-stu-id="d0c7e-108">Duration of simulated time-evolution in single Trotter step.</span></span>


### <a name="trotterorder--int"></a><span data-ttu-id="d0c7e-109">Trokorder: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d0c7e-109">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d0c7e-110">Araba tümleştirici sırası.</span><span class="sxs-lookup"><span data-stu-id="d0c7e-110">Order of Trotter integrator.</span></span> <span data-ttu-id="d0c7e-111">Bu, 1 veya çift bir sayı olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="d0c7e-111">This must be either 1 or an even number.</span></span>


### <a name="maxtime--double"></a><span data-ttu-id="d0c7e-112">maxTime: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="d0c7e-112">maxTime : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="d0c7e-113">Simülasyon $t toplam süresi.</span><span class="sxs-lookup"><span data-stu-id="d0c7e-113">Total duration of simulation $t$.</span></span>


### <a name="evolutiongenerator--evolutiongenerator"></a><span data-ttu-id="d0c7e-114">evolutionGenerator: [Evolutiongenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span><span class="sxs-lookup"><span data-stu-id="d0c7e-114">evolutionGenerator : [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span></span>

<span data-ttu-id="d0c7e-115">Benzetim yapılacak sistemin tüm açıklaması.</span><span class="sxs-lookup"><span data-stu-id="d0c7e-115">A complete description of the system to be simulated.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="d0c7e-116">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="d0c7e-116">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="d0c7e-117">Bu, simülasyonu tarafından üzerinde işlem yaptığı.</span><span class="sxs-lookup"><span data-stu-id="d0c7e-117">Qubits acted on by simulation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d0c7e-118">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d0c7e-118">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

