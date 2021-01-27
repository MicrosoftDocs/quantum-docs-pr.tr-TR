---
uid: Microsoft.Quantum.Preparation.StatePreparationPositiveCoefficients
title: StatePreparationPositiveCoefficients işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: StatePreparationPositiveCoefficients
qsharp.summary: >-
  > [!WARNING]

  > StatePreparationPositiveCoefficients has been deprecated. Please use <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateD> instead.


  Returns an operation that prepares the given quantum state.

  The returned operation $U$ prepares an arbitrary quantum state $\ket{\psi}$ with positive coefficients $\alpha_j\ge 0$ from the $n$-qubit computational basis state $\ket{0...0}$.

  The action of U on a newly-allocated register is given by $$ \begin{align} U \ket{0\cdots 0} = \ket{\psi} = \frac{\sum_{j=0}^{2^n-1}\alpha_j \ket{j}}{\sqrt{\sum_{j=0}^{2^n-1}|\alpha_j|^2}}. \end{align} $$
ms.openlocfilehash: 081541d93bf853fa0de1573038dc00c296432281
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855853"
---
# <a name="statepreparationpositivecoefficients-function"></a>StatePreparationPositiveCoefficients işlevi

Ad alanı: [Microsoft. hisse. hazırlık](xref:Microsoft.Quantum.Preparation)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


> [!WARNING]
> StatePreparationPositiveCoefficients kullanım dışı bırakıldı. Lütfen <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateD> bunun yerine kullanın.

Verilen hisse cıya durumunu hazırlayan bir işlem döndürür.

Döndürülen $U $ $-qubit hesaplama tabanlı durumu $ \ket{0...0} $ $n $ \ alpha_j \ge $0 pozitif katlarla rastgele bir hisse alma $ \ket{\psı} $ hazırlar.

Yeni ayrılmış bir kayıttaki U eylemi $ $ \begin{hizalaması} U \ket{0\cnoktalar 0} = \ket{\psı} = \frac{\ sum_ {j = 0 tarafından verilir} ^ {2 ^ n-1} \ alpha_j \ket{j}}{\sqrt{\ sum_ {j = 0} ^ {2 ^ n-1} | \ alpha_j | ^ 2}}.
\end{hizalaması} $ $

```qsharp
function StatePreparationPositiveCoefficients (coefficients : Double[]) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)
```


## <a name="input"></a>Giriş

### <a name="coefficients--double"></a>katsayılar: [Double](xref:microsoft.quantum.lang-ref.double)[]

Dizi $2 ^ n $ katsayısı $ \ alpha_j $. $J $ TH katsayısı, küçük endian biçiminde $ \ket{j} $ kodlu durum sayısını dizine ekler.



## <a name="output--littleendian--unit--is-adj--ctl"></a>Çıkış: [litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [birimi](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL

Bir durum hazırlama Unitary işlemi $U $.

## <a name="example"></a>Örnek

Aşağıdaki kod parçacığı, qubit kaydındaki hisse durumu $ \ket{\psı} = \ sqrt {1/8} \ {0} Tus+ \ sqrt {7/8} \ {2} Tus$ ' i hazırlar `qubitsLE` .

```qsharp
let amplitudes = [Sqrt(0.125), 0.0, Sqrt(0.875), 0.0];
let op = StatePreparationPositiveCoefficients(amplitudes);
using (qubits = Qubit[2]) {
    let qubitsLE = LittleEndian(qubits);
    op(qubitsLE);
}
```

## <a name="remarks"></a>Açıklamalar

Negatif giriş katsayıları $ \ alpha_j < $0, $ | \ alpha_j | $ değeri ile pozitif olarak değerlendirilir. `coefficients` $ \ alpha_j = $0,0 öğelerinden daha az $2 ^ n $ belirtilirse, bu öğelerle doldurulur.