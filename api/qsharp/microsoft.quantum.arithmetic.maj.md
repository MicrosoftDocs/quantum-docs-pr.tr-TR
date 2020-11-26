---
uid: Microsoft.Quantum.Arithmetic.MAJ
title: MAJ işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MAJ
qsharp.summary: This applies the in-place majority operation to 3 qubits.
ms.openlocfilehash: 356689baa6d47b7b93a393f3672991bb589f6921
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222771"
---
# <a name="maj-operation"></a>MAJ işlemi

Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bu, yerinde çoğunluk işlemini 3 qubit 'e uygular.

```qsharp
operation MAJ (input0 : Qubit, input1 : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a>Açıklama

Hedef qubit durumunu $ \ket{z} $ olarak belirtirseniz, ve giriş qubits 'in $ \ket{x} $ ve $ \ket{y} $ olarak giriş durumları, bu işlem şu dönüşümü gerçekleştirir: $ \ket{xyz} \estarrow \ket{x \oplus z} \ket{y \oplus z} \ket{\operatorname{MAJ} (x, y, z)} $.

## <a name="input"></a>Giriş

### <a name="input0--qubit"></a>input0: [qubit](xref:microsoft.quantum.lang-ref.qubit)

İlk giriş qubit.


### <a name="input1--qubit"></a>input1: [qubit](xref:microsoft.quantum.lang-ref.qubit)

İkinci giriş qubit.


### <a name="target--qubit"></a>Hedef: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Çoğunluk işlevinin uygulanacağı bir qubit.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)

