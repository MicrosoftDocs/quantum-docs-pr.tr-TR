---
uid: Microsoft.Quantum.Math.PNormalized
title: Pnormalleştirilmiş işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PNormalized
qsharp.summary: >-
  Normalizes a vector of `Double`s in the `L(p)` norm.

  That is, given an array $x$ of type `Double[]`, this returns an array where all elements are divided by the $p$-norm $\|x\|_p$.
ms.openlocfilehash: ea6a88d07d3b246f666b793f0b10ab6598ea4ff6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854842"
---
# <a name="pnormalized-function"></a>Pnormalleştirilmiş işlevi

Ad alanı: [Microsoft. hisse. Math](xref:Microsoft.Quantum.Math)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Norm içindeki bir vektörü normalleştirir `Double` `L(p)` .

Diğer bir deyişle, türünde bir dizi $x `Double[]` , bu, tüm öğelerin $p $-norm $ \| x _p $ tarafından bölündüğü bir dizi döndürür \| .

```qsharp
function PNormalized (p : Double, array : Double[]) : Double[]
```


## <a name="input"></a>Giriş

### <a name="p--double"></a>p: [Double](xref:microsoft.quantum.lang-ref.double)

$P $-norm içindeki üs $p $.


### <a name="array--double"></a>dizi: [Double](xref:microsoft.quantum.lang-ref.double)[]





## <a name="output--double"></a>Çıkış: [Double](xref:microsoft.quantum.lang-ref.double)[]

Dizi $x $-norm $ \| x _p $ $p tarafından normalleştirilmelidir \| .

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Math. PNorm](xref:Microsoft.Quantum.Math.PNorm)