---
uid: Microsoft.Quantum.Preparation.PrepareUniformSuperposition
title: Preparebirlik superposition işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareUniformSuperposition
qsharp.summary: >-
  Creates a uniform superposition over states that encode 0 through `nIndices - 1`.

  That is, this unitary $U$ creates a uniform superposition over all number states $0$ to $M-1$, given an input state $\ket{0\cdots 0}$. In other words, $$ \begin{align} U\ket{0}=\frac{1}{\sqrt{M}}\sum_{j=0}^{M-1}\ket{j}. \end{align} $$.
ms.openlocfilehash: 8b57a7a02e9f704cf9677574824dfdc93fff25b0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725825"
---
# <a name="prepareuniformsuperposition-operation"></a>Preparebirlik superposition işlemi

Ad alanı: [Microsoft. hisse. hazırlık](xref:Microsoft.Quantum.Preparation)

Leyebilir [](https://nuget.org/packages/)


0 ile kodlayan durumlar üzerinde Tekdüzen üst konumu oluşturur `nIndices - 1` .

Diğer bir deyişle, bu Unitary $U $, $0 $ ile $M-$1 arasında tek bir üst konum oluşturarak bir giriş durumu $ \ket{0\cnoktalar 0} $ olarak sunulur. Diğer bir deyişle, $ $ \begin{hizalaması} U\ket {0} = \frac {1} {\Sqrt{m}}\ sum_ {j = 0} ^ {M-1} \ket{j}.
\end{hizalaması} $ $.

```qsharp
operation PrepareUniformSuperposition (nIndices : Int, indexRegister : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a>Giriş

### <a name="nindices--int"></a>nDizinler: [Int](xref:microsoft.quantum.lang-ref.int)

Tekdüzen üst konumunda istenen sayıda durum $M.


### <a name="indexregister--littleendian"></a>ındexregister: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Sayı durumlarını depolayan qubit kaydı `LittleEndian` .
Bu yazmaç $M-$1 numarasını depolayabilmelidir ve $ \ket{0\cnoktalar 0} $ durumunda başlatılmıştı.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Açıklamalar

İşlem adjointable ' dır, ancak söz konusu `indexRegister` durumda ilk temel durumlar üzerinde bir Tekdüzen üst konumunda olmasını gerektirir `nIndices` .