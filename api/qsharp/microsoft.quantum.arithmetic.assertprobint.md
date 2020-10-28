---
uid: Microsoft.Quantum.Arithmetic.AssertProbInt
title: Assertprobınt işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertProbInt
qsharp.summary: Asserts that the probability of a specific state of a quantum register has the expected value.
ms.openlocfilehash: a8e4217e18528adc0aa9923f1c0dcfb59e1d2488
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731679"
---
# <a name="assertprobint-operation"></a>Assertprobınt işlemi

Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)

Leyebilir [](https://nuget.org/packages/)


Bir hisse amacının belirli bir durumunun beklenen değere sahip olma olasılığını onaylar.

```qsharp
operation AssertProbInt (stateIndex : Int, expected : Double, qubits : Microsoft.Quantum.Arithmetic.LittleEndian, tolerance : Double) : Unit
```


## <a name="description"></a>Açıklama

Bir $n $-qubit hisse durumu $ \ket{\psı} = \sum ^ {2 ^ n-1} _ {j = 0} \ alpha_j \ket{j} $ olarak verildiğinde, $j $ tarafından dizini oluşturulan $ \ket{j} $ durumunun $ | \ alpha_j | ^ 2 $ değerinin beklenen değere sahip olduğunu onaylar.

## <a name="input"></a>Giriş

### <a name="stateindex--int"></a>Stateındex: [Int](xref:microsoft.quantum.lang-ref.int)

Bir yazmaç tarafından temsil edilen $ \ket{j} $ durumunun $j $ dizini `LittleEndian` .


### <a name="expected--double"></a>beklenen: [çift](xref:microsoft.quantum.lang-ref.double)

$ | \ Alpha_j | ^ 2 $ değerinin beklenen değeri.


### <a name="qubits--littleendian"></a>qubits: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$ \Ket{\psı} $ ' i küçük endian biçiminde depolayan qubit kaydı.


### <a name="tolerance--double"></a>Tolerans: [Double](xref:microsoft.quantum.lang-ref.double)

Gerçek ve beklenen arasındaki fark için mutlak tolerans.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)

