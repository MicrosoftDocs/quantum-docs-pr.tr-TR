---
uid: Microsoft.Quantum.Simulation.IntToPauli
title: Inttopauli işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IntToPauli
qsharp.summary: Converts a integer to a single-qubit Pauli operator.
ms.openlocfilehash: 76f482b86ff4a27b6e6ce6ae4ec3d59422563f12
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842244"
---
# <a name="inttopauli-function"></a>Inttopauli işlevi

Ad alanı: [Microsoft. hisse. benzetim](xref:Microsoft.Quantum.Simulation)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir tamsayıyı tek qubit Pauli işlecine dönüştürür.

```qsharp
function IntToPauli (idx : Int) : Pauli
```


## <a name="input"></a>Giriş

### <a name="idx--int"></a>idx: [Int](xref:microsoft.quantum.lang-ref.int)

`0..3`Pauli işleçlerine dönüştürülecek aralıktaki tamsayı.



## <a name="output--pauli"></a>Çıkış: [Pauli](xref:microsoft.quantum.lang-ref.pauli)

`Pauli`Tarafından verilen bir işleç `[PauliI, PauliX, PauliY, PauliZ][idx]` .