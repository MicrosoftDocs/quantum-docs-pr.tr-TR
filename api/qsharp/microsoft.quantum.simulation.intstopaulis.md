---
uid: Microsoft.Quantum.Simulation.IntsToPaulis
title: IntsToPaulis işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IntsToPaulis
qsharp.summary: Converts an array of integers to an array of single-qubit Pauli operators.
ms.openlocfilehash: 2333dcbd2988480e2b2b9b217b26705f3578de00
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230540"
---
# <a name="intstopaulis-function"></a><span data-ttu-id="86e01-102">IntsToPaulis işlevi</span><span class="sxs-lookup"><span data-stu-id="86e01-102">IntsToPaulis function</span></span>

<span data-ttu-id="86e01-103">Ad alanı: [Microsoft. hisse. benzetim](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="86e01-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="86e01-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="86e01-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="86e01-105">Bir tamsayılar dizisini tek qubit Pauli işleçleri dizisine dönüştürür.</span><span class="sxs-lookup"><span data-stu-id="86e01-105">Converts an array of integers to an array of single-qubit Pauli operators.</span></span>

```qsharp
function IntsToPaulis (ints : Int[]) : Pauli[]
```


## <a name="input"></a><span data-ttu-id="86e01-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="86e01-106">Input</span></span>

### <a name="ints--int"></a><span data-ttu-id="86e01-107">litre: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="86e01-107">ints : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="86e01-108">`0..3`Pauli işleçlerine dönüştürülecek aralıktaki tamsayılar dizisi.</span><span class="sxs-lookup"><span data-stu-id="86e01-108">Array of integers in the range `0..3`  to be converted to Pauli operators.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="86e01-109">Çıkış: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="86e01-109">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="86e01-110">`paulis`Pauli işleçlerinin bir dizisi `Pauli[]` , `ints` `paulis[idxPauli]` tarafından verilen öğesine eşit olan şekilde aynı uzunluktadır `[PauliI, PauliX, PauliY, PauliZ]` `ints[idxPauli]` .</span><span class="sxs-lookup"><span data-stu-id="86e01-110">An array `paulis` of Pauli operators `Pauli[]` the same length as `ints` such that `paulis[idxPauli]` is equal to the element of `[PauliI, PauliX, PauliY, PauliZ]` given by `ints[idxPauli]`.</span></span>