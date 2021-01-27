---
uid: Microsoft.Quantum.AmplitudeAmplification.StandardAmplitudeAmplification
title: Standarsönlitudeamplifleştirme işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: StandardAmplitudeAmplification
qsharp.summary: Standard Amplitude Amplification algorithm
ms.openlocfilehash: 984bfee89b6d79750228b8ca6aaf404f58aecd41
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843939"
---
# <a name="standardamplitudeamplification-function"></a>Standarsönlitudeamplifleştirme işlevi

Ad alanı: [Microsoft. hisse. yükseltilmiş Tudeamplif](xref:Microsoft.Quantum.AmplitudeAmplification)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Standart genliği yükseltme algoritması

```qsharp
function StandardAmplitudeAmplification (nIterations : Int, stateOracle : Microsoft.Quantum.Oracles.StateOracle, idxFlagQubit : Int) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a>Giriş

### <a name="niterations--int"></a>Nyinelemeler: [Int](xref:microsoft.quantum.lang-ref.int)

Genliği yükseltme $n yineleme sayısı


### <a name="stateoracle--stateoracle"></a>stateOracle: [Stateoracle](xref:Microsoft.Quantum.Oracles.StateOracle)

Başlangıç durumunu hazırlayan Unitary Oracle $A $


### <a name="idxflagqubit--int"></a>ıdxflagqubit: [Int](xref:microsoft.quantum.lang-ref.int)

Bayrak qubit 'e kadar Dizin



## <a name="output--qubit--unit--is-adj--ctl"></a>Output: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [birimi](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL

Standart genliği yükseltme hisse algoritması algoritmasını uygulayan bir işlem

## <a name="remarks"></a>Açıklamalar

Bu, `AmpAmpPhasesStandard` \begin{hizalaması} A\ket {0} \_ {f} {0} \_ \gens = \lambda\tusf\ket {1} \_ {\ Text {Target}} \_ + \ sqrt{1-| \lambda | ^ 2} {0} \_ \tusf\cnoktalar, \end{hizalaması} bu işlem, çoğu durumda \begin{hizalaması} \operatorname{AmpAmpByOracle}\ket {0} \_ {f} {0} \_ \tuss = \sin ((2n + 1) \sin ^ {-1} (\lambda)) {1} \_ \tusf\ket {\ Text {Target}} \_ s + \cdots\tusf {0} \_ \end{hizalaması} durumunu hazırlar. `flagQubit` ve `auxiliaryRegister` $ \demet {0} \_ f\tusa $ ' da başlatılır {0} \_ .

## <a name="references"></a>Başvurular

- [*G. Brassard, P. Hoyer, M. Mosca, a. Tapp*](https://arxiv.org/abs/quant-ph/0005055)