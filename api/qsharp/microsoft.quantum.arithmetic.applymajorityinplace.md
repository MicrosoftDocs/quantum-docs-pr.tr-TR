---
uid: Microsoft.Quantum.Arithmetic.ApplyMajorityInPlace
title: Applymajorityınplace işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyMajorityInPlace
qsharp.summary: Applies the three-qubit majority operation in-place on a register of qubits.
ms.openlocfilehash: 3664ffe96cd1db8cf5e8898387fe7f2d45b4ea98
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731834"
---
# <a name="applymajorityinplace-operation"></a>Applymajorityınplace işlemi

Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)

Leyebilir [](https://nuget.org/packages/)


Qubits 'in bir kaydındaki üç qubit çoğunluk işlemini yerinde uygular.

```qsharp
operation ApplyMajorityInPlace (output : Qubit, input : Qubit[]) : Unit
```


## <a name="description"></a>Açıklama

Bu işlem çoğunluk fonksiyonunu 3 qubit üzerinde yerinde hesaplar.

Çıkış qubit $z $ ve giriş qubitleri $x $ ve $y $ olarak belirtirseniz, işlem şu dönüşümü gerçekleştirir: $ \ket{xyz} \sağtarrow \ket{x \oplus z} \ket{y \ OPLUS z} \ket{\operatorname{MAJ} (x, y, z)} $.

## <a name="input"></a>Giriş

### <a name="output--qubit"></a>Çıkış: [qubit](xref:microsoft.quantum.lang-ref.qubit)

İlk giriş qubit. Çıktının yerinde hesaplandığına ve bu qubit 'de depolandığını unutmayın.


### <a name="input--qubit"></a>Giriş: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

İkinci ve üçüncü giriş qubit.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)

