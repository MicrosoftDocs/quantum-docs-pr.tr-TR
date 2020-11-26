---
uid: Microsoft.Quantum.Characterization.ContinuousPhaseEstimationIteration
title: ContinuousPhaseEstimationIteration işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: ContinuousPhaseEstimationIteration
qsharp.summary: Performs a single iteration of an iterative (classically-controlled) phase estimation algorithm using arbitrary real powers of a unitary oracle.
ms.openlocfilehash: 3c0f6cf084311598346b25dd7028e290946cd87f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216294"
---
# <a name="continuousphaseestimationiteration-operation"></a>ContinuousPhaseEstimationIteration işlemi

Ad alanı: [Microsoft. hisse. karakterleştirme](xref:Microsoft.Quantum.Characterization)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir Unitary Oracle 'ın rastgele gerçek üslerinin kullanıldığı yinelemeli (sınıflı kontrollü) bir aşama tahmini algoritması için tek bir yineleme gerçekleştirir.

```qsharp
operation ContinuousPhaseEstimationIteration (oracle : Microsoft.Quantum.Oracles.ContinuousOracle, time : Double, theta : Double, targetState : Qubit[], controlQubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a>Giriş

### <a name="oracle--continuousoracle"></a>Oracle: [ContinuousOracle](xref:Microsoft.Quantum.Oracles.ContinuousOracle)

$U $, aşaması tahmin edilecek olan Unitary ve $t $, Oracle 'a verilen tamsayı gücü olduğu için, bir çift $t $ ve bir $U yazmaç üzerinde işlem gören işlem.


### <a name="time--double"></a>zaman: [Double](xref:microsoft.quantum.lang-ref.double)

Verilen Unitary Oracle 'ın kaç kez uygulanacağını.


### <a name="theta--double"></a>Teta: [Double](xref:microsoft.quantum.lang-ref.double)

Hedef durum üzerinde işlem yapmadan önce denetim qubit üzerindeki aşamanın tersine çevirmek için kullanılacak açı.


### <a name="targetstate--qubit"></a>targetState: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Verilen Unitary Oracle tarafından üzerinde işlem yapılan durum kaydı.


### <a name="controlqubit--qubit"></a>controlQubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)





## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)

