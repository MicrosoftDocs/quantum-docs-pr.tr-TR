---
uid: Microsoft.Quantum.Diagnostics.AllowAtMostNQubits
title: AllowAtMostNQubits işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllowAtMostNQubits
qsharp.summary: Between a call to this operation and its adjoint, asserts that at most a given number of additional qubits are allocated with using statements.
ms.openlocfilehash: 5376b6f39d12d664342fbf71e67442c6ef8a0827
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202558"
---
# <a name="allowatmostnqubits-operation"></a>AllowAtMostNQubits işlemi

Ad alanı: [Microsoft. hisse. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bu işleme ve adeklem çağrısı arasında, using deyimleri ile verilen sayıda ek qubit için en fazla bir kaç sayının ayrıldığını onaylar.

```qsharp
operation AllowAtMostNQubits (nQubits : Int, message : String) : Unit is Adj
```


## <a name="input"></a>Giriş

### <a name="nqubits--int"></a>nQubits: [Int](xref:microsoft.quantum.lang-ref.int)

Ayrılabilen en fazla qubit sayısı.


### <a name="message--string"></a>ileti: [dize](xref:microsoft.quantum.lang-ref.string)

Hata durumunda görüntülenecek bir ileti.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Açıklamalar

Bu işlem, onu desteklemeyen hedefler üzerinde bir işleç ile değiştirilebilir.