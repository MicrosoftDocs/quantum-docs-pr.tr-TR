---
uid: Microsoft.Quantum.Canon.ApplyToFirstTwoQubits
title: ApplyToFirstTwoQubits işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstTwoQubits
qsharp.summary: Applies an operation to the first two qubits in the register.
ms.openlocfilehash: e4f1eb396efb390c7470ea2aaf5c3b5be60b8c1b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217416"
---
# <a name="applytofirsttwoqubits-operation"></a>ApplyToFirstTwoQubits işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Kayıttaki ilk iki qubit 'e bir işlem uygular.

```qsharp
operation ApplyToFirstTwoQubits (op : ((Qubit, Qubit) => Unit), register : Qubit[]) : Unit
```


## <a name="input"></a>Giriş

### <a name="op--qubitqubit--unit"></a>Op: ([qubit](xref:microsoft.quantum.lang-ref.qubit),[qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit) 

İlk iki qubit 'e uygulanacak bir işlem


### <a name="register--qubit"></a>kaydol: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

İşlemin uygulandığı ilk iki qubit için qubit dizisi.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Açıklamalar

Bu eşdeğerdir:

```qsharp
op(register[0], register[1]);
```

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Canon. ApplyToFirstTwoQubitsA](xref:Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsA)
- [Microsoft. hisse. Canon. ApplyToFirstTwoQubitsC](xref:Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsC)
- [Microsoft. hisse. Canon. ApplyToFirstTwoQubitsCA](xref:Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsCA)