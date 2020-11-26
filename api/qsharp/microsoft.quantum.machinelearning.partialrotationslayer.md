---
uid: Microsoft.Quantum.MachineLearning.PartialRotationsLayer
title: PartialRotationsLayer işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: PartialRotationsLayer
qsharp.summary: Returns an array of single-qubit rotations along a given axis, parameterized by distinct model parameters.
ms.openlocfilehash: ade0640b07f633982e98d5d02239fa205909bcce
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196251"
---
# <a name="partialrotationslayer-function"></a><span data-ttu-id="1cb23-102">PartialRotationsLayer işlevi</span><span class="sxs-lookup"><span data-stu-id="1cb23-102">PartialRotationsLayer function</span></span>

<span data-ttu-id="1cb23-103">Ad alanı: [Microsoft. hisse. Machinöğrenim](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="1cb23-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="1cb23-104">Paket: [Microsoft. hisse. Machine-öğrenim](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="1cb23-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="1cb23-105">Ayrı model parametrelerine göre parametreli, belirli bir eksen üzerinde tek qubit döndürmelerdeki oluşan bir dizi döndürür.</span><span class="sxs-lookup"><span data-stu-id="1cb23-105">Returns an array of single-qubit rotations along a given axis, parameterized by distinct model parameters.</span></span>

```qsharp
function PartialRotationsLayer (idxsQubits : Int[], axis : Pauli) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a><span data-ttu-id="1cb23-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="1cb23-106">Input</span></span>

### <a name="idxsqubits--int"></a><span data-ttu-id="1cb23-107">ıdxsqubits: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="1cb23-107">idxsQubits : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="1cb23-108">Her döndürme için hedef olarak kullanılacak qubits dizinleri.</span><span class="sxs-lookup"><span data-stu-id="1cb23-108">Indices for the qubits to be used as the targets for each rotation.</span></span>


### <a name="axis--pauli"></a><span data-ttu-id="1cb23-109">eksen: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="1cb23-109">axis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="1cb23-110">Verilen katmandaki her bir döndürme için döndürme ekseni.</span><span class="sxs-lookup"><span data-stu-id="1cb23-110">The rotation axis for each rotation in the given layer.</span></span>



## <a name="output--controlledrotation"></a><span data-ttu-id="1cb23-111">Çıkış: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span><span class="sxs-lookup"><span data-stu-id="1cb23-111">Output : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span></span>

<span data-ttu-id="1cb23-112">Her bir qubit üzerinde bir tane olmak üzere, verilen eksen hakkında kontrollü bir dizin dizisi `nQubits` .</span><span class="sxs-lookup"><span data-stu-id="1cb23-112">An array of controlled rotations about the given axis, one on each of `nQubits` qubits.</span></span>