---
uid: Microsoft.Quantum.AmplitudeAmplification.ApplyFixedPointAmplification
title: Applyfixedpoinkurname işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ApplyFixedPointAmplification
qsharp.summary: Fixed-Point Amplitude Amplification algorithm
ms.openlocfilehash: f506be7b2e3f65cf89694e30d79c04ec30d25035
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732023"
---
# <a name="applyfixedpointamplification-operation"></a>Applyfixedpoinkurname işlemi

Ad alanı: [Microsoft. hisse. yükseltilmiş Tudeamplif](xref:Microsoft.Quantum.AmplitudeAmplification)

Leyebilir [](https://nuget.org/packages/)


Fixed-Point genliği yükseltme algoritması

```qsharp
operation ApplyFixedPointAmplification (statePrepOracle : Microsoft.Quantum.Oracles.StateOracle, startQubits : Qubit[]) : Unit
```


## <a name="input"></a>Giriş

### <a name="statepreporacle--stateoracle"></a>statePrepOracle: [Stateoracle](xref:Microsoft.Quantum.Oracles.StateOracle)

Başlangıç durumunu hazırlayan, Unitary Oracle.


### <a name="startqubits--qubit"></a>startQubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubit kayıt



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Açıklamalar

StartQubits $ \ket{0 \cnoktalar 0} $ durumunda olmalıdır. Bu işlem, bir dizi sorguya ulaşılıncaya veya hedef durum bulunana kadar $2 $ üsleri üzerinde birkaç sorgu üzerinde yinelenir.