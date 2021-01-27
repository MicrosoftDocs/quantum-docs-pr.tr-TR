---
uid: Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsCA
title: ApplyToFirstTwoQubitsCA işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstTwoQubitsCA
qsharp.summary: Applies an operation to the first two qubits in the register. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: 5bea9ec1be1fc379823877684c81e99f86807d89
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850656"
---
# <a name="applytofirsttwoqubitsca-operation"></a>ApplyToFirstTwoQubitsCA işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Kayıttaki ilk iki qubit 'e bir işlem uygular.
Değiştirici, `CA` işlemin denetlenebilir ve adjointable olduğunu gösterir.

```qsharp
operation ApplyToFirstTwoQubitsCA (op : ((Qubit, Qubit) => Unit is Adj + Ctl), register : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Giriş

### <a name="op--qubitqubit--unit--is-adj--ctl"></a>Op: ([qubit](xref:microsoft.quantum.lang-ref.qubit),[qubit](xref:microsoft.quantum.lang-ref.qubit)) => [birimi](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL

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

- [Microsoft. hisse. Canon. ApplyToFirstTwoQubits](xref:Microsoft.Quantum.Canon.ApplyToFirstTwoQubits)