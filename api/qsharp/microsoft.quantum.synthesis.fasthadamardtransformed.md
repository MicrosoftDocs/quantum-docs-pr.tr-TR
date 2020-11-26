---
uid: Microsoft.Quantum.Synthesis.FastHadamardTransformed
title: Fasthadamarddönüştürüldü işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: FastHadamardTransformed
qsharp.summary: Computes Hadamard transform of a Boolean function in {-1,1} encoding using Yates's method
ms.openlocfilehash: 3e48701f22ddf154721355866e15a85fca0bc7df
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203102"
---
# <a name="fasthadamardtransformed-function"></a>Fasthadamarddönüştürüldü işlevi

Ad alanı: [Microsoft. hisse. sensıs](xref:Microsoft.Quantum.Synthesis)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


{-1,1}Yates 'in yöntemi kullanılarak Kodlamadaki bir Boole Işlevinin Hadamard dönüşümünü hesaplar

```qsharp
function FastHadamardTransformed (func : Int[]) : Int[]
```


## <a name="input"></a>Giriş

### <a name="func--int"></a>Func: [Int](xref:microsoft.quantum.lang-ref.int)[]

Kodlamadaki Truth tablosu {-1,1}



## <a name="output--int"></a>Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)[]

İşlevin Spectral katsayısıdır