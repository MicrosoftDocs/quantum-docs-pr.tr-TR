---
uid: Microsoft.Quantum.Simulation.AdiabaticStateEnergyUnitary
title: AdiabaticStateEnergyUnitary işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: AdiabaticStateEnergyUnitary
qsharp.summary: Performs state preparation by applying a `statePrepUnitary` on the input state, followed by adiabatic state preparation using a `adiabaticUnitary`, and finally phase estimation with respect to `qpeUnitary`on the resulting state using a `phaseEstAlgorithm`.
ms.openlocfilehash: 642f6a0af76b3b2d0703f0377c379abf33ecee71
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732514"
---
# <a name="adiabaticstateenergyunitary-operation"></a>AdiabaticStateEnergyUnitary işlemi

Ad alanı: [Microsoft. hisse. benzetim](xref:Microsoft.Quantum.Simulation)

Leyebilir [](https://nuget.org/packages/)


Giriş durumuna uygulayarak durum hazırlama işlemini gerçekleştirir ve sonuç olarak bir ile bir `statePrepUnitary` `adiabaticUnitary` , son aşama tahmini kullanarak, bir, ve son derece tahmini kullanarak bir, ve son aşama tahmini kullanın `qpeUnitary` `phaseEstAlgorithm` .

```qsharp
operation AdiabaticStateEnergyUnitary (statePrepUnitary : (Qubit[] => Unit), adiabaticUnitary : (Qubit[] => Unit), qpeUnitary : (Qubit[] => Unit is Adj + Ctl), phaseEstAlgorithm : ((Microsoft.Quantum.Oracles.DiscreteOracle, Qubit[]) => Double), qubits : Qubit[]) : Double
```


## <a name="input"></a>Giriş

### <a name="stateprepunitary--qubit--unit"></a>statePrepUnitary: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [birim](xref:microsoft.quantum.lang-ref.unit) 

İlk dinamik oluşturucusunun durum hazırlanmasını temsil eden bir Oracle.


### <a name="adiabaticunitary--qubit--unit"></a>adiabaticUnitary: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [birim](xref:microsoft.quantum.lang-ref.unit) 

En iyi EPS 'yi algoritmanın son durumuna uygulamak için kullanılacak Adiabatik evsel algoritmayı temsil eden bir Oracle.


### <a name="qpeunitary--qubit--unit-adj--ctl"></a>qpeUnitary: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [birim](xref:microsoft.quantum.lang-ref.unit) ayarlama ve CTL

Bir Unitary işlecini temsil eden bir Oracle $U $ \ma{\phi} $ ve taban durumu enerji $E = \fi \\ , \ Delta t $ ile bir dinamik üreticisi altında


### <a name="phaseestalgorithm--discreteoraclequbit--double"></a>phaseEstAlgorithm: ([DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Double](xref:microsoft.quantum.lang-ref.double) 

Belirli bir Unitary işleminde aşama tahmini gerçekleştiren bir işlem.
Daha fazla ayrıntı için bkz. [yinelemeli aşama tahmini](/quantum/libraries/characterization#iterative-phase-estimation) .


### <a name="qubits--qubit"></a>qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Simülasyonu gerçekleştirmek için kullanılacak qubit kaydı.



## <a name="output--double"></a>Çıkış: [Double](xref:microsoft.quantum.lang-ref.double)

$U $ tarafından temsil edilen oluşturucunun zemin devlet enerji $ \phi $ tahmini $ \hat{\phi} $.