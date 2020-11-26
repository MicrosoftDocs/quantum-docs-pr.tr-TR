---
uid: Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecompositionWithVariableOrder
title: Applyperdeğiştirici Tionusingdekompozisyontionwithvariableorder işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyPermutationUsingDecompositionWithVariableOrder
qsharp.summary: Permutes the amplitudes in a quantum state given a permutation using decomposition-based synthesis.
ms.openlocfilehash: a5ca9b366f7ff477070e21fea047ff04b425439c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203442"
---
# <a name="applypermutationusingdecompositionwithvariableorder-operation"></a>Applyperdeğiştirici Tionusingdekompozisyontionwithvariableorder işlemi

Ad alanı: [Microsoft. hisse. sensıs](xref:Microsoft.Quantum.Synthesis)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir hisse cıklarca, ayrıştırma tabanlı senklerde bir PERMÜTASYONA göre rekabet eden bir değer sağlar.

```qsharp
operation ApplyPermutationUsingDecompositionWithVariableOrder (perm : Int[], variableOrder : Int[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>Açıklama

Bu işlem, @"microsoft.quantum.synthesis.applypermutationusingdecomposition" değişken sırasının belirtibileceği daha genel bir sürümdür. Farklı bir değişken sırası, ayrıştırma dizisini ve kontrollü kapılar için kullanılan Truth tablolarını değiştirir @"microsoft.quantum.intrinsic.x" .  Bu nedenle, değişken sırasını değiştirmek, permütasyon sağlamak için kullanılan toplam kapı sayısını değiştirir.

## <a name="input"></a>Giriş

### <a name="perm--int"></a>izin: [Int](xref:microsoft.quantum.lang-ref.int)[]

0 ' dan başlayarak $2 ^ n $ öğe için bir permütasyon.


### <a name="variableorder--int"></a>variableOrder: [Int](xref:microsoft.quantum.lang-ref.int)[]

0 ' dan başlayarak $n $ öğelerinden oluşan bir permütasyon.


### <a name="qubits--littleendian"></a>qubits: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Permütasyonun uygulandığı $n $ qubits listesi.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Sensıs. Applyperdeğiştirici Tionusingayrıştırma](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition)
- [Microsoft. hisse. Sensıs. Applyperdeğiştirici Tionusingtransformation](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation)