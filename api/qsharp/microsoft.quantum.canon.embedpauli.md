---
uid: Microsoft.Quantum.Canon.EmbedPauli
title: EmbedPauli işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: EmbedPauli
qsharp.summary: Given a single-qubit Pauli operator and the index of a qubit, returns a multi-qubit Pauli operator with the given single-qubit operator at that index and `PauliI` at every other index.
ms.openlocfilehash: 0e6a93e22ee495abcc44bdf522e7c72c0981308b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840527"
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



## <a name="example"></a>Örnek

Diziyi almak için `[PauliI, PauliI, PauliX, PauliI]` :

```qsharp
EmbedPauli(PauliX, 2, 3);
```