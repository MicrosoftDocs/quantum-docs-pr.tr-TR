---
uid: Microsoft.Quantum.AmplitudeAmplification.StandardReflectionPhases
title: Standardreflectionaşamalar işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: StandardReflectionPhases
qsharp.summary: Computes partial reflection phases for standard amplitude amplification.
ms.openlocfilehash: c189b34b641989ab458986fb3f2872759b949be5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731922"
---
# <a name="standardreflectionphases-function"></a>Standardreflectionaşamalar işlevi

Ad alanı: [Microsoft. hisse. yükseltilmiş Tudeamplif](xref:Microsoft.Quantum.AmplitudeAmplification)

Leyebilir [](https://nuget.org/packages/)


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