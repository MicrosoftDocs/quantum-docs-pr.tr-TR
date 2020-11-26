---
uid: Microsoft.Quantum.Math.PNormalized
title: Pnormalleştirilmiş işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PNormalized
qsharp.summary: >-
  Normalizes a vector of `Double`s in the `L(p)` norm.

  That is, given an array $x$ of type `Double[]`, this returns an array where all elements are divided by the $p$-norm $\|x\|_p$.
ms.openlocfilehash: 196bdab67528aa8672a010ac3830459e27276ce9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96227531"
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