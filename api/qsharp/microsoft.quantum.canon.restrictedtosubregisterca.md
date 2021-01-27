---
uid: Microsoft.Quantum.Canon.RestrictedToSubregisterCA
title: Kısıttedtosubregisterca işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RestrictedToSubregisterCA
qsharp.summary: Restricts an operation to an array of indices of a register, i.e., a subregister. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: 9b1c8a6d1c843fb0533af16aafc4b3ca2ba2f0e2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852183"
---
# <a name="restrictedtosubregisterca-function"></a>Kısıttedtosubregisterca işlevi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir işlemi, bir kaydın dizin dizini (örneğin, alt kayıt) ile kısıtlar.
Değiştirici, `CA` işlemin denetlenebilir ve adjointable olduğunu gösterir.

```qsharp
function RestrictedToSubregisterCA (op : (Qubit[] => Unit is Adj + Ctl), idxs : Int[]) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a>Giriş

### <a name="op--qubit--unit--is-adj--ctl"></a>Op: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [birimi](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL

Bir alt kayıt ile kısıtlanması için işlem.


### <a name="idxs--int"></a>ıdxs: [Int](xref:microsoft.quantum.lang-ref.int)[]

İşlemin hangi qubits 'e kısıtlanacağını gösteren dizin dizisi.



## <a name="output--qubit--unit--is-adj--ctl"></a>Output: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [birimi](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL



## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Canon. kısıtlayıcı Tedtosubregister](xref:Microsoft.Quantum.Canon.RestrictedToSubregister)