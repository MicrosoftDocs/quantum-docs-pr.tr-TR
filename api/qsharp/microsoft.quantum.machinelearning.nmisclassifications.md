---
uid: Microsoft.Quantum.MachineLearning.NMisclassifications
title: Nmissınıflandırmalar işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: NMisclassifications
qsharp.summary: Given a set of inferred labels and a set of correct labels, returns the number of indices at which each set of labels differ.
ms.openlocfilehash: 9e356d68233519978e007e5a2999ca1be8cb7f83
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725945"
---
# <a name="nmisclassifications-function"></a><span data-ttu-id="6cf1a-102">Nmissınıflandırmalar işlevi</span><span class="sxs-lookup"><span data-stu-id="6cf1a-102">NMisclassifications function</span></span>

<span data-ttu-id="6cf1a-103">Ad alanı: [Microsoft. hisse. Machinöğrenim](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="6cf1a-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="6cf1a-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6cf1a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6cf1a-105">Çıkarılan Etiketler kümesi ve doğru Etiketler kümesi verildiğinde, her etiket kümesinin farklı olduğu dizin sayısını döndürür.</span><span class="sxs-lookup"><span data-stu-id="6cf1a-105">Given a set of inferred labels and a set of correct labels, returns the number of indices at which each set of labels differ.</span></span>

```qsharp
function NMisclassifications (proposed : Int[], actual : Int[]) : Int
```


## <a name="input"></a><span data-ttu-id="6cf1a-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="6cf1a-106">Input</span></span>

### <a name="proposed--int"></a><span data-ttu-id="6cf1a-107">Önerilen: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="6cf1a-107">proposed : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>




### <a name="actual--int"></a><span data-ttu-id="6cf1a-108">gerçek: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="6cf1a-108">actual : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>





## <a name="output--int"></a><span data-ttu-id="6cf1a-109">Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6cf1a-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6cf1a-110">Bu şekilde dizin sayısı `idx` `inferredLabels[idx] != actualLabels[idx]` .</span><span class="sxs-lookup"><span data-stu-id="6cf1a-110">The number of indices `idx` such that `inferredLabels[idx] != actualLabels[idx]`.</span></span>