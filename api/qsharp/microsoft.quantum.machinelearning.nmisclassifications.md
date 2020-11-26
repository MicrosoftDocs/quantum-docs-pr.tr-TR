---
uid: Microsoft.Quantum.MachineLearning.NMisclassifications
title: Nmissınıflandırmalar işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: NMisclassifications
qsharp.summary: Given a set of inferred labels and a set of correct labels, returns the number of indices at which each set of labels differ.
ms.openlocfilehash: 30d049ba54630cd2f5f350280bad7f587599f459
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196319"
---
# <a name="nmisclassifications-function"></a><span data-ttu-id="dbc1b-102">Nmissınıflandırmalar işlevi</span><span class="sxs-lookup"><span data-stu-id="dbc1b-102">NMisclassifications function</span></span>

<span data-ttu-id="dbc1b-103">Ad alanı: [Microsoft. hisse. Machinöğrenim](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="dbc1b-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="dbc1b-104">Paket: [Microsoft. hisse. Machine-öğrenim](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="dbc1b-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="dbc1b-105">Çıkarılan Etiketler kümesi ve doğru Etiketler kümesi verildiğinde, her etiket kümesinin farklı olduğu dizin sayısını döndürür.</span><span class="sxs-lookup"><span data-stu-id="dbc1b-105">Given a set of inferred labels and a set of correct labels, returns the number of indices at which each set of labels differ.</span></span>

```qsharp
function NMisclassifications (proposed : Int[], actual : Int[]) : Int
```


## <a name="input"></a><span data-ttu-id="dbc1b-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="dbc1b-106">Input</span></span>

### <a name="proposed--int"></a><span data-ttu-id="dbc1b-107">Önerilen: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="dbc1b-107">proposed : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>




### <a name="actual--int"></a><span data-ttu-id="dbc1b-108">gerçek: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="dbc1b-108">actual : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>





## <a name="output--int"></a><span data-ttu-id="dbc1b-109">Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="dbc1b-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="dbc1b-110">Bu şekilde dizin sayısı `idx` `inferredLabels[idx] != actualLabels[idx]` .</span><span class="sxs-lookup"><span data-stu-id="dbc1b-110">The number of indices `idx` such that `inferredLabels[idx] != actualLabels[idx]`.</span></span>