---
uid: Microsoft.Quantum.MachineLearning.LocalRotationsLayer
title: LocalRotationsLayer işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: LocalRotationsLayer
qsharp.summary: Returns an array of uncontrolled (single-qubit) rotations along a given axis, with one rotation for each qubit in a register, parameterized by distinct model parameters.
ms.openlocfilehash: a3658bbf62068c9eea2d9b763cbff5596f426135
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854987"
---
# <a name="localrotationslayer-function"></a><span data-ttu-id="2780f-102">LocalRotationsLayer işlevi</span><span class="sxs-lookup"><span data-stu-id="2780f-102">LocalRotationsLayer function</span></span>

<span data-ttu-id="2780f-103">Ad alanı: [Microsoft. hisse. Machinöğrenim](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="2780f-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="2780f-104">Paket: [Microsoft. hisse. Machine-öğrenim](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="2780f-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="2780f-105">Bir kayıttaki her bir qubit için tek bir dönüşle, ayrı model parametrelerine göre parametrelendirilmiş bir, denetlenmeyen (tek qubit) döndürmeler dizisini döndürür.</span><span class="sxs-lookup"><span data-stu-id="2780f-105">Returns an array of uncontrolled (single-qubit) rotations along a given axis, with one rotation for each qubit in a register, parameterized by distinct model parameters.</span></span>

```qsharp
function LocalRotationsLayer (nQubits : Int, axis : Pauli) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a><span data-ttu-id="2780f-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="2780f-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="2780f-107">nQubits: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2780f-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2780f-108">Verilen katman tarafından üzerinde işlem yapılan qubits sayısı.</span><span class="sxs-lookup"><span data-stu-id="2780f-108">The number of qubits acted on by the given layer.</span></span>


### <a name="axis--pauli"></a><span data-ttu-id="2780f-109">eksen: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="2780f-109">axis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="2780f-110">Verilen katmandaki her bir döndürme için döndürme ekseni.</span><span class="sxs-lookup"><span data-stu-id="2780f-110">The rotation axis for each rotation in the given layer.</span></span>



## <a name="output--controlledrotation"></a><span data-ttu-id="2780f-111">Çıkış: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span><span class="sxs-lookup"><span data-stu-id="2780f-111">Output : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span></span>

<span data-ttu-id="2780f-112">Her bir qubit üzerinde bir tane olmak üzere, verilen eksen hakkında kontrollü bir dizin dizisi `nQubits` .</span><span class="sxs-lookup"><span data-stu-id="2780f-112">An array of controlled rotations about the given axis, one on each of `nQubits` qubits.</span></span>