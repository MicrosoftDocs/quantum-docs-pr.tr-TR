---
uid: Microsoft.Quantum.MachineLearning.CyclicEntanglingLayer
title: CyclicEntanglingLayer işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: CyclicEntanglingLayer
qsharp.summary: Returns an array of singly controlled rotations along a given axis, arranged cyclically across a register of qubits, and parameterized by distinct model parameters.
ms.openlocfilehash: 6e0f5057b35baefe2677126ba70ee4fddde7d4db
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731111"
---
# <a name="cyclicentanglinglayer-function"></a>CyclicEntanglingLayer işlevi

Ad alanı: [Microsoft. hisse. Machinöğrenim](xref:Microsoft.Quantum.MachineLearning)

Leyebilir [](https://nuget.org/packages/)


Belirli bir eksen boyunca listedir kontrollü nesnelerin bir dizisini döndürür, qubits 'in bir kaydındaki periyodik düzenlenir ve ayrı model parametrelerine göre parametrelenir.

```qsharp
function CyclicEntanglingLayer (nQubits : Int, axis : Pauli, stride : Int) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a>Giriş

### <a name="nqubits--int"></a>nQubits: [Int](xref:microsoft.quantum.lang-ref.int)

Verilen katman tarafından üzerinde işlem yapılan qubits sayısı.


### <a name="axis--pauli"></a>eksen: [Pauli](xref:microsoft.quantum.lang-ref.pauli)

Verilen katmandaki her bir döndürme için döndürme ekseni.


### <a name="stride--int"></a>ilerleme: [Int](xref:microsoft.quantum.lang-ref.int)

Her bir döndürme için hedef ve denetim dizinleri arasındaki ayrım.



## <a name="output--controlledrotation"></a>Çıkış: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]

Qubits 'in bir kaydındaki periyodik bir yerde bulunan iki qubit kontrollü bir döndürme dizisi `nQubits` .