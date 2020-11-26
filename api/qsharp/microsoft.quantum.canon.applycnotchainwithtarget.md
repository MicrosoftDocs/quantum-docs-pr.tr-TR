---
uid: Microsoft.Quantum.Canon.ApplyCNOTChainWithTarget
title: ApplyCNOTChainWithTarget işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCNOTChainWithTarget
qsharp.summary: Computes the parity of an array of qubits into a target qubit.
ms.openlocfilehash: 8ec85ce5805b3bbd1e1f7c739f27de3a861bc79e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219116"
---
# <a name="applycnotchainwithtarget-operation"></a>ApplyCNOTChainWithTarget işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir qubits dizisinin bir hedef qubit 'e eşlik durumunu hesaplar.

```qsharp
operation ApplyCNOTChainWithTarget (qubits : Qubit[], targetQubit : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a>Açıklama

Dizi başlangıçta $ \ket{q_0} \ket{q_1} \cnoktalar \ket{q_ {\Text{Target}}} $ durumunda ise, son durum $ \ket{q_0} \ket{q_1 \oplus q_0} \cnoktalar \ket{q_ {n-1} \oplus \cnoktalar \oplus q_0 \oplus q_ {\Text{Target}}} $ tarafından verilir.

## <a name="input"></a>Giriş

### <a name="qubits--qubit"></a>qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Eşlik öğesinin hesaplandığı qubit dizisi.


### <a name="targetqubit--qubit"></a>targetQubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)

' Qubits ' öğesinin eşliği XORed olduğu son qubit.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Açıklamalar

Aşağıdakiler eşdeğerdir:

```qsharp
ApplyCNOTChainWithTarget(Most(qs), Last(qs));
```

ve

```qsharp
ApplyCNOTChain(qs);
```