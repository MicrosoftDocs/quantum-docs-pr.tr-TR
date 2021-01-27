---
uid: Microsoft.Quantum.MachineLearning.Misclassifications
title: Hatalı sınıflandırmalar işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: Misclassifications
qsharp.summary: Given a set of inferred labels and a set of correct labels, returns indices for where each set of labels differs.
ms.openlocfilehash: 3913395fbd9f7cf96732c17ca0c726289e5087ed
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853918"
---
# <a name="misclassifications-function"></a><span data-ttu-id="74d97-102">Hatalı sınıflandırmalar işlevi</span><span class="sxs-lookup"><span data-stu-id="74d97-102">Misclassifications function</span></span>

<span data-ttu-id="74d97-103">Ad alanı: [Microsoft. hisse. Machinöğrenim](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="74d97-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="74d97-104">Paket: [Microsoft. hisse. Machine-öğrenim](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="74d97-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="74d97-105">Çıkarılan Etiketler kümesi ve doğru Etiketler kümesi verildiğinde, her bir etiket kümesinin farklı olduğu dizinler döndürür.</span><span class="sxs-lookup"><span data-stu-id="74d97-105">Given a set of inferred labels and a set of correct labels, returns indices for where each set of labels differs.</span></span>

```qsharp
function Misclassifications (inferredLabels : Int[], actualLabels : Int[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="74d97-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="74d97-106">Input</span></span>

### <a name="inferredlabels--int"></a><span data-ttu-id="74d97-107">ınferredlabels: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="74d97-107">inferredLabels : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="74d97-108">Belirli bir eğitim veya doğrulama kümesi için gösterilen Etiketler.</span><span class="sxs-lookup"><span data-stu-id="74d97-108">The labels inferred for a given training or validation set.</span></span>


### <a name="actuallabels--int"></a><span data-ttu-id="74d97-109">actualLabels: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="74d97-109">actualLabels : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="74d97-110">Belirli bir eğitim veya doğrulama kümesi için doğru Etiketler.</span><span class="sxs-lookup"><span data-stu-id="74d97-110">The true labels for a given training or validation set.</span></span>



## <a name="output--int"></a><span data-ttu-id="74d97-111">Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="74d97-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="74d97-112">Bu tür bir dizin dizisi `idx` `inferredLabels[idx] != actualLabels[idx]` .</span><span class="sxs-lookup"><span data-stu-id="74d97-112">An array of indices `idx` such that `inferredLabels[idx] != actualLabels[idx]`.</span></span>

## <a name="example"></a><span data-ttu-id="74d97-113">Örnek</span><span class="sxs-lookup"><span data-stu-id="74d97-113">Example</span></span>

```qsharp
let misclassifications = Misclassifications([0, 1, 0, 0], [0, 1, 1, 0]);
Message($"{misclassifications}"); // Will print [2].
```