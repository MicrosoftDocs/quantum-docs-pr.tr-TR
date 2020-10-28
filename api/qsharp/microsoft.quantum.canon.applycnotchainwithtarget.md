---
uid: Microsoft.Quantum.Canon.ApplyCNOTChainWithTarget
title: ApplyCNOTChainWithTarget işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCNOTChainWithTarget
qsharp.summary: Computes the parity of an array of qubits into a target qubit.
ms.openlocfilehash: fd0a0f3e1db89946aec2c63f3cde7a021608eea5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729679"
---
# <a name="applycnotchainwithtarget-operation"></a>ApplyCNOTChainWithTarget işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Leyebilir [](https://nuget.org/packages/)


Bir qubits dizisinin bir hedef qubit 'e eşlik durumunu hesaplar.

```qsharp
operation ApplyCNOTChainWithTarget (qubits : Qubit[], targetQubit : Qubit) : Unit
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