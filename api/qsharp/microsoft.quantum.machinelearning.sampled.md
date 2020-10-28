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
# <a name="sampled-function"></a>Örneklenmiş işlev

Ad alanı: [Microsoft. hisse. Machinöğrenim](xref:Microsoft.Quantum.MachineLearning)

Leyebilir [](https://nuget.org/packages/)


Verilen zamanlamayı kullanarak belirli bir diziyi örnekler.

```qsharp
function Sampled<'T> (schedule : Microsoft.Quantum.MachineLearning.SamplingSchedule, values : 'T[]) : 'T[]
```


## <a name="input"></a>Giriş

### <a name="schedule--samplingschedule"></a>zamanlama: [Samplingschedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)

Örnekleme değerlerinde kullanılacak zamanlama.


### <a name="values--t"></a>değerler: 'T []

Örneklendiği değerler dizisi.



## <a name="output--t"></a>Çıkış: 'T []

Verilen zamanlamayı izleyerek değerlerden bir dizi öğe.

## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen

