---
uid: Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsA
title: ApplyToFirstThreeQubitsA işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstThreeQubitsA
qsharp.summary: Applies an operation to the first three qubits in the register. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: 7c464b1decb5a30a996dfc1df9f1f1921613c73e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841410"
---
# <a name="applytofirstthreequbitsa-operation"></a>ApplyToFirstThreeQubitsA işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Kayıttaki ilk üç qubit 'e bir işlem uygular.
Değiştirici, `A` işlemin adjointable olduğunu gösterir.

```qsharp
operation ApplyToFirstThreeQubitsA (op : ((Qubit, Qubit, Qubit) => Unit is Adj), register : Qubit[]) : Unit is Adj
```


## <a name="input"></a>Giriş

### <a name="op--qubitqubitqubit--unit--is-adj"></a>Op: ([qubit](xref:microsoft.quantum.lang-ref.qubit),[qubit](xref:microsoft.quantum.lang-ref.qubit),[qubit](xref:microsoft.quantum.lang-ref.qubit)) => [birimi](xref:microsoft.quantum.lang-ref.unit)  sıfatı

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

- [Microsoft. hisse. Canon. ApplyToFirstThreeQubits](xref:Microsoft.Quantum.Canon.ApplyToFirstThreeQubits)