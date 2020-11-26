---
uid: Microsoft.Quantum.Simulation.PauliBlockEncoding
title: Pauliblockenkodlamaya işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliBlockEncoding
qsharp.summary: >-
  Creates a block-encoding unitary for a Hamiltonian.

  The Hamiltonian $H=\sum_{j}\alpha_j P_j$ is described by a sum of Pauli terms $P_j$, each with real coefficient $\alpha_j$.
ms.openlocfilehash: b1df6d239e6ef061cf0a4784c652e9dd126991d5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230438"
---
# <a name="pauliblockencoding-function"></a><span data-ttu-id="38acc-102">Pauliblockenkodlamaya işlevi</span><span class="sxs-lookup"><span data-stu-id="38acc-102">PauliBlockEncoding function</span></span>

<span data-ttu-id="38acc-103">Ad alanı: [Microsoft. hisse. benzetim](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="38acc-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="38acc-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="38acc-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="38acc-105">Hamiltonian için blok kodlama Unitary oluşturur.</span><span class="sxs-lookup"><span data-stu-id="38acc-105">Creates a block-encoding unitary for a Hamiltonian.</span></span>

<span data-ttu-id="38acc-106">Hamiltonian $H = \ sum_ {j} \ alpha_j P_j $, her biri gerçek katsayı değeri $ \ $P $ olan Pauli terimlerinin toplamı ile açıklanmıştır _j $.</span><span class="sxs-lookup"><span data-stu-id="38acc-106">The Hamiltonian $H=\sum_{j}\alpha_j P_j$ is described by a sum of Pauli terms $P_j$, each with real coefficient $\alpha_j$.</span></span>

```qsharp
function PauliBlockEncoding (generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem) : (Double, Microsoft.Quantum.Simulation.BlockEncodingReflection)
```


## <a name="input"></a><span data-ttu-id="38acc-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="38acc-107">Input</span></span>

### <a name="generatorsystem--generatorsystem"></a><span data-ttu-id="38acc-108">generatorSystem: [Generatorsystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="38acc-108">generatorSystem : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="38acc-109">`GeneratorSystem`Pauli koşullarının toplamı olarak $H $ tanımlayan bir.</span><span class="sxs-lookup"><span data-stu-id="38acc-109">A `GeneratorSystem` that describes $H$ as a sum of Pauli terms</span></span>



## <a name="output--doubleblockencodingreflection"></a><span data-ttu-id="38acc-110">Çıkış: ([Double](xref:microsoft.quantum.lang-ref.double),[blockencodingreflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection))</span><span class="sxs-lookup"><span data-stu-id="38acc-110">Output : ([Double](xref:microsoft.quantum.lang-ref.double),[BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection))</span></span>

## <a name="first-parameter"></a><span data-ttu-id="38acc-111">İlk parametre</span><span class="sxs-lookup"><span data-stu-id="38acc-111">First parameter</span></span>

<span data-ttu-id="38acc-112">Katsayıların $ \alfa = \ sum_ {j} | \ alpha_j | $ sayısının bir normu.</span><span class="sxs-lookup"><span data-stu-id="38acc-112">The one-norm of coefficients $\alpha=\sum_{j}|\alpha_j|$.</span></span>

## <a name="second-parameter"></a><span data-ttu-id="38acc-113">İkinci parametre</span><span class="sxs-lookup"><span data-stu-id="38acc-113">Second parameter</span></span>

<span data-ttu-id="38acc-114">`BlockEncodingReflection`Hamiltonian $H $ 'ın Unitary $U $.</span><span class="sxs-lookup"><span data-stu-id="38acc-114">A `BlockEncodingReflection` unitary $U$ of the Hamiltonian $H$.</span></span> <span data-ttu-id="38acc-115">Bu Unitary, $U ^ 2 = I $ ile aynı zamanda bir yansıdır.</span><span class="sxs-lookup"><span data-stu-id="38acc-115">As this unitary satisfies $U^2 = I$, it is also a reflection.</span></span>

## <a name="remarks"></a><span data-ttu-id="38acc-116">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="38acc-116">Remarks</span></span>

<span data-ttu-id="38acc-117">Bu, $ \ sum_ {j} \sqrt{\ alpha_j/\Alpha}\ket{j} $ durumunun hazırlanması ve hazırlanması ve çarpma kontrollü bir Unitary ve oluşturma yoluyla elde edilir <xref:microsoft.quantum.preparation.statepreparationpositivecoefficients> <xref:microsoft.quantum.canon.multiplexoperationsfromgenerator> .</span><span class="sxs-lookup"><span data-stu-id="38acc-117">This is obtained by preparing and unpreparing the state $\sum_{j}\sqrt{\alpha_j/\alpha}\ket{j}$, and constructing a multiply-controlled unitary <xref:microsoft.quantum.preparation.statepreparationpositivecoefficients> and <xref:microsoft.quantum.canon.multiplexoperationsfromgenerator>.</span></span>