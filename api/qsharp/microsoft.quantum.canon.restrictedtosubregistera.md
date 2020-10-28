---
uid: Microsoft.Quantum.Canon.RestrictedToSubregisterA
title: Kısıttedtosubregistera işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RestrictedToSubregisterA
qsharp.summary: Restricts an operation to an array of indices of a register, i.e., a subregister. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: d45c43caed35df8fb89d9d38e540faf5a21ea064
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728429"
---
# <a name="restrictedtosubregistera-function"></a>Kısıttedtosubregistera işlevi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Leyebilir [](https://nuget.org/packages/)


Bir işlemi, bir kaydın dizin dizini (örneğin, alt kayıt) ile kısıtlar.
Değiştirici, `A` işlemin adjointable olduğunu gösterir.

```qsharp
function RestrictedToSubregisterA (op : (Qubit[] => Unit is Adj), idxs : Int[]) : (Qubit[] => Unit is Adj)
```


## <a name="input"></a>Giriş

### <a name="op--qubit--unit-adj"></a>Op: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [birim](xref:microsoft.quantum.lang-ref.unit) ayarlama

Bir alt kayıt ile kısıtlanması için işlem.


### <a name="idxs--int"></a>ıdxs: [Int](xref:microsoft.quantum.lang-ref.int)[]

İşlemin hangi qubits 'e kısıtlanacağını gösteren dizin dizisi.



## <a name="output--qubit--unit-adj"></a>Output: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [birim](xref:microsoft.quantum.lang-ref.unit) ayarlama



## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Canon. kısıtlayıcı Tedtosubregister](xref:Microsoft.Quantum.Canon.RestrictedToSubregister)