---
uid: Microsoft.Quantum.Canon.ApplyMultiplyControlledLowDepthAnd
title: ApplyMultiplyControlledLowDepthAnd işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiplyControlledLowDepthAnd
qsharp.summary: Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.  The adjoint operation assumes that the target qubit will be reset to 0.  Requires a Rz depth of 1, while the number of helper qubits are exponential in the number of qubits.
ms.openlocfilehash: 0ad4b6eabcbbb63751489dd92a13a6673c1ae6b1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841668"
---
# <a name="applymultiplycontrolledlowdepthand-operation"></a>ApplyMultiplyControlledLowDepthAnd işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


, Hedef qubitin 0 olarak başlatıldığını varsayarak, birden çok kontrollü bir Toffoli kapısı uygular.  Adjoint işlemi, hedef qubitin 0 olarak sıfırlanacağı varsayılır.  RZ derinliğine sahip olmak için 1, yardımcı qubit sayısı, qubit sayısında üstel olmalıdır.

```qsharp
operation ApplyMultiplyControlledLowDepthAnd (controls : Qubit[], target : Qubit) : Unit is Adj
```


## <a name="input"></a>Giriş

### <a name="controls--qubit"></a>denetimler: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Denetim qubits


### <a name="target--qubit"></a>Hedef: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Hedef qubit



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)

