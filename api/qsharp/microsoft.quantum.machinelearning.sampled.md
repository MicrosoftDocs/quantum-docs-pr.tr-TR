---
uid: Microsoft.Quantum.MachineLearning.Sampled
title: Örneklenmiş işlev
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: Sampled
qsharp.summary: Samples a given array, using the given schedule.
ms.openlocfilehash: ddff72bbed6f20e8e0ceb3bfe3fc50a3da0bd2a9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211636"
---
# <a name="sampled-function"></a><span data-ttu-id="5e2f6-102">Örneklenmiş işlev</span><span class="sxs-lookup"><span data-stu-id="5e2f6-102">Sampled function</span></span>

<span data-ttu-id="5e2f6-103">Ad alanı: [Microsoft. hisse. Machinöğrenim](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="5e2f6-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="5e2f6-104">Paket: [Microsoft. hisse. Machine-öğrenim](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="5e2f6-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="5e2f6-105">Verilen zamanlamayı kullanarak belirli bir diziyi örnekler.</span><span class="sxs-lookup"><span data-stu-id="5e2f6-105">Samples a given array, using the given schedule.</span></span>

```qsharp
function Sampled<'T> (schedule : Microsoft.Quantum.MachineLearning.SamplingSchedule, values : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="5e2f6-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="5e2f6-106">Input</span></span>

### <a name="schedule--samplingschedule"></a><span data-ttu-id="5e2f6-107">zamanlama: [Samplingschedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span><span class="sxs-lookup"><span data-stu-id="5e2f6-107">schedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span></span>

<span data-ttu-id="5e2f6-108">Örnekleme değerlerinde kullanılacak zamanlama.</span><span class="sxs-lookup"><span data-stu-id="5e2f6-108">A schedule to use in sampling values.</span></span>


### <a name="values--t"></a><span data-ttu-id="5e2f6-109">değerler: 'T []</span><span class="sxs-lookup"><span data-stu-id="5e2f6-109">values : 'T[]</span></span>

<span data-ttu-id="5e2f6-110">Örneklendiği değerler dizisi.</span><span class="sxs-lookup"><span data-stu-id="5e2f6-110">An array of values to be sampled.</span></span>



## <a name="output--t"></a><span data-ttu-id="5e2f6-111">Çıkış: 'T []</span><span class="sxs-lookup"><span data-stu-id="5e2f6-111">Output : 'T[]</span></span>

<span data-ttu-id="5e2f6-112">Verilen zamanlamayı izleyerek değerlerden bir dizi öğe.</span><span class="sxs-lookup"><span data-stu-id="5e2f6-112">An array of elements from values, following the given schedule.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="5e2f6-113">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="5e2f6-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="5e2f6-114">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="5e2f6-114">'T</span></span>

