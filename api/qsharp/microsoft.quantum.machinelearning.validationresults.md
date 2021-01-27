---
uid: Microsoft.Quantum.MachineLearning.ValidationResults
title: ValidationResults Kullanıcı tanımlı türü
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ValidationResults
qsharp.summary: The results from having validated a classifier against a set of samples.
ms.openlocfilehash: 923fd80333b6bf77daeaac2bf205db620e61cfd0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846086"
---
# <a name="validationresults-user-defined-type"></a><span data-ttu-id="a0336-102">ValidationResults Kullanıcı tanımlı türü</span><span class="sxs-lookup"><span data-stu-id="a0336-102">ValidationResults user defined type</span></span>

<span data-ttu-id="a0336-103">Ad alanı: [Microsoft. hisse. Machinöğrenim](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="a0336-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="a0336-104">Paket: [Microsoft. hisse. Machine-öğrenim](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="a0336-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="a0336-105">Bir sınıflandırıcının bir örnek kümesiyle doğrulanması için sonuçlar.</span><span class="sxs-lookup"><span data-stu-id="a0336-105">The results from having validated a classifier against a set of samples.</span></span>

```qsharp

newtype ValidationResults = (NMisclassifications : Int, NValidationSamples : Int);
```



## <a name="named-items"></a><span data-ttu-id="a0336-106">Adlandırılmış öğeler</span><span class="sxs-lookup"><span data-stu-id="a0336-106">Named Items</span></span>

### <a name="nmisclassifications--int"></a><span data-ttu-id="a0336-107">NHatalı sınıflandırmalar: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a0336-107">NMisclassifications : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a0336-108">Doğrulama sırasında gözlemlenen hatalı sınıflandırmaların sayısı.</span><span class="sxs-lookup"><span data-stu-id="a0336-108">The number of misclassifications observed during validation.</span></span>
### <a name="nvalidationsamples--int"></a><span data-ttu-id="a0336-109">NValidationSamples: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a0336-109">NValidationSamples : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

