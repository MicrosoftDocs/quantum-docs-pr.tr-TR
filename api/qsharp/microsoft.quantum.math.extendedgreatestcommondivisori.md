---
uid: Microsoft.Quantum.Math.ExtendedGreatestCommonDivisorI
title: ExtendedGreatestCommonDivisorI işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExtendedGreatestCommonDivisorI
qsharp.summary: Computes a tuple $(u,v)$ such that $u \cdot a + v \cdot b = \operatorname{GCD}(a, b)$, where $\operatorname{GCD}$ is $a$ greatest common divisor of $a$ and $b$. The GCD is always positive.
ms.openlocfilehash: 365e91e84add0d57d5a3cf203bbf23d96979b251
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96195537"
---
# <a name="extendedgreatestcommondivisori-function"></a>ExtendedGreatestCommonDivisorI işlevi

Ad alanı: [Microsoft. hisse. Math](xref:Microsoft.Quantum.Math)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


\Cdot a + v \cdot b = \operatorname{GCD} (a, b) $ $u bir demet $ (u, v) $, burada $ \operatorname{GCD} $, $a $ ve $b $ $a $ en büyük ortak bölenini hesaplar. GCD her zaman pozitif olur.

```qsharp
function ExtendedGreatestCommonDivisorI (a : Int, b : Int) : (Int, Int)
```


## <a name="input"></a>Giriş

### <a name="a--int"></a>y: [Int](xref:microsoft.quantum.lang-ref.int)

Genişletilmiş en büyük ortak ayırıcının hesaplandığı ilk sayı


### <a name="b--int"></a>b: [Int](xref:microsoft.quantum.lang-ref.int)

Genişletilmiş en büyük ortak ayırıcının hesaplandığı ikinci sayı



## <a name="output--intint"></a>Çıkış: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int))

Demet $ (u, v) $, özellik $u \cdot a + v \cdot b = \operatorname{GCD} (a, b) $.

## <a name="references"></a>Başvurular

- Bu uygulama şunlara göre yapılır https://en.wikipedia.org/wiki/Extended_Euclidean_algorithm