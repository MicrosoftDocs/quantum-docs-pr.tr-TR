---
uid: Microsoft.Quantum.MachineLearning.PartialRotationsLayer
title: PartialRotationsLayer işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: PartialRotationsLayer
qsharp.summary: Returns an array of single-qubit rotations along a given axis, parameterized by distinct model parameters.
ms.openlocfilehash: ab964d2c43a13a5daf64aefdeccd1c26cd371ff4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732322"
---
# <a name="partialrotationslayer-function"></a>PartialRotationsLayer işlevi

Ad alanı: [Microsoft. hisse. Machinöğrenim](xref:Microsoft.Quantum.MachineLearning)

Leyebilir [](https://nuget.org/packages/)


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