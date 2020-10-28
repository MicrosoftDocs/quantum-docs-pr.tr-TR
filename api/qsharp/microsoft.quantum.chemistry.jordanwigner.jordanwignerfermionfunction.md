---
uid: Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerFermionFunction
title: JordanWignerFermionFunction işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: JordanWignerFermionFunction
qsharp.summary: Represents a dynamical generator as a set of simulatable gates and an expansion in the JordanWigner basis.
ms.openlocfilehash: 7d29393293acfc1748a1805f339951b1ff0f9b10
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727782"
---
# <a name="jordanwignerfermionfunction-function"></a><span data-ttu-id="f3c4a-102">JordanWignerFermionFunction işlevi</span><span class="sxs-lookup"><span data-stu-id="f3c4a-102">JordanWignerFermionFunction function</span></span>

<span data-ttu-id="f3c4a-103">Ad alanı: [Microsoft. hisse. Chemistry. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="f3c4a-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="f3c4a-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f3c4a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f3c4a-105">Bir dinamik üreticisini bir simulatable Gates kümesi ve JordanWigner temelinde bir genişletme olarak temsil eder.</span><span class="sxs-lookup"><span data-stu-id="f3c4a-105">Represents a dynamical generator as a set of simulatable gates and an expansion in the JordanWigner basis.</span></span>

```qsharp
function JordanWignerFermionFunction (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.EvolutionUnitary
```


## <a name="input"></a><span data-ttu-id="f3c4a-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="f3c4a-106">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="f3c4a-107">Generatorındex: [Generatorındex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="f3c4a-107">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="f3c4a-108">JordanWigner içinde Unitary evrimi olarak temsil edilecek bir Oluşturucu dizini.</span><span class="sxs-lookup"><span data-stu-id="f3c4a-108">A generator index to be represented as unitary evolution in the JordanWigner.</span></span>



## <a name="output--evolutionunitary"></a><span data-ttu-id="f3c4a-109">Çıkış: [Evolutionunitary](xref:Microsoft.Quantum.Simulation.EvolutionUnitary)</span><span class="sxs-lookup"><span data-stu-id="f3c4a-109">Output : [EvolutionUnitary](xref:Microsoft.Quantum.Simulation.EvolutionUnitary)</span></span>

<span data-ttu-id="f3c4a-110">`EvolutionUnitary`' Generatorındex ' içinde başvurulan terime göre zaman gelişini temsil eden bir.</span><span class="sxs-lookup"><span data-stu-id="f3c4a-110">An `EvolutionUnitary` representing time-evolution by the term referenced in \`generatorIndex.</span></span>