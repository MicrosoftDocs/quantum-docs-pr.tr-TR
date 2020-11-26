---
uid: Microsoft.Quantum.MachineLearning.LabeledSample
title: LabeledSample Kullanıcı tanımlı türü
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: LabeledSample
qsharp.summary: A sample, labeled with a class to which that sample belongs.
ms.openlocfilehash: a7c7dae5cd9e82d66bb98313f4200838006ca291
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196336"
---
# <a name="labeledsample-user-defined-type"></a><span data-ttu-id="006f3-102">LabeledSample Kullanıcı tanımlı türü</span><span class="sxs-lookup"><span data-stu-id="006f3-102">LabeledSample user defined type</span></span>

<span data-ttu-id="006f3-103">Ad alanı: [Microsoft. hisse. Machinöğrenim](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="006f3-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="006f3-104">Paket: [Microsoft. hisse. Machine-öğrenim](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="006f3-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="006f3-105">Örnek ait olduğu sınıf ile etiketlenmiş bir örnek.</span><span class="sxs-lookup"><span data-stu-id="006f3-105">A sample, labeled with a class to which that sample belongs.</span></span>

```qsharp

newtype LabeledSample = (Features : Double[], Label : Int);
```



## <a name="named-items"></a><span data-ttu-id="006f3-106">Adlandırılmış öğeler</span><span class="sxs-lookup"><span data-stu-id="006f3-106">Named Items</span></span>

### <a name="features--double"></a><span data-ttu-id="006f3-107">Özellikler: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="006f3-107">Features : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="006f3-108">Verilen örnek için bir özellik vektörü.</span><span class="sxs-lookup"><span data-stu-id="006f3-108">A vector of features for the given sample.</span></span>
### <a name="label--int"></a><span data-ttu-id="006f3-109">Etiket: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="006f3-109">Label : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="006f3-110">Bu örneğin ait olduğu sınıf için bir tamsayı etiketi.</span><span class="sxs-lookup"><span data-stu-id="006f3-110">An integer label for the class to which this sample belongs.</span></span>