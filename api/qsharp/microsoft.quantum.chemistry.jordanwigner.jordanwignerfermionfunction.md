---
uid: Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerFermionFunction
title: JordanWignerFermionFunction işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: JordanWignerFermionFunction
qsharp.summary: Represents a dynamical generator as a set of simulatable gates and an expansion in the JordanWigner basis.
ms.openlocfilehash: e1eeed0dcd4084401e2680ff1188db4225ee85ca
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214764"
---
# <a name="jordanwignerfermionfunction-function"></a><span data-ttu-id="548e3-102">JordanWignerFermionFunction işlevi</span><span class="sxs-lookup"><span data-stu-id="548e3-102">JordanWignerFermionFunction function</span></span>

<span data-ttu-id="548e3-103">Ad alanı: [Microsoft. hisse. Chemistry. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="548e3-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="548e3-104">Paket: [Microsoft. hisse. Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="548e3-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="548e3-105">Bir dinamik üreticisini bir simulatable Gates kümesi ve JordanWigner temelinde bir genişletme olarak temsil eder.</span><span class="sxs-lookup"><span data-stu-id="548e3-105">Represents a dynamical generator as a set of simulatable gates and an expansion in the JordanWigner basis.</span></span>

```qsharp
function JordanWignerFermionFunction (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.EvolutionUnitary
```


## <a name="input"></a><span data-ttu-id="548e3-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="548e3-106">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="548e3-107">Generatorındex: [Generatorındex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="548e3-107">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="548e3-108">JordanWigner içinde Unitary evrimi olarak temsil edilecek bir Oluşturucu dizini.</span><span class="sxs-lookup"><span data-stu-id="548e3-108">A generator index to be represented as unitary evolution in the JordanWigner.</span></span>



## <a name="output--evolutionunitary"></a><span data-ttu-id="548e3-109">Çıkış: [Evolutionunitary](xref:Microsoft.Quantum.Simulation.EvolutionUnitary)</span><span class="sxs-lookup"><span data-stu-id="548e3-109">Output : [EvolutionUnitary](xref:Microsoft.Quantum.Simulation.EvolutionUnitary)</span></span>

<span data-ttu-id="548e3-110">`EvolutionUnitary`' Generatorındex ' içinde başvurulan terime göre zaman gelişini temsil eden bir.</span><span class="sxs-lookup"><span data-stu-id="548e3-110">An `EvolutionUnitary` representing time-evolution by the term referenced in \`generatorIndex.</span></span>