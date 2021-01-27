---
uid: Microsoft.Quantum.Synthesis.FastHadamardTransformed
title: Fasthadamarddönüştürüldü işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: FastHadamardTransformed
qsharp.summary: Computes Hadamard transform of a Boolean function in {-1,1} encoding using Yates's method
ms.openlocfilehash: be54413ef2d3fdaf7ddc726bc0906adb4ec382ff
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855463"
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

## <a name="example"></a>Örnek

```qsharp
FastHadamardTransformed([1, 1, 1, -1]); // [2, 2, 2, -2]
```