---
uid: Microsoft.Quantum.Simulation.IntsToPaulis
title: IntsToPaulis işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IntsToPaulis
qsharp.summary: Converts an array of integers to an array of single-qubit Pauli operators.
ms.openlocfilehash: 2333dcbd2988480e2b2b9b217b26705f3578de00
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230540"
---
# <a name="intstopaulis-function"></a>IntsToPaulis işlevi

Ad alanı: [Microsoft. hisse. benzetim](xref:Microsoft.Quantum.Simulation)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir tamsayılar dizisini tek qubit Pauli işleçleri dizisine dönüştürür.

```qsharp
function IntsToPaulis (ints : Int[]) : Pauli[]
```


## <a name="input"></a>Giriş

### <a name="ints--int"></a>litre: [Int](xref:microsoft.quantum.lang-ref.int)[]

`0..3`Pauli işleçlerine dönüştürülecek aralıktaki tamsayılar dizisi.



## <a name="output--pauli"></a>Çıkış: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

`paulis`Pauli işleçlerinin bir dizisi `Pauli[]` , `ints` `paulis[idxPauli]` tarafından verilen öğesine eşit olan şekilde aynı uzunluktadır `[PauliI, PauliX, PauliY, PauliZ]` `ints[idxPauli]` .