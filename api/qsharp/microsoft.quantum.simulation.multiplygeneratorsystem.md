---
uid: Microsoft.Quantum.Simulation.MultiplyGeneratorSystem
title: MultiplyGeneratorSystem işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: MultiplyGeneratorSystem
qsharp.summary: Multiplies the coefficient of all terms in a `GeneratorSystem`.
ms.openlocfilehash: cebd08c86ad8a3793ba7d0e9ce241d7a1ef046ae
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858506"
---
# <a name="multiplygeneratorsystem-function"></a><span data-ttu-id="b26fd-102">MultiplyGeneratorSystem işlevi</span><span class="sxs-lookup"><span data-stu-id="b26fd-102">MultiplyGeneratorSystem function</span></span>

<span data-ttu-id="b26fd-103">Ad alanı: [Microsoft. hisse. benzetim](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="b26fd-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="b26fd-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b26fd-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b26fd-105">İçindeki tüm koşulların katsayısını çarpar `GeneratorSystem` .</span><span class="sxs-lookup"><span data-stu-id="b26fd-105">Multiplies the coefficient of all terms in a `GeneratorSystem`.</span></span>

```qsharp
function MultiplyGeneratorSystem (multiplier : Double, generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="b26fd-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="b26fd-106">Input</span></span>

### <a name="multiplier--double"></a><span data-ttu-id="b26fd-107">çarpan: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b26fd-107">multiplier : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b26fd-108">Katlayıcı üzerindeki çarpan.</span><span class="sxs-lookup"><span data-stu-id="b26fd-108">The multiplier on the coefficient.</span></span>


### <a name="generatorsystem--generatorsystem"></a><span data-ttu-id="b26fd-109">generatorSystem: [Generatorsystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="b26fd-109">generatorSystem : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="b26fd-110">`GeneratorSystem`Çarpmak için.</span><span class="sxs-lookup"><span data-stu-id="b26fd-110">The `GeneratorSystem` to be multiplied.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="b26fd-111">Çıkış: [Generatorsystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="b26fd-111">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="b26fd-112">`GeneratorSystem`Çarpanların çarpanlarını daha büyük olan bir sistemi temsil eden `multiplier` .</span><span class="sxs-lookup"><span data-stu-id="b26fd-112">A `GeneratorSystem` representing a system with coefficients a factor `multiplier` larger.</span></span>

## <a name="see-also"></a><span data-ttu-id="b26fd-113">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="b26fd-113">See Also</span></span>

- [<span data-ttu-id="b26fd-114">Microsoft. hisse. simülasyon. GeneratorSystem</span><span class="sxs-lookup"><span data-stu-id="b26fd-114">Microsoft.Quantum.Simulation.GeneratorSystem</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorSystem)