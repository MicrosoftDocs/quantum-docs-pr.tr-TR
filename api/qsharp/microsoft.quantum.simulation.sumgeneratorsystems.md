---
uid: Microsoft.Quantum.Simulation.SumGeneratorSystems
title: SumGeneratorSystems işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: SumGeneratorSystems
qsharp.summary: Adds multiple `GeneratorSystem`s to create a new GeneratorSystem.
ms.openlocfilehash: 7cb18e161dce3a52d7c9a0bf6a45d4818db2b849
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192477"
---
# <a name="sumgeneratorsystems-function"></a><span data-ttu-id="3188b-102">SumGeneratorSystems işlevi</span><span class="sxs-lookup"><span data-stu-id="3188b-102">SumGeneratorSystems function</span></span>

<span data-ttu-id="3188b-103">Ad alanı: [Microsoft. hisse. benzetim](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="3188b-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="3188b-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3188b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3188b-105">`GeneratorSystem`Yeni bir GeneratorSystem oluşturmak için birden çok s ekler.</span><span class="sxs-lookup"><span data-stu-id="3188b-105">Adds multiple `GeneratorSystem`s to create a new GeneratorSystem.</span></span>

```qsharp
function SumGeneratorSystems (generatorSystems : Microsoft.Quantum.Simulation.GeneratorSystem[]) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="3188b-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="3188b-106">Input</span></span>

### <a name="generatorsystems--generatorsystem"></a><span data-ttu-id="3188b-107">generatorSystems: [generatorsystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)[]</span><span class="sxs-lookup"><span data-stu-id="3188b-107">generatorSystems : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)[]</span></span>

<span data-ttu-id="3188b-108">Türünde bir dizi `GeneratorSystem[]` .</span><span class="sxs-lookup"><span data-stu-id="3188b-108">An array of type `GeneratorSystem[]`.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="3188b-109">Çıkış: [Generatorsystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="3188b-109">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="3188b-110">`GeneratorSystem`Giriş Oluşturucu sistemlerinin toplamı olan bir sistemi temsil eden.</span><span class="sxs-lookup"><span data-stu-id="3188b-110">A `GeneratorSystem` representing a system that is the sum of the input generator systems.</span></span>

## <a name="see-also"></a><span data-ttu-id="3188b-111">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="3188b-111">See Also</span></span>

- [<span data-ttu-id="3188b-112">Microsoft. hisse. simülasyon. GeneratorSystem</span><span class="sxs-lookup"><span data-stu-id="3188b-112">Microsoft.Quantum.Simulation.GeneratorSystem</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorSystem)