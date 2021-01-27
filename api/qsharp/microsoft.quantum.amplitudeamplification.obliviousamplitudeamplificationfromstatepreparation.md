---
uid: Microsoft.Quantum.AmplitudeAmplification.ObliviousAmplitudeAmplificationFromStatePreparation
title: ObliviousAmplitudeAmplificationFromStatePreparation işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ObliviousAmplitudeAmplificationFromStatePreparation
qsharp.summary: Oblivious amplitude amplification by oracles for partial reflections.
ms.openlocfilehash: 873c436d4b8d8efc9dc61c2baba9b0e0f7f09fc2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845815"
---
# <a name="obliviousamplitudeamplificationfromstatepreparation-function"></a>ObliviousAmplitudeAmplificationFromStatePreparation işlevi

Ad alanı: [Microsoft. hisse. yükseltilmiş Tudeamplif](xref:Microsoft.Quantum.AmplitudeAmplification)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Yükümlülüğü, kısmi yansıtımları için Oracles tarafından bir şekilde geliştirilmiştir.

```qsharp
function ObliviousAmplitudeAmplificationFromStatePreparation (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateOracle : Microsoft.Quantum.Oracles.DeterministicStateOracle, signalOracle : Microsoft.Quantum.Oracles.ObliviousOracle, idxFlagQubit : Int) : ((Qubit[], Qubit[]) => Unit is Adj + Ctl)
```


## <a name="input"></a>Giriş

### <a name="phases--reflectionphases"></a>Aşamalar: [Reflectionaşamalar](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)

Kısmi yansıtımları aşamaları


### <a name="startstateoracle--deterministicstateoracle"></a>startStateOracle: [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)

Yardımcı başlangıç durumunu hazırlayan Unitary Oracle $A $


### <a name="signaloracle--obliviousoracle"></a>signalOracle: [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)

Ortak `ObliviousOracle` ve sistem kaydı üzerinde birlikte çalışan türdeki Unitary oracle $O $


### <a name="idxflagqubit--int"></a>ıdxflagqubit: [Int](xref:microsoft.quantum.lang-ref.int)

Tek qubit bayrak kaydına yönelik Dizin



## <a name="output--qubitqubit--unit--is-adj--ctl"></a>Çıkış: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [birimi](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL

Yükümlülüğü uygulayan, kısmi yansımaları temel alan bir işlem.

## <a name="remarks"></a>Açıklamalar

Bu, yardımcı başlangıç ve hedef durumlarının biçimine kıyasla daha sıkı koşullar uygular `AmpAmpObliviousByReflectionPhases` .
$A {0} \_ \tusf\demet {0} \_ A = \ket{\Text{Start}} \_ {FA} $, yardımcı başlangıç durumunu $ \ket{\Text{Start}} \_ {FA} $ değerini hesaplama tabanlı $ {0} \_ \tusf\ket $ ' nden hazırlar {0} .
Hedef durumun $ \ket f $ tarafından işaretlenmiş olduğu varsayılır {1} \_ .
\Begin{hizalaması} O\ket {\ Text {Start}} \_ {FA} \ket{\psı} \_ s = \lambdad\tusf\tus{ {1} \_ \ Text {bir}} \_ a\tus{\ Text {Target}} \_ s U \ket{\psı} \_ s + \sqrt{1-| \lambda | ^ 2} \tusf\cnoktalar {0} \_ , \end{hizalaması}, bazı Unitary $U $.