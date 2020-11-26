---
uid: Microsoft.Quantum.MachineLearning.PartialRotationsLayer
title: PartialRotationsLayer işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: PartialRotationsLayer
qsharp.summary: Returns an array of single-qubit rotations along a given axis, parameterized by distinct model parameters.
ms.openlocfilehash: ade0640b07f633982e98d5d02239fa205909bcce
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196251"
---
# <a name="partialrotationslayer-function"></a>PartialRotationsLayer işlevi

Ad alanı: [Microsoft. hisse. Machinöğrenim](xref:Microsoft.Quantum.MachineLearning)

Paket: [Microsoft. hisse. Machine-öğrenim](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Ayrı model parametrelerine göre parametreli, belirli bir eksen üzerinde tek qubit döndürmelerdeki oluşan bir dizi döndürür.

```qsharp
function PartialRotationsLayer (idxsQubits : Int[], axis : Pauli) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a>Giriş

### <a name="idxsqubits--int"></a>ıdxsqubits: [Int](xref:microsoft.quantum.lang-ref.int)[]

Her döndürme için hedef olarak kullanılacak qubits dizinleri.


### <a name="axis--pauli"></a>eksen: [Pauli](xref:microsoft.quantum.lang-ref.pauli)

Verilen katmandaki her bir döndürme için döndürme ekseni.



## <a name="output--controlledrotation"></a>Çıkış: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]

Her bir qubit üzerinde bir tane olmak üzere, verilen eksen hakkında kontrollü bir dizin dizisi `nQubits` .