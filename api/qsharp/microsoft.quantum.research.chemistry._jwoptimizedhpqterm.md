---
uid: Microsoft.Quantum.Research.Chemistry._JWOptimizedHpqTerm
title: _JWOptimizedHpqTerm işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _JWOptimizedHpqTerm
qsharp.summary: Applies time-evolution by a PQ term described by a `GeneratorIndex`.
ms.openlocfilehash: b008315ded7cabc085e6d5da8f646e92914bf743
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854806"
---
# <a name="_jwoptimizedhpqterm-operation"></a>_JWOptimizedHpqTerm işlemi

Ad alanı: [Microsoft. hisse. Research. Chemistry](xref:Microsoft.Quantum.Research.Chemistry)

Paket: [Microsoft. hisse. Research. Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)


Tarafından tanımlanan bir PQ terimiyle saat evrimi uygular `GeneratorIndex` .

```qsharp
operation _JWOptimizedHpqTerm (term : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, parityQubit : Qubit, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Giriş

### <a name="term--generatorindex"></a>terim: [Generatorındex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

`GeneratorIndex` PQ terimini temsil eden.


### <a name="stepsize--double"></a>stepSize: [Double](xref:microsoft.quantum.lang-ref.double)

Zaman evrimi süresi.


### <a name="parityqubit--qubit"></a>parityQubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Zaman evrimi 'nin işaretini belirleyen qubit.


### <a name="qubits--qubit"></a>qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Hamiltonian, qubit.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)

