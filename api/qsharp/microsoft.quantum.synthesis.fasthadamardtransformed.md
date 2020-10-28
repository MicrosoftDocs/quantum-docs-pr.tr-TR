---
uid: Microsoft.Quantum.Synthesis.FastHadamardTransformed
title: Fasthadamarddönüştürüldü işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: FastHadamardTransformed
qsharp.summary: Computes Hadamard transform of a Boolean function in {-1,1} encoding using Yates's method
ms.openlocfilehash: 2b84e92d08a3baad2552780cae91f447830cac82
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733895"
---
# <a name="fasthadamardtransformed-function"></a>Fasthadamarddönüştürüldü işlevi

Ad alanı: [Microsoft. hisse. sensıs](xref:Microsoft.Quantum.Synthesis)

Leyebilir [](https://nuget.org/packages/)


{-1,1}Yates 'in yöntemi kullanılarak Kodlamadaki bir Boole Işlevinin Hadamard dönüşümünü hesaplar

```qsharp
function FastHadamardTransformed (func : Int[]) : Int[]
```


## <a name="input"></a>Giriş

### <a name="func--int"></a>Func: [Int](xref:microsoft.quantum.lang-ref.int)[]

Kodlamadaki Truth tablosu {-1,1}



## <a name="output--int"></a>Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)[]

İşlevin Spectral katsayısıdır