---
uid: Microsoft.Quantum.AmplitudeAmplification.RotationPhasesAsReflectionPhases
title: Rotationphasesasreflectionaşamalar işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: RotationPhasesAsReflectionPhases
qsharp.summary: Converts phases specified as single-qubit rotations to phases specified as partial reflections.
ms.openlocfilehash: d62a7584324c9467ccc759e4bed81acbceee719c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731935"
---
# <a name="rotationphasesasreflectionphases-function"></a>Rotationphasesasreflectionaşamalar işlevi

Ad alanı: [Microsoft. hisse. yükseltilmiş Tudeamplif](xref:Microsoft.Quantum.AmplitudeAmplification)

Leyebilir [](https://nuget.org/packages/)


Tek qubit döndürmeler olarak belirtilen aşamaları kısmi yansıtılamalar olarak belirtilen aşamalara dönüştürür.

```qsharp
function RotationPhasesAsReflectionPhases (rotPhases : Microsoft.Quantum.AmplitudeAmplification.RotationPhases) : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
```


## <a name="input"></a>Giriş

### <a name="rotphases--rotationphases"></a>Rotaşamaları: [Rotationaşamalar](xref:Microsoft.Quantum.AmplitudeAmplification.RotationPhases)

Kısmi yansıtımları 'na dönüştürülecek tek qubit döndürmeler dizisi.



## <a name="output--reflectionphases"></a>Çıkış: [Reflectionaşamalar](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)

Kısmi yansıtımları olarak belirtilen aşamaları uygulayan bir işlem.

## <a name="references"></a>Referanslar

İçindeki kuralını kullanıyoruz

- Tek qubit döndürme aşamalarını yansıma işleci aşamalarına ilişkilendirmek için [ *G.H. Low, i. L. Chuang*](https://arxiv.org/abs/1707.05391) .