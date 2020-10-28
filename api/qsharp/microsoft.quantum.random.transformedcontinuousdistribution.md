---
uid: Microsoft.Quantum.Random.TransformedContinuousDistribution
title: TransformedContinuousDistribution işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: TransformedContinuousDistribution
qsharp.summary: Given a continuous distribution, returns a new distribution that transforms the original by a given function.
ms.openlocfilehash: 6a6e0c26bd650fd4c05208197ff23f951d1c3b5c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726461"
---
# <a name="transformedcontinuousdistribution-function"></a><span data-ttu-id="d85eb-102">TransformedContinuousDistribution işlevi</span><span class="sxs-lookup"><span data-stu-id="d85eb-102">TransformedContinuousDistribution function</span></span>

<span data-ttu-id="d85eb-103">Ad alanı: [Microsoft. hisse. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="d85eb-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="d85eb-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d85eb-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d85eb-105">Sürekli dağıtım verildiğinde, belirli bir işlev tarafından orijinali dönüştüren yeni bir dağıtım döndürür.</span><span class="sxs-lookup"><span data-stu-id="d85eb-105">Given a continuous distribution, returns a new distribution that transforms the original by a given function.</span></span>

```qsharp
function TransformedContinuousDistribution (transform : (Double -> Double), distribution : Microsoft.Quantum.Random.ContinuousDistribution) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a><span data-ttu-id="d85eb-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="d85eb-106">Input</span></span>

### <a name="transform--double---double"></a><span data-ttu-id="d85eb-107">Dönüştür: [çift](xref:microsoft.quantum.lang-ref.double) -> [çift](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="d85eb-107">transform : [Double](xref:microsoft.quantum.lang-ref.double) -> [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="d85eb-108">Özgün dağıtımın varisayısını dönüştürülmüş dağıtıma dönüştüren bir işlev.</span><span class="sxs-lookup"><span data-stu-id="d85eb-108">A function that transforms variates of the original distribution to the transformed distribution.</span></span>


### <a name="distribution--continuousdistribution"></a><span data-ttu-id="d85eb-109">Dağıtım: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="d85eb-109">distribution : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>

<span data-ttu-id="d85eb-110">Dönüştürülecek orijinal dağıtım.</span><span class="sxs-lookup"><span data-stu-id="d85eb-110">The original distribution to be transformed.</span></span>



## <a name="output--continuousdistribution"></a><span data-ttu-id="d85eb-111">Çıkış: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="d85eb-111">Output : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>

<span data-ttu-id="d85eb-112">Tarafından verilen dönüşümde ile ilişkili yeni bir dağıtım `distribution` `transform` .</span><span class="sxs-lookup"><span data-stu-id="d85eb-112">A new distribution related to `distribution` by the transformation given by `transform`.</span></span>