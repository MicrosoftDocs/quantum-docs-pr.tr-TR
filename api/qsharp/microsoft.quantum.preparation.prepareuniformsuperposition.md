---
uid: Microsoft.Quantum.Preparation.PrepareUniformSuperposition
title: Preparebirlik superposition işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareUniformSuperposition
qsharp.summary: >-
  Creates a uniform superposition over states that encode 0 through `nIndices - 1`.

  That is, this unitary $U$ creates a uniform superposition over all number states $0$ to $M-1$, given an input state $\ket{0\cdots 0}$. In other words, $$ \begin{align} U\ket{0}=\frac{1}{\sqrt{M}}\sum_{j=0}^{M-1}\ket{j}. \end{align} $$.
ms.openlocfilehash: 9b9f182ed7c1ea24ae74b8a2321a309042a17c97
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230098"
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



## <a name="remarks"></a>Açıklamalar

İşlem adjointable ' dır, ancak söz konusu `indexRegister` durumda ilk temel durumlar üzerinde bir Tekdüzen üst konumunda olmasını gerektirir `nIndices` .