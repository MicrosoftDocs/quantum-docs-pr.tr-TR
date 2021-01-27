---
uid: Microsoft.Quantum.Research.Chemistry._DeltaParityCNOTbitstring
title: _DeltaParityCNOTbitstring işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _DeltaParityCNOTbitstring
qsharp.summary: Classical processing step of `ApplyDeltaParity`. This computes a list of control qubits for evaluating parity difference between any two PQRS... terms of even length.
ms.openlocfilehash: 3dd2d299a094577d377780d731e76287815e8d03
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847595"
---
# <a name="_deltaparitycnotbitstring-function"></a><span data-ttu-id="f92b7-102">_DeltaParityCNOTbitstring işlevi</span><span class="sxs-lookup"><span data-stu-id="f92b7-102">_DeltaParityCNOTbitstring function</span></span>

<span data-ttu-id="f92b7-103">Ad alanı: [Microsoft. hisse. Research. Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="f92b7-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="f92b7-104">Paket: [Microsoft. hisse. Research. Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="f92b7-104">Package: [Microsoft.Quantum.Research.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span></span>


<span data-ttu-id="f92b7-105">Klasik işleme adımı `ApplyDeltaParity` .</span><span class="sxs-lookup"><span data-stu-id="f92b7-105">Classical processing step of `ApplyDeltaParity`.</span></span>
<span data-ttu-id="f92b7-106">Bu, herhangi iki PQRS arasındaki eşlik farkını değerlendirmek için denetim qubits listesini hesaplar... Hatta uzunluk terimi.</span><span class="sxs-lookup"><span data-stu-id="f92b7-106">This computes a list of control qubits for evaluating parity difference between any two PQRS... terms of even length.</span></span>

```qsharp
function _DeltaParityCNOTbitstring (prevFermionicTerm : Int[], nextFermionicTerm : Int[]) : (Int, Bool[])
```


## <a name="input"></a><span data-ttu-id="f92b7-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="f92b7-107">Input</span></span>

### <a name="prevfermionicterm--int"></a><span data-ttu-id="f92b7-108">Prevfermıonicterm: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="f92b7-108">prevFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>




### <a name="nextfermionicterm--int"></a><span data-ttu-id="f92b7-109">Nextfermıonicterm: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="f92b7-109">nextFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>





## <a name="output--intbool"></a><span data-ttu-id="f92b7-110">Çıkış: ([Int](xref:microsoft.quantum.lang-ref.int),[bool](xref:microsoft.quantum.lang-ref.bool)[])</span><span class="sxs-lookup"><span data-stu-id="f92b7-110">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Bool](xref:microsoft.quantum.lang-ref.bool)[])</span></span>



## <a name="remarks"></a><span data-ttu-id="f92b7-111">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="f92b7-111">Remarks</span></span>

<span data-ttu-id="f92b7-112">Bu, koşulların uzunluğunun eşit olduğunu varsayar.</span><span class="sxs-lookup"><span data-stu-id="f92b7-112">This assumes that the length of terms is even.</span></span>
<span data-ttu-id="f92b7-113">İki terim arasındaki eşlik farkı için denetim listesini hesaplar.</span><span class="sxs-lookup"><span data-stu-id="f92b7-113">Computes list of controls for parity difference between any two terms.</span></span>
<span data-ttu-id="f92b7-114">Bu, giriş listelerinin artan düzende sıralanacağını varsayar.</span><span class="sxs-lookup"><span data-stu-id="f92b7-114">This assumes that the input lists is sorted in ascending order.</span></span>