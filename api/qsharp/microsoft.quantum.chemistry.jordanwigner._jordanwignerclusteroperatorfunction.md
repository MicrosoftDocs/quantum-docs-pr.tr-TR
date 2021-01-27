---
uid: Microsoft.Quantum.Chemistry.JordanWigner._JordanWignerClusterOperatorFunction
title: _JordanWignerClusterOperatorFunction işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _JordanWignerClusterOperatorFunction
qsharp.summary: Represents a dynamical generator as a set of simulatable gates and an expansion in the JordanWigner basis.
ms.openlocfilehash: 71aa0256b4d2911fe9d8e3ca091735d6375ed23e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839501"
---
# <a name="_jordanwignerclusteroperatorfunction-function"></a><span data-ttu-id="fd7c9-102">_JordanWignerClusterOperatorFunction işlevi</span><span class="sxs-lookup"><span data-stu-id="fd7c9-102">_JordanWignerClusterOperatorFunction function</span></span>

<span data-ttu-id="fd7c9-103">Ad alanı: [Microsoft. hisse. Chemistry. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="fd7c9-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="fd7c9-104">Paket: [Microsoft. hisse. Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="fd7c9-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="fd7c9-105">Bir dinamik üreticisini bir simulatable Gates kümesi ve JordanWigner temelinde bir genişletme olarak temsil eder.</span><span class="sxs-lookup"><span data-stu-id="fd7c9-105">Represents a dynamical generator as a set of simulatable gates and an expansion in the JordanWigner basis.</span></span>

```qsharp
function _JordanWignerClusterOperatorFunction (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.EvolutionUnitary
```


## <a name="input"></a><span data-ttu-id="fd7c9-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="fd7c9-106">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="fd7c9-107">Generatorındex: [Generatorındex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="fd7c9-107">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="fd7c9-108">JordanWigner içinde Unitary evrimi olarak temsil edilecek bir Oluşturucu dizini.</span><span class="sxs-lookup"><span data-stu-id="fd7c9-108">A generator index to be represented as unitary evolution in the JordanWigner.</span></span>



## <a name="output--evolutionunitary"></a><span data-ttu-id="fd7c9-109">Çıkış: [Evolutionunitary](xref:Microsoft.Quantum.Simulation.EvolutionUnitary)</span><span class="sxs-lookup"><span data-stu-id="fd7c9-109">Output : [EvolutionUnitary](xref:Microsoft.Quantum.Simulation.EvolutionUnitary)</span></span>

<span data-ttu-id="fd7c9-110">`EvolutionUnitary`' Generatorındex ' içinde başvurulan terime göre zaman gelişini temsil eden bir.</span><span class="sxs-lookup"><span data-stu-id="fd7c9-110">An `EvolutionUnitary` representing time-evolution by the term referenced in \`generatorIndex.</span></span>