---
uid: Microsoft.Quantum.MachineLearning.ScheduleLength
title: ScheduleLength işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ScheduleLength
qsharp.summary: Returns the number of elements in a given sampling schedule.
ms.openlocfilehash: 008bdcdc0a7c0ad2775dea65ebba46556092beed
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211602"
---
# <a name="schedulelength-function"></a><span data-ttu-id="de326-102">ScheduleLength işlevi</span><span class="sxs-lookup"><span data-stu-id="de326-102">ScheduleLength function</span></span>

<span data-ttu-id="de326-103">Ad alanı: [Microsoft. hisse. Machinöğrenim](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="de326-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="de326-104">Paket: [Microsoft. hisse. Machine-öğrenim](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="de326-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="de326-105">Belirli bir örnekleme zamanlaması içindeki öğe sayısını döndürür.</span><span class="sxs-lookup"><span data-stu-id="de326-105">Returns the number of elements in a given sampling schedule.</span></span>

```qsharp
function ScheduleLength (schedule : Microsoft.Quantum.MachineLearning.SamplingSchedule) : Int
```


## <a name="input"></a><span data-ttu-id="de326-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="de326-106">Input</span></span>

### <a name="schedule--samplingschedule"></a><span data-ttu-id="de326-107">zamanlama: [Samplingschedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span><span class="sxs-lookup"><span data-stu-id="de326-107">schedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span></span>

<span data-ttu-id="de326-108">Uzunluğu döndürülecek olan örnekleme zamanlaması.</span><span class="sxs-lookup"><span data-stu-id="de326-108">A sampling schedule whose length is to be returned.</span></span>



## <a name="output--int"></a><span data-ttu-id="de326-109">Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="de326-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="de326-110">Verilen örnekleme zamanlamadaki öğelerin sayısı.</span><span class="sxs-lookup"><span data-stu-id="de326-110">The number of elements in the given sampling schedule.</span></span>