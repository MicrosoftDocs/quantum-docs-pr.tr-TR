---
uid: Microsoft.Quantum.Simulation.IntToPauli
title: Inttopauli işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IntToPauli
qsharp.summary: Converts a integer to a single-qubit Pauli operator.
ms.openlocfilehash: f0f1186f14a0dc30bb34bd29f148cdc830fd1337
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733703"
---
# <a name="inttopauli-function"></a>Inttopauli işlevi

Ad alanı: [Microsoft. hisse. benzetim](xref:Microsoft.Quantum.Simulation)

Leyebilir [](https://nuget.org/packages/)


Bir tamsayıyı tek qubit Pauli işlecine dönüştürür.

```qsharp
function IntToPauli (idx : Int) : Pauli
```


## <a name="input"></a>Giriş

### <a name="idx--int"></a>idx: [Int](xref:microsoft.quantum.lang-ref.int)

`0..3`Pauli işleçlerine dönüştürülecek aralıktaki tamsayı.



## <a name="output--pauli"></a>Çıkış: [Pauli](xref:microsoft.quantum.lang-ref.pauli)

`Pauli`Tarafından verilen bir işleç `[PauliI, PauliX, PauliY, PauliZ][idx]` .