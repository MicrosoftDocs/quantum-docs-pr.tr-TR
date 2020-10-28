---
uid: Microsoft.Quantum.Simulation.PauliStringFromGenIdx
title: PauliStringFromGenIdx işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliStringFromGenIdx
qsharp.summary: Extracts the Pauli string and its qubit indices of a Pauli term described by a `GeneratorIndex`.
ms.openlocfilehash: 33da4bc3d7e58b87aef75b453b6af09a51214923
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726288"
---
# <a name="paulistringfromgenidx-function"></a><span data-ttu-id="c0d67-102">PauliStringFromGenIdx işlevi</span><span class="sxs-lookup"><span data-stu-id="c0d67-102">PauliStringFromGenIdx function</span></span>

<span data-ttu-id="c0d67-103">Ad alanı: [Microsoft. hisse. benzetim](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="c0d67-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="c0d67-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c0d67-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c0d67-105">Pauli dizesini ve tarafından tanımlanan Pauli teriminin qubit dizinlerini ayıklar `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="c0d67-105">Extracts the Pauli string and its qubit indices of a Pauli term described by a `GeneratorIndex`.</span></span>

```qsharp
function PauliStringFromGenIdx (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex) : (Pauli[], Int[])
```


## <a name="input"></a><span data-ttu-id="c0d67-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="c0d67-106">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="c0d67-107">Generatorındex: [Generatorındex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="c0d67-107">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="c0d67-108">`GeneratorIndex` Pauli terimini kodlayan tür.</span><span class="sxs-lookup"><span data-stu-id="c0d67-108">`GeneratorIndex` type that encodes a Pauli term.</span></span>



## <a name="output--pauliint"></a><span data-ttu-id="c0d67-109">Çıkış: ([Pauli](xref:microsoft.quantum.lang-ref.pauli)[],[Int](xref:microsoft.quantum.lang-ref.int)[])</span><span class="sxs-lookup"><span data-stu-id="c0d67-109">Output : ([Pauli](xref:microsoft.quantum.lang-ref.pauli)[],[Int](xref:microsoft.quantum.lang-ref.int)[])</span></span>

<span data-ttu-id="c0d67-110">Tarafından açıklanan terimin Pauli dizesi `GeneratorIndex` ve üzerinde hareket eden qubits dizinleri.</span><span class="sxs-lookup"><span data-stu-id="c0d67-110">The Pauli string of the term described by a `GeneratorIndex`, and indices to the qubits it acts on.</span></span>