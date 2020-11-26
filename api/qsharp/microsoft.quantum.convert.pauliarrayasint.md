---
uid: Microsoft.Quantum.Convert.PauliArrayAsInt
title: Pauliarrayasınt işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: PauliArrayAsInt
qsharp.summary: Encodes a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators into an integer.
ms.openlocfilehash: 6077110cc07c8626b22eb404c1de096ed43efcc3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224250"
---
# <a name="pauliarrayasint-function"></a>Pauliarrayasınt işlevi

Ad alanı: [Microsoft. hisse. Convert](xref:Microsoft.Quantum.Convert)

Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Tek qubit Pauli işleçleri dizisi olarak temsil edilen bir multi-qubit Pauli işlecini tamsayı olarak kodlar.

```qsharp
function PauliArrayAsInt (paulis : Pauli[]) : Int
```


## <a name="input"></a>Giriş

### <a name="paulis--pauli"></a>Paulis: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

En fazla 31 tek-qubit Pauli işleçlerinden oluşan dizi.



## <a name="output--int"></a>Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)

Aşağıda açıklandığı gibi benzersiz şekilde tanımlayan bir tamsayı `paulis` .

## <a name="remarks"></a>Açıklamalar

Her Pauli işleci iki bit kullanılarak kodlanabilir: $ $ \begin{hizalaması} \cıvadone \mapsto 00, \dörtlü X \mapsto 01, \dörtlü Y \mapsto 11, \quad Z \mapsto 10.
\end{hizalaması} $ $

Pauli işleçleri dizisi verildiğinde `[P0, ..., Pn]` , bu işlev, her Pauli işlecinin eşlemelerini büyük endian sırasıyla birleştirerek ikili genişletmeyle biçimlendirilmiş bir tamsayı döndürür `bits(Pn) ... bits(P0)` .