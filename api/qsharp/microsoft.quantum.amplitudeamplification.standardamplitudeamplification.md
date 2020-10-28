---
uid: Microsoft.Quantum.AmplitudeAmplification.StandardAmplitudeAmplification
title: Standarsönlitudeamplifleştirme işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: StandardAmplitudeAmplification
qsharp.summary: Standard Amplitude Amplification algorithm
ms.openlocfilehash: 18228d45c4df280b004c595a7b0f1e2a607b8b2c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731930"
---
# <a name="standardamplitudeamplification-function"></a>Standarsönlitudeamplifleştirme işlevi

Ad alanı: [Microsoft. hisse. yükseltilmiş Tudeamplif](xref:Microsoft.Quantum.AmplitudeAmplification)

Leyebilir [](https://nuget.org/packages/)


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



## <a name="output--qubit--unit-adj--ctl"></a>Output: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [birim](xref:microsoft.quantum.lang-ref.unit) ayarlama ve CTL

Standart genliği yükseltme hisse algoritması algoritmasını uygulayan bir işlem

## <a name="remarks"></a>Açıklamalar

Bu, `AmpAmpPhasesStandard` \begin{hizalaması} A\ket {0} \_ {f} {0} \_ \gens = \lambda\tusf\ket {1} \_ {\ Text {Target}} \_ + \ sqrt{1-| \lambda | ^ 2} {0} \_ \tusf\cnoktalar, \end{hizalaması} bu işlem, çoğu durumda \begin{hizalaması} \operatorname{AmpAmpByOracle}\ket {0} \_ {f} {0} \_ \tuss = \sin ((2n + 1) \sin ^ {-1} (\lambda)) {1} \_ \tusf\ket {\ Text {Target}} \_ s + \cdots\tusf {0} \_ \end{hizalaması} durumunu hazırlar. `flagQubit` ve `auxiliaryRegister` $ \demet {0} \_ f\tusa $ ' da başlatılır {0} \_ .

## <a name="references"></a>Referanslar

- [*G. Brassard, P. Hoyer, M. Mosca, a. Tapp*](https://arxiv.org/abs/quant-ph/0005055)