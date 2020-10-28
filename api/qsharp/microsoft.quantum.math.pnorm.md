---
uid: Microsoft.Quantum.Math.PNorm
title: PNorm işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PNorm
qsharp.summary: >-
  Returns the `L(p)` norm of a vector of `Double`s.

  That is, given an array $x$ of type `Double[]`, this returns the $p$-norm $\|x\|\_p= (\sum_{j}|x_j|^{p})^{1/p}$.
ms.openlocfilehash: cea85715e448305486f6d8a6c10e11da56edf3ee
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732247"
---
# <a name="pnorm-function"></a>PNorm işlevi

Ad alanı: [Microsoft. hisse. Math](xref:Microsoft.Quantum.Math)

Leyebilir [](https://nuget.org/packages/)


`L(p)`Bir vektörün vektörini döndürür `Double` .

Diğer bir deyişle, türünde bir dizi $x olarak belirtilen `Double[]` Bu, $-norm $ \| x \| \_ p = (\ sum_ {j} | x_j | ^ {p}) ^ {1/p} $ $p döndürür.

```qsharp
function PNorm (p : Double, array : Double[]) : Double
```


## <a name="input"></a>Giriş

### <a name="p--double"></a>p: [Double](xref:microsoft.quantum.lang-ref.double)

$P $-norm içindeki üs $p $.


### <a name="array--double"></a>dizi: [Double](xref:microsoft.quantum.lang-ref.double)[]





## <a name="output--double"></a>Çıkış: [Double](xref:microsoft.quantum.lang-ref.double)

$P $-norm $ \| x \| _p $.