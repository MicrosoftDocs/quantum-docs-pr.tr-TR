---
uid: Microsoft.Quantum.Convert.PauliArrayAsInt
title: Pauliarrayasınt işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: PauliArrayAsInt
qsharp.summary: Encodes a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators into an integer.
ms.openlocfilehash: 4c3c51813ef509fdc52773b15a956c0a99500603
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98832716"
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