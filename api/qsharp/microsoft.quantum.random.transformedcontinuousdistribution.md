---
uid: Microsoft.Quantum.Random.TransformedContinuousDistribution
title: TransformedContinuousDistribution işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: TransformedContinuousDistribution
qsharp.summary: Given a continuous distribution, returns a new distribution that transforms the original by a given function.
ms.openlocfilehash: b317eaaa0ff0180ea5d240464c96d1c6b59c9c70
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226273"
---
# <a name="transformedcontinuousdistribution-function"></a><span data-ttu-id="f0190-102">TransformedContinuousDistribution işlevi</span><span class="sxs-lookup"><span data-stu-id="f0190-102">TransformedContinuousDistribution function</span></span>

<span data-ttu-id="f0190-103">Ad alanı: [Microsoft. hisse. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="f0190-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="f0190-104">Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="f0190-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="f0190-105">Sürekli dağıtım verildiğinde, belirli bir işlev tarafından orijinali dönüştüren yeni bir dağıtım döndürür.</span><span class="sxs-lookup"><span data-stu-id="f0190-105">Given a continuous distribution, returns a new distribution that transforms the original by a given function.</span></span>

```qsharp
function TransformedContinuousDistribution (transform : (Double -> Double), distribution : Microsoft.Quantum.Random.ContinuousDistribution) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a><span data-ttu-id="f0190-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="f0190-106">Input</span></span>

### <a name="transform--double---double"></a><span data-ttu-id="f0190-107">Dönüştür: [çift](xref:microsoft.quantum.lang-ref.double) -> [çift](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="f0190-107">transform : [Double](xref:microsoft.quantum.lang-ref.double) -> [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="f0190-108">Özgün dağıtımın varisayısını dönüştürülmüş dağıtıma dönüştüren bir işlev.</span><span class="sxs-lookup"><span data-stu-id="f0190-108">A function that transforms variates of the original distribution to the transformed distribution.</span></span>


### <a name="distribution--continuousdistribution"></a><span data-ttu-id="f0190-109">Dağıtım: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="f0190-109">distribution : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>

<span data-ttu-id="f0190-110">Dönüştürülecek orijinal dağıtım.</span><span class="sxs-lookup"><span data-stu-id="f0190-110">The original distribution to be transformed.</span></span>



## <a name="output--continuousdistribution"></a><span data-ttu-id="f0190-111">Çıkış: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="f0190-111">Output : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>

<span data-ttu-id="f0190-112">Tarafından verilen dönüşümde ile ilişkili yeni bir dağıtım `distribution` `transform` .</span><span class="sxs-lookup"><span data-stu-id="f0190-112">A new distribution related to `distribution` by the transformation given by `transform`.</span></span>