---
uid: Microsoft.Quantum.MachineLearning.ScheduleLength
title: ScheduleLength işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ScheduleLength
qsharp.summary: Returns the number of elements in a given sampling schedule.
ms.openlocfilehash: dd042b1282d2f5386ee0b67bf57ad4027eefd493
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854917"
---
# <a name="schedulelength-function"></a><span data-ttu-id="e25f0-102">ScheduleLength işlevi</span><span class="sxs-lookup"><span data-stu-id="e25f0-102">ScheduleLength function</span></span>

<span data-ttu-id="e25f0-103">Ad alanı: [Microsoft. hisse. Machinöğrenim](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="e25f0-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="e25f0-104">Paket: [Microsoft. hisse. Machine-öğrenim](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="e25f0-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="e25f0-105">Belirli bir örnekleme zamanlaması içindeki öğe sayısını döndürür.</span><span class="sxs-lookup"><span data-stu-id="e25f0-105">Returns the number of elements in a given sampling schedule.</span></span>

```qsharp
function ScheduleLength (schedule : Microsoft.Quantum.MachineLearning.SamplingSchedule) : Int
```


## <a name="input"></a><span data-ttu-id="e25f0-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="e25f0-106">Input</span></span>

### <a name="schedule--samplingschedule"></a><span data-ttu-id="e25f0-107">zamanlama: [Samplingschedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span><span class="sxs-lookup"><span data-stu-id="e25f0-107">schedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span></span>

<span data-ttu-id="e25f0-108">Uzunluğu döndürülecek olan örnekleme zamanlaması.</span><span class="sxs-lookup"><span data-stu-id="e25f0-108">A sampling schedule whose length is to be returned.</span></span>



## <a name="output--int"></a><span data-ttu-id="e25f0-109">Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e25f0-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e25f0-110">Verilen örnekleme zamanlamadaki öğelerin sayısı.</span><span class="sxs-lookup"><span data-stu-id="e25f0-110">The number of elements in the given sampling schedule.</span></span>