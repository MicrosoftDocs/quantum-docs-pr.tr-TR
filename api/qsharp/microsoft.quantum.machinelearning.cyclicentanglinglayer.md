---
uid: Microsoft.Quantum.MachineLearning.CyclicEntanglingLayer
title: CyclicEntanglingLayer işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: CyclicEntanglingLayer
qsharp.summary: Returns an array of singly controlled rotations along a given axis, arranged cyclically across a register of qubits, and parameterized by distinct model parameters.
ms.openlocfilehash: 6e0f5057b35baefe2677126ba70ee4fddde7d4db
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731111"
---
# <a name="cyclicentanglinglayer-function"></a><span data-ttu-id="bac48-102">CyclicEntanglingLayer işlevi</span><span class="sxs-lookup"><span data-stu-id="bac48-102">CyclicEntanglingLayer function</span></span>

<span data-ttu-id="bac48-103">Ad alanı: [Microsoft. hisse. Machinöğrenim](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="bac48-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="bac48-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="bac48-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="bac48-105">Belirli bir eksen boyunca listedir kontrollü nesnelerin bir dizisini döndürür, qubits 'in bir kaydındaki periyodik düzenlenir ve ayrı model parametrelerine göre parametrelenir.</span><span class="sxs-lookup"><span data-stu-id="bac48-105">Returns an array of singly controlled rotations along a given axis, arranged cyclically across a register of qubits, and parameterized by distinct model parameters.</span></span>

```qsharp
function CyclicEntanglingLayer (nQubits : Int, axis : Pauli, stride : Int) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a><span data-ttu-id="bac48-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="bac48-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="bac48-107">nQubits: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="bac48-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="bac48-108">Verilen katman tarafından üzerinde işlem yapılan qubits sayısı.</span><span class="sxs-lookup"><span data-stu-id="bac48-108">The number of qubits acted on by the given layer.</span></span>


### <a name="axis--pauli"></a><span data-ttu-id="bac48-109">eksen: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="bac48-109">axis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="bac48-110">Verilen katmandaki her bir döndürme için döndürme ekseni.</span><span class="sxs-lookup"><span data-stu-id="bac48-110">The rotation axis for each rotation in the given layer.</span></span>


### <a name="stride--int"></a><span data-ttu-id="bac48-111">ilerleme: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="bac48-111">stride : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="bac48-112">Her bir döndürme için hedef ve denetim dizinleri arasındaki ayrım.</span><span class="sxs-lookup"><span data-stu-id="bac48-112">The separation between the target and control indices for each rotation.</span></span>



## <a name="output--controlledrotation"></a><span data-ttu-id="bac48-113">Çıkış: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span><span class="sxs-lookup"><span data-stu-id="bac48-113">Output : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span></span>

<span data-ttu-id="bac48-114">Qubits 'in bir kaydındaki periyodik bir yerde bulunan iki qubit kontrollü bir döndürme dizisi `nQubits` .</span><span class="sxs-lookup"><span data-stu-id="bac48-114">An array of two-qubit controlled rotations laid out cyclically across a register of `nQubits` qubits.</span></span>