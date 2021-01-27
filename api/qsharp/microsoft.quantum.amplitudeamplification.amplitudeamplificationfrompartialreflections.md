---
uid: Microsoft.Quantum.AmplitudeAmplification.AmplitudeAmplificationFromPartialReflections
title: Amptudeamplificationfrompartialyansıtıctions işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: AmplitudeAmplificationFromPartialReflections
qsharp.summary: Amplitude amplification by partial reflections.
ms.openlocfilehash: e4030aabcab55db35bcb8199e37bee837ead6ad0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845914"
---
# <a name="amplitudeamplificationfrompartialreflections-function"></a>Amptudeamplificationfrompartialyansıtıctions işlevi

Ad alanı: [Microsoft. hisse. yükseltilmiş Tudeamplif](xref:Microsoft.Quantum.AmplitudeAmplification)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


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



## <a name="output--qubit--unit--is-adj--ctl"></a>Output: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [birimi](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL

Kısmi yansıtımları tarafından genliği uygulayan bir işlem.

## <a name="remarks"></a>Açıklamalar

Genlik yükseltme, hiçbir sistem qubit olmadığı ve yükümlülüğü olarak Oracle 'ın kimlik olarak ayarlandığı, yükümlülüğü bir genlik genkezliği olan özel bir durumdur.
Çoğu durumda, $ `startQubits` \_ -$1 eigenstate olan $ \ket{\Text{Start}} $1 durumunda başlatılır `startStateReflection` .