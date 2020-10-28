---
uid: Microsoft.Quantum.Simulation.PauliEvolutionImpl
title: Paulievolutionımpl işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliEvolutionImpl
qsharp.summary: >-
  Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.

  See [Dynamical Generator Modeling](/quantum/libraries/data-structures#dynamical-generator-modeling) for more details.
ms.openlocfilehash: 2fc9fda2dd6eec71d8b17ba8a00d8545e517eec8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730906"
---
# <a name="paulievolutionimpl-operation"></a><span data-ttu-id="baaa1-102">Paulievolutionımpl işlemi</span><span class="sxs-lookup"><span data-stu-id="baaa1-102">PauliEvolutionImpl operation</span></span>

<span data-ttu-id="baaa1-103">Ad alanı: [Microsoft. hisse. benzetim](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="baaa1-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="baaa1-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="baaa1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="baaa1-105">Bir dinamik üreticisini bir simulatable Gates kümesi ve Pauli temelinde genişletme olarak temsil eder.</span><span class="sxs-lookup"><span data-stu-id="baaa1-105">Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.</span></span>

<span data-ttu-id="baaa1-106">Daha fazla ayrıntı için bkz. [Dynamical Oluşturucu modelleme](/quantum/libraries/data-structures#dynamical-generator-modeling) .</span><span class="sxs-lookup"><span data-stu-id="baaa1-106">See [Dynamical Generator Modeling](/quantum/libraries/data-structures#dynamical-generator-modeling) for more details.</span></span>

```qsharp
operation PauliEvolutionImpl (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex, delta : Double, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="baaa1-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="baaa1-107">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="baaa1-108">Generatorındex: [Generatorındex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="baaa1-108">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="baaa1-109">Pauli temelinde Unitary evrimi olarak temsil edilecek bir Oluşturucu dizini.</span><span class="sxs-lookup"><span data-stu-id="baaa1-109">A generator index to be represented as unitary evolution in the Pauli basis.</span></span>


### <a name="delta--double"></a><span data-ttu-id="baaa1-110">Delta: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="baaa1-110">delta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="baaa1-111">' De başvurulan terime göre geçen süre için bir çarpan `generatorIndex` .</span><span class="sxs-lookup"><span data-stu-id="baaa1-111">A multiplier on the duration of time-evolution by the term referenced in `generatorIndex`.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="baaa1-112">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="baaa1-112">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="baaa1-113">Zaman-gelişme işlecinden sonra kayıt yapılır.</span><span class="sxs-lookup"><span data-stu-id="baaa1-113">Register acted upon by time-evolution operator.</span></span>



## <a name="output--unit"></a><span data-ttu-id="baaa1-114">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="baaa1-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

