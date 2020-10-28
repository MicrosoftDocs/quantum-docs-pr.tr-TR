---
uid: Microsoft.Quantum.Simulation.PauliEvolutionImpl
title: Paulievolutionımpl işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliEvolutionImpl
qsharp.summary: >-
  Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.

  See [Dynamical Generator Modeling](/quantum/libraries/data-structures#dynamical-generator-modeling) for more details.
ms.openlocfilehash: 2fc9fda2dd6eec71d8b17ba8a00d8545e517eec8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730906"
---
# <a name="paulievolutionimpl-operation"></a>Paulievolutionımpl işlemi

Ad alanı: [Microsoft. hisse. benzetim](xref:Microsoft.Quantum.Simulation)

Leyebilir [](https://nuget.org/packages/)


Bir dinamik üreticisini bir simulatable Gates kümesi ve Pauli temelinde genişletme olarak temsil eder.

Daha fazla ayrıntı için bkz. [Dynamical Oluşturucu modelleme](/quantum/libraries/data-structures#dynamical-generator-modeling) .

```qsharp
operation PauliEvolutionImpl (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex, delta : Double, qubits : Qubit[]) : Unit
```


## <a name="input"></a>Giriş

### <a name="generatorindex--generatorindex"></a>Generatorındex: [Generatorındex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

Pauli temelinde Unitary evrimi olarak temsil edilecek bir Oluşturucu dizini.


### <a name="delta--double"></a>Delta: [Double](xref:microsoft.quantum.lang-ref.double)

' De başvurulan terime göre geçen süre için bir çarpan `generatorIndex` .


### <a name="qubits--qubit"></a>qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Zaman-gelişme işlecinden sonra kayıt yapılır.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)

