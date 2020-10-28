---
uid: Microsoft.Quantum.Research.Chemistry.JWOptimizedFermionEvolutionFunction
title: Jwoptimizedfermıonevolutionfunction işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: JWOptimizedFermionEvolutionFunction
qsharp.summary: Represents a dynamical generator as a set of simulatable gates and an expansion in the JWOptimized basis.
ms.openlocfilehash: 952f3dc4ab0595ace0ee34c040cb21969afa111f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726401"
---
# <a name="jwoptimizedfermionevolutionfunction-function"></a><span data-ttu-id="f8fc9-102">Jwoptimizedfermıonevolutionfunction işlevi</span><span class="sxs-lookup"><span data-stu-id="f8fc9-102">JWOptimizedFermionEvolutionFunction function</span></span>

<span data-ttu-id="f8fc9-103">Ad alanı: [Microsoft. hisse. Research. Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="f8fc9-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="f8fc9-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f8fc9-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f8fc9-105">Bir dinamik üreticisini bir simulatable Gates kümesi ve jwoptimize temelinde bir genişletme olarak temsil eder.</span><span class="sxs-lookup"><span data-stu-id="f8fc9-105">Represents a dynamical generator as a set of simulatable gates and an expansion in the JWOptimized basis.</span></span>

```qsharp
function JWOptimizedFermionEvolutionFunction (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex, parityQubit : Qubit) : Microsoft.Quantum.Simulation.EvolutionUnitary
```


## <a name="input"></a><span data-ttu-id="f8fc9-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="f8fc9-106">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="f8fc9-107">Generatorındex: [Generatorındex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="f8fc9-107">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="f8fc9-108">Jwoptimize temelinde Unitary evrimi olarak temsil edilecek bir Oluşturucu dizin.</span><span class="sxs-lookup"><span data-stu-id="f8fc9-108">A generator index to be represented as unitary evolution in the JWOptimized basis.</span></span>


### <a name="parityqubit--qubit"></a><span data-ttu-id="f8fc9-109">parityQubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="f8fc9-109">parityQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="f8fc9-110">Zaman evrimi 'nin işaretini belirleyen qubit.</span><span class="sxs-lookup"><span data-stu-id="f8fc9-110">Qubit that determines the sign of time-evolution.</span></span>



## <a name="output--evolutionunitary"></a><span data-ttu-id="f8fc9-111">Çıkış: [Evolutionunitary](xref:Microsoft.Quantum.Simulation.EvolutionUnitary)</span><span class="sxs-lookup"><span data-stu-id="f8fc9-111">Output : [EvolutionUnitary](xref:Microsoft.Quantum.Simulation.EvolutionUnitary)</span></span>

<span data-ttu-id="f8fc9-112">`EvolutionUnitary`' Generatorındex ' içinde başvurulan terime göre zaman gelişini temsil eden bir.</span><span class="sxs-lookup"><span data-stu-id="f8fc9-112">An `EvolutionUnitary` representing time-evolution by the term referenced in \`generatorIndex.</span></span>