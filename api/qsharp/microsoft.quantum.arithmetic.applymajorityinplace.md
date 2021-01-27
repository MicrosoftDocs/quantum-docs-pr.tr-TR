---
uid: Microsoft.Quantum.Arithmetic.ApplyMajorityInPlace
title: Applymajorityınplace işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyMajorityInPlace
qsharp.summary: Applies the three-qubit majority operation in-place on a register of qubits.
ms.openlocfilehash: 10b512392b2098663c09b2e07a09c4025da90706
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843721"
---
# <a name="applymajorityinplace-operation"></a>Applymajorityınplace işlemi

Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Qubits 'in bir kaydındaki üç qubit çoğunluk işlemini yerinde uygular.

```qsharp
operation ApplyMajorityInPlace (output : Qubit, input : Qubit[]) : Unit is Adj + Ctl
```


## <a name="description"></a>Description

Bu işlem çoğunluk fonksiyonunu 3 qubit üzerinde yerinde hesaplar.

Çıkış qubit $z $ ve giriş qubitleri $x $ ve $y $ olarak belirtirseniz, işlem şu dönüşümü gerçekleştirir: $ \ket{xyz} \sağtarrow \ket{x \oplus z} \ket{y \ OPLUS z} \ket{\operatorname{MAJ} (x, y, z)} $.

## <a name="input"></a>Giriş

### <a name="output--qubit"></a>Çıkış: [qubit](xref:microsoft.quantum.lang-ref.qubit)

İlk giriş qubit. Çıktının yerinde hesaplandığına ve bu qubit 'de depolandığını unutmayın.


### <a name="input--qubit"></a>Giriş: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

İkinci ve üçüncü giriş qubit.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)

