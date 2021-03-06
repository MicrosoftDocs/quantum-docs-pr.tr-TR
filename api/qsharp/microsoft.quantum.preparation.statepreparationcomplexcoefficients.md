---
uid: Microsoft.Quantum.Preparation.StatePreparationComplexCoefficients
title: StatePreparationComplexCoefficients işlevi
ms.date: 1/23/2021 12:00:00 AM
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
ms.openlocfilehash: c16df0fe075b15cff745a6b7d5b79aac39c14d09
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856128"
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

## <a name="example"></a>Örnek

Aşağıdaki kod parçacığı, qubit kaydındaki hisse durumu $ \ket{\psı} = e ^ {i 0,1} \ sqrt {1/8} \ {0} Tus+ \ sqrt {7/8} \ {2} Tus$ değerini hazırlar `qubitsLE` .

```qsharp
let amplitudes = [Sqrt(0.125), 0.0, Sqrt(0.875), 0.0];
let phases = [0.1, 0.0, 0.0, 0.0];
mutable complexNumbers = new ComplexPolar[4];
for (idx in 0..3) {
    set complexNumbers[idx] = ComplexPolar(amplitudes[idx], phases[idx]);
}
let op = StatePreparationComplexCoefficients(complexNumbers);
using (qubits = Qubit[2]) {
    let qubitsLE = LittleEndian(qubits);
    op(qubitsLE);
}
```

## <a name="remarks"></a>Açıklamalar

_J < $0 $r negatif giriş katsayılarını $ | r_j | $ değeri ile pozitif kabul edilir. `coefficients` $2 ^ n $ değerinden azı belirtilmişse $ (r_j, t_j) = (0,0, 0,0) $ öğeleri ile doldurulur.