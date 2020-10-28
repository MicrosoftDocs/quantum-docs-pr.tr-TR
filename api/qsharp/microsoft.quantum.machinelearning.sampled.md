---
uid: Microsoft.Quantum.MachineLearning.Sampled
title: Örneklenmiş işlev
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: Sampled
qsharp.summary: Samples a given array, using the given schedule.
ms.openlocfilehash: 9f9f91bc50861c5b31a76e28050189d13efda71e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732319"
---
# <a name="sampled-function"></a><span data-ttu-id="7bd7b-102">Örneklenmiş işlev</span><span class="sxs-lookup"><span data-stu-id="7bd7b-102">Sampled function</span></span>

<span data-ttu-id="7bd7b-103">Ad alanı: [Microsoft. hisse. Machinöğrenim](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="7bd7b-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="7bd7b-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7bd7b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7bd7b-105">Verilen zamanlamayı kullanarak belirli bir diziyi örnekler.</span><span class="sxs-lookup"><span data-stu-id="7bd7b-105">Samples a given array, using the given schedule.</span></span>

```qsharp
function Sampled<'T> (schedule : Microsoft.Quantum.MachineLearning.SamplingSchedule, values : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="7bd7b-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="7bd7b-106">Input</span></span>

### <a name="schedule--samplingschedule"></a><span data-ttu-id="7bd7b-107">zamanlama: [Samplingschedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span><span class="sxs-lookup"><span data-stu-id="7bd7b-107">schedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span></span>

<span data-ttu-id="7bd7b-108">Örnekleme değerlerinde kullanılacak zamanlama.</span><span class="sxs-lookup"><span data-stu-id="7bd7b-108">A schedule to use in sampling values.</span></span>


### <a name="values--t"></a><span data-ttu-id="7bd7b-109">değerler: 'T []</span><span class="sxs-lookup"><span data-stu-id="7bd7b-109">values : 'T[]</span></span>

<span data-ttu-id="7bd7b-110">Örneklendiği değerler dizisi.</span><span class="sxs-lookup"><span data-stu-id="7bd7b-110">An array of values to be sampled.</span></span>



## <a name="output--t"></a><span data-ttu-id="7bd7b-111">Çıkış: 'T []</span><span class="sxs-lookup"><span data-stu-id="7bd7b-111">Output : 'T[]</span></span>

<span data-ttu-id="7bd7b-112">Verilen zamanlamayı izleyerek değerlerden bir dizi öğe.</span><span class="sxs-lookup"><span data-stu-id="7bd7b-112">An array of elements from values, following the given schedule.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="7bd7b-113">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="7bd7b-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7bd7b-114">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="7bd7b-114">'T</span></span>

