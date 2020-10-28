---
uid: Microsoft.Quantum.Simulation.GetGeneratorSystemFunction
title: GetGeneratorSystemFunction işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: GetGeneratorSystemFunction
qsharp.summary: Retrieves the `GeneratorIndex` function in a `GeneratorSystem`.
ms.openlocfilehash: 60ebbdbd1020d41a54426377043fc0c84ceec504
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733535"
---
# <a name="getgeneratorsystemfunction-function"></a><span data-ttu-id="7740e-102">GetGeneratorSystemFunction işlevi</span><span class="sxs-lookup"><span data-stu-id="7740e-102">GetGeneratorSystemFunction function</span></span>

<span data-ttu-id="7740e-103">Ad alanı: [Microsoft. hisse. benzetim](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="7740e-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="7740e-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7740e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7740e-105">`GeneratorIndex`İçindeki işlevini alır `GeneratorSystem` .</span><span class="sxs-lookup"><span data-stu-id="7740e-105">Retrieves the `GeneratorIndex` function in a `GeneratorSystem`.</span></span>

```qsharp
function GetGeneratorSystemFunction (generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem) : (Int -> Microsoft.Quantum.Simulation.GeneratorIndex)
```


## <a name="input"></a><span data-ttu-id="7740e-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="7740e-106">Input</span></span>

### <a name="generatorsystem--generatorsystem"></a><span data-ttu-id="7740e-107">generatorSystem: [Generatorsystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="7740e-107">generatorSystem : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="7740e-108">`GeneratorSystem`İlgi çekici.</span><span class="sxs-lookup"><span data-stu-id="7740e-108">The `GeneratorSystem` of interest.</span></span>



## <a name="output--int---generatorindex"></a><span data-ttu-id="7740e-109">Çıkış: [Int](xref:microsoft.quantum.lang-ref.int) -> [generatorındex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="7740e-109">Output : [Int](xref:microsoft.quantum.lang-ref.int) -> [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="7740e-110">`GeneratorIndex`Hamiltonian içindeki her terimi dizine alan bir işlev.</span><span class="sxs-lookup"><span data-stu-id="7740e-110">An function that indexes each `GeneratorIndex` term in a Hamiltonian.</span></span>

## <a name="see-also"></a><span data-ttu-id="7740e-111">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="7740e-111">See Also</span></span>

- [<span data-ttu-id="7740e-112">Microsoft. hisse. simülasyon. Generatorındex</span><span class="sxs-lookup"><span data-stu-id="7740e-112">Microsoft.Quantum.Simulation.GeneratorIndex</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorIndex)
- [<span data-ttu-id="7740e-113">Microsoft. hisse. simülasyon. GeneratorSystem</span><span class="sxs-lookup"><span data-stu-id="7740e-113">Microsoft.Quantum.Simulation.GeneratorSystem</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorSystem)