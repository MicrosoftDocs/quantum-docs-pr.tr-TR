---
uid: Microsoft.Quantum.Canon.EmbedPauli
title: EmbedPauli işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: EmbedPauli
qsharp.summary: Given a single-qubit Pauli operator and the index of a qubit, returns a multi-qubit Pauli operator with the given single-qubit operator at that index and `PauliI` at every other index.
ms.openlocfilehash: e9042ca9eac4b8791057037dc5698eb14deadd31
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207046"
---
# <a name="embedpauli-function"></a>EmbedPauli işlevi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir tek qubit Pauli operatörü ve bir qubit dizini verildiğinde, bu dizinde ve diğer her dizinde verilen tek qubit işleciyle bir multi-qubit Pauli işleci döndürür `PauliI` .

```qsharp
function EmbedPauli (pauli : Pauli, location : Int, n : Int) : Pauli[]
```


## <a name="input"></a>Giriş

### <a name="pauli--pauli"></a>Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)

Verilen konuma yerleştirilecek tek qubit Pauli işleci.


### <a name="location--int"></a>Konum: [Int](xref:microsoft.quantum.lang-ref.int)

`output[location] == pauli`Bu işlevin çıktısı olduğu gibi bir dizin `output` .


### <a name="n--int"></a>n: [Int](xref:microsoft.quantum.lang-ref.int)

Döndürülecek dizinin uzunluğu.



## <a name="output--pauli"></a>Çıkış: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

