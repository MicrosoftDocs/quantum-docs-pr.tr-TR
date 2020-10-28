---
uid: Microsoft.Quantum.Canon.EmbedPauli
title: EmbedPauli işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: EmbedPauli
qsharp.summary: Given a single-qubit Pauli operator and the index of a qubit, returns a multi-qubit Pauli operator with the given single-qubit operator at that index and `PauliI` at every other index.
ms.openlocfilehash: c78406aa4557834ac2bb40cf1847696d075e5135
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728712"
---
# <a name="embedpauli-function"></a>EmbedPauli işlevi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Leyebilir [](https://nuget.org/packages/)


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

