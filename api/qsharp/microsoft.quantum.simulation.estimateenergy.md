---
uid: Microsoft.Quantum.Simulation.EstimateEnergy
title: Estimateenerji işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: EstimateEnergy
qsharp.summary: Performs state preparation by applying a `statePrepUnitary` on an automatically allocated input state phase estimation with respect to `qpeUnitary`on the resulting state using a `phaseEstAlgorithm`.
ms.openlocfilehash: f9243557718e12d168afadbf641492291afd1704
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856760"
---
# <a name="estimateenergy-operation"></a>Estimateenerji işlemi

Ad alanı: [Microsoft. hisse. benzetim](xref:Microsoft.Quantum.Simulation)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


`statePrepUnitary`, `qpeUnitary` İle elde edilen duruma göre otomatik olarak ayrılmış bir giriş durumu aşaması tahmini temelinde bir durum hazırlığı gerçekleştirir `phaseEstAlgorithm` .

```qsharp
operation EstimateEnergy (nQubits : Int, statePrepUnitary : (Qubit[] => Unit), qpeUnitary : (Qubit[] => Unit is Adj + Ctl), phaseEstAlgorithm : ((Microsoft.Quantum.Oracles.DiscreteOracle, Qubit[]) => Double)) : Double
```


## <a name="input"></a>Giriş

### <a name="nqubits--int"></a>nQubits: [Int](xref:microsoft.quantum.lang-ref.int)

Simülasyonu gerçekleştirmek için kullanılan qubits sayısı.


### <a name="stateprepunitary--qubit--unit"></a>statePrepUnitary: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [birim](xref:microsoft.quantum.lang-ref.unit) 

İlk dinamik oluşturucusunun durum hazırlanmasını temsil eden bir Oracle.


### <a name="qpeunitary--qubit--unit--is-adj--ctl"></a>qpeUnitary: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [birim](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL

Bir Unitary işlecini temsil eden bir Oracle $U $ \ma{\phi} $ ve taban durumu enerji $E = \fi \\ , \ Delta t $ ile bir dinamik üreticisi altında


### <a name="phaseestalgorithm--discreteoraclequbit--double"></a>phaseEstAlgorithm: ([DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Double](xref:microsoft.quantum.lang-ref.double) 

Belirli bir Unitary işleminde aşama tahmini gerçekleştiren bir işlem.
Daha fazla ayrıntı için bkz. [yinelemeli aşama tahmini](/quantum/libraries/characterization#iterative-phase-estimation) .



## <a name="output--double"></a>Çıkış: [Double](xref:microsoft.quantum.lang-ref.double)

$U $ tarafından temsil edilen oluşturucunun zemin devlet enerjisi 'nin zemin devlet enerji $ \phi $ \hat{\phi} $.