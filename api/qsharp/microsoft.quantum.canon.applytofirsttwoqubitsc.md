---
uid: Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsC
title: ApplyToFirstTwoQubitsC işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstTwoQubitsC
qsharp.summary: Applies an operation to the first two qubits in the register. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: 6b6ee5f05ace92c15ce2038e2fedbaa2fee3dcc9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217365"
---
# <a name="applytofirsttwoqubitsc-operation"></a>ApplyToFirstTwoQubitsC işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Kayıttaki ilk iki qubit 'e bir işlem uygular.
Değiştirici, `C` işlemin denetlenebilir olduğunu gösterir.

```qsharp
operation ApplyToFirstTwoQubitsC (op : ((Qubit, Qubit) => Unit is Ctl), register : Qubit[]) : Unit is Ctl
```


## <a name="input"></a>Giriş

### <a name="op--qubitqubit--unit--is-ctl"></a>Op: ([qubit](xref:microsoft.quantum.lang-ref.qubit),[qubit](xref:microsoft.quantum.lang-ref.qubit)) => [birimi](xref:microsoft.quantum.lang-ref.unit)  CTL

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