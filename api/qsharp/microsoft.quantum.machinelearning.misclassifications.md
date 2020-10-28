---
uid: Microsoft.Quantum.MachineLearning.Misclassifications
title: Hatalı sınıflandırmalar işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: Misclassifications
qsharp.summary: Given a set of inferred labels and a set of correct labels, returns indices for where each set of labels differs.
ms.openlocfilehash: 500c2910f7c5616c88ff6c70ab3cc16680e199fb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732978"
---
# <a name="misclassifications-function"></a><span data-ttu-id="3d353-102">Hatalı sınıflandırmalar işlevi</span><span class="sxs-lookup"><span data-stu-id="3d353-102">Misclassifications function</span></span>

<span data-ttu-id="3d353-103">Ad alanı: [Microsoft. hisse. Machinöğrenim](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="3d353-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="3d353-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3d353-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3d353-105">Çıkarılan Etiketler kümesi ve doğru Etiketler kümesi verildiğinde, her bir etiket kümesinin farklı olduğu dizinler döndürür.</span><span class="sxs-lookup"><span data-stu-id="3d353-105">Given a set of inferred labels and a set of correct labels, returns indices for where each set of labels differs.</span></span>

```qsharp
function Misclassifications (inferredLabels : Int[], actualLabels : Int[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="3d353-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="3d353-106">Input</span></span>

### <a name="inferredlabels--int"></a><span data-ttu-id="3d353-107">ınferredlabels: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="3d353-107">inferredLabels : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="3d353-108">Belirli bir eğitim veya doğrulama kümesi için gösterilen Etiketler.</span><span class="sxs-lookup"><span data-stu-id="3d353-108">The labels inferred for a given training or validation set.</span></span>


### <a name="actuallabels--int"></a><span data-ttu-id="3d353-109">actualLabels: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="3d353-109">actualLabels : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="3d353-110">Belirli bir eğitim veya doğrulama kümesi için doğru Etiketler.</span><span class="sxs-lookup"><span data-stu-id="3d353-110">The true labels for a given training or validation set.</span></span>



## <a name="output--int"></a><span data-ttu-id="3d353-111">Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="3d353-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="3d353-112">Bu tür bir dizin dizisi `idx` `inferredLabels[idx] != actualLabels[idx]` .</span><span class="sxs-lookup"><span data-stu-id="3d353-112">An array of indices `idx` such that `inferredLabels[idx] != actualLabels[idx]`.</span></span>