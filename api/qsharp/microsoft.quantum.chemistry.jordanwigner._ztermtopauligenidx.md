---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ZTermToPauliGenIdx
title: _ZTermToPauliGenIdx işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ZTermToPauliGenIdx
qsharp.summary: Converts a GeneratorIndex describing a Z term to an expression 'GeneratorIndex[]' in terms of Paulis.
ms.openlocfilehash: 1569ec742778549b8754cdca8b2d9872310e8976
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727847"
---
# <a name="_ztermtopauligenidx-function"></a><span data-ttu-id="e6eef-102">_ZTermToPauliGenIdx işlevi</span><span class="sxs-lookup"><span data-stu-id="e6eef-102">_ZTermToPauliGenIdx function</span></span>

<span data-ttu-id="e6eef-103">Ad alanı: [Microsoft. hisse. Chemistry. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="e6eef-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="e6eef-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e6eef-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e6eef-105">Bir Z terimini, Paulıs açısından ' Generatorındex [] ' ifadesine tanıtan bir Generatorındex dönüştürür.</span><span class="sxs-lookup"><span data-stu-id="e6eef-105">Converts a GeneratorIndex describing a Z term to an expression 'GeneratorIndex[]' in terms of Paulis.</span></span>

```qsharp
function _ZTermToPauliGenIdx (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.GeneratorIndex[]
```


## <a name="input"></a><span data-ttu-id="e6eef-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="e6eef-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="e6eef-107">terim: [Generatorındex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="e6eef-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="e6eef-108">`GeneratorIndex` Z terimini temsil eden.</span><span class="sxs-lookup"><span data-stu-id="e6eef-108">`GeneratorIndex` representing a Z term.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="e6eef-109">Output: [Generatorındex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span><span class="sxs-lookup"><span data-stu-id="e6eef-109">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span></span>

<span data-ttu-id="e6eef-110">' Generatorındex [] ', Z terimini Pauli terimleri olarak ifade.</span><span class="sxs-lookup"><span data-stu-id="e6eef-110">'GeneratorIndex[]' expressing Z term as Pauli terms.</span></span>