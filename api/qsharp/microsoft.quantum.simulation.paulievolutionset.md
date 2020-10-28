---
uid: Microsoft.Quantum.Simulation.PauliEvolutionSet
title: PauliEvolutionSet işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliEvolutionSet
qsharp.summary: Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.
ms.openlocfilehash: 89c81aca4cfad6087d764ac8f5a0f1426e905e4b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732103"
---
# <a name="paulievolutionset-function"></a><span data-ttu-id="062b8-102">PauliEvolutionSet işlevi</span><span class="sxs-lookup"><span data-stu-id="062b8-102">PauliEvolutionSet function</span></span>

<span data-ttu-id="062b8-103">Ad alanı: [Microsoft. hisse. benzetim](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="062b8-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="062b8-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="062b8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="062b8-105">Bir dinamik üreticisini bir simulatable Gates kümesi ve Pauli temelinde genişletme olarak temsil eder.</span><span class="sxs-lookup"><span data-stu-id="062b8-105">Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.</span></span>

```qsharp
function PauliEvolutionSet () : Microsoft.Quantum.Simulation.EvolutionSet
```


## <a name="output--evolutionset"></a><span data-ttu-id="062b8-106">Çıkış: [Evolutionset](xref:Microsoft.Quantum.Simulation.EvolutionSet)</span><span class="sxs-lookup"><span data-stu-id="062b8-106">Output : [EvolutionSet](xref:Microsoft.Quantum.Simulation.EvolutionSet)</span></span>

<span data-ttu-id="062b8-107">`EvolutionSet` `GeneratorIndex` Pauli tabanlı için bir ' EvolutionUnitary ' ile eşleyen bir.</span><span class="sxs-lookup"><span data-stu-id="062b8-107">An `EvolutionSet` that maps a `GeneratorIndex` for the Pauli basis to an \`EvolutionUnitary.</span></span>

## <a name="remarks"></a><span data-ttu-id="062b8-108">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="062b8-108">Remarks</span></span>

<span data-ttu-id="062b8-109">Bu, kısmi uygulaması tarafından elde edilir <xref:microsoft.quantum.simulation.paulievolutionfunction> .</span><span class="sxs-lookup"><span data-stu-id="062b8-109">This is obtained by partial application of <xref:microsoft.quantum.simulation.paulievolutionfunction>.</span></span>