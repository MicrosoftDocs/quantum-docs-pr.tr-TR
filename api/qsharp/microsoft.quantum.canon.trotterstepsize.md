---
uid: Microsoft.Quantum.Canon.TrotterStepSize
title: Troesstepsize işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TrotterStepSize
qsharp.summary: Computes Trotter step size in recursive implementation of Trotter simulation algorithm.
ms.openlocfilehash: aa5b63e058e1ea726b0d4c6eca73078831daaf3b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204700"
---
# <a name="trotterstepsize-function"></a><span data-ttu-id="bdefa-102">Troesstepsize işlevi</span><span class="sxs-lookup"><span data-stu-id="bdefa-102">TrotterStepSize function</span></span>

<span data-ttu-id="bdefa-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="bdefa-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="bdefa-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="bdefa-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="bdefa-105">, Trour benzetim algoritmasının özyinelemeli uygulamasında araba adım boyutunu hesaplar.</span><span class="sxs-lookup"><span data-stu-id="bdefa-105">Computes Trotter step size in recursive implementation of Trotter simulation algorithm.</span></span>

```qsharp
function TrotterStepSize (order : Int) : Double
```


## <a name="input"></a><span data-ttu-id="bdefa-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="bdefa-106">Input</span></span>

### <a name="order--int"></a><span data-ttu-id="bdefa-107">sıra: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="bdefa-107">order : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--double"></a><span data-ttu-id="bdefa-108">Çıkış: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="bdefa-108">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>



## <a name="remarks"></a><span data-ttu-id="bdefa-109">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="bdefa-109">Remarks</span></span>

<span data-ttu-id="bdefa-110">Bu işlem, [Quant-pH/0508139](https://arxiv.org/abs/quant-ph/0508139)öğesinden farklı bir dizin oluşturma kuralı kullanıyor.</span><span class="sxs-lookup"><span data-stu-id="bdefa-110">This operation uses a different indexing convention than that of [quant-ph/0508139](https://arxiv.org/abs/quant-ph/0508139).</span></span> <span data-ttu-id="bdefa-111">Özellikle, `DecomposedIntoTimeStepsCA(_, 4)` Quant-pH/0508139 içindeki skaler $p _2 (\lambda) $ öğesine karşılık gelir.</span><span class="sxs-lookup"><span data-stu-id="bdefa-111">In particular, `DecomposedIntoTimeStepsCA(_, 4)` corresponds to the scalar $p_2(\lambda)$ in quant-ph/0508139.</span></span>