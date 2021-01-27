---
uid: Microsoft.Quantum.Arithmetic.MAJ
title: MAJ işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MAJ
qsharp.summary: This applies the in-place majority operation to 3 qubits.
ms.openlocfilehash: 68236f1deeb409a01152d4b7e854202a1134314e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846542"
---
# <a name="maj-operation"></a>MAJ işlemi

Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bu, yerinde çoğunluk işlemini 3 qubit 'e uygular.

```qsharp
operation MAJ (input0 : Qubit, input1 : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a>Description

Hedef qubit durumunu $ \ket{z} $ olarak belirtirseniz, ve giriş qubits 'in $ \ket{x} $ ve $ \ket{y} $ olarak giriş durumları, bu işlem şu dönüşümü gerçekleştirir: $ \ket{xyz} \estarrow \ket{x \oplus z} \ket{y \oplus z} \ket{\operatorname{MAJ} (x, y, z)} $.

## <a name="input"></a>Giriş

### <a name="input0--qubit"></a>input0: [qubit](xref:microsoft.quantum.lang-ref.qubit)

İlk giriş qubit.


### <a name="input1--qubit"></a>input1: [qubit](xref:microsoft.quantum.lang-ref.qubit)

İkinci giriş qubit.


### <a name="target--qubit"></a>Hedef: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Çoğunluk işlevinin uygulanacağı bir qubit.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)

