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
# <a name="sampled-function"></a>Örneklenmiş işlev

Ad alanı: [Microsoft. hisse. Machinöğrenim](xref:Microsoft.Quantum.MachineLearning)

Paket: [Microsoft. hisse. Machine-öğrenim](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


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

