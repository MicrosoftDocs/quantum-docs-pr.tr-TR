---
uid: Microsoft.Quantum.Simulation.PauliStringFromGenIdx
title: PauliStringFromGenIdx işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliStringFromGenIdx
qsharp.summary: Extracts the Pauli string and its qubit indices of a Pauli term described by a `GeneratorIndex`.
ms.openlocfilehash: 33da4bc3d7e58b87aef75b453b6af09a51214923
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726288"
---
# <a name="paulistringfromgenidx-function"></a>PauliStringFromGenIdx işlevi

Ad alanı: [Microsoft. hisse. benzetim](xref:Microsoft.Quantum.Simulation)

Leyebilir [](https://nuget.org/packages/)


Pauli dizesini ve tarafından tanımlanan Pauli teriminin qubit dizinlerini ayıklar `GeneratorIndex` .

```qsharp
function PauliStringFromGenIdx (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex) : (Pauli[], Int[])
```


## <a name="input"></a>Giriş

### <a name="generatorindex--generatorindex"></a>Generatorındex: [Generatorındex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

`GeneratorIndex` Pauli terimini kodlayan tür.



## <a name="output--pauliint"></a>Çıkış: ([Pauli](xref:microsoft.quantum.lang-ref.pauli)[],[Int](xref:microsoft.quantum.lang-ref.int)[])

Tarafından açıklanan terimin Pauli dizesi `GeneratorIndex` ve üzerinde hareket eden qubits dizinleri.