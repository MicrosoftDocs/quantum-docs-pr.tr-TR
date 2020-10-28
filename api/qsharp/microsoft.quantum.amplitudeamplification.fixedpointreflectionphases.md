---
uid: Microsoft.Quantum.AmplitudeAmplification.FixedPointReflectionPhases
title: Fixedpointreflectionaşamalar işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: FixedPointReflectionPhases
qsharp.summary: Computes partial reflection phases for fixed-point amplitude amplification.
ms.openlocfilehash: 6ab2a8c6cb0b390f96aa13ece5d5b89c196a6107
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731994"
---
# <a name="fixedpointreflectionphases-function"></a>Fixedpointreflectionaşamalar işlevi

Ad alanı: [Microsoft. hisse. yükseltilmiş Tudeamplif](xref:Microsoft.Quantum.AmplitudeAmplification)

Leyebilir [](https://nuget.org/packages/)


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

## <a name="references"></a>Referanslar

"En Iyi sayıdaki sorgu ile sabit noktalı geniz yükseltme" aşamalarını kullanıyoruz

- [YoderLowChuang2014](https://arxiv.org/abs/1409.3305) Ayrıca bkz. "bileşik hisse kapıları Metodolojisi"
- [LowYoderChuang2016](https://arxiv.org/abs/1603.03996) Şu biçimdeki aşamalar için LowYoderChuang2016 `RotationPhases` .