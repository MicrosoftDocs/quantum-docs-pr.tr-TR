---
uid: Microsoft.Quantum.Canon.RestrictedToSubregisterC
title: Kısıttedtosubregisterc işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RestrictedToSubregisterC
qsharp.summary: Restricts an operation to an array of indices of a register, i.e., a subregister. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: 2ca32cf8c85f33f498a30f71833b3dd69db6da6e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728418"
---
# <a name="restrictedtosubregisterc-function"></a>Kısıttedtosubregisterc işlevi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Leyebilir [](https://nuget.org/packages/)


Bir işlemi, bir kaydın dizin dizini (örneğin, alt kayıt) ile kısıtlar.
Değiştirici, `C` işlemin denetlenebilir olduğunu gösterir.

```qsharp
function RestrictedToSubregisterC (op : (Qubit[] => Unit is Ctl), idxs : Int[]) : (Qubit[] => Unit is Ctl)
```


## <a name="input"></a>Giriş

### <a name="op--qubit--unit-ctl"></a>Op: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [birim](xref:microsoft.quantum.lang-ref.unit) CTL

Bir alt kayıt ile kısıtlanması için işlem.


### <a name="idxs--int"></a>ıdxs: [Int](xref:microsoft.quantum.lang-ref.int)[]

İşlemin hangi qubits 'e kısıtlanacağını gösteren dizin dizisi.



## <a name="output--qubit--unit-ctl"></a>Output: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [birim](xref:microsoft.quantum.lang-ref.unit) CTL



## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Canon. kısıtlayıcı Tedtosubregister](xref:Microsoft.Quantum.Canon.RestrictedToSubregister)