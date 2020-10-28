---
uid: Microsoft.Quantum.Synthesis.TruthTablesFromPermutationFolder
title: Truthtablesfromperdeğiştirici Tionfolder işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: TruthTablesFromPermutationFolder
qsharp.summary: Decomposition logic for a single variable index
ms.openlocfilehash: 6b00c9e880ed7b7b3bf446dcb17dab3bab7a83a7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733479"
---
# <a name="truthtablesfrompermutationfolder-function"></a><span data-ttu-id="cf0a6-102">Truthtablesfromperdeğiştirici Tionfolder işlevi</span><span class="sxs-lookup"><span data-stu-id="cf0a6-102">TruthTablesFromPermutationFolder function</span></span>

<span data-ttu-id="cf0a6-103">Ad alanı: [Microsoft. hisse. sensıs](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="cf0a6-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="cf0a6-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="cf0a6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="cf0a6-105">Tek bir değişken dizini için ayrıştırma mantığı</span><span class="sxs-lookup"><span data-stu-id="cf0a6-105">Decomposition logic for a single variable index</span></span>

```qsharp
function TruthTablesFromPermutationFolder (numVars : Int, state : Microsoft.Quantum.Synthesis.DecompositionState, index : Int) : Microsoft.Quantum.Synthesis.DecompositionState
```


## <a name="description"></a><span data-ttu-id="cf0a6-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="cf0a6-106">Description</span></span>

<span data-ttu-id="cf0a6-107">Bu, geçerli durumu alır ve güncelleştirilmiş bir permütasyon oluşturur ve denetimli kapıları için yeni işlevler ekler.</span><span class="sxs-lookup"><span data-stu-id="cf0a6-107">This takes the current state and generates an updated permutation and possibly adds new functions for controlled gates.</span></span>

## <a name="input"></a><span data-ttu-id="cf0a6-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="cf0a6-108">Input</span></span>

### <a name="numvars--int"></a><span data-ttu-id="cf0a6-109">numVars: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="cf0a6-109">numVars : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="state--decompositionstate"></a><span data-ttu-id="cf0a6-110">durum: [Dekompozisyontionstate](xref:Microsoft.Quantum.Synthesis.DecompositionState)</span><span class="sxs-lookup"><span data-stu-id="cf0a6-110">state : [DecompositionState](xref:Microsoft.Quantum.Synthesis.DecompositionState)</span></span>




### <a name="index--int"></a><span data-ttu-id="cf0a6-111">Dizin: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="cf0a6-111">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--decompositionstate"></a><span data-ttu-id="cf0a6-112">Çıkış: [Dekompozisyontionstate](xref:Microsoft.Quantum.Synthesis.DecompositionState)</span><span class="sxs-lookup"><span data-stu-id="cf0a6-112">Output : [DecompositionState](xref:Microsoft.Quantum.Synthesis.DecompositionState)</span></span>

