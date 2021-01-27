---
uid: Microsoft.Quantum.Simulation.InterpolateGeneratorSystems
title: Enterpolategeneratorsystems işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: InterpolateGeneratorSystems
qsharp.summary: Returns a `TimeDependentGeneratorSystem` representing the linear interpolation between two `GeneratorSystem`s.
ms.openlocfilehash: c56f1eaf13afb649777c0d9368e97d85996cc67b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842273"
---
# <a name="interpolategeneratorsystems-function"></a><span data-ttu-id="9fd30-102">Enterpolategeneratorsystems işlevi</span><span class="sxs-lookup"><span data-stu-id="9fd30-102">InterpolateGeneratorSystems function</span></span>

<span data-ttu-id="9fd30-103">Ad alanı: [Microsoft. hisse. benzetim](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="9fd30-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="9fd30-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9fd30-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9fd30-105">`TimeDependentGeneratorSystem`İki s arasındaki doğrusal ilişkilendirmeyi temsil eden bir döndürür `GeneratorSystem` .</span><span class="sxs-lookup"><span data-stu-id="9fd30-105">Returns a `TimeDependentGeneratorSystem` representing the linear interpolation between two `GeneratorSystem`s.</span></span>

```qsharp
function InterpolateGeneratorSystems (generatorSystemStart : Microsoft.Quantum.Simulation.GeneratorSystem, generatorSystemEnd : Microsoft.Quantum.Simulation.GeneratorSystem) : Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem
```


## <a name="input"></a><span data-ttu-id="9fd30-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="9fd30-106">Input</span></span>

### <a name="generatorsystemstart--generatorsystem"></a><span data-ttu-id="9fd30-107">generatorSystemStart: [Generatorsystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="9fd30-107">generatorSystemStart : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="9fd30-108">Başlat `GeneratorSystem` .</span><span class="sxs-lookup"><span data-stu-id="9fd30-108">The start `GeneratorSystem`.</span></span>


### <a name="generatorsystemend--generatorsystem"></a><span data-ttu-id="9fd30-109">generatorSystemEnd: [Generatorsystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="9fd30-109">generatorSystemEnd : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="9fd30-110">Son `GeneratorSystem` .</span><span class="sxs-lookup"><span data-stu-id="9fd30-110">The end `GeneratorSystem`.</span></span>



## <a name="output--timedependentgeneratorsystem"></a><span data-ttu-id="9fd30-111">Çıkış: [Timedependentgeneratorsystem](xref:Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="9fd30-111">Output : [TimeDependentGeneratorSystem](xref:Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem)</span></span>

<span data-ttu-id="9fd30-112">`TimeDependentGeneratorSystem`Ağırlık $ (1-s) $ on `generatorSystemStart` ve ağırlık $s $ on ile giriş Oluşturucu sistemlerinin toplamı olan bir sistemi temsil eden bir sistemdir `generatorSystemEnd` .</span><span class="sxs-lookup"><span data-stu-id="9fd30-112">A `TimeDependentGeneratorSystem` representing a system that is the sum of the input generator systems, with weight $(1-s)$ on `generatorSystemStart` and weight $s$ on `generatorSystemEnd`.</span></span>

## <a name="see-also"></a><span data-ttu-id="9fd30-113">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="9fd30-113">See Also</span></span>

- [<span data-ttu-id="9fd30-114">Microsoft. hisse. simülasyon. GeneratorSystem</span><span class="sxs-lookup"><span data-stu-id="9fd30-114">Microsoft.Quantum.Simulation.GeneratorSystem</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorSystem)
- [<span data-ttu-id="9fd30-115">Microsoft. hisse. simülasyon. TimeDependentGeneratorSystem</span><span class="sxs-lookup"><span data-stu-id="9fd30-115">Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem</span></span>](xref:Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem)