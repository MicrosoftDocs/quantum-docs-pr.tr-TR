---
uid: Microsoft.Quantum.Simulation.PauliStringFromGenIdx
title: PauliStringFromGenIdx işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliStringFromGenIdx
qsharp.summary: Extracts the Pauli string and its qubit indices of a Pauli term described by a `GeneratorIndex`.
ms.openlocfilehash: 048f91411099d24f3c0c5fd8ae3703779e7ab8a2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847905"
---
# <a name="paulistringfromgenidx-function"></a><span data-ttu-id="57f8f-102">PauliStringFromGenIdx işlevi</span><span class="sxs-lookup"><span data-stu-id="57f8f-102">PauliStringFromGenIdx function</span></span>

<span data-ttu-id="57f8f-103">Ad alanı: [Microsoft. hisse. benzetim](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="57f8f-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="57f8f-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="57f8f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="57f8f-105">Pauli dizesini ve tarafından tanımlanan Pauli teriminin qubit dizinlerini ayıklar `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="57f8f-105">Extracts the Pauli string and its qubit indices of a Pauli term described by a `GeneratorIndex`.</span></span>

```qsharp
function PauliStringFromGenIdx (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex) : (Pauli[], Int[])
```


## <a name="input"></a><span data-ttu-id="57f8f-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="57f8f-106">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="57f8f-107">Generatorındex: [Generatorındex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="57f8f-107">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="57f8f-108">`GeneratorIndex` Pauli terimini kodlayan tür.</span><span class="sxs-lookup"><span data-stu-id="57f8f-108">`GeneratorIndex` type that encodes a Pauli term.</span></span>



## <a name="output--pauliint"></a><span data-ttu-id="57f8f-109">Çıkış: ([Pauli](xref:microsoft.quantum.lang-ref.pauli)[],[Int](xref:microsoft.quantum.lang-ref.int)[])</span><span class="sxs-lookup"><span data-stu-id="57f8f-109">Output : ([Pauli](xref:microsoft.quantum.lang-ref.pauli)[],[Int](xref:microsoft.quantum.lang-ref.int)[])</span></span>

<span data-ttu-id="57f8f-110">Tarafından açıklanan terimin Pauli dizesi `GeneratorIndex` ve üzerinde hareket eden qubits dizinleri.</span><span class="sxs-lookup"><span data-stu-id="57f8f-110">The Pauli string of the term described by a `GeneratorIndex`, and indices to the qubits it acts on.</span></span>