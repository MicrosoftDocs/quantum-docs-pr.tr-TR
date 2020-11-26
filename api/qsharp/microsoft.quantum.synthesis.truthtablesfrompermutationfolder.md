---
uid: Microsoft.Quantum.Synthesis.TruthTablesFromPermutationFolder
title: Truthtablesfromperdeğiştirici Tionfolder işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: TruthTablesFromPermutationFolder
qsharp.summary: Decomposition logic for a single variable index
ms.openlocfilehash: 86e112782825303805029b2f9f6cfd9d6ce9e8b6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96231033"
---
# <a name="truthtablesfrompermutationfolder-function"></a><span data-ttu-id="a8acc-102">Truthtablesfromperdeğiştirici Tionfolder işlevi</span><span class="sxs-lookup"><span data-stu-id="a8acc-102">TruthTablesFromPermutationFolder function</span></span>

<span data-ttu-id="a8acc-103">Ad alanı: [Microsoft. hisse. sensıs](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="a8acc-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="a8acc-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a8acc-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a8acc-105">Tek bir değişken dizini için ayrıştırma mantığı</span><span class="sxs-lookup"><span data-stu-id="a8acc-105">Decomposition logic for a single variable index</span></span>

```qsharp
function TruthTablesFromPermutationFolder (numVars : Int, state : Microsoft.Quantum.Synthesis.DecompositionState, index : Int) : Microsoft.Quantum.Synthesis.DecompositionState
```


## <a name="description"></a><span data-ttu-id="a8acc-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="a8acc-106">Description</span></span>

<span data-ttu-id="a8acc-107">Bu, geçerli durumu alır ve güncelleştirilmiş bir permütasyon oluşturur ve denetimli kapıları için yeni işlevler ekler.</span><span class="sxs-lookup"><span data-stu-id="a8acc-107">This takes the current state and generates an updated permutation and possibly adds new functions for controlled gates.</span></span>

## <a name="input"></a><span data-ttu-id="a8acc-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="a8acc-108">Input</span></span>

### <a name="numvars--int"></a><span data-ttu-id="a8acc-109">numVars: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a8acc-109">numVars : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="state--decompositionstate"></a><span data-ttu-id="a8acc-110">durum: [Dekompozisyontionstate](xref:Microsoft.Quantum.Synthesis.DecompositionState)</span><span class="sxs-lookup"><span data-stu-id="a8acc-110">state : [DecompositionState](xref:Microsoft.Quantum.Synthesis.DecompositionState)</span></span>




### <a name="index--int"></a><span data-ttu-id="a8acc-111">Dizin: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a8acc-111">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--decompositionstate"></a><span data-ttu-id="a8acc-112">Çıkış: [Dekompozisyontionstate](xref:Microsoft.Quantum.Synthesis.DecompositionState)</span><span class="sxs-lookup"><span data-stu-id="a8acc-112">Output : [DecompositionState](xref:Microsoft.Quantum.Synthesis.DecompositionState)</span></span>

