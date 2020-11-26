---
uid: Microsoft.Quantum.Simulation.InterpolatedEvolution
title: Enterpolategerileme işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: InterpolatedEvolution
qsharp.summary: Interpolates between two generators with a uniform schedule, returning an operation that applies simulated evolution under the resulting time-dependent generator to a qubit register.
ms.openlocfilehash: 2ad907c02a2412dd4bf95630f401b5f1db5c8a08
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225117"
---
# <a name="interpolatedevolution-function"></a><span data-ttu-id="d755a-102">Enterpolategerileme işlevi</span><span class="sxs-lookup"><span data-stu-id="d755a-102">InterpolatedEvolution function</span></span>

<span data-ttu-id="d755a-103">Ad alanı: [Microsoft. hisse. benzetim](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="d755a-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="d755a-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d755a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d755a-105">, Zaman içinde zamana bağlı Oluşturucu altında bir qubit kaydına benzetimci uygulayan bir işlem döndüren, tek düzen ile iki üretici arasında enterpolasyonlar.</span><span class="sxs-lookup"><span data-stu-id="d755a-105">Interpolates between two generators with a uniform schedule, returning an operation that applies simulated evolution under the resulting time-dependent generator to a qubit register.</span></span>

```qsharp
function InterpolatedEvolution (interpolationTime : Double, evolutionGeneratorStart : Microsoft.Quantum.Simulation.EvolutionGenerator, evolutionGeneratorEnd : Microsoft.Quantum.Simulation.EvolutionGenerator, timeDependentSimulationAlgorithm : Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="d755a-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="d755a-106">Input</span></span>

### <a name="interpolationtime--double"></a><span data-ttu-id="d755a-107">Enterpolalationtime: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="d755a-107">interpolationTime : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="d755a-108">İlişkilendirmeyi gerçekleştirme süresi.</span><span class="sxs-lookup"><span data-stu-id="d755a-108">Time to perform the interpolation over.</span></span>


### <a name="evolutiongeneratorstart--evolutiongenerator"></a><span data-ttu-id="d755a-109">evolutionGeneratorStart: [Evolutiongenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span><span class="sxs-lookup"><span data-stu-id="d755a-109">evolutionGeneratorStart : [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span></span>

<span data-ttu-id="d755a-110">Altında gelişmeye benzetim yapılacak ilk Oluşturucu.</span><span class="sxs-lookup"><span data-stu-id="d755a-110">Initial generator to simulate evolution under.</span></span>


### <a name="evolutiongeneratorend--evolutiongenerator"></a><span data-ttu-id="d755a-111">evolutionGeneratorEnd: [Evolutiongenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span><span class="sxs-lookup"><span data-stu-id="d755a-111">evolutionGeneratorEnd : [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span></span>

<span data-ttu-id="d755a-112">Altındaki evçanın benzetimini yapmak için nihai Oluşturucu.</span><span class="sxs-lookup"><span data-stu-id="d755a-112">Final generator to simulate evolution under.</span></span>


### <a name="timedependentsimulationalgorithm--timedependentsimulationalgorithm"></a><span data-ttu-id="d755a-113">timeDependentSimulationAlgorithm: [timeDependentSimulationAlgorithm](xref:Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm)</span><span class="sxs-lookup"><span data-stu-id="d755a-113">timeDependentSimulationAlgorithm : [TimeDependentSimulationAlgorithm](xref:Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm)</span></span>

<span data-ttu-id="d755a-114">Tekdüzen ilişkilendirme zamanlaması sırasında evrimde benzetimini yapmak için kullanılacak zamana bağlı bir simülasyon algoritması.</span><span class="sxs-lookup"><span data-stu-id="d755a-114">A time-dependent simulation algorithm that will be used to simulate evolution during the uniform interpolation schedule.</span></span>



## <a name="output--qubit--unit--is-adj--ctl"></a><span data-ttu-id="d755a-115">Output: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [birimi](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL</span><span class="sxs-lookup"><span data-stu-id="d755a-115">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>



## <a name="remarks"></a><span data-ttu-id="d755a-116">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="d755a-116">Remarks</span></span>

<span data-ttu-id="d755a-117">Enterpolasyon süresi Adiabatik koşullarını karşılayacak şekilde seçilirse, bu işlev son dinamik üreticisi için Adiabatik durum hazırlığı gerçekleştiren bir işlem döndürür.</span><span class="sxs-lookup"><span data-stu-id="d755a-117">If the interpolation time is chosen to meet the adiabatic conditions, then this function returns an operation which performs adiabatic state preparation for the final dynamical generator.</span></span>