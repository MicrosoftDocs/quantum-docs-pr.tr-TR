---
uid: Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecompositionWithVariableOrder
title: Applyperdeğiştirici Tionusingdekompozisyontionwithvariableorder işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyPermutationUsingDecompositionWithVariableOrder
qsharp.summary: Permutes the amplitudes in a quantum state given a permutation using decomposition-based synthesis.
ms.openlocfilehash: f33d2980ff1775b1ae8d2e2e7a4fa1e5cbe7d5ba
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858874"
---
# <a name="applypermutationusingdecompositionwithvariableorder-operation"></a>Applyperdeğiştirici Tionusingdekompozisyontionwithvariableorder işlemi

Ad alanı: [Microsoft. hisse. sensıs](xref:Microsoft.Quantum.Synthesis)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir hisse cıklarca, ayrıştırma tabanlı senklerde bir PERMÜTASYONA göre rekabet eden bir değer sağlar.

```qsharp
operation ApplyPermutationUsingDecompositionWithVariableOrder (perm : Int[], variableOrder : Int[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>Description

Bu işlem, @"microsoft.quantum.synthesis.applypermutationusingdecomposition" değişken sırasının belirtibileceği daha genel bir sürümdür. Farklı bir değişken sırası, ayrıştırma dizisini ve kontrollü kapılar için kullanılan Truth tablolarını değiştirir @"microsoft.quantum.intrinsic.x" .  Bu nedenle, değişken sırasını değiştirmek, permütasyon sağlamak için kullanılan toplam kapı sayısını değiştirir.

## <a name="input"></a>Giriş

### <a name="perm--int"></a>izin: [Int](xref:microsoft.quantum.lang-ref.int)[]

0 ' dan başlayarak $2 ^ n $ öğe için bir permütasyon.


### <a name="variableorder--int"></a>variableOrder: [Int](xref:microsoft.quantum.lang-ref.int)[]

0 ' dan başlayarak $n $ öğelerinden oluşan bir permütasyon.


### <a name="qubits--littleendian"></a>qubits: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Permütasyonun uygulandığı $n $ qubits listesi.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="example"></a>Örnek

Bir işlemi sentezleştirmek için `SWAP` :

```qsharp
using (qubits = Qubit[2]) {
  ApplyPermutationUsingDecompositionWithVariableOrder([0, 2, 1, 3], [1, 0], LittleEndian(qubits));
}
```

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Sensıs. Applyperdeğiştirici Tionusingayrıştırma](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition)
- [Microsoft. hisse. Sensıs. Applyperdeğiştirici Tionusingtransformation](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation)