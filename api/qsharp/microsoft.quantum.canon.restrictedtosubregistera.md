---
uid: Microsoft.Quantum.Canon.RestrictedToSubregisterA
title: Kısıttedtosubregistera işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RestrictedToSubregisterA
qsharp.summary: Restricts an operation to an array of indices of a register, i.e., a subregister. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: c260a0e422d7ffb8137f6ac41e1cb398b2f4a2a7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852191"
---
# <a name="restrictedtosubregistera-function"></a>Kısıttedtosubregistera işlevi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir işlemi, bir kaydın dizin dizini (örneğin, alt kayıt) ile kısıtlar.
Değiştirici, `A` işlemin adjointable olduğunu gösterir.

```qsharp
function RestrictedToSubregisterA (op : (Qubit[] => Unit is Adj), idxs : Int[]) : (Qubit[] => Unit is Adj)
```


## <a name="input"></a>Giriş

### <a name="op--qubit--unit--is-adj"></a>Op: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [birimi](xref:microsoft.quantum.lang-ref.unit)  sıfatı

Bir alt kayıt ile kısıtlanması için işlem.


### <a name="idxs--int"></a>ıdxs: [Int](xref:microsoft.quantum.lang-ref.int)[]

İşlemin hangi qubits 'e kısıtlanacağını gösteren dizin dizisi.



## <a name="output--qubit--unit--is-adj"></a>Output: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [birimi](xref:microsoft.quantum.lang-ref.unit)  sıfatı



## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Canon. kısıtlayıcı Tedtosubregister](xref:Microsoft.Quantum.Canon.RestrictedToSubregister)