---
uid: Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation
title: Applyperdeğiştirici Tionusingtransformation işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyPermutationUsingTransformation
qsharp.summary: Permutes the amplitudes in a quantum state given a permutation using transformation-based synthesis.
ms.openlocfilehash: a05b433eae2612bbf5c87522c4ef251976184aa8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192069"
---
# <a name="applypermutationusingtransformation-operation"></a>Applyperdeğiştirici Tionusingtransformation işlemi

Ad alanı: [Microsoft. hisse. sensıs](xref:Microsoft.Quantum.Synthesis)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


, Dönüştürme tabanlı senklik kullanarak bir PERMÜTASYONA, bir hisse cıklarca rekabet eden bir permütasyon.

```qsharp
operation ApplyPermutationUsingTransformation (perm : Int[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>Açıklama

Bu yordam tek yönlü dönüştürme tabanlı sensıs yaklaşımını uygular.  Giriş, \{ \} $n $-değişken ters çevrilebilir Boole işlevini temsil eden, $2 ^ n $ öğe $0, \noktalar, 2 ^ n-1 $ üzerinden bir permütasyon $ \pı $.
Algoritma aşağıdaki adımları tekrarlayarak gerçekleştirir:

1. $X \ne \pi (x) = y $ gibi en küçük $x $ bulun.
2. Çıkışlara uygulanan birden çok kontrollü Toffoli işlemlerini bul $ \pi (x) = x $ ve tüm $x ' < x $ $ $ $ $ $ $ $ $ $ $ $ $ $ olarak değiştirme

## <a name="input"></a>Giriş

### <a name="perm--int"></a>izin: [Int](xref:microsoft.quantum.lang-ref.int)[]

0 ' dan başlayarak $2 ^ n $ öğe için bir permütasyon.


### <a name="qubits--littleendian"></a>qubits: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Permütasyonun uygulandığı $n $ qubits listesi.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>Başvurular

- [*D. Michael Miller*, *Dmitrı Maslov*, *Gerhard W. Dueck*, proc. dac 2003, ıeee, PP. 318-323, 2003](https://doi.org/10.1145/775832.775915)
- [*Mathias Soeken*, *Gerhard W. Dueck*, *D. MICHAEL Miller*, proc. RC 2016, sprçe, PP. 307-321, 2016](https://doi.org/10.1007/978-3-319-40578-0_22)

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Sensıs. Applyperdeğiştirici Tionusingayrıştırma](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition)