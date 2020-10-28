---
uid: Microsoft.Quantum.Simulation.InterpolatedEvolution
title: Enterpolategerileme işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: InterpolatedEvolution
qsharp.summary: Interpolates between two generators with a uniform schedule, returning an operation that applies simulated evolution under the resulting time-dependent generator to a qubit register.
ms.openlocfilehash: 18026b9872f6a3344a1e5c2122f55927975ccb59
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726306"
---
# <a name="interpolatedevolution-function"></a><span data-ttu-id="55455-102">Enterpolategerileme işlevi</span><span class="sxs-lookup"><span data-stu-id="55455-102">InterpolatedEvolution function</span></span>

<span data-ttu-id="55455-103">Ad alanı: [Microsoft. hisse. benzetim](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="55455-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="55455-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="55455-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="55455-105">, Zaman içinde zamana bağlı Oluşturucu altında bir qubit kaydına benzetimci uygulayan bir işlem döndüren, tek düzen ile iki üretici arasında enterpolasyonlar.</span><span class="sxs-lookup"><span data-stu-id="55455-105">Interpolates between two generators with a uniform schedule, returning an operation that applies simulated evolution under the resulting time-dependent generator to a qubit register.</span></span>

```qsharp
function InterpolatedEvolution (interpolationTime : Double, evolutionGeneratorStart : Microsoft.Quantum.Simulation.EvolutionGenerator, evolutionGeneratorEnd : Microsoft.Quantum.Simulation.EvolutionGenerator, timeDependentSimulationAlgorithm : Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="55455-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="55455-106">Input</span></span>

### <a name="interpolationtime--double"></a><span data-ttu-id="55455-107">Enterpolalationtime: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="55455-107">interpolationTime : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="55455-108">İlişkilendirmeyi gerçekleştirme süresi.</span><span class="sxs-lookup"><span data-stu-id="55455-108">Time to perform the interpolation over.</span></span>


### <a name="evolutiongeneratorstart--evolutiongenerator"></a><span data-ttu-id="55455-109">evolutionGeneratorStart: [Evolutiongenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span><span class="sxs-lookup"><span data-stu-id="55455-109">evolutionGeneratorStart : [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span></span>

<span data-ttu-id="55455-110">Altında gelişmeye benzetim yapılacak ilk Oluşturucu.</span><span class="sxs-lookup"><span data-stu-id="55455-110">Initial generator to simulate evolution under.</span></span>


### <a name="evolutiongeneratorend--evolutiongenerator"></a><span data-ttu-id="55455-111">evolutionGeneratorEnd: [Evolutiongenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span><span class="sxs-lookup"><span data-stu-id="55455-111">evolutionGeneratorEnd : [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span></span>

<span data-ttu-id="55455-112">Altındaki evçanın benzetimini yapmak için nihai Oluşturucu.</span><span class="sxs-lookup"><span data-stu-id="55455-112">Final generator to simulate evolution under.</span></span>


### <a name="timedependentsimulationalgorithm--timedependentsimulationalgorithm"></a><span data-ttu-id="55455-113">timeDependentSimulationAlgorithm: [timeDependentSimulationAlgorithm](xref:Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm)</span><span class="sxs-lookup"><span data-stu-id="55455-113">timeDependentSimulationAlgorithm : [TimeDependentSimulationAlgorithm](xref:Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm)</span></span>

<span data-ttu-id="55455-114">Tekdüzen ilişkilendirme zamanlaması sırasında evrimde benzetimini yapmak için kullanılacak zamana bağlı bir simülasyon algoritması.</span><span class="sxs-lookup"><span data-stu-id="55455-114">A time-dependent simulation algorithm that will be used to simulate evolution during the uniform interpolation schedule.</span></span>



## <a name="output--qubit--unit-adj--ctl"></a><span data-ttu-id="55455-115">Output: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [birim](xref:microsoft.quantum.lang-ref.unit) ayarlama ve CTL</span><span class="sxs-lookup"><span data-stu-id="55455-115">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>



## <a name="remarks"></a><span data-ttu-id="55455-116">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="55455-116">Remarks</span></span>

<span data-ttu-id="55455-117">Enterpolasyon süresi Adiabatik koşullarını karşılayacak şekilde seçilirse, bu işlev son dinamik üreticisi için Adiabatik durum hazırlığı gerçekleştiren bir işlem döndürür.</span><span class="sxs-lookup"><span data-stu-id="55455-117">If the interpolation time is chosen to meet the adiabatic conditions, then this function returns an operation which performs adiabatic state preparation for the final dynamical generator.</span></span>