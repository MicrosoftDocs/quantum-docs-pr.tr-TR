---
uid: Microsoft.Quantum.AmplitudeAmplification.StandardReflectionPhases
title: Standardreflectionaşamalar işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: StandardReflectionPhases
qsharp.summary: Computes partial reflection phases for standard amplitude amplification.
ms.openlocfilehash: 703b50d0186cd0f4eddb9a29fa3cffb2b746c8d6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843909"
---
# <a name="standardreflectionphases-function"></a>Standardreflectionaşamalar işlevi

Ad alanı: [Microsoft. hisse. yükseltilmiş Tudeamplif](xref:Microsoft.Quantum.AmplitudeAmplification)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Standart genliği yükseltme için kısmi yansıma aşamalarını hesaplar.

```qsharp
function StandardReflectionPhases (nIterations : Int) : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
```


## <a name="input"></a>Giriş

### <a name="niterations--int"></a>Nyinelemeler: [Int](xref:microsoft.quantum.lang-ref.int)

İçin kısmi yansıma aşamaları oluşturmak üzere genliği yükseltme yinelemesi sayısı.



## <a name="output--reflectionphases"></a>Çıkış: [Reflectionaşamalar](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)

Kısmi yansıtımları olarak belirtilen aşamaları uygulayan bir işlem

## <a name="remarks"></a>Açıklamalar

Başlangıç durumuna ilişkin ilk yansıma ve $0 $ olan hedef durum hakkında son yansıma dışında tüm aşamalar $ \pı $ ' tir.