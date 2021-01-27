---
uid: Microsoft.Quantum.Preparation.PrepareUniformSuperposition
title: Preparebirlik superposition işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareUniformSuperposition
qsharp.summary: >-
  Creates a uniform superposition over states that encode 0 through `nIndices - 1`.

  That is, this unitary $U$ creates a uniform superposition over all number states $0$ to $M-1$, given an input state $\ket{0\cdots 0}$. In other words, $$ \begin{align} U\ket{0}=\frac{1}{\sqrt{M}}\sum_{j=0}^{M-1}\ket{j}. \end{align} $$.
ms.openlocfilehash: dc9d4ce1638b397748cafaa757241ce78633c67c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854314"
---
# <a name="prepareuniformsuperposition-operation"></a>Preparebirlik superposition işlemi

Ad alanı: [Microsoft. hisse. hazırlık](xref:Microsoft.Quantum.Preparation)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


0 ile kodlayan durumlar üzerinde Tekdüzen üst konumu oluşturur `nIndices - 1` .

Diğer bir deyişle, bu Unitary $U $, $0 $ ile $M-$1 arasında tek bir üst konum oluşturarak bir giriş durumu $ \ket{0\cnoktalar 0} $ olarak sunulur. Diğer bir deyişle, $ $ \begin{hizalaması} U\ket {0} = \frac {1} {\Sqrt{m}}\ sum_ {j = 0} ^ {M-1} \ket{j}.
\end{hizalaması} $ $.

```qsharp
operation PrepareUniformSuperposition (nIndices : Int, indexRegister : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>Giriş

### <a name="nindices--int"></a>nDizinler: [Int](xref:microsoft.quantum.lang-ref.int)

Tekdüzen üst konumunda istenen sayıda durum $M.


### <a name="indexregister--littleendian"></a>ındexregister: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Sayı durumlarını depolayan qubit kaydı `LittleEndian` .
Bu yazmaç $M-$1 numarasını depolayabilmelidir ve $ \ket{0\cnoktalar 0} $ durumunda başlatılmıştı.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="example"></a>Örnek

Aşağıdaki örnek, {1} $3 $ qubits üzerinde $ \frac {\sqrt {6} } \ sum_ {j = 0} ^ {5} \ket{j} $ durumunu hazırlar.

```qsharp
let nIndices = 6;
using(indexRegister = Qubit[3]) {
    PrepareUniformSuperposition(nIndices, LittleEndian(indexRegister));
    // ...
}
```

## <a name="remarks"></a>Açıklamalar

İşlem adjointable ' dır, ancak söz konusu `indexRegister` durumda ilk temel durumlar üzerinde bir Tekdüzen üst konumunda olmasını gerektirir `nIndices` .