---
uid: Microsoft.Quantum.MachineLearning.ValidationResults
title: ValidationResults Kullanıcı tanımlı türü
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ValidationResults
qsharp.summary: The results from having validated a classifier against a set of samples.
ms.openlocfilehash: 42bfab7fd1f9372d9394f2eaf2d698b39b4307e1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211500"
---
# <a name="validationresults-user-defined-type"></a><span data-ttu-id="2ea01-102">ValidationResults Kullanıcı tanımlı türü</span><span class="sxs-lookup"><span data-stu-id="2ea01-102">ValidationResults user defined type</span></span>

<span data-ttu-id="2ea01-103">Ad alanı: [Microsoft. hisse. Machinöğrenim](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="2ea01-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="2ea01-104">Paket: [Microsoft. hisse. Machine-öğrenim](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="2ea01-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="2ea01-105">Bir sınıflandırıcının bir örnek kümesiyle doğrulanması için sonuçlar.</span><span class="sxs-lookup"><span data-stu-id="2ea01-105">The results from having validated a classifier against a set of samples.</span></span>

```qsharp

newtype ValidationResults = (NMisclassifications : Int, NValidationSamples : Int);
```



## <a name="named-items"></a><span data-ttu-id="2ea01-106">Adlandırılmış öğeler</span><span class="sxs-lookup"><span data-stu-id="2ea01-106">Named Items</span></span>

### <a name="nmisclassifications--int"></a><span data-ttu-id="2ea01-107">NHatalı sınıflandırmalar: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2ea01-107">NMisclassifications : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2ea01-108">Doğrulama sırasında gözlemlenen hatalı sınıflandırmaların sayısı.</span><span class="sxs-lookup"><span data-stu-id="2ea01-108">The number of misclassifications observed during validation.</span></span>
### <a name="nvalidationsamples--int"></a><span data-ttu-id="2ea01-109">NValidationSamples: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2ea01-109">NValidationSamples : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

