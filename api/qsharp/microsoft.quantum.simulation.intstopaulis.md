---
uid: Microsoft.Quantum.Simulation.IntsToPaulis
title: IntsToPaulis işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IntsToPaulis
qsharp.summary: Converts an array of integers to an array of single-qubit Pauli operators.
ms.openlocfilehash: 605257aa7ca39e457127e3c3459b5891145b1863
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725820"
---
# <a name="intstopaulis-function"></a>IntsToPaulis işlevi

Ad alanı: [Microsoft. hisse. benzetim](xref:Microsoft.Quantum.Simulation)

Leyebilir [](https://nuget.org/packages/)


Bir tamsayılar dizisini tek qubit Pauli işleçleri dizisine dönüştürür.

```qsharp
function IntsToPaulis (ints : Int[]) : Pauli[]
```


## <a name="input"></a>Giriş

### <a name="ints--int"></a>litre: [Int](xref:microsoft.quantum.lang-ref.int)[]

`0..3`Pauli işleçlerine dönüştürülecek aralıktaki tamsayılar dizisi.



## <a name="output--pauli"></a>Çıkış: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

`paulis`Pauli işleçlerinin bir dizisi `Pauli[]` , `ints` `paulis[idxPauli]` tarafından verilen öğesine eşit olan şekilde aynı uzunluktadır `[PauliI, PauliX, PauliY, PauliZ]` `ints[idxPauli]` .