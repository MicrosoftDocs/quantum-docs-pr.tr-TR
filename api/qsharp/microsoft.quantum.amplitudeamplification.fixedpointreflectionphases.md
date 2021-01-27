---
uid: Microsoft.Quantum.AmplitudeAmplification.FixedPointReflectionPhases
title: Fixedpointreflectionaşamalar işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: FixedPointReflectionPhases
qsharp.summary: Computes partial reflection phases for fixed-point amplitude amplification.
ms.openlocfilehash: 2ded197801111c26d8a33f9c2363b46ca4b6c4b9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845851"
---
# <a name="fixedpointreflectionphases-function"></a>Fixedpointreflectionaşamalar işlevi

Ad alanı: [Microsoft. hisse. yükseltilmiş Tudeamplif](xref:Microsoft.Quantum.AmplitudeAmplification)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Sabit nokta genliği yükseltme için kısmi yansıma aşamalarını hesaplar.

```qsharp
function FixedPointReflectionPhases (nQueries : Int, successMin : Double) : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
```


## <a name="input"></a>Giriş

### <a name="nqueries--int"></a>nQueries: [Int](xref:microsoft.quantum.lang-ref.int)

Durum hazırlığı Oracle 'a yapılan sorgu sayısı. Tek bir tamsayı olmalıdır.


### <a name="successmin--double"></a>Başarılı smın: [Double](xref:microsoft.quantum.lang-ref.double)

Hedef en kısa başarı olasılığı.



## <a name="output--reflectionphases"></a>Çıkış: [Reflectionaşamalar](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)

Sabit nokta genampme hisse algoritması uygulamasında kullanılabilen aşamaların dizisi.

## <a name="references"></a>Başvurular

"En Iyi sayıdaki sorgu ile sabit noktalı geniz yükseltme" aşamalarını kullanıyoruz

- [YoderLowChuang2014](https://arxiv.org/abs/1409.3305) Ayrıca bkz. "bileşik hisse kapıları Metodolojisi"
- [](https://arxiv.org/abs/1603.03996) Şu biçimdeki aşamalar için LowYoderChuang2016 `RotationPhases` .