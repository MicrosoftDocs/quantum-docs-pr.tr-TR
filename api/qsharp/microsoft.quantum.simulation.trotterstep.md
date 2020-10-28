---
uid: Microsoft.Quantum.Simulation.TrotterStep
title: Trobir Step işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TrotterStep
qsharp.summary: Implements a single time-step of time-evolution by the system described in an `EvolutionGenerator` using a Trotter–Suzuki decomposition.
ms.openlocfilehash: 7a1a27ba4dc4b8b7bbc4da6a378d4a1494bc9415
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733991"
---
# <a name="trotterstep-function"></a><span data-ttu-id="f781d-102">Trobir Step işlevi</span><span class="sxs-lookup"><span data-stu-id="f781d-102">TrotterStep function</span></span>

<span data-ttu-id="f781d-103">Ad alanı: [Microsoft. hisse. benzetim](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="f781d-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="f781d-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f781d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f781d-105">, `EvolutionGenerator` Bir Trour – Suzuki ayrıştırma kullanımı ile açıklanan sistem tarafından tek seferlik bir zaman adımı uygular.</span><span class="sxs-lookup"><span data-stu-id="f781d-105">Implements a single time-step of time-evolution by the system described in an `EvolutionGenerator` using a Trotter–Suzuki decomposition.</span></span>

```qsharp
function TrotterStep (evolutionGenerator : Microsoft.Quantum.Simulation.EvolutionGenerator, trotterOrder : Int, trotterStepSize : Double) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="f781d-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="f781d-106">Input</span></span>

### <a name="evolutiongenerator--evolutiongenerator"></a><span data-ttu-id="f781d-107">evolutionGenerator: [Evolutiongenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span><span class="sxs-lookup"><span data-stu-id="f781d-107">evolutionGenerator : [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span></span>

<span data-ttu-id="f781d-108">Benzetim yapılacak sistemin tüm açıklaması.</span><span class="sxs-lookup"><span data-stu-id="f781d-108">A complete description of the system to be simulated.</span></span>


### <a name="trotterorder--int"></a><span data-ttu-id="f781d-109">Trokorder: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f781d-109">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f781d-110">Araba tümleştirici sırası.</span><span class="sxs-lookup"><span data-stu-id="f781d-110">Order of Trotter integrator.</span></span> <span data-ttu-id="f781d-111">Bu, 1 veya çift bir sayı olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="f781d-111">This must be either 1 or an even number.</span></span>


### <a name="trotterstepsize--double"></a><span data-ttu-id="f781d-112">Troesstepsize: [çift](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="f781d-112">trotterStepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="f781d-113">Tek bir rahatlık adımında benzetimli zaman-gelişme süresi.</span><span class="sxs-lookup"><span data-stu-id="f781d-113">Duration of simulated time-evolution in single Trotter step.</span></span>



## <a name="output--qubit--unit-adj--ctl"></a><span data-ttu-id="f781d-114">Output: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [birim](xref:microsoft.quantum.lang-ref.unit) ayarlama ve CTL</span><span class="sxs-lookup"><span data-stu-id="f781d-114">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="f781d-115">Süre için tek bir zaman gelişini yaklaştırın Unitary işlemi `trotterStepSize` .</span><span class="sxs-lookup"><span data-stu-id="f781d-115">Unitary operation that approximates a single step of time-evolution for duration `trotterStepSize`.</span></span>

## <a name="remarks"></a><span data-ttu-id="f781d-116">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="f781d-116">Remarks</span></span>

<span data-ttu-id="f781d-117">Trour – Suzuki ayrıştırma hakkında daha fazla bilgi için bkz. [zaman Içinde sıralı bileşim](/quantum/libraries/control-flow#time-ordered-composition).</span><span class="sxs-lookup"><span data-stu-id="f781d-117">For more on the Trotter–Suzuki decomposition, see [Time-Ordered Composition](/quantum/libraries/control-flow#time-ordered-composition).</span></span>