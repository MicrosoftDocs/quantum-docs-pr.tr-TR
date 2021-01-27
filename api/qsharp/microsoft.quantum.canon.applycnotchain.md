---
uid: Microsoft.Quantum.Canon.ApplyCNOTChain
title: ApplyCNOTChain işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCNOTChain
qsharp.summary: Computes the parity of a register of qubits in-place.
ms.openlocfilehash: b5a74eb66529095233c89a4ec7ea37c996458cb4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841956"
---
# <a name="applycnotchain-operation"></a>ApplyCNOTChain işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir qubits kaydının bir yerinde olan eşlik düzeyini hesaplar.

```qsharp
operation ApplyCNOTChain (qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="description"></a>Description

Bu işlem girişinin durumunu $ $ \begin{hizalaması} \ket{q_0} \ket{q_1} \cnoktalar \ket{q_ {n-1}} & \mapsto \ket{q_0 olarak dönüştürür} \ket{q_0 \oplus q_1} \ket{q_0 \oplus q_1 \oplus q_2} \cnoktalar \ket{q_0 \oplus \cnoktalara \oplus q_ {n-1}}.
\end{hizalaması} $ $

## <a name="input"></a>Giriş

### <a name="qubits--qubit"></a>qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Eşliği hesaplanmak ve depolanacak qubit dizisi.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)

