---
uid: Microsoft.Quantum.MachineLearning.LabeledSample
title: LabeledSample Kullanıcı tanımlı türü
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: LabeledSample
qsharp.summary: A sample, labeled with a class to which that sample belongs.
ms.openlocfilehash: 8b4afa1eaf7ca69938b2606163cd1ec17a1ad80f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726629"
---
# <a name="labeledsample-user-defined-type"></a><span data-ttu-id="9f7ac-102">LabeledSample Kullanıcı tanımlı türü</span><span class="sxs-lookup"><span data-stu-id="9f7ac-102">LabeledSample user defined type</span></span>

<span data-ttu-id="9f7ac-103">Ad alanı: [Microsoft. hisse. Machinöğrenim](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="9f7ac-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="9f7ac-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9f7ac-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9f7ac-105">Örnek ait olduğu sınıf ile etiketlenmiş bir örnek.</span><span class="sxs-lookup"><span data-stu-id="9f7ac-105">A sample, labeled with a class to which that sample belongs.</span></span>

```qsharp

newtype LabeledSample = (Features : Double[], Label : Int);
```



## <a name="named-items"></a><span data-ttu-id="9f7ac-106">Adlandırılmış öğeler</span><span class="sxs-lookup"><span data-stu-id="9f7ac-106">Named Items</span></span>

### <a name="features--double"></a><span data-ttu-id="9f7ac-107">Özellikler: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="9f7ac-107">Features : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="9f7ac-108">Verilen örnek için bir özellik vektörü.</span><span class="sxs-lookup"><span data-stu-id="9f7ac-108">A vector of features for the given sample.</span></span>
### <a name="label--int"></a><span data-ttu-id="9f7ac-109">Etiket: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9f7ac-109">Label : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9f7ac-110">Bu örneğin ait olduğu sınıf için bir tamsayı etiketi.</span><span class="sxs-lookup"><span data-stu-id="9f7ac-110">An integer label for the class to which this sample belongs.</span></span>