---
uid: Microsoft.Quantum.Preparation.StatePreparationComplexCoefficients
title: StatePreparationComplexCoefficients işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: StatePreparationComplexCoefficients
qsharp.summary: >-
  > [!WARNING]

  > StatePreparationComplexCoefficients has been deprecated. Please use <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateCP> instead.


  Returns an operation that prepares a specific quantum state.

  The returned operation $U$ prepares an arbitrary quantum state $\ket{\psi}$ with complex coefficients $r_j e^{i t_j}$ from the $n$-qubit computational basis state $\ket{0...0}$.

  The action of U on a newly-allocated register is given by $$ \begin{align} U\ket{0...0}=\ket{\psi}=\frac{\sum_{j=0}^{2^n-1}r_j e^{i t_j}\ket{j}}{\sqrt{\sum_{j=0}^{2^n-1}|r_j|^2}}. \end{align} $$
ms.openlocfilehash: 1d0efa7b83d2e8e75c4b293866f3929f357ec44b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210378"
---
# <a name="statepreparationcomplexcoefficients-function"></a>StatePreparationComplexCoefficients işlevi

Ad alanı: [Microsoft. hisse. hazırlık](xref:Microsoft.Quantum.Preparation)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


> [!WARNING]
> StatePreparationComplexCoefficients kullanım dışı bırakıldı. Lütfen <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateCP> bunun yerine kullanın.

Belirli bir hisse durumu hazırlayan bir işlem döndürür.

Döndürülen $U $, $n $-qubit hesaplama tabanlı durum $ \ket{0...0} $ t_j _j $r karmaşık katlara sahip, rastgele bir hisse

Yeni ayrılmış bir kayıttaki U eylemi $ $ \begin{hizalaması} U\ket {0... tarafından verilir. 0} = \ket{\psı} = \frac{\ sum_ {j = 0} ^ {2 ^ n-1} r_j e ^ {i t_j} \ket{j}}{\sqrt{\ sum_ {j = 0} ^ {2 ^ n-1} | r_j | ^ 2}}.
\end{hizalaması} $ $

```qsharp
function StatePreparationComplexCoefficients (coefficients : Microsoft.Quantum.Math.ComplexPolar[]) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)
```


## <a name="input"></a>Giriş

### <a name="coefficients--complexpolar"></a>katsayılar: [Complexkutupsal](xref:Microsoft.Quantum.Math.ComplexPolar)[]

Mutlak değerleri ve aşama $ (r_j, t_j) ile temsil edilen en fazla $2 ^ n $ karmaşık katsayılar dizisi. $J $ TH katsayısı, küçük endian biçiminde $ \ket{j} $ kodlu durum sayısını dizine ekler.



## <a name="output--littleendian--unit--is-adj--ctl"></a>Çıkış: [litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [birimi](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL

Bir durum hazırlama Unitary işlemi $U $.

## <a name="remarks"></a>Açıklamalar

_J < $0 $r negatif giriş katsayılarını $ | r_j | $ değeri ile pozitif kabul edilir. `coefficients` $2 ^ n $ değerinden azı belirtilmişse $ (r_j, t_j) = (0,0, 0,0) $ öğeleri ile doldurulur.