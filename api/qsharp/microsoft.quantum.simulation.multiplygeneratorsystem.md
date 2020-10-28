---
uid: Microsoft.Quantum.Simulation.MultiplyGeneratorSystem
title: MultiplyGeneratorSystem işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: MultiplyGeneratorSystem
qsharp.summary: Multiplies the coefficient of all terms in a `GeneratorSystem`.
ms.openlocfilehash: 1d28de99dab3f7aca4bf3706fe98f5ef7c5286a7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730927"
---
# <a name="multiplygeneratorsystem-function"></a><span data-ttu-id="e63f5-102">MultiplyGeneratorSystem işlevi</span><span class="sxs-lookup"><span data-stu-id="e63f5-102">MultiplyGeneratorSystem function</span></span>

<span data-ttu-id="e63f5-103">Ad alanı: [Microsoft. hisse. benzetim](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="e63f5-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="e63f5-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e63f5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e63f5-105">İçindeki tüm koşulların katsayısını çarpar `GeneratorSystem` .</span><span class="sxs-lookup"><span data-stu-id="e63f5-105">Multiplies the coefficient of all terms in a `GeneratorSystem`.</span></span>

```qsharp
function MultiplyGeneratorSystem (multiplier : Double, generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="e63f5-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="e63f5-106">Input</span></span>

### <a name="multiplier--double"></a><span data-ttu-id="e63f5-107">çarpan: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e63f5-107">multiplier : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e63f5-108">Katlayıcı üzerindeki çarpan.</span><span class="sxs-lookup"><span data-stu-id="e63f5-108">The multiplier on the coefficient.</span></span>


### <a name="generatorsystem--generatorsystem"></a><span data-ttu-id="e63f5-109">generatorSystem: [Generatorsystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="e63f5-109">generatorSystem : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="e63f5-110">`GeneratorSystem`Çarpmak için.</span><span class="sxs-lookup"><span data-stu-id="e63f5-110">The `GeneratorSystem` to be multiplied.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="e63f5-111">Çıkış: [Generatorsystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="e63f5-111">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="e63f5-112">`GeneratorSystem`Çarpanların çarpanlarını daha büyük olan bir sistemi temsil eden `multiplier` .</span><span class="sxs-lookup"><span data-stu-id="e63f5-112">A `GeneratorSystem` representing a system with coefficients a factor `multiplier` larger.</span></span>

## <a name="see-also"></a><span data-ttu-id="e63f5-113">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="e63f5-113">See Also</span></span>

- [<span data-ttu-id="e63f5-114">Microsoft. hisse. simülasyon. GeneratorSystem</span><span class="sxs-lookup"><span data-stu-id="e63f5-114">Microsoft.Quantum.Simulation.GeneratorSystem</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorSystem)