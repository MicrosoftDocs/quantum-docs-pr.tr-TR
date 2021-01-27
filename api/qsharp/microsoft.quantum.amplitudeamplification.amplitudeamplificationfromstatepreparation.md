---
uid: Microsoft.Quantum.AmplitudeAmplification.AmplitudeAmplificationFromStatePreparation
title: Yükseltilmiş Tudeamplificationfromstatehazırlama işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: AmplitudeAmplificationFromStatePreparation
qsharp.summary: Amplitude amplification by oracles for partial reflections.
ms.openlocfilehash: e64ad5ad4e975483f20f92c0b070dd6788ef296b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847448"
---
# <a name="amplitudeamplificationfromstatepreparation-function"></a>Yükseltilmiş Tudeamplificationfromstatehazırlama işlevi

Ad alanı: [Microsoft. hisse. yükseltilmiş Tudeamplif](xref:Microsoft.Quantum.AmplitudeAmplification)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


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



## <a name="output--qubit--unit--is-adj--ctl"></a>Output: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [birimi](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL

Kısmi yansıtımları tarafından uygulanan Oracles tarafından kullanılan genliği uygulayan bir işlem.

## <a name="remarks"></a>Açıklamalar

Bu, başlangıç ve hedef durumlarının biçiminde öğesinden daha sıkı koşullar uygular `AmpAmpByReflectionPhases` .
Hedef durumun $ \ket f $ tarafından işaretlenmiş olduğu varsayılır {1} \_ .
\Begin{hizalaması} A\ket {0} \_ {f} \demet {0} \_ s = \lambda\tusf\ket {1} \_ {\ Text {Target}} \_ s + \sqrt{1-| \lambda | ^ 2} {0} \_ \tusf\cnoktalar, \end{hizalaması} çoğu durumda `flagQubit` ve `auxiliaryRegister` $ \demet {0} \_ {f} \ demet {0} \_ s $ durumunda başlatılır.