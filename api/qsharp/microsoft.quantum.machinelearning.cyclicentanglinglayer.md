---
uid: Microsoft.Quantum.MachineLearning.CyclicEntanglingLayer
title: CyclicEntanglingLayer işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: CyclicEntanglingLayer
qsharp.summary: Returns an array of singly controlled rotations along a given axis, arranged cyclically across a register of qubits, and parameterized by distinct model parameters.
ms.openlocfilehash: 5421765e36ef3e8e744e118206dafcb2bb582cc2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211942"
---
# <a name="cyclicentanglinglayer-function"></a><span data-ttu-id="2f1ae-102">CyclicEntanglingLayer işlevi</span><span class="sxs-lookup"><span data-stu-id="2f1ae-102">CyclicEntanglingLayer function</span></span>

<span data-ttu-id="2f1ae-103">Ad alanı: [Microsoft. hisse. Machinöğrenim](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="2f1ae-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="2f1ae-104">Paket: [Microsoft. hisse. Machine-öğrenim](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="2f1ae-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="2f1ae-105">Belirli bir eksen boyunca listedir kontrollü nesnelerin bir dizisini döndürür, qubits 'in bir kaydındaki periyodik düzenlenir ve ayrı model parametrelerine göre parametrelenir.</span><span class="sxs-lookup"><span data-stu-id="2f1ae-105">Returns an array of singly controlled rotations along a given axis, arranged cyclically across a register of qubits, and parameterized by distinct model parameters.</span></span>

```qsharp
function CyclicEntanglingLayer (nQubits : Int, axis : Pauli, stride : Int) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a><span data-ttu-id="2f1ae-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="2f1ae-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="2f1ae-107">nQubits: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2f1ae-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2f1ae-108">Verilen katman tarafından üzerinde işlem yapılan qubits sayısı.</span><span class="sxs-lookup"><span data-stu-id="2f1ae-108">The number of qubits acted on by the given layer.</span></span>


### <a name="axis--pauli"></a><span data-ttu-id="2f1ae-109">eksen: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="2f1ae-109">axis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="2f1ae-110">Verilen katmandaki her bir döndürme için döndürme ekseni.</span><span class="sxs-lookup"><span data-stu-id="2f1ae-110">The rotation axis for each rotation in the given layer.</span></span>


### <a name="stride--int"></a><span data-ttu-id="2f1ae-111">ilerleme: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2f1ae-111">stride : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2f1ae-112">Her bir döndürme için hedef ve denetim dizinleri arasındaki ayrım.</span><span class="sxs-lookup"><span data-stu-id="2f1ae-112">The separation between the target and control indices for each rotation.</span></span>



## <a name="output--controlledrotation"></a><span data-ttu-id="2f1ae-113">Çıkış: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span><span class="sxs-lookup"><span data-stu-id="2f1ae-113">Output : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span></span>

<span data-ttu-id="2f1ae-114">Qubits 'in bir kaydındaki periyodik bir yerde bulunan iki qubit kontrollü bir döndürme dizisi `nQubits` .</span><span class="sxs-lookup"><span data-stu-id="2f1ae-114">An array of two-qubit controlled rotations laid out cyclically across a register of `nQubits` qubits.</span></span>