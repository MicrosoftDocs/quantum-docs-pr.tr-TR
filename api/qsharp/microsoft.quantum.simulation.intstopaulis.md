---
uid: Microsoft.Quantum.Simulation.IntsToPaulis
title: IntsToPaulis işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IntsToPaulis
qsharp.summary: Converts an array of integers to an array of single-qubit Pauli operators.
ms.openlocfilehash: 605257aa7ca39e457127e3c3459b5891145b1863
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725820"
---
# <a name="intstopaulis-function"></a><span data-ttu-id="68fa0-102">IntsToPaulis işlevi</span><span class="sxs-lookup"><span data-stu-id="68fa0-102">IntsToPaulis function</span></span>

<span data-ttu-id="68fa0-103">Ad alanı: [Microsoft. hisse. benzetim](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="68fa0-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="68fa0-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="68fa0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="68fa0-105">Bir tamsayılar dizisini tek qubit Pauli işleçleri dizisine dönüştürür.</span><span class="sxs-lookup"><span data-stu-id="68fa0-105">Converts an array of integers to an array of single-qubit Pauli operators.</span></span>

```qsharp
function IntsToPaulis (ints : Int[]) : Pauli[]
```


## <a name="input"></a><span data-ttu-id="68fa0-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="68fa0-106">Input</span></span>

### <a name="ints--int"></a><span data-ttu-id="68fa0-107">litre: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="68fa0-107">ints : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="68fa0-108">`0..3`Pauli işleçlerine dönüştürülecek aralıktaki tamsayılar dizisi.</span><span class="sxs-lookup"><span data-stu-id="68fa0-108">Array of integers in the range `0..3`  to be converted to Pauli operators.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="68fa0-109">Çıkış: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="68fa0-109">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="68fa0-110">`paulis`Pauli işleçlerinin bir dizisi `Pauli[]` , `ints` `paulis[idxPauli]` tarafından verilen öğesine eşit olan şekilde aynı uzunluktadır `[PauliI, PauliX, PauliY, PauliZ]` `ints[idxPauli]` .</span><span class="sxs-lookup"><span data-stu-id="68fa0-110">An array `paulis` of Pauli operators `Pauli[]` the same length as `ints` such that `paulis[idxPauli]` is equal to the element of `[PauliI, PauliX, PauliY, PauliZ]` given by `ints[idxPauli]`.</span></span>