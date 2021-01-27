---
uid: Microsoft.Quantum.Canon.TrotterStepSize
title: Troesstepsize işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TrotterStepSize
qsharp.summary: Computes Trotter step size in recursive implementation of Trotter simulation algorithm.
ms.openlocfilehash: c7b6432645dcad2bd47c62b91e04e0b42cd04ca9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840067"
---
# <a name="trotterstepsize-function"></a><span data-ttu-id="42aa8-102">Troesstepsize işlevi</span><span class="sxs-lookup"><span data-stu-id="42aa8-102">TrotterStepSize function</span></span>

<span data-ttu-id="42aa8-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="42aa8-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="42aa8-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="42aa8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="42aa8-105">, Trour benzetim algoritmasının özyinelemeli uygulamasında araba adım boyutunu hesaplar.</span><span class="sxs-lookup"><span data-stu-id="42aa8-105">Computes Trotter step size in recursive implementation of Trotter simulation algorithm.</span></span>

```qsharp
function TrotterStepSize (order : Int) : Double
```


## <a name="input"></a><span data-ttu-id="42aa8-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="42aa8-106">Input</span></span>

### <a name="order--int"></a><span data-ttu-id="42aa8-107">sıra: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="42aa8-107">order : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--double"></a><span data-ttu-id="42aa8-108">Çıkış: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="42aa8-108">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>



## <a name="remarks"></a><span data-ttu-id="42aa8-109">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="42aa8-109">Remarks</span></span>

<span data-ttu-id="42aa8-110">Bu işlem, [Quant-pH/0508139](https://arxiv.org/abs/quant-ph/0508139)öğesinden farklı bir dizin oluşturma kuralı kullanıyor.</span><span class="sxs-lookup"><span data-stu-id="42aa8-110">This operation uses a different indexing convention than that of [quant-ph/0508139](https://arxiv.org/abs/quant-ph/0508139).</span></span> <span data-ttu-id="42aa8-111">Özellikle, `DecomposedIntoTimeStepsCA(_, 4)` Quant-pH/0508139 içindeki skaler $p _2 (\lambda) $ öğesine karşılık gelir.</span><span class="sxs-lookup"><span data-stu-id="42aa8-111">In particular, `DecomposedIntoTimeStepsCA(_, 4)` corresponds to the scalar $p_2(\lambda)$ in quant-ph/0508139.</span></span>