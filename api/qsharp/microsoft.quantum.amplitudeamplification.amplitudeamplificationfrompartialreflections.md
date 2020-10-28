---
uid: Microsoft.Quantum.AmplitudeAmplification.AmplitudeAmplificationFromPartialReflections
title: Amptudeamplificationfrompartialyansıtıctions işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: AmplitudeAmplificationFromPartialReflections
qsharp.summary: Amplitude amplification by partial reflections.
ms.openlocfilehash: fc7c2c0d05ea626f7f7e5d8ebf3ce5ecea61390b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732047"
---
# <a name="amplitudeamplificationfrompartialreflections-function"></a>Amptudeamplificationfrompartialyansıtıctions işlevi

Ad alanı: [Microsoft. hisse. yükseltilmiş Tudeamplif](xref:Microsoft.Quantum.AmplitudeAmplification)

Leyebilir [](https://nuget.org/packages/)


Kısmi yansıtımları ile genliği yükseltme.

```qsharp
function AmplitudeAmplificationFromPartialReflections (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, targetStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a>Giriş

### <a name="phases--reflectionphases"></a>Aşamalar: [Reflectionaşamalar](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)

Kısmi yansıtımları aşamaları


### <a name="startstatereflection--reflectionoracle"></a>Startstatereftaction: [Reflectionoracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)

Başlangıç durumu hakkında yansıma işleci


### <a name="targetstatereflection--reflectionoracle"></a>Targetstatereftaction: [Reflectionoracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)

Hedef durumu hakkında yansıma işleci



## <a name="output--qubit--unit-adj--ctl"></a>Output: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [birim](xref:microsoft.quantum.lang-ref.unit) ayarlama ve CTL

Kısmi yansıtımları tarafından genliği uygulayan bir işlem.

## <a name="remarks"></a>Açıklamalar

Genlik yükseltme, hiçbir sistem qubit olmadığı ve yükümlülüğü olarak Oracle 'ın kimlik olarak ayarlandığı, yükümlülüğü bir genlik genkezliği olan özel bir durumdur.
Çoğu durumda, $ `startQubits` \_ -$1 eigenstate olan $ \ket{\Text{Start}} $1 durumunda başlatılır `startStateReflection` .