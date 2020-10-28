---
uid: Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerFermionImpl
title: JordanWignerFermionImpl işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: JordanWignerFermionImpl
qsharp.summary: >-
  Represents a dynamical generator as a set of simulatable gates and an expansion in the JordanWigner basis.

  See [Dynamical Generator Modeling](../libraries/data-structures#dynamical-generator-modeling) for more details.
ms.openlocfilehash: 616174d4d7f5ac8f4cea9454098d819468076648
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727775"
---
# <a name="jordanwignerfermionimpl-operation"></a><span data-ttu-id="e8062-102">JordanWignerFermionImpl işlemi</span><span class="sxs-lookup"><span data-stu-id="e8062-102">JordanWignerFermionImpl operation</span></span>

<span data-ttu-id="e8062-103">Ad alanı: [Microsoft. hisse. Chemistry. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="e8062-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="e8062-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e8062-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e8062-105">Bir dinamik üreticisini bir simulatable Gates kümesi ve JordanWigner temelinde bir genişletme olarak temsil eder.</span><span class="sxs-lookup"><span data-stu-id="e8062-105">Represents a dynamical generator as a set of simulatable gates and an expansion in the JordanWigner basis.</span></span>

<span data-ttu-id="e8062-106">Daha fazla ayrıntı için bkz. [Dynamical Oluşturucu modelleme](../libraries/data-structures#dynamical-generator-modeling) .</span><span class="sxs-lookup"><span data-stu-id="e8062-106">See [Dynamical Generator Modeling](../libraries/data-structures#dynamical-generator-modeling) for more details.</span></span>

```qsharp
operation JordanWignerFermionImpl (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="e8062-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="e8062-107">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="e8062-108">Generatorındex: [Generatorındex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="e8062-108">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="e8062-109">JordanWigner içinde Unitary evrimi olarak temsil edilecek bir Oluşturucu dizini.</span><span class="sxs-lookup"><span data-stu-id="e8062-109">A generator index to be represented as unitary evolution in the JordanWigner.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="e8062-110">stepSize: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e8062-110">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e8062-111">' De başvurulan terime göre geçen süre için bir çarpan `generatorIndex` .</span><span class="sxs-lookup"><span data-stu-id="e8062-111">A multiplier on the duration of time-evolution by the term referenced in `generatorIndex`.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="e8062-112">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="e8062-112">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="e8062-113">Zaman-gelişme işlecinden sonra kayıt yapılır.</span><span class="sxs-lookup"><span data-stu-id="e8062-113">Register acted upon by time-evolution operator.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e8062-114">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e8062-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

