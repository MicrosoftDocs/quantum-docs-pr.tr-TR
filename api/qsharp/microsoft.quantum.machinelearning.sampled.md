---
uid: Microsoft.Quantum.MachineLearning.Sampled
title: Örneklenmiş işlev
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: Sampled
qsharp.summary: Samples a given array, using the given schedule.
ms.openlocfilehash: 5dd599246847718f4f0411715585cb416595db9d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854944"
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

