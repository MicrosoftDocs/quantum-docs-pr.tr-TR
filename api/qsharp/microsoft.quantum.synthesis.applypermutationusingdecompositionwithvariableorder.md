---
uid: Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecompositionWithVariableOrder
title: Applyperdeğiştirici Tionusingdekompozisyontionwithvariableorder işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyPermutationUsingDecompositionWithVariableOrder
qsharp.summary: Permutes the amplitudes in a quantum state given a permutation using decomposition-based synthesis.
ms.openlocfilehash: 1edbc0a2948fdf3ae67f14b3c552676feaa7f498
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733959"
---
# <a name="applypermutationusingdecompositionwithvariableorder-operation"></a>Applyperdeğiştirici Tionusingdekompozisyontionwithvariableorder işlemi

Ad alanı: [Microsoft. hisse. sensıs](xref:Microsoft.Quantum.Synthesis)

Leyebilir [](https://nuget.org/packages/)


Bir hisse cıklarca, ayrıştırma tabanlı senklerde bir PERMÜTASYONA göre rekabet eden bir değer sağlar.

```qsharp
operation ApplyPermutationUsingDecompositionWithVariableOrder (perm : Int[], variableOrder : Int[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
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