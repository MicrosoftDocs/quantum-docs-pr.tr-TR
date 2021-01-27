---
uid: Microsoft.Quantum.Canon.ApplyToFirstThreeQubits
title: ApplyToFirstThreeQubits işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstThreeQubits
qsharp.summary: Applies an operation to the first three qubits in the register.
ms.openlocfilehash: b01c1072306cfdebcb90827a14683a32312481fc
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850696"
---
# <a name="applytofirstthreequbits-operation"></a>ApplyToFirstThreeQubits işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Kayıttaki ilk üç qubit 'e bir işlem uygular.

```qsharp
operation ApplyToFirstThreeQubits (op : ((Qubit, Qubit, Qubit) => Unit), register : Qubit[]) : Unit
```


## <a name="input"></a>Giriş

### <a name="op--qubitqubitqubit--unit"></a>Op: ([qubit](xref:microsoft.quantum.lang-ref.qubit),[qubit](xref:microsoft.quantum.lang-ref.qubit),[qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit) 

İlk üç qubit 'e uygulanacak bir işlem


### <a name="register--qubit"></a>kaydol: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

İşlemin uygulandığı ilk üç qubit için qubit dizisi.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Açıklamalar

Bu eşdeğerdir:

```qsharp
op(register[0], register[1], register[2]);
```

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Canon. ApplyToFirstThreeQubitsC](xref:Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsC)
- [Microsoft. hisse. Canon. ApplyToFirstThreeQubitsA](xref:Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsA)
- [Microsoft. hisse. Canon. ApplyToFirstThreeQubitsCA](xref:Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsCA)