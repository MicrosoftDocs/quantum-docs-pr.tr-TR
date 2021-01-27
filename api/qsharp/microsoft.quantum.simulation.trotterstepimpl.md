---
uid: Microsoft.Quantum.Simulation.TrotterStepImpl
title: Troesstepımpl işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TrotterStepImpl
qsharp.summary: Implements time-evolution by a term contained in a `GeneratorSystem`.
ms.openlocfilehash: 33dc922cd5a60590a1306369fb99615fc6575b22
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856723"
---
# <a name="trotterstepimpl-operation"></a>Troesstepımpl işlemi

Ad alanı: [Microsoft. hisse. benzetim](xref:Microsoft.Quantum.Simulation)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


, İçinde bulunan bir terim ile zaman gelişimini uygular `GeneratorSystem` .

```qsharp
operation TrotterStepImpl (evolutionGenerator : Microsoft.Quantum.Simulation.EvolutionGenerator, idx : Int, stepsize : Double, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Giriş

### <a name="evolutiongenerator--evolutiongenerator"></a>evolutionGenerator: [Evolutiongenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)

Benzetim yapılacak sistemin tüm açıklaması.


### <a name="idx--int"></a>idx: [Int](xref:microsoft.quantum.lang-ref.int)

Tanımlanan sistemdeki bir terimin tamsayı dizini.


### <a name="stepsize--double"></a>stepSize: [Double](xref:microsoft.quantum.lang-ref.double)

Tarafından dizin oluşturulan, terim süresi boyunca çarpan `idx` .


### <a name="qubits--qubit"></a>qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Bu, simülasyonu tarafından üzerinde işlem yaptığı.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)

