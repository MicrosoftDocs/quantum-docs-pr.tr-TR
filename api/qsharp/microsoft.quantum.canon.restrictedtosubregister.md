---
uid: Microsoft.Quantum.Canon.RestrictedToSubregister
title: Kısıttedtosubregister işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RestrictedToSubregister
qsharp.summary: Restricts an operation to an array of indices of a register, i.e., a subregister.
ms.openlocfilehash: a8b599035de6fede10bdaf8cef17f2124a59f064
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728430"
---
# <a name="restrictedtosubregister-function"></a>Kısıttedtosubregister işlevi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Leyebilir [](https://nuget.org/packages/)


Bir işlemi, bir kaydın dizin dizini (örneğin, alt kayıt) ile kısıtlar.

```qsharp
function RestrictedToSubregister (op : (Qubit[] => Unit), idxs : Int[]) : (Qubit[] => Unit)
```


## <a name="input"></a>Giriş

### <a name="op--qubit--unit"></a>Op: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [birim](xref:microsoft.quantum.lang-ref.unit) 

Bir alt kayıt ile kısıtlanması için işlem.


### <a name="idxs--int"></a>ıdxs: [Int](xref:microsoft.quantum.lang-ref.int)[]

İşlemin hangi qubits 'e kısıtlanacağını gösteren dizin dizisi.



## <a name="output--qubit--unit"></a>Çıkış: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) 



## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Canon. kısıtlayıcı Tedtosubregistera](xref:Microsoft.Quantum.Canon.RestrictedToSubregisterA)
- [Microsoft. hisse. Canon. Kısıttedtosubregisterc](xref:Microsoft.Quantum.Canon.RestrictedToSubregisterC)
- [Microsoft. hisse. Canon. kısıtlayıcı Tedtosubregisterca](xref:Microsoft.Quantum.Canon.RestrictedToSubregisterCA)