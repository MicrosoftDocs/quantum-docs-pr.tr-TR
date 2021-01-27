---
uid: Microsoft.Quantum.Characterization.ContinuousPhaseEstimationIteration
title: ContinuousPhaseEstimationIteration işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: ContinuousPhaseEstimationIteration
qsharp.summary: Performs a single iteration of an iterative (classically-controlled) phase estimation algorithm using arbitrary real powers of a unitary oracle.
ms.openlocfilehash: 925b9040f6d9cda074b18a6f9079ccb653f9fa98
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851903"
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

