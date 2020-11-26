---
uid: Microsoft.Quantum.MachineLearning.Misclassifications
title: Hatalı sınıflandırmalar işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: Misclassifications
qsharp.summary: Given a set of inferred labels and a set of correct labels, returns indices for where each set of labels differs.
ms.openlocfilehash: e13a9b9b65931678d5d87878e81fa172329a28ea
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211687"
---
# <a name="misclassifications-function"></a><span data-ttu-id="761f2-102">Hatalı sınıflandırmalar işlevi</span><span class="sxs-lookup"><span data-stu-id="761f2-102">Misclassifications function</span></span>

<span data-ttu-id="761f2-103">Ad alanı: [Microsoft. hisse. Machinöğrenim](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="761f2-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="761f2-104">Paket: [Microsoft. hisse. Machine-öğrenim](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="761f2-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="761f2-105">Çıkarılan Etiketler kümesi ve doğru Etiketler kümesi verildiğinde, her bir etiket kümesinin farklı olduğu dizinler döndürür.</span><span class="sxs-lookup"><span data-stu-id="761f2-105">Given a set of inferred labels and a set of correct labels, returns indices for where each set of labels differs.</span></span>

```qsharp
function Misclassifications (inferredLabels : Int[], actualLabels : Int[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="761f2-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="761f2-106">Input</span></span>

### <a name="inferredlabels--int"></a><span data-ttu-id="761f2-107">ınferredlabels: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="761f2-107">inferredLabels : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="761f2-108">Belirli bir eğitim veya doğrulama kümesi için gösterilen Etiketler.</span><span class="sxs-lookup"><span data-stu-id="761f2-108">The labels inferred for a given training or validation set.</span></span>


### <a name="actuallabels--int"></a><span data-ttu-id="761f2-109">actualLabels: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="761f2-109">actualLabels : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="761f2-110">Belirli bir eğitim veya doğrulama kümesi için doğru Etiketler.</span><span class="sxs-lookup"><span data-stu-id="761f2-110">The true labels for a given training or validation set.</span></span>



## <a name="output--int"></a><span data-ttu-id="761f2-111">Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="761f2-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="761f2-112">Bu tür bir dizin dizisi `idx` `inferredLabels[idx] != actualLabels[idx]` .</span><span class="sxs-lookup"><span data-stu-id="761f2-112">An array of indices `idx` such that `inferredLabels[idx] != actualLabels[idx]`.</span></span>