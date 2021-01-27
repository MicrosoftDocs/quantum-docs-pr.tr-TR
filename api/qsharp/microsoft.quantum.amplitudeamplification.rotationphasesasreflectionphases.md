---
uid: Microsoft.Quantum.AmplitudeAmplification.RotationPhasesAsReflectionPhases
title: Rotationphasesasreflectionaşamalar işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: RotationPhasesAsReflectionPhases
qsharp.summary: Converts phases specified as single-qubit rotations to phases specified as partial reflections.
ms.openlocfilehash: 5d50b3fdc2b0f948e93cb11b5c69403d97574ccd
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843948"
---
# <a name="rotationphasesasreflectionphases-function"></a>Rotationphasesasreflectionaşamalar işlevi

Ad alanı: [Microsoft. hisse. yükseltilmiş Tudeamplif](xref:Microsoft.Quantum.AmplitudeAmplification)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Tek qubit döndürmeler olarak belirtilen aşamaları kısmi yansıtılamalar olarak belirtilen aşamalara dönüştürür.

```qsharp
function RotationPhasesAsReflectionPhases (rotPhases : Microsoft.Quantum.AmplitudeAmplification.RotationPhases) : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
```


## <a name="input"></a>Giriş

### <a name="rotphases--rotationphases"></a>Rotaşamaları: [Rotationaşamalar](xref:Microsoft.Quantum.AmplitudeAmplification.RotationPhases)

Kısmi yansıtımları 'na dönüştürülecek tek qubit döndürmeler dizisi.



## <a name="output--reflectionphases"></a>Çıkış: [Reflectionaşamalar](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)

Kısmi yansıtımları olarak belirtilen aşamaları uygulayan bir işlem.

## <a name="references"></a>Başvurular

İçindeki kuralını kullanıyoruz

- Tek qubit döndürme aşamalarını yansıma işleci aşamalarına ilişkilendirmek için [ *G.H. Low, i. L. Chuang*](https://arxiv.org/abs/1707.05391) .