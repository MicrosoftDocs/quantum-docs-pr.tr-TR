---
uid: Microsoft.Quantum.AmplitudeAmplification.AmplitudeAmplificationFromStatePreparation
title: Yükseltilmiş Tudeamplificationfromstatehazırlama işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: AmplitudeAmplificationFromStatePreparation
qsharp.summary: Amplitude amplification by oracles for partial reflections.
ms.openlocfilehash: 7725ff327e327578ff36242a2b1bc6d03fab0d0c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732042"
---
# <a name="amplitudeamplificationfromstatepreparation-function"></a>Yükseltilmiş Tudeamplificationfromstatehazırlama işlevi

Ad alanı: [Microsoft. hisse. yükseltilmiş Tudeamplif](xref:Microsoft.Quantum.AmplitudeAmplification)

Leyebilir [](https://nuget.org/packages/)


Kısmi yansıtımları için Oracles tarafından bir aşağı yönlü yükseltme.

```qsharp
function AmplitudeAmplificationFromStatePreparation (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, stateOracle : Microsoft.Quantum.Oracles.StateOracle, idxFlagQubit : Int) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a>Giriş

### <a name="phases--reflectionphases"></a>Aşamalar: [Reflectionaşamalar](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)

Kısmi yansıtımları aşamaları


### <a name="stateoracle--stateoracle"></a>stateOracle: [Stateoracle](xref:Microsoft.Quantum.Oracles.StateOracle)

Başlangıç durumunu hazırlayan Unitary Oracle $A $


### <a name="idxflagqubit--int"></a>ıdxflagqubit: [Int](xref:microsoft.quantum.lang-ref.int)

Bayrak qubit 'e kadar Dizin



## <a name="output--qubit--unit-adj--ctl"></a>Output: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [birim](xref:microsoft.quantum.lang-ref.unit) ayarlama ve CTL

Kısmi yansıtımları tarafından uygulanan Oracles tarafından kullanılan genliği uygulayan bir işlem.

## <a name="remarks"></a>Açıklamalar

Bu, başlangıç ve hedef durumlarının biçiminde öğesinden daha sıkı koşullar uygular `AmpAmpByReflectionPhases` .
Hedef durumun $ \ket f $ tarafından işaretlenmiş olduğu varsayılır {1} \_ .
\Begin{hizalaması} A\ket {0} \_ {f} \demet {0} \_ s = \lambda\tusf\ket {1} \_ {\ Text {Target}} \_ s + \sqrt{1-| \lambda | ^ 2} {0} \_ \tusf\cnoktalar, \end{hizalaması} çoğu durumda `flagQubit` ve `auxiliaryRegister` $ \demet {0} \_ {f} \ demet {0} \_ s $ durumunda başlatılır.