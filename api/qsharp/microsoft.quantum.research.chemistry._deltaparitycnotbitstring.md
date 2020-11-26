---
uid: Microsoft.Quantum.Research.Chemistry._DeltaParityCNOTbitstring
title: _DeltaParityCNOTbitstring işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _DeltaParityCNOTbitstring
qsharp.summary: Classical processing step of `ApplyDeltaParity`. This computes a list of control qubits for evaluating parity difference between any two PQRS... terms of even length.
ms.openlocfilehash: 0c0da60e3c389f8208f9f7d5c84a09893f3c1bda
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226086"
---
# <a name="_deltaparitycnotbitstring-function"></a><span data-ttu-id="0a5a1-102">_DeltaParityCNOTbitstring işlevi</span><span class="sxs-lookup"><span data-stu-id="0a5a1-102">_DeltaParityCNOTbitstring function</span></span>

<span data-ttu-id="0a5a1-103">Ad alanı: [Microsoft. hisse. Research. Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="0a5a1-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="0a5a1-104">Paket: [Microsoft. hisse. Research. Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="0a5a1-104">Package: [Microsoft.Quantum.Research.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span></span>


<span data-ttu-id="0a5a1-105">Klasik işleme adımı `ApplyDeltaParity` .</span><span class="sxs-lookup"><span data-stu-id="0a5a1-105">Classical processing step of `ApplyDeltaParity`.</span></span>
<span data-ttu-id="0a5a1-106">Bu, herhangi iki PQRS arasındaki eşlik farkını değerlendirmek için denetim qubits listesini hesaplar... Hatta uzunluk terimi.</span><span class="sxs-lookup"><span data-stu-id="0a5a1-106">This computes a list of control qubits for evaluating parity difference between any two PQRS... terms of even length.</span></span>

```qsharp
function _DeltaParityCNOTbitstring (prevFermionicTerm : Int[], nextFermionicTerm : Int[]) : (Int, Bool[])
```


## <a name="input"></a><span data-ttu-id="0a5a1-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="0a5a1-107">Input</span></span>

### <a name="prevfermionicterm--int"></a><span data-ttu-id="0a5a1-108">Prevfermıonicterm: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="0a5a1-108">prevFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>




### <a name="nextfermionicterm--int"></a><span data-ttu-id="0a5a1-109">Nextfermıonicterm: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="0a5a1-109">nextFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>





## <a name="output--intbool"></a><span data-ttu-id="0a5a1-110">Çıkış: ([Int](xref:microsoft.quantum.lang-ref.int),[bool](xref:microsoft.quantum.lang-ref.bool)[])</span><span class="sxs-lookup"><span data-stu-id="0a5a1-110">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Bool](xref:microsoft.quantum.lang-ref.bool)[])</span></span>



## <a name="remarks"></a><span data-ttu-id="0a5a1-111">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="0a5a1-111">Remarks</span></span>

<span data-ttu-id="0a5a1-112">Bu, koşulların uzunluğunun eşit olduğunu varsayar.</span><span class="sxs-lookup"><span data-stu-id="0a5a1-112">This assumes that the length of terms is even.</span></span>
<span data-ttu-id="0a5a1-113">İki terim arasındaki eşlik farkı için denetim listesini hesaplar.</span><span class="sxs-lookup"><span data-stu-id="0a5a1-113">Computes list of controls for parity difference between any two terms.</span></span>
<span data-ttu-id="0a5a1-114">Bu, giriş listelerinin artan düzende sıralanacağını varsayar.</span><span class="sxs-lookup"><span data-stu-id="0a5a1-114">This assumes that the input lists is sorted in ascending order.</span></span>