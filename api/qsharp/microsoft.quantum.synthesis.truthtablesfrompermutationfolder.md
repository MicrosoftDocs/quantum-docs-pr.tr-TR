---
uid: Microsoft.Quantum.Synthesis.TruthTablesFromPermutationFolder
title: Truthtablesfromperdeğiştirici Tionfolder işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: TruthTablesFromPermutationFolder
qsharp.summary: Decomposition logic for a single variable index
ms.openlocfilehash: 881bb8e29d3d7761cc521837502ea79b0714b381
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855244"
---
# <a name="truthtablesfrompermutationfolder-function"></a><span data-ttu-id="64068-102">Truthtablesfromperdeğiştirici Tionfolder işlevi</span><span class="sxs-lookup"><span data-stu-id="64068-102">TruthTablesFromPermutationFolder function</span></span>

<span data-ttu-id="64068-103">Ad alanı: [Microsoft. hisse. sensıs](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="64068-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="64068-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="64068-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="64068-105">Tek bir değişken dizini için ayrıştırma mantığı</span><span class="sxs-lookup"><span data-stu-id="64068-105">Decomposition logic for a single variable index</span></span>

```qsharp
function TruthTablesFromPermutationFolder (numVars : Int, state : Microsoft.Quantum.Synthesis.DecompositionState, index : Int) : Microsoft.Quantum.Synthesis.DecompositionState
```


## <a name="description"></a><span data-ttu-id="64068-106">Description</span><span class="sxs-lookup"><span data-stu-id="64068-106">Description</span></span>

<span data-ttu-id="64068-107">Bu, geçerli durumu alır ve güncelleştirilmiş bir permütasyon oluşturur ve denetimli kapıları için yeni işlevler ekler.</span><span class="sxs-lookup"><span data-stu-id="64068-107">This takes the current state and generates an updated permutation and possibly adds new functions for controlled gates.</span></span>

## <a name="input"></a><span data-ttu-id="64068-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="64068-108">Input</span></span>

### <a name="numvars--int"></a><span data-ttu-id="64068-109">numVars: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="64068-109">numVars : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="state--decompositionstate"></a><span data-ttu-id="64068-110">durum: [Dekompozisyontionstate](xref:Microsoft.Quantum.Synthesis.DecompositionState)</span><span class="sxs-lookup"><span data-stu-id="64068-110">state : [DecompositionState](xref:Microsoft.Quantum.Synthesis.DecompositionState)</span></span>




### <a name="index--int"></a><span data-ttu-id="64068-111">Dizin: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="64068-111">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--decompositionstate"></a><span data-ttu-id="64068-112">Çıkış: [Dekompozisyontionstate](xref:Microsoft.Quantum.Synthesis.DecompositionState)</span><span class="sxs-lookup"><span data-stu-id="64068-112">Output : [DecompositionState](xref:Microsoft.Quantum.Synthesis.DecompositionState)</span></span>

