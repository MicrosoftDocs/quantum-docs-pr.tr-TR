---
uid: Microsoft.Quantum.Arithmetic.MAJ
title: MAJ işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MAJ
qsharp.summary: This applies the in-place majority operation to 3 qubits.
ms.openlocfilehash: c1801d1d7ed04ead11b672f24d44a94989cf8f1d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731447"
---
# <a name="maj-operation"></a>MAJ işlemi

Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)

Leyebilir [](https://nuget.org/packages/)


Bu, yerinde çoğunluk işlemini 3 qubit 'e uygular.

```qsharp
operation MAJ (input0 : Qubit, input1 : Qubit, target : Qubit) : Unit
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

