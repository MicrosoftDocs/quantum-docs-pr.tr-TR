---
uid: Microsoft.Quantum.Arithmetic.AssertProbInt
title: Assertprobınt işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertProbInt
qsharp.summary: Asserts that the probability of a specific state of a quantum register has the expected value.
ms.openlocfilehash: 85ff04bbad9dc2ed0f803db65508fdfbb0d22c56
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843398"
---
# <a name="assertprobint-operation"></a>Assertprobınt işlemi

Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir hisse amacının belirli bir durumunun beklenen değere sahip olma olasılığını onaylar.

```qsharp
operation AssertProbInt (stateIndex : Int, expected : Double, qubits : Microsoft.Quantum.Arithmetic.LittleEndian, tolerance : Double) : Unit
```


## <a name="description"></a>Description

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



## <a name="example"></a>Örnek

`qubits`Yazmacın bir 3-qubit hisse durumu $ \ket{\psı} = \ sqrt {1/8} \ {0} Tus+ \ sqrt {7/8} \ hayvan {6} $ ' i küçük endian biçiminde kodluyor olduğunu varsayalım.
Bu sayı, $ \ ayraç {0} \ equiv\ayraç \ ayraç {0} {0} \ {0} ve $ \ ayraç {6} \ equiv\ayraç {0} \ {1} {1} ayraç \ Ardından, aşağıdaki onaylar başarılı olur:

```qsharp
AssertProbInt(0, 0.125, qubits, 10e-10);
AssertProbInt(6, 0.875, qubits, 10e-10);
```