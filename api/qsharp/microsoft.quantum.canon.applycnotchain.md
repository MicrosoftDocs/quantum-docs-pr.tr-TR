---
uid: Microsoft.Quantum.Canon.ApplyCNOTChain
title: ApplyCNOTChain işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCNOTChain
qsharp.summary: Computes the parity of a register of qubits in-place.
ms.openlocfilehash: c98fe24ca352952162acb7a9c4fc93d5da4285b8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729687"
---
# <a name="applycnotchain-operation"></a>ApplyCNOTChain işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Leyebilir [](https://nuget.org/packages/)


Bir qubits kaydının bir yerinde olan eşlik düzeyini hesaplar.

```qsharp
operation ApplyCNOTChain (qubits : Qubit[]) : Unit
```


## <a name="description"></a>Açıklama

Bu işlem girişinin durumunu $ $ \begin{hizalaması} \ket{q_0} \ket{q_1} \cnoktalar \ket{q_ {n-1}} & \mapsto \ket{q_0 olarak dönüştürür} \ket{q_0 \oplus q_1} \ket{q_0 \oplus q_1 \oplus q_2} \cnoktalar \ket{q_0 \oplus \cnoktalara \oplus q_ {n-1}}.
\end{hizalaması} $ $

## <a name="input"></a>Giriş

### <a name="qubits--qubit"></a>qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Eşliği hesaplanmak ve depolanacak qubit dizisi.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)

