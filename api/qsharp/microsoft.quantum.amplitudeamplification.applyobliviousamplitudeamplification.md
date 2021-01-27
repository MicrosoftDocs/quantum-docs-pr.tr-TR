---
uid: Microsoft.Quantum.AmplitudeAmplification.ApplyObliviousAmplitudeAmplification
title: ApplyObliviousAmplitudeAmplification işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ApplyObliviousAmplitudeAmplification
qsharp.summary: Oblivious amplitude amplification by specifying partial reflections.
ms.openlocfilehash: c171021272076cc3960307523e25c4493bb49c5a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845868"
---
# <a name="applyobliviousamplitudeamplification-operation"></a>ApplyObliviousAmplitudeAmplification işlemi

Ad alanı: [Microsoft. hisse. yükseltilmiş Tudeamplif](xref:Microsoft.Quantum.AmplitudeAmplification)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


, Kısmi yansımalar belirterek yükümlülüğü genliği bir şekilde yükseltme.

```qsharp
operation ApplyObliviousAmplitudeAmplification (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, targetStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, signalOracle : Microsoft.Quantum.Oracles.ObliviousOracle, auxiliaryRegister : Qubit[], systemRegister : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Giriş

### <a name="phases--reflectionphases"></a>Aşamalar: [Reflectionaşamalar](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)

Kısmi yansıtımları aşamaları


### <a name="startstatereflection--reflectionoracle"></a>Startstatereftaction: [Reflectionoracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)

Yardımcı kaydın başlangıç durumu hakkında yansıma işleci


### <a name="targetstatereflection--reflectionoracle"></a>Targetstatereftaction: [Reflectionoracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)

Yardımcı kaydın hedef durumu hakkında yansıma işleci


### <a name="signaloracle--obliviousoracle"></a>signalOracle: [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)

Yardımcı ve sistem Yazmaçları üzerinde ortaklaşa çalışan türde Unitary Oracle $O $ `ObliviousOracle` .


### <a name="auxiliaryregister--qubit"></a>auxiliaryRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Yardımcı kayıt


### <a name="systemregister--qubit"></a>systemRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Sistem kaydı



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Açıklamalar

Belirli bir yardımcı başlangıç durumu $ \ket{\Text{Start}} \_ a $, belirli bir yardımcı hedef durumu $ \ket{\Text{Target}} \_ a $ ve herhangi bir sistem durumu $ \ket{\psı} \_ s $ olarak verildi. \begin{hizalaması} o\ket {\ Text {Start}} \_ a\ket {\ PSI} \_ s = \lambdad\ket{\Text{Target}} \_ a U \ket{\psıd olduğunu varsayalım.} \_ s + \sqrt{1-| \lambda | ^ 2} \ket{\Text{Target} ^ \perp} \_ a\cnoktalar \end{hizalaması}, bazı Unitary $U $.
, Ve Adjoint 'ın uygulamaları tarafından, yardımcı kayıt arasındaki başlangıç ve hedef durumları hakkında bir dizi yansıma ile `signalOracle` , U 'nin uygulanması için başarılı olma olasılığı da değişebilir.

Çoğu durumda, `auxiliaryRegister` $ \ket{\Text{Start}} \_ a $ durumunda başlatılır.

## <a name="references"></a>Başvurular

Bkz.

- Standart sürüm için [ *D.W. Braz, Child, r. Cleve, r. Kothari, R.D. Somma*](https://arxiv.org/abs/1312.1414) .
  Bkz.
- [ *G.H. Low, I.L. Chuang*](https://arxiv.org/abs/1610.06546) kısmi yansıtımları Genelleştirme için.