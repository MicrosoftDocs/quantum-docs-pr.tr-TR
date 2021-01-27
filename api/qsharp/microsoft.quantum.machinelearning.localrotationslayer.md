---
uid: Microsoft.Quantum.MachineLearning.LocalRotationsLayer
title: LocalRotationsLayer işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: LocalRotationsLayer
qsharp.summary: Returns an array of uncontrolled (single-qubit) rotations along a given axis, with one rotation for each qubit in a register, parameterized by distinct model parameters.
ms.openlocfilehash: a3658bbf62068c9eea2d9b763cbff5596f426135
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854987"
---
# <a name="localrotationslayer-function"></a>LocalRotationsLayer işlevi

Ad alanı: [Microsoft. hisse. Machinöğrenim](xref:Microsoft.Quantum.MachineLearning)

Paket: [Microsoft. hisse. Machine-öğrenim](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Bir kayıttaki her bir qubit için tek bir dönüşle, ayrı model parametrelerine göre parametrelendirilmiş bir, denetlenmeyen (tek qubit) döndürmeler dizisini döndürür.

```qsharp
function LocalRotationsLayer (nQubits : Int, axis : Pauli) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a>Giriş

### <a name="nqubits--int"></a>nQubits: [Int](xref:microsoft.quantum.lang-ref.int)

Verilen katman tarafından üzerinde işlem yapılan qubits sayısı.


### <a name="axis--pauli"></a>eksen: [Pauli](xref:microsoft.quantum.lang-ref.pauli)

Verilen katmandaki her bir döndürme için döndürme ekseni.



## <a name="output--controlledrotation"></a>Çıkış: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]

Her bir qubit üzerinde bir tane olmak üzere, verilen eksen hakkında kontrollü bir dizin dizisi `nQubits` .