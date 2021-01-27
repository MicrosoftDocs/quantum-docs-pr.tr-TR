---
uid: Microsoft.Quantum.Canon.ApplyToSubregisterC
title: ApplyToSubregisterC işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToSubregisterC
qsharp.summary: Applies an operation to a subregister of a register, with qubits specified by an array of their indices. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: 52564e64d8cc9cdbeb2626ed8694168b8ed48c22
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850455"
---
# <a name="applytosubregisterc-operation"></a>ApplyToSubregisterC işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir kaydın alt kaydına bir işlem uygular, bu, dizinlerinin bir dizisi tarafından belirtilen qubits ile.
Değiştirici, `C` işlemin denetlenebilir olduğunu gösterir.

```qsharp
operation ApplyToSubregisterC (op : (Qubit[] => Unit is Ctl), idxs : Int[], target : Qubit[]) : Unit is Ctl
```


## <a name="input"></a>Giriş

### <a name="op--qubit--unit--is-ctl"></a>Op: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [birim](xref:microsoft.quantum.lang-ref.unit)  CTL

Alt kayda uygulanacak işlem.


### <a name="idxs--int"></a>ıdxs: [Int](xref:microsoft.quantum.lang-ref.int)[]

İşlemin hangi qubits uygulanacağını gösteren dizin dizisi.


### <a name="target--qubit"></a>Hedef: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

İşlemin işlem gördüğü kayıt.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Canon. ApplyToSubregister](xref:Microsoft.Quantum.Canon.ApplyToSubregister)