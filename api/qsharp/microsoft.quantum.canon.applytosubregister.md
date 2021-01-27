---
uid: Microsoft.Quantum.Canon.ApplyToSubregister
title: ApplyToSubregister işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToSubregister
qsharp.summary: Applies an operation to a subregister of a register, with qubits specified by an array of their indices.
ms.openlocfilehash: be820c87ee19230713d6c3e5681bbe3678040e95
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850480"
---
# <a name="applytosubregister-operation"></a>ApplyToSubregister işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir kaydın alt kaydına bir işlem uygular, bu, dizinlerinin bir dizisi tarafından belirtilen qubits ile.

```qsharp
operation ApplyToSubregister (op : (Qubit[] => Unit), idxs : Int[], target : Qubit[]) : Unit
```


## <a name="input"></a>Giriş

### <a name="op--qubit--unit"></a>Op: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [birim](xref:microsoft.quantum.lang-ref.unit) 

Alt kayda uygulanacak işlem.


### <a name="idxs--int"></a>ıdxs: [Int](xref:microsoft.quantum.lang-ref.int)[]

İşlemin hangi qubits uygulanacağını gösteren dizin dizisi.


### <a name="target--qubit"></a>Hedef: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

İşlemin işlem gördüğü kayıt.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="example"></a>Örnek

Üç qubit durumu $ \frac {1} {\sqrt {2} } \ket {0} \_ 2 (\demet {0} \_ 1 \ ayraç {0} _3 + \ demet {1} \_ 1 \ ayraç {1} _3) $:

```qsharp
    using (register = Qubit[3]) {
        ApplyToSubregister(Exp([PauliX,PauliY],PI() / 4.0,_), [1,3], register);
    }
```

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Canon. ApplyToSubregisterA](xref:Microsoft.Quantum.Canon.ApplyToSubregisterA)
- [Microsoft. hisse. Canon. ApplyToSubregisterC](xref:Microsoft.Quantum.Canon.ApplyToSubregisterC)
- [Microsoft. hisse. Canon. ApplyToSubregisterCA](xref:Microsoft.Quantum.Canon.ApplyToSubregisterCA)