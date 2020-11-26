---
uid: Microsoft.Quantum.Canon.ApplyCNOTChain
title: ApplyCNOTChain işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCNOTChain
qsharp.summary: Computes the parity of a register of qubits in-place.
ms.openlocfilehash: e237e4424661de816e73b0c78523180b41190cf9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219150"
---
# <a name="applycnotchain-operation"></a>ApplyCNOTChain işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir qubits kaydının bir yerinde olan eşlik düzeyini hesaplar.

```qsharp
operation ApplyCNOTChain (qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="description"></a>Açıklama

Bu işlem girişinin durumunu $ $ \begin{hizalaması} \ket{q_0} \ket{q_1} \cnoktalar \ket{q_ {n-1}} & \mapsto \ket{q_0 olarak dönüştürür} \ket{q_0 \oplus q_1} \ket{q_0 \oplus q_1 \oplus q_2} \cnoktalar \ket{q_0 \oplus \cnoktalara \oplus q_ {n-1}}.
\end{hizalaması} $ $

## <a name="input"></a>Giriş

### <a name="qubits--qubit"></a>qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Eşliği hesaplanmak ve depolanacak qubit dizisi.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)

