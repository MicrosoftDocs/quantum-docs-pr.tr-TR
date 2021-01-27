---
uid: Microsoft.Quantum.Research.Chemistry.JWOptimizedFermionEvolutionFunction
title: Jwoptimizedfermıonevolutionfunction işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: JWOptimizedFermionEvolutionFunction
qsharp.summary: Represents a dynamical generator as a set of simulatable gates and an expansion in the JWOptimized basis.
ms.openlocfilehash: d70bea8fcb5bd82ddad6dcd2b67c3eb178283bb3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857874"
---
# <a name="jwoptimizedfermionevolutionfunction-function"></a>Jwoptimizedfermıonevolutionfunction işlevi

Ad alanı: [Microsoft. hisse. Research. Chemistry](xref:Microsoft.Quantum.Research.Chemistry)

Paket: [Microsoft. hisse. Research. Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)


Bir dinamik üreticisini bir simulatable Gates kümesi ve jwoptimize temelinde bir genişletme olarak temsil eder.

```qsharp
function JWOptimizedFermionEvolutionFunction (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex, parityQubit : Qubit) : Microsoft.Quantum.Simulation.EvolutionUnitary
```


## <a name="input"></a>Giriş

### <a name="generatorindex--generatorindex"></a>Generatorındex: [Generatorındex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

Jwoptimize temelinde Unitary evrimi olarak temsil edilecek bir Oluşturucu dizin.


### <a name="parityqubit--qubit"></a>parityQubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Zaman evrimi 'nin işaretini belirleyen qubit.



## <a name="output--evolutionunitary"></a>Çıkış: [Evolutionunitary](xref:Microsoft.Quantum.Simulation.EvolutionUnitary)

`EvolutionUnitary`' Generatorındex ' içinde başvurulan terime göre zaman gelişini temsil eden bir.